# 方法耗时

当方法执行时间过长时，可以通过 DebugTools 快速查看方法耗时。

## 配置

![trace_method_config.png](/images/trace_method_config.png){v-zoom}

- `Trace method`：是否追踪方法耗时
- `Max depth`: 最大堆栈深度
- `MyBatis`: 是否追踪MyBatis的Mapper方法耗时
- `SQL`：是否追踪SQL方法耗时
- `Skip get/set method`：是否跳过get/set方法
- `Business package`：正则匹配业务包路径。符合这个路径的方法才会被追踪
- `Ignore package`：正则匹配忽略包路径。符合这个路径的方法不会被追踪

::: tip 注意
- 这个配置的作用是当唤醒调试面板时，如果这个方法之前没有配置过，会自动读取这个配置添加默认值。
- 如果需要打印SQL，则启动的时候就需要选中SQL配置(因为SQL是启动时修改的字节码)。开启 print sql 或者 trace method 的 SQL 配置均可。
:::

## 调试面板

![quick_debug_trace_method.png](/images/quick_debug_trace_method.png){v-zoom}

- `Trace method`：是否追踪方法耗时
- `Max depth`: 最大堆栈深度
- `MyBatis`: 是否追踪MyBatis的Mapper方法耗时
- `SQL`：是否追踪SQL方法耗时
- `Skip get/set method`：是否跳过get/set方法
- `Business package`：正则匹配业务包路径。符合这个路径的方法才会被追踪
- `Ignore package`：正则匹配忽略包路径。符合这个路径的方法不会被追踪

::: tip 注意
- 这个配置对当前这个方法生效。
- 如果需要打印SQL，则启动之前就需要再配置中选中SQL配置。开启 print sql 或者 trace method 的 SQL 配置均可。
:::

## 手动配置

![manual_trace_method.png](/images/manual_trace_method.png){v-zoom}

正常的情况下，一个方法中会调用很多方法，如果Max depth过大会导致字节码转换时间过长。

这个时候建议手动增加要追踪的方法，在方法体中点击右键菜单添加或移除方法追踪。

- `Add Method To Trace`：添加追踪方法
- `Remove Method From Trace`：移除追踪方法

手动添加的方法会显示如下图标：

![trace_line_status.png](/images/trace_line_status.png){v-zoom}

点击图标或者通过`Remove Method From Trace`可以取消追踪当前方法。

## 展示结果

通过 `trace` 类型查看执行方法耗时

- `Goto method source`: 方法上右键菜单可以跳转到对应的方法。

![run_result_trace.png](/images/run_result_trace.png){v-zoom}

- `Show sql detail`: 方法上右键菜单可以全屏格式化查看sql（双击也可以）。

![run_result_sql.png](/images/run_result_sql.png){v-zoom}

![run_result_trace_sql.png](/images/run_result_trace_sql.png){v-zoom}