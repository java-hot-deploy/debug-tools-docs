# 前后置脚本

支持在执行方法之前前置、后置、异常、最终时执行脚本代码。

脚本以文件存储在 `${project_dir}/.idea/method-around` 目录下。

## 菜单位置

### toolwindow

可以在ToolWindow处配置全局脚本

![method-around-toolwindow.png](/images/method-around-toolwindow.png){v-zoom}

### 调试面板

![method-around-quick-debug.png](/images/method-around-quick-debug.png){v-zoom}

### 参数含义

- `Method Around`: 选择生效的脚本
- `Reload`: 根据脚本文件重新载入脚本下拉选项
- `Detail`: 查看当前脚本内容
- `Delete`: 运行当前脚本及文件
- `Add`: 添加新脚本

::: tip 注意
- 调试面板设置的优先级高于toolwindow
- toolwindow设置的脚本会在调试面板没设置的情况下自动选中
:::

## 编写脚本

点击 `Add` 、`Detail` 按钮编写脚本

### 编辑器

![method-around-editor.png](/images/method-around-editor.png){v-zoom}

- `Method around name`: 脚本名称
- `Optimize imports`: 优化导入信息
- `Reformat code`: 格式化代码
- `Shorten class reference`: 压缩类引用
- `Cancel`: 取消编写
- `Save`: 保存脚本

### 编写内容

- `onBefore`: 调用方法之前执行
- `onAfter`: 调用方法之后执行，异常时不会调用
- `onException`: 调用方法异常时执行，成功时不会调用
- `onFinally`: 调用方法完成时执行，最终成功失败时都会调用

```java
package io.github.future0923.debug.tools.base.around;

import java.util.List;
import java.util.Map;

/**
 * 方法脚本
 */
public class RunMethodAround {

    /**
     * 调用方法之前执行
     * 
     * @param headers   传入的头信息
     * @param xxlJobParam 传入的xxl-job参数
     * @param className 调用的类名
     * @param methodName 调用的方法名
     * @param methodParameterTypes 调用的方法参数类型
     * @param methodParameters 调用的方法参数
     */
    public void onBefore(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters) {

    }

    /**
     * 调用方法之后执行
     *
     * @param headers   传入的头信息
     * @param xxlJobParam 传入的xxl-job参数
     * @param className 调用的类名
     * @param methodName 调用的方法名
     * @param methodParameterTypes 调用的方法参数类型
     * @param methodParameters 调用的方法参数
     * @param result 调用方法执行的结果
     */
    public void onAfter(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Object result) {

    }

    /**
     * 调用方法异常时执行
     *
     * @param headers   传入的头信息
     * @param xxlJobParam 传入的xxl-job参数
     * @param className 调用的类名
     * @param methodName 调用的方法名
     * @param methodParameterTypes 调用的方法参数类型
     * @param methodParameters 调用的方法参数
     * @param throwable 调用方法抛出的异常
     */
    public void onException(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Throwable throwable) {

    }

    /**
     * 调用方法完成时执行
     *
     * @param headers   传入的头信息
     * @param xxlJobParam 传入的xxl-job参数
     * @param className 调用的类名
     * @param methodName 调用的方法名
     * @param methodParameterTypes 调用的方法参数类型
     * @param methodParameters 调用的方法参数
     * @param result 调用方法执行结果
     * @param throwable 调用方法抛出的异常
     */
    public void onFinally(Map<String, String> headers, String xxlJobParam, String className, String methodName, List<String> methodParameterTypes, Object[] methodParameters, Object result, Throwable throwable) {

    }
}
```

::: tip 注意
- 方法名称与参数值都不允许更改，否则将无法找到对应的方法
- 如果使用热重载/热部署的jdk，才可以编辑器里才可以动态的修改类签名(增删改方法/字段)等信息，否则必须与源代码类签名一致
:::