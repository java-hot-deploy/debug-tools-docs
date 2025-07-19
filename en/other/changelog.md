---
layout: doc
aside: false
---
# ChangeLog

## [4.1.2](https://github.com/java-hot-deploy/debug-tools/compare/v4.1.1...v4.1.2) (2025-07-15)

- Fixed the bug of dynamic-datasource4.2+ startup failure
- Fixed the bug of mybatis-spring2.0.2 startup failure
- Fixed the bug of fastjson2 high version not getting getKotlinConstructor method
- Fixed the bug of unable to switch class loader
- Fixed the bug of startup java.lang.NullPointerException: Cannot read field "string" because "utf" is null

## [4.1.1](https://github.com/java-hot-deploy/debug-tools/compare/v4.1.0...v4.1.1) (2025-07-09)

- Add ToolWindow quick jump settings and document buttons by [@ayuayue](https://github.com/ayuayue)
- Add support for hot reload of JDK8 under MacOS aarch64 (M chip) [@yaoxinghuo](https://github.com/yaoxinghuo)
- Fix the bug that the project cannot be used under MacOS aarch64 (M chip) by [@yaoxinghuo](https://github.com/yaoxinghuo)
- Fix the bug that hot reload [dynamic-datasource](https://github.com/baomidou/dynamic-datasource) is invalid under 4.3+ by [@anweicloud](https://github.com/anweicloud)
- Fix hot reload [MyBatisPlus](https://baomidou.com/) 3.5.6+ lambdaQuery() failed to obtain when inheriting ServiceImpl
- Fixed the bug that oracle and sqlserver failed to print sql
- Fixed the bug that Spring Class information could not be found in Groovy
- Fixed the bug that the UI was stuck when viewing large json in the return result json mode

## [4.1.0](https://github.com/java-hot-deploy/debug-tools/compare/v4.0.1...v4.1.0) (2025-06-27)

- Hot deployment supports modifying MyBatis Mapper files
- Hot deployment supports modifying MyBatis Plus Entity/Mapper files
- Hot reload supports [Solon](https://solon.noear.org/) applications
- Calling Java methods supports [Solon](https://solon.noear.org/) Bean methods
- Add remote connection configuration function by [@anweicloud](https://github.com/anweicloud)
- Add printing compression SQL option configuration (Pretty, Compress, No)
- Optimize the logic of calling static methods.
- Optimize the logic of automatic attachment startup application
- Optimize command execution logic
- Fixed the bug that SQL statements cannot be printed under Jdk21
- Fixed the bug of StackOverflowError when Jackson deserializes nested classes
- Fixed the bug that the list of attached project class loaders does not refresh when closing ToolWindow
- Fixed the bug that application attachment fails when only automatic attachment is enabled
- Fixed the bug that the status cannot be updated when the remote connection is disconnected
- Fixed the bug that the application project cannot be packaged under jdk21

## [4.0.1](https://github.com/java-hot-deploy/debug-tools/compare/v4.0.0...v4.0.1) (2025-06-04)

- Fixed the bug that Exception in thread java.lang.UnsatisfiedLinkError: io.github.future0923.debug.tools.vm.VmTool.getInstances0(Ljava/lang/Class;I)[Ljava/lang/0bject; 的bug([#63](https://github.com/java-hot-deploy/debug-tools/issues/63))

## [4.0.0](https://github.com/java-hot-deploy/debug-tools/compare/v3.4.4...v4.0.0)(2025-06-03)

- Added hot deployment function to achieve hot update of remote application code in seconds.
- Added remote dynamic compilation function. When hot deploying and hot reloading, you can choose to compile the code with local Idea or dynamically compile the code with remote application.
- Added default class loader selection function, which allows you to select class loader when performing hot deployment, hot reload, and Groovy scripts
- Added [dynamic-datasource](https://github.com/baomidou/dynamic-datasource) dynamic data source `@DS` annotation hot reload ([#8](https://github.com/java-hot-deploy/debug-tools/issues/8))
- Added [hutool](https://hutool.cn) hot reload([#48](https://github.com/java-hot-deploy/debug-tools/issues/48))
- Added [Gson](https://github.com/google/gson) hot reload([#49](https://github.com/java-hot-deploy/debug-tools/issues/49))
- Added [EasyExcel](https://github.com/alibaba/easyexcel) hot reload([#46](https://github.com/java-hot-deploy/debug-tools/issues/46))
- Added [FastJson](https://github.com/alibaba/fastjson)、[FastJson2](https://github.com/alibaba/fastjson2) hot reload([#56](https://github.com/java-hot-deploy/debug-tools/issues/56))
- Added [Jackson](https://github.com/FasterXML/jackson-databind) hot reload([#50](https://github.com/java-hot-deploy/debug-tools/issues/50))
- Added [hibernate-validator](https://github.com/hibernate/hibernate-validator) hot reload([#60](https://github.com/java-hot-deploy/debug-tools/issues/60))
- Refactor the calling method function, remote calling supports hot deployment of classes
- Supports calling internal class methods at more than two levels([#43](https://github.com/java-hot-deploy/debug-tools/issues/43))
- Automatically attach the application launched in the current project([#58](https://github.com/java-hot-deploy/debug-tools/issues/58))
- Optimized heartbeat logic
- Optimize http timeout
- Fixed the bug that RuntimeExceptionWithAttachments：Read access is allowed from inside read-action only([#38](https://github.com/java-hot-deploy/debug-tools/issues/38)).

## [3.4.4](https://github.com/java-hot-deploy/debug-tools/compare/v3.4.3...v3.4.4) (2025-04-22)

- Support IntelliJ IDEA 2025.1 version ([#37](https://github.com/java-hot-deploy/debug-tools/issues/37)).

## [3.4.3](https://github.com/java-hot-deploy/debug-tools/compare/v3.4.2...v3.4.3) (2025-04-01)

- Fixed the problem that there is only one Controller under the folder File renaming hot reload failed BUG ([#31](https://github.com/java-hot-deploy/debug-tools/issues/31)).
- Modify JDK21 hot reload startup failure BUG ([#30](https://github.com/java-hot-deploy/debug-tools/issues/30)).
- Modify WebFlux can not call BUG ([#29](https://github.com/java-hot-deploy/debug-tools/issues/29)).

## [3.4.2](https://github.com/java-hot-deploy/debug-tools/compare/v3.4.1...v3.4.2) (2025-03-17)

- Add button to trigger compilation XML File to trigger ([#21](https://github.com/java-hot-deploy/debug-tools/issues/21)).
- Fix the bug that hot reload cannot be triggered when the Controller file is renamed ([#23](https://github.com/java-hot-deploy/debug-tools/issues/23)).
- Fix the bug that failed to connect to the remote application ([#27](https://github.com/java-hot-deploy/debug-tools/issues/27)).

## [3.4.1](https://github.com/java-hot-deploy/debug-tools/compare/v3.4.0...v3.4.1) (2025-02-27)

- Fix ConcurrentModificationException when multiple MyBatis Mappers are hot reloaded BUG ([#20](https://github.com/java-hot-deploy/debug-tools/issues/20)).

## [3.4.0](https://github.com/java-hot-deploy/debug-tools/compare/v3.3.0...v3.4.0) (2025-02-20)

- Hot reload supports static variables, static final variables, and static code blocks ([#10](https://github.com/java-hot-deploy/debug-tools/issues/10)).
- Hot reload supports Enum ([#10](https://github.com/java-hot-deploy/debug-tools/issues/10))
- Fixed the bug that non-Bean classes cannot be called in Spring environment ([#16](https://github.com/java-hot-deploy/debug-tools/issues/16)).

## [3.3.0](https://github.com/java-hot-deploy/debug-tools/compare/v3.2.0...v3.3.0) (2025-02-11)

- Hot reload supports MyBatis Plus to add Entity, modify Entity, add Mapper, modify Mapper, add xml, modify xml.
- Hot reload supports MyBatis to add Mapper, modify Mapper, add xml, modify xml.
- Add the function of executing the last time through the default class loader ([#12](https://github.com/java-hot-deploy/debug-tools/issues/12)).
- Fixed the bug that Maven commands cannot be executed when SQL printing is turned on ([#7](https://github.com/java-hot-deploy/debug-tools/issues/7)).

## [3.2.0](https://github.com/java-hot-deploy/debug-tools/compare/v3.1.2...v3.2.0) (2025-01-09)

- Added hot reload function to make the written code effective without restarting the application.

## [3.1.2](https://github.com/java-hot-deploy/debug-tools/compare/v3.1.1...v3.1.2) (2024-12-30)

- Fix the bug that failed to remove ContextPath ([#3](https://github.com/java-hot-deploy/debug-tools/issues/3)).
- Fix the bug that multiple projects share an additional button ([#4](https://github.com/java-hot-deploy/debug-tools/issues/4)).

## [3.1.1](https://github.com/java-hot-deploy/debug-tools/compare/v3.1.0...v3.1.1) (2024-12-18)

- ContextPath information can be removed when searching for http urls
- Fix the bug that domain names cannot be matched when there is no http(s)

## [3.1.0](https://github.com/java-hot-deploy/debug-tools/compare/v3.0.1...v3.1.0) (2024-12-17)

- Added the function of searching http url.
- Fixed the bug that the default class loader cannot be obtained when Groovy is executed in remote application.
- Fixed the bug that DebugToolsClassLoader repeatedly loaded the AppClassLoader base package, causing an exception to be thrown when using DefaultClassLoader.
- Optimize log printing ([#2](https://github.com/java-hot-deploy/debug-tools/issues/2))

## [3.0.1](https://github.com/java-hot-deploy/debug-tools/compare/v3.0.0...v3.0.1) (2024-12-12)

- Support IntelliJ IDEA 2024.3 version.
- Fix the bug that Groovy cannot get the default class loader when executing in remote application.

## 3.0.0 (2024-11-01)

- Add the function of calling remote application methods.
- Add the function of selecting class loader when calling methods.

## 2.3.0 (2024-09-19)

- Add groovy console, which can quickly execute code through the target application
- Add debug mode to quickly copy name and value
- Add attach The application can disconnect and stop the service

## 2.2.0 (2024-08-28)

- Support toString, json, debug to view the return result
- Support console, debug to view the exception information
- Support org.springframework.web.multipart.MultipartFile type parameter input
- Optimize the plugin style
- Fix the recursive stack overflow exception when the parameters are nested

## 2.1.0 (2024-08-19)

- Support 2024.2 version
- Support calls in non-Spring environments
- Support passing xxl-job parameters
- Support more parameter passing
  - request (MockHttpServletRequest)
  - response (MockHttpServletResponse)
  - file (absolute path to File object)
  - class (class full name to Class object)
- Optimize the window parameter logic

## 2.0.1 (2024-08-09)

- Fixed the bug that the heartbeat is too short and causes the business execution to be interrupted
- Fixed the bug that the exception information is not printed completely

## 2.0.0 (2024-08-06)

- Added interactive logic to support the caller to view the execution results and error information.
- Fixed the bug that the SQL print display error is NULL.

## 1.2.1 (2024-06-13)

- Added cache cleaning logic
- Added the exception return information of failed execution
- Optimized the request header parameter input logic
- Fixed the bug that the batch operation cannot print SQL

## 1.2.0 (2024-06-07)

- Optimized the core library loading logic
- Added the function of printing SQL statements and time consumption
- Fixed the bug that the library loading failed under window

## 1.1.1 (2024-06-04)

- Added a custom class loader to separate the target application
- Fixed the StackOverflowError when the collection type BUG

## 1.1.0 (2024-05-30)

- Add call configuration information
- Add request header parameter passing

## 1.0.0 (2024-05-29)

- Can call any Java method and support parameter passing

## First line of code submission (2024-05-08)