# Method Around

Scripts can be executed before, after, during exceptions, or at the end of a method call.

Scripts are stored as files in the `${project_dir}/.idea/method-around` directory.

## Menu Location

### ToolWindow

Global scripts can be configured in the ToolWindow.

![method-around-toolwindow.png](/images/method-around-toolwindow.png){v-zoom}

### Debug Panel

![method-around-quick-debug.png](/images/method-around-quick-debug.png){v-zoom}

### Parameter Meanings

- `Method Around`: Select the active script
- `Reload`: Reload the script drop-down list based on the script file
- `Detail`: View the current script contents
- `Delete`: Run the current script and file
- `Add`: Add a new script

::: tip
- Debug Panel settings take precedence over ToolWindow settings
- Scripts configured in the ToolWindow will be automatically selected if no settings are configured in the Debug Panel.
:::

## Writing Scripts

Click the `Add` and `Detail` buttons to write a script

### Editor

![method-around-editor.png](/images/method-around-editor.png){v-zoom}

- `Method around name`: Script name
- `Optimize imports`: Optimize import information
- `Reformat code`: Format code
- `Shorten class reference`: Compress class references
- `Cancel`: Cancel writing
- `Save`: Save script

### Writing content

- `onBefore`: Executed before method call
- `onAfter`: Executed after method call, not called if an exception occurs
- `onException`: Executed if method call fails, not called if successful
- `onFinally`: Executed when method call completes, called for both success and failure

```java
package io.github.future0923.debug.tools.base.around;

import java.util.List;
import java.util.Map;

/**
 * Method Script
 */
public class RunMethodAround {

    /**
     * Executed before a method is called
     *
     * @param headers: Incoming header information
     * @param xxlJobParam: Incoming xxl-job parameters
     * @param className: Incoming class name
     * @param methodName: Incoming method name
     * @param methodParameterTypes: Incoming method parameter types
     * @param methodParameters: Incoming method parameters
     */
    public void onBefore(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters) {

    }

    /**
     * Executed after a method is called
     *
     * @param headers: Incoming header information
     * @param xxlJobParam: Incoming xxl-job parameters
     * @param className: Incoming class name
     * @param methodName: Incoming method name
     * @param methodParameterTypes Parameter types of the method being called
     * @param methodParameters Parameters of the method being called
     * @param result Result of the method being called
     */
    public void onAfter(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Object result) {

    }

    /**
     * Executed when an exception occurs during a method call
     *
     * @param headers Received header information
     * @param xxlJobParam Received xxl-job parameters
     * @param className Received class name
     * @param methodName Received method name
     * @param methodParameterTypes Parameter types of the method being called
     * @param methodParameters Parameters of the method being called
     * @param throwable Exception thrown by the method being called
     */
    public void onException(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Throwable throwable) {

    }

    /**
     * Executed when the method call completes
     *
     * @param headers: Incoming header information
     * @param xxlJobParam: Incoming xxl-job parameters
     * @param className: Invoked class name
     * @param methodName: Invoked method name
     * @param methodParameterTypes: Invoked method parameter types
     * @param methodParameters: Invoked method parameters
     * @param result: Invoked method execution result
     * @param throwable: Invoked method exception thrown
     */
    public void onFinally(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Object result, Throwable throwable) {

    }
}
```

::: tip
- Neither method names nor parameter values can be changed; otherwise, the corresponding method will not be found.
- Dynamically modifying class signatures (adding, deleting, or modifying methods/fields) in the editor is only possible if you use JDK hot reload/hot deployment. Otherwise, the signature must match the source code class signature.
:::