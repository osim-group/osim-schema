# 贡献指南

感谢您对 Open Security Information Model (OSIM) 项目的关注！我们热烈欢迎社区成员参与贡献，共同推动安全数据标准化的发展。

## 贡献者行为准则

参与本项目即表示您同意遵守我们的 [行为准则](CODE_OF_CONDUCT.md)。请在您与项目的所有互动中遵循它。

## 开始贡献

### 前置要求

- 基本的 Git 和 GitHub 使用知识
- 了解 JSON 格式
- 熟悉网络安全基础概念（针对 Schema 贡献）

### 首次贡献

如果您是首次贡献者，我们推荐从以下类型的任务开始：

- 文档改进和错别字修正
- 现有 Schema 描述的优化
- 为字段添加更清晰的描述或示例
- 报告明确的 Schema 定义问题

您可以在 Issue 列表中寻找标有 `good first issue` 或 `help wanted` 的标签。

## 贡献流程

### 1. 报告问题

#### 创建 Issue
在创建新 Issue 前，请：
- 检查 [Issue 列表](https://github.com/osim-group/osim-schema/issues) 是否已有类似问题
- 使用清晰的标题和描述
- 对于 Schema 问题，提供具体的 Schema 名称和字段名称
- 描述期望的行为或改进建议

#### Issue 模板
我们提供以下 Issue 模板：
- **Schema 问题**: 用于报告 Schema 定义中的问题
- **文档改进**: 用于文档相关的改进建议
- **功能请求**: 用于建议新的 Schema 或字段
- **问题咨询**: 用于技术咨询和讨论

### 2. 开发环境设置

#### Fork 和克隆仓库
```bash
# Fork 本仓库到您的 GitHub 账户
# 克隆您的 fork
git clone https://github.com/您的用户名/osim-schema.git
cd osim-schema

# 添加上游仓库
git remote add upstream https://github.com/osim-group/osim-schema.git
```

### 3. 创建分支

我们使用特性分支工作流：
```bash
# 从 main 分支创建新分支
git checkout -b schema/简短描述
# 或者修复问题
git checkout -b fix/问题描述
```

分支命名约定：
- `schema/`: 新增或修改 Schema
- `docs/`: 文档改进
- `fix/`: 问题修复
- `enhancement/`: 现有 Schema 的优化

### 4. 进行修改

#### Schema 开发指南

**新增 Schema**
1. 确定适当的 `group` 和 `category`（参考现有 Schema 的分类）
2. 创建新的 JSON 文件
3. 遵循以下结构格式：
```json
{
  "group": "log",
  "category": "category_name",
  "title": "schema_name",
  "label": "Human Readable Label",
  "description": "Detailed description of this schema's purpose and usage scenarios.",
  "tag": ["relevant", "tags"],
  "dataSource": ["Data Source 1", "Data Source 2"],
  "definitions": {
    "fieldName": {
      "label": "Field Label",
      "requirement": "REQUIRED/OPTIONAL/RECOMMENDED",
      "description": "Detailed description of the field, including its purpose and usage.",
      "type": "string/integer/long/boolean/array/enum",
      "valid_type": "string_t/integer_t/boolean_t/array_t",
      "dataSource": ["Optional data source information"],
      "enum": {
          "enumValue": {
              "label": "Enum Label",
              "description": "Detailed description of the value"
          }
      }
    }
  }
}
```

**修改现有 Schema**

1. 保持向后兼容性，避免删除或重命名现有字段
2. 如果需要添加新字段，确保它们有清晰的描述
3. 更新字段的 `requirement` 属性时要谨慎

**字段定义规范**

- `requirement`: 必须为 "REQUIRED"、"OPTIONAL" 或 "RECOMMENDED"
- `type`: 基本的数据类型
- `valid_type`: 更具体的验证类型（参考现有 Schema 的用法），详情可见[valid.json](https://github.com/osim-group/osim-schema/blob/main/valid.json)
- `description`: 必须清晰说明字段的用途和预期值

**分类指南**
- **group**: 高层次分组（如 log, alert, incident等）
- **category**: 更具体的分类（如 authentication_and_access, network_security 等）
- **tag**: 用于搜索和过滤的关键词
- **dataSource**: 此 Schema 适用的数据源类型

#### 文档贡献
- 确保所有字段都有完整的中文或英文描述
- 更新 README.md 中的分类说明
- 添加 Schema 使用的最佳实践指南
- 维护数据字典和术语表

### 5. 提交更改

#### 提交消息规范
我们采用约定式提交：
```
<类型>[可选的作用域]: <描述>

[可选的正文]

[可选的脚注]
```

类型包括：
- `feat`: 新增 Schema 或字段
- `fix`: Schema 问题修复
- `docs`: 文档更新
- `enhance`: 现有 Schema 的优化
- `refactor`: Schema 结构调整
- `other`: 其他更新内容

示例：
```bash
git commit -m "feat(authentication): 新增应用访问认证 Schema

- 新增 application_access_authentication.json
- 包含 machineCode 等必需字段
- 添加相关标签和数据源
- 提供详细的字段描述

Closes #123"
```

### 6. 推送和创建 Pull Request

```bash
# 推送到您的 fork
git push origin schema/您的功能名称
```

然后在 GitHub 上创建 Pull Request：

#### PR 模板要求
每个 PR 应该包含：
- **清晰的标题**: 描述修改内容
- **详细描述**: 说明修改的原因、内容和影响
- **相关 Issue**: 链接到相关的 Issue
- **验证说明**: 描述如何验证这些修改
- **检查清单**: 确保完成所有必要步骤

#### PR 检查清单
在创建 PR 前，请确认：
- [ ] Schema 格式正确，符合 JSON 规范
- [ ] 字段描述清晰完整
- [ ] 使用了正确的分类和标签
- [ ] 更新了相关文档（如需要）
- [ ] 提交信息符合规范
- [ ] 分支与最新 main 分支同步

## 贡献领域

### Schema 设计贡献
- 新增Schema类型
- 添加新的字段定义
- 优化现有字段描述
- 扩展数据源支持

### 分类体系贡献
- 建议新的 group 或 category
- 改进标签系统
- 建立 Schema 间的关系

### 文档贡献
- 完善字段描述和示例
- 编写使用指南和最佳实践
- 创建 Schema 关系图
- 翻译文档内容

### 社区贡献
- 回答问题，帮助其他用户
- 评审其他人的 PR
- 分享实施经验
- 参与社区讨论

## 审查流程

1. **格式检查**: 验证 JSON 格式正确性
2. **内容审查**: 至少需要一名维护者审查 Schema 内容
3. **一致性检查**: 确保与现有 Schema 保持一致性
4. **修改请求**: 如有需要，贡献者根据反馈进行修改
5. **合并**: 审查通过后由维护者合并

### 审查重点
- Schema 结构的完整性和正确性
- 字段描述的清晰度和准确性
- 分类和标签的合理性
- 与现有 Schema 的一致性
- 向后兼容性考虑

## 社区角色

### 贡献者
所有提交过 PR 的社区成员都是贡献者。

### 维护者
活跃的贡献者可能被邀请成为维护者，职责包括：
- Schema 审查和合并
- Issue 分类和响应
- 项目发展规划
- 版本发布管理

## 获取帮助

- **技术问题**: 在 GitHub Discussions 中提问
- **Schema 设计咨询**: 在 Issue 中讨论
- **文档**: 查看项目文档

## 版本发布

项目采用语义化版本控制：
- **主版本 (X.0.0)**: 不兼容的 Schema 修改
- **次版本 (0.X.0)**: 向后兼容的功能新增
- **修订号 (0.0.X)**: 向后兼容的问题修正

发布流程：
1. Schema 冻结和社区审查
2. 版本号确定和更新
3. 正式版本发布
4. 发布公告

## 知识产权

- 所有贡献必须遵循项目的开源协议
- 贡献者保留其内容的版权，但同意在项目协议下授权使用
- 确保您的贡献不侵犯第三方知识产权

## 致谢

所有贡献者都将被列入项目的致谢列表。重大的贡献可能会获得维护者提名。

---

再次感谢您的贡献！您的参与让开源社区更加美好。

如有任何问题，请随时在 Issue 中提出或通过讨论区联系我们。

Happy Contributing! 🎉
