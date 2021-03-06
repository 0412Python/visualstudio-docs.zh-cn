# [Visual Studio 调试器可扩展性](visual-studio-debugger-extensibility.md)
# [选择调试引擎实施策略](choosing-a-debug-engine-implementation-strategy.md)
# [创建自定义调试引擎](creating-a-custom-debug-engine.md)
## [注册自定义调试引擎](registering-a-custom-debug-engine.md)
## [启用要进行调试的程序](enabling-a-program-to-be-debugged.md)
### [获取端口](getting-a-port.md)
### [注册程序](registering-the-program.md)
### [附加到程序](attaching-to-the-program.md)
### [基于启动的附件](launch-based-attachment.md)
### [发送必需事件](sending-the-required-events.md)
## [执行控件和状态计算](execution-control-and-state-evaluation.md)
### [程序控制](program-control.md)
### [断点相关的方法](breakpoint-related-methods.md)
### [调用堆栈计算](call-stack-evaluation.md)
### [表达式计算](expression-evaluation-visual-studio-debugging-sdk.md)
### [控件事件](control-events.md)
## [发送事件](sending-events.md)
### [事件源](event-sources-visual-studio-sdk.md)
### [支持的事件类型](supported-event-types.md)
### [事件说明](event-descriptions.md)
## [终止和分离](termination-and-detaching.md)
## [调用调试器事件](calling-debugger-events.md)
### [附加到程序和从程序分离](attaching-and-detaching-to-a-program.md)
### [启动调试器](launching-the-debugger.md)
### [终止程序](terminating-a-program.md)
### [创建断点](creating-a-breakpoint.md)
### [断点绑定或解除绑定时](when-a-breakpoint-binds-or-becomes-unbound.md)
### [断点错误](breakpoint-errors.md)
### [命中断点](hitting-a-breakpoint.md)
### [删除断点](deleting-a-breakpoint.md)
### [进入中断模式](entering-break-mode.md)
### [步入中断模式](stepping-in-break-mode.md)
### [中断模式中的表达式计算](expression-evaluation-in-break-mode.md)
### [异常处理](exception-handling-visual-studio-sdk.md)
## [如何：调试自定义调试引擎](how-to-debug-a-custom-debug-engine.md)
# [入门](getting-started-with-debugger-extensibility.md)
## [扩展调试器的路线图](roadmap-for-extending-the-debugger.md)
## [调试器组件](debugger-components.md)
### [调试包](debug-package.md)
### [进程调试管理器](process-debug-manager.md)
### [会话调试管理器](session-debug-manager.md)
### [调试引擎](debug-engine.md)
### [操作模式](operational-modes.md)
### [表达式计算器](expression-evaluator.md)
### [符号提供程序](symbol-provider.md)
### [类型可视化工具和自定义查看器](type-visualizer-and-custom-viewer.md)
## [调试器概念](debugger-concepts.md)
### [调试会话](debug-session.md)
### [服务器](servers-visual-studio-sdk.md)
### [端口提供程序](port-suppliers.md)
### [端口](ports.md)
### [进程](processes.md)
### [程序节点](program-nodes.md)
### [程序](programs.md)
### [线程](threads.md)
### [堆栈帧](stack-frames.md)
### [模块](modules.md)
### [断点](breakpoints-visual-studio-sdk.md)
## [调试器上下文](debugger-contexts.md)
### [代码上下文](code-context.md)
### [文档位置](document-position.md)
### [文档上下文](document-context.md)
### [表达式计算上下文](expression-evaluation-context.md)
## [调试任务](debugging-tasks.md)
### [安全问题](security-issues.md)
### [启动程序](launching-a-program.md)
#### [通知端口](notifying-the-port.md)
#### [启动后附加](attaching-after-a-launch.md)
### [直接附加到程序](attaching-directly-to-a-program.md)
### [启动后发送启动事件](sending-startup-events-after-a-launch.md)
### [控制执行](control-of-execution.md)
### [绑定断点](binding-breakpoints.md)
### [计算表达式](evaluating-expressions.md)
### [可视化和查看数据](visualizing-and-viewing-data.md)
# [编写 CLR 表达式计算器](writing-a-common-language-runtime-expression-evaluator.md)
## [公共语言运行时和表达式计算](common-language-runtime-and-expression-evaluation.md)
## [表达式计算器体系结构](expression-evaluator-architecture.md)
### [计算上下文](evaluation-context.md)
### [键表达式计算器接口](key-expression-evaluator-interfaces.md)
## [注册表达式计算器](registering-an-expression-evaluator.md)
## [实现表达式计算器](implementing-an-expression-evaluator.md)
### [表达式计算器实施策略](expression-evaluator-implementation-strategy.md)
## [显示局部](displaying-locals.md)
### [局部的实现示例](sample-implementation-of-locals.md)
#### [实现 GetMethodProperty](implementing-getmethodproperty.md)
#### [枚举局部](enumerating-locals.md)
#### [获取局部属性](getting-local-properties.md)
#### [获取局部值](getting-local-values.md)
#### [计算局部](evaluating-locals.md)
## [计算监视窗口表达式](evaluating-a-watch-window-expression.md)
### [表达式计算的实现示例](sample-implementation-of-expression-evaluation.md)
### [计算监视表达式](evaluating-a-watch-expression.md)
## [更改局部值](changing-the-value-of-a-local.md)
### [更改值的实现示例](sample-implementation-of-changing-values.md)
## [实现类型可视化工具和自定义查看器](implementing-type-visualizers-and-custom-viewers.md)
# [实现端口提供程序](implementing-a-port-supplier.md)
## [实现和注册端口提供程序](implementing-and-registering-a-port-supplier.md)
## [所需的端口提供程序接口](required-port-supplier-interfaces.md)
# [.NET Framework 的并行扩展内幕](parallel-extension-internals-for-the-dotnet-framework.md)
## [Task 类](task-class-internal-members.md)
### [m_action 字段](m-action-field.md)
### [m_contingentProperties 字段](m-contingentproperties-field.md)
### [m_parent 字段](m-parent-field.md)
### [m_stateFlags 字段](m-stateflags-field.md)
### [m_stateObject 字段](m-stateobject-field.md)
### [m_taskId 字段](m-taskid-field.md)
### [s_taskIdCounter 字段](s-taskidcounter-field.md)
### [TASK_STATE_CANCELED 字段](task-state-canceled-field.md)
### [TASK_STATE_EXECUTED 字段](task-state-executed-field.md)
### [TASK_STATE_FAULTED 字段](task-state-faulted-field.md)
### [TASK_STATE_RAN_TO_COMPLETION 字段](task-state-ran-to-completion-field.md)
### [TASK_STATE_WAITING_ON_CHILDREN 字段](task-state-waiting-on-children-field.md)
### [SetNotificationForWaitCompletion 方法](setnotificationforwaitcompletion-method.md)
### [NotifyDebuggerOfWaitCompletion 方法](notifydebuggerofwaitcompletion-method.md)
## [TaskScheduler 类](taskscheduler-class-internal-members.md)
### [GetScheduledTasksForDebugger 方法](getscheduledtasksfordebugger-method.md)
### [GetTaskSchedulersForDebugger 方法](gettaskschedulersfordebugger-method.md)
## [ContingentProperties 类](contingentproperties-class-internal-members.md)
### [m_children 字段](m-children-field.md)
## [AsyncTaskMethodBuilder 结构](asynctaskmethodbuilder-structure-internal-members.md)
### [ObjectIdForDebugger 属性](asynctaskmethodbuilder-objectidfordebugger-property.md)
### [m_builder 字段](asynctaskmethodbuilder-m-builder-field.md)
## [AsyncTaskMethodBuilder\<TResult> 结构](asynctaskmethodbuilder-tresult-structure-internal-members.md)
### [ObjectIdForDebugger 属性](asynctaskmethodbuilder-tresult-objectidfordebugger-property.md)
### [m_task 字段](asynctaskmethodbuilder-tresult-m-task-field.md)
## [AsyncVoidMethodBuilder 结构](asyncvoidmethodbuilder-structure-internal-members.md)
### [ObjectIdForDebugger 属性](asyncvoidmethodbuilder-objectidfordebugger-property.md)
### [m_objectIdForDebugger 字段](asyncvoidmethodbuilder-m-objectidfordebugger-field.md)
# [引用](reference/reference-visual-studio-debugging-apis.md)
# [示例](visual-studio-debugging-samples.md)

