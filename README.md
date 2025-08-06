agent系统使用及构建说明

## 使用说明
1. 操作人需要将整个core_documents放到自己的项目根目录之下；
2. 操作人需要填充如下内容到对应文档：prd、技术架构、uiux、project_rules;
3. 操作人需要指挥AI模型进行项目初始化，创建claude.md文档；
4. 操作人需要将core_documents/agents/ArchitectAgent.md给到AI，让它完成service、database、workflow文档的初始化；
5. 至此，全部文档准备完毕，可以开始使用core_documents/agents/ArchitectAgent.md让AI制定第一版本方案了，然后让AI按照core_documents/agents/EngineerAgent.md进行开发、测试。


## agent通用工作流程
1. 接收操作员指令
2. 激活背景知识：通过subagent机制进行文档搜索
	- 必读：CLAUDE. Md（建立全局认知）
	- 必读：Core_documents/docs_index. Md（建立全局认知之后根据此文件去定位重点阅读文件）
3. 根据自己的内置任务流程规划任务
4. 与操作员确认计划
5. 执行计划
6. 与操作员确认完成
7. 按照文档标准维护文档


## Prompt 包含的通用内容
1. 角色指定
2. 工作流程说明（告知 agent 7 步工作流程）
3. 任务模板：开始规划任务的时候 agent 可以调用自己内置的任务流，比如 architectagent 就有制定版本计划、维护数据库文档等多个任务流程；
4. 文档维护标准：根据已有格式补充内容


## Agent 职责与文档相关性
1. ArchitectAgent（架构师）
  - 任务流程模板：
    - 制定版本计划
    - 针对某个功能设计开发方案
    - 针对某个功能做架构问题诊断
  - 需要维护的文档：
    - Core_documents/library/develop_plan/
    - Core_documents/library/service.md
    - Core_documents/library/workflow.md
    - Core_documents/library/database.md
2. EngineerAgent（工程师）
  - 任务流程模板：
    - 针对某个功能做性能问题诊断
    - 针对ArchitectAgent的某个计划做开发（包含测试）
    - 代码实现和优化
    - 技术问题排查和解决
  - 需要维护的文档：
    - Core_documents/library/history_record/
    - Core_documents/test_instances/
    - 相关源代码文件
3. ProductManagerAgent（产品经理）
  - 任务流程模板：
    - 根据最新的产品功能要求维护文档
    - 用户需求分析和转化
    - 用户体验优化设计
    - 产品竞争力分析
  - 需要维护的文档：
    - Core_documents/library/prd.md
    - Core_documents/library/uiux.md
4. ProjectAdminAgent（项目管理员）
  - 任务流程模板：
    - 扫描core_documents下所有文档，更新两个核心文档
    - 项目知识沉淀和经验总结
    - 项目文档质量审核
    - 项目规则和流程优化
  - 需要维护的文档：
    - CLAUDE.md
    - Core_documents/docs_index.md
5. BackendEngineerAgent（后端工程师）
  - 任务流程模板：
    - 后端服务架构设计和实现
    - API接口开发和优化
    - 数据库操作和性能优化
    - 后端系统问题诊断
  - 需要维护的文档：
    - Core_documents/library/history_record/ (后端相关)
    - Core_documents/test_instances/ (后端测试)
    - 后端源代码文件
6. FrontendEngineerAgent（前端工程师）
  - 任务流程模板：
    - 前端界面开发和实现
    - 用户交互逻辑实现
    - 前端性能优化
    - 前端问题诊断和修复
  - 需要维护的文档：
    - Core_documents/library/history_record/ (前端相关)
    - Core_documents/test_instances/ (前端测试)
    - 前端源代码文件
7. QAAgent（质量保证）
  - 任务流程模板：
    - 测试用例设计和执行
    - 质量标准制定和执行
    - 问题发现和跟踪
    - 测试报告生成
  - 需要维护的文档：
    - Core_documents/test_instances/
    - 测试相关文档和报告


### 文档维护要求：

1. 全局文件：
	- 全局文件更新要求：
		- 每次更新都要增加更新注释：XXXXX 时间，增删改了 XXX 模块；
		- 需要删除的部分打上删除线，不能直接删除；在原位增加新的内容。增加注释
	-  全局文件目录
		- Core_documents/library/prd. Md（整体的产品文档）
		- Core_documents/library/uiux. Md（整体的交互文档）
		- Core_documents/library/structure. Md（整体的架构文档）
2. 其他文件的维护要求：
  - 需要初始化的文档（操作人只给了要求，没做内容填充）：按照文档内的格式要求进行内容补充：
    - Core_documents/library/service. md（服务构建及 API 对接说明）
		- Core_documents/library/workflow. md（重点模块的业务流程）
		- Core_documents/library/database. md（数据库构建详情）
	- 不需要初始化的文档（操作人已经实现填充了内容） ：维护的时候只要是检查需不需要新增文件、替换矛盾的内容
		- CLAUDE.md（建立全局认知）
		- Core_documents/docs_index.md（建立全局认知之后根据此文件去定位重点阅读文件）
	- 没有格式要求的文档：AI 模型自行决定文档结构和内容
		- Core_documents/test_instances
		- Core_documents/library/history_record
		- Core_documents/library/develop_plan



### 其他机制：使用subagent进行文档搜索，节省context消耗


