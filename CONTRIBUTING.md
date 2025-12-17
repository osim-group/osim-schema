
# 贡献指南

感谢您对 Open Security Information Model (OSIM) 项目的关注！我们热烈欢迎社区成员参与贡献，共同推动安全数据标准化的发展。

## 贡献者行为准则

参与本项目即表示您同意遵守我们的 [行为准则](CODE_OF_CONDUCT.md)。请确保阅读并理解其中的内容，请在您与项目的所有互动中遵循它。

## 开始贡献

### 前置要求

- 基本的 Git 和 GitHub 使用知识
- 了解 JSON格式
- 熟悉网络安全基础概念（针对技术贡献）

### 首次贡献

如果您是首次贡献者，我们推荐从以下类型的任务开始：

- 文档改进和错别字修正
- 内容及语法更正
- 对现有内容的扩展，当扩展有令人信服的理由时
- 报告明确的 bug

您可以在 Issue 列表中寻找标有 `good first issue` 或 `help wanted` 的标签。

## 贡献流程

### 1. 报告问题

#### 创建 Issue
在创建新 Issue 前，请：
- 检查 [Issue 列表](链接到项目的 Issues 页面) 是否已有类似问题
- 使用清晰的标题和描述
- 提供详细的重现步骤（针对 bug）
- 附上相关日志或截图

#### Issue 模板
我们提供以下 Issue 模板：
- **Bug 报告**: 用于报告缺陷
- **功能请求**: 用于建议新功能
- **文档改进**: 用于文档相关的改进建议
- **问题咨询**: 用于技术咨询和讨论

### 2. 开发环境设置

#### Fork 和克隆仓库
```bash
# Fork 本仓库到您的 GitHub 账户
# 克隆您的 fork
git clone https://github.com/您的用户名/open-security-information-model.git
cd open-security-information-model

# 添加上游仓库
git remote add upstream https://github.com/原组织/open-security-information-model.git
```

#### 环境要求
- Node.js 14+ (用于工具脚本)
- Python 3.8+ (可选，用于验证工具)
- 文本编辑器或 IDE

### 3. 创建分支

我们使用特性分支工作流：
```bash
# 从 main 分支创建新分支
git checkout -b feature/您的功能名称
# 或者修复 bug
git checkout -b fix/问题描述
```

分支命名约定：
- `feature/`: 新功能
- `fix/`: bug 修复
- `docs/`: 文档改进
- `test/`: 测试相关
- `refactor/`: 重构代码

### 4. 进行修改

#### Schema 开发指南

**添加新 Schema**
1. 更新 `dictionaries.json` 和 `valid.json`
2. 参考现有 schema 的结构
3. 在 `schemas/` 目录下创建相应的子目录
4. 在 `examples/` 中添加对应的数据样例

**Schema 规范要求**
```json
{
  "title": "Descriptive Title",
  "description": "Clear description of the schema purpose",
  "type": "object",
  "properties": {
    "required_field": {
      "type": "string",
      "description": "字段描述",
      "example": "示例值"
    },
    "optional_field": {
      "type": "integer",
      "description": "可选字段描述",
      "example": 123
    }
  },
  "required": ["required_field"],
  "additionalProperties": true
}
```

#### 文档贡献
- 所有Schema 都需要文档
- 使用清晰的中文编写
- 提供实际的数据示例
- 更新相关的 README 文件

#### 代码贡献
- 遵循项目的代码风格
- 添加适当的注释
- 补充优化项目工具
- 更新相关的测试用例

### 5. 提交更改

#### 提交消息规范
我们采用约定式提交：
```
<类型>[可选的作用域]: <描述>

[可选的正文]

[可选的脚注]
```

类型包括：
- `feat`: 新功能
- `fix`: bug 修复
- `docs`: 文档更新
- `style`: 代码格式调整
- `refactor`: 重构
- `test`: 测试相关
- `chore`: 构建过程或辅助工具变动

示例：
```bash
git commit -m "feat(alert): 添加恶意软件检测告警 schema

- 新增 malware_detection 事件类型
- 添加恶意软件家族字段
- 更新相关数据字典

Closes #123"
```

### 6. 推送和创建 Pull Request

```bash
# 推送到您的 fork
git push origin feature/您的功能名称
```

然后在 GitHub 上创建 Pull Request：

#### PR 模板
每个 PR 应该包含：
- **清晰的标题**: 描述修改内容
- **详细描述**: 说明修改的原因和内容
- **相关 Issue**: 链接到相关的 Issue
- **测试说明**: 描述如何测试这些修改
- **检查清单**: 确保完成所有必要步骤

#### PR 检查清单
在创建 PR 前，请确认：
- [ ] 代码遵循项目的编码规范
- [ ] 添加或更新了必要的测试
- [ ] 所有测试通过
- [ ] 更新了相关文档
- [ ] 提交信息符合规范
- [ ] 分支与最新 main 分支同步

## 贡献领域

### 技术贡献
- 新增或改进 Schema 定义
- 开发验证工具和脚本
- 性能优化
- 测试框架改进

### 文档贡献
- 完善使用指南和教程
- 改进 API 文档
- 翻译文档
- 添加使用案例

### 社区贡献
- 回答问题，帮助其他用户
- 评审其他人的 PR
- 推广项目
- 组织或参与社区活动

## 代码审查流程

1. **初步检查**: 维护者检查 PR 的基本要求
2. **自动化测试**: CI/CD 流水线运行测试
3. **代码审查**: 至少需要一名维护者的批准
4. **修改请求**: 如有需要，贡献者根据反馈进行修改
5. **合并**: 审查通过后由维护者合并

### 审查重点
- 功能正确性
- 代码质量
- 测试覆盖
- 文档完整性
- 性能影响

## 社区角色

### 贡献者
所有提交过 PR 的社区成员都是贡献者。

### 维护者
活跃的贡献者可能被邀请成为维护者，职责包括：
- 代码审查和合并
- Issue 分类和响应
- 项目发展规划
- 版本发布

## 获取帮助

- **技术问题**: 在 GitHub Discussions 中提问
- **即时交流**: 加入我们的 [Slack/Discord 频道]
- **文档**: 查看项目文档和 FAQ
- **邮件**: 发送邮件到 [项目邮箱]

## 版本发布

项目采用语义化版本控制：
- **主版本**: 不兼容的 API 修改
- **次版本**: 向下兼容的功能新增
- **修订号**: 向下兼容的问题修正

发布流程：
1. 功能冻结和测试
2. RC 版本发布和社区测试
3. 正式版本发布
4. 发布公告和文档更新

## 知识产权

- 所有贡献必须遵循项目的开源协议
- 贡献者保留其代码的版权，但同意在项目协议下授权使用
- 确保您的贡献不侵犯第三方知识产权

## 致谢

所有贡献者都将被列入项目的 [致谢列表](致谢文件链接)。重大的贡献可能会获得维护者提名。

---

再次感谢您的贡献！您的参与让开源社区更加美好。

如有任何问题，请随时联系我们。

Happy Contributing! 🎉
