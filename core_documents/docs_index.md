# 项目文档导引索引 (Project Documentation Guide)

## 🎯 必读基础文档 (Essential Foundation Documents)

### CLAUDE.md（建立全局认知）
**文档性质**：项目全局认知基础，每次执行任务前必读
**核心内容**：项目概览、核心架构、Agent职责矩阵、工作原则、协作流程
**适用场景**：所有Agent在开始任何任务前都必须完整阅读此文档
**关键信息**：
- 项目是AI驱动的多Agent开发框架
- 两层协作架构：操作员直接指挥AI Agent团队
- 各Agent的专业分工和文档维护责任
- 人机协作的7步标准工作流程

### Core_documents/docs_index.md（文档导航地图）
**文档性质**：文档索引导航，建立全局认知后的定位工具
**核心内容**：完整文档结构、使用场景分类、快速定位指南
**适用场景**：确定具体任务需要阅读哪些相关文档
**关键信息**：按任务类型分类的文档阅读建议

---

## 🚀 开发新版本新功能推荐阅读 (New Development Documents)

### Core_documents/library/prd.md（产品需求文档）
**文档性质**：全局文件，需要版本控制，由ProductManagerAgent维护
**核心内容**：完整产品需求、用户故事、功能规格、验收标准
**适用场景**：开发任何新功能前了解产品需求和用户价值
**关键信息**：
- 目标用户群体和使用场景
- 核心功能需求和优先级排序
- 功能的商业价值和成功指标
- 与现有功能的关联和影响
**使用提示**：ArchitectAgent制定开发方案、ProductManagerAgent维护需求、EngineerAgent理解开发目标时必读

### Core_documents/library/uiux.md（用户体验设计文档）
**文档性质**：全局文件，需要版本控制，由ProductManagerAgent维护
**核心内容**：用户界面设计、交互流程、用户体验规范
**适用场景**：开发前端功能、设计用户交互、优化用户体验时必读
**关键信息**：
- 用户界面布局和视觉设计规范
- 用户操作流程和交互逻辑
- 响应式设计和多设备适配要求
- 可访问性和包容性设计标准
**使用提示**：FrontendEngineerAgent实现界面、ProductManagerAgent设计体验、ArchitectAgent考虑技术实现时必读

### Core_documents/library/structure.md（技术架构文档）
**文档性质**：全局文件，需要版本控制，由ArchitectAgent维护
**核心内容**：整体技术架构、技术选型、系统设计原则
**适用场景**：技术方案设计、架构决策、系统集成时必读
**关键信息**：
- 系统架构模式和组件关系
- 技术栈选择和版本信息
- 性能要求和扩展性设计
- 安全机制和数据保护策略
**使用提示**：ArchitectAgent设计方案、EngineerAgent选择技术、所有Agent了解技术约束时必读

---

## 🔍 深度排查问题需要阅读 (Deep Analysis Documents)

### Core_documents/library/develop_plan/（版本开发计划）
**文档性质**：无固定格式，由ArchitectAgent维护
**核心内容**：历次版本规划、开发计划、里程碑记录
**适用场景**：了解项目发展历程、分析开发模式、制定新版本计划
**关键信息**：
- 各版本的功能规划和实施路径
- 开发资源分配和时间安排
- 里程碑达成情况和经验总结
- 计划调整的原因和影响分析
**使用提示**：ArchitectAgent制定计划、ProjectAdminAgent沉淀经验时必读

### Core_documents/library/history_record/（开发历史记录）
**文档性质**：无固定格式，由EngineerAgent维护
**核心内容**：重点模块开发记录、问题解决方案、技术决策记录
**适用场景**：问题诊断、经验复用、技术债务管理
**关键信息**：
- 重要功能的开发过程和技术选择
- 遇到问题的分析过程和解决方案
- 性能优化的实施方案和效果评估
- 技术决策的背景、理由和结果评价
**使用提示**：EngineerAgent诊断问题、ArchitectAgent参考经验、ProjectAdminAgent总结知识时必读

### Core_documents/library/service.md（API服务文档）
**文档性质**：需要初始化格式，由ArchitectAgent维护
**核心内容**：API接口设计、服务架构、集成规范
**适用场景**：API开发、服务集成、接口调用、性能优化
**关键信息**：
- API端点定义和参数规范
- 服务间通信协议和数据格式
- 认证授权机制和安全控制
- 性能监控和错误处理机制
**使用提示**：ArchitectAgent设计API、EngineerAgent实现接口、所有Agent理解系统集成时必读

### Core_documents/library/workflow.md（业务流程文档）
**文档性质**：需要初始化格式，由ArchitectAgent维护
**核心内容**：重点模块业务流程、处理逻辑、状态转换
**适用场景**：理解业务逻辑、设计处理流程、优化用户体验
**关键信息**：
- 核心业务流程的步骤和决策点
- 数据流转和状态变化规则
- 异常处理和错误恢复机制
- 业务规则和约束条件
**使用提示**：ArchitectAgent设计流程、EngineerAgent实现逻辑、ProductManagerAgent优化体验时必读

### Core_documents/library/database.md（数据库设计文档）
**文档性质**：需要初始化格式，由ArchitectAgent维护
**核心内容**：数据模型设计、数据库结构、查询优化
**适用场景**：数据库设计、数据操作、性能优化、数据迁移
**关键信息**：
- 实体关系模型和字段定义
- 索引策略和查询优化方案
- 数据迁移和版本升级策略
- 数据备份和恢复机制
**使用提示**：ArchitectAgent设计数据模型、EngineerAgent实现数据操作、所有Agent理解数据结构时必读

### Core_documents/test_instances/（测试用例库）
**文档性质**：无固定格式，由EngineerAgent维护
**核心内容**：重点功能测试用例、测试数据、测试报告
**适用场景**：功能测试、回归测试、质量保证、问题复现
**关键信息**：
- 核心功能的测试用例和测试数据
- 自动化测试脚本和执行结果
- 性能测试数据和基准对比
- Bug记录和修复验证过程
**使用提示**：EngineerAgent设计测试、QAAgent执行质量保证、所有Agent验证功能时参考

---

## 📋 代码开发必须遵循 (Development Standards)

### Core_documents/project_rules.md（项目规范文档）
**文档性质**：项目规范基础，所有代码开发必须遵循
**核心内容**：编码规范、Git工作流、质量标准、最佳实践
**适用场景**：任何涉及代码开发的工作都必须严格遵循
**关键信息**：
- 代码风格和命名规范
- Git提交规范和分支策略
- 代码审查和质量检查标准
- 文档编写和维护规范
**使用提示**：EngineerAgent开发代码、所有Agent维护文档时必须严格遵循

---

## 📖 文档使用最佳实践 (Best Practices)

### 🔄 标准阅读流程
1. **必读基础**：始终先读CLAUDE.md建立全局认知
2. **任务导航**：根据docs_index.md确定任务相关文档
3. **深入研究**：按需深入阅读具体领域文档
4. **规范检查**：涉及开发时确保遵循project_rules.md

### 📊 文档分类说明
- **全局文件**：需要版本控制，更新时添加时间注释和删除线
- **初始化文件**：按既定格式补充内容，保持结构一致性
- **自由格式文件**：AI自行决定结构，重点关注内容完整性

### ⚡ 快速定位技巧
- **产品功能相关**：prd.md → uiux.md → structure.md
- **技术实现相关**：structure.md → service.md → database.md → workflow.md
- **问题诊断相关**：history_record → service.md → database.md → test_instances
- **项目管理相关**：develop_plan → history_record → project_rules.md
