# OSIM

## 项目简介

Open Security Information Model (OSIM) 是一个开源的安全数据标准化项目，旨在定义和规范安全数据的种类、字段格式、数据样例等 schema 信息。通过建立统一的数据标准，推动中国安全行业的数据开放与互联互通，实现跨厂商、跨产品的安全数据无缝对接。

## 项目背景

随着网络安全形势日益复杂，各类安全产品和系统产生了海量的安全数据。然而，由于缺乏统一的数据标准，不同厂商、不同产品之间的数据格式各异，导致：

- 数据孤岛现象严重
- 跨系统数据分析困难
- 安全运维效率低下
- 威胁情报共享受阻

OSIM项目希望通过建立行业公认的数据标准，解决这些痛点，促进安全生态的健康发展。

## 核心目标

- **标准化**: 定义统一的安全数据 schema 标准
- **开放性**: 推动安全数据的开放与共享
- **互联互通**: 实现跨厂商、跨产品的数据无缝对接
- **生态建设**: 构建健康、协作的安全开发生态

## 数据 Schema 范围

项目目前涵盖以下安全数据类型的 schema 定义：

- 设备检测（Device Detection）
- 日志信息（Log）
- 告警信息（Alert）
- 资产信息（Asset）
- 安全事件 (Security Incident)

## 项目结构

```
osim-schema/
├── schemas/                     # Schema 定义文件
│   ├── asset/           
│   ├── device_detection/
│   ├── log/
│   ├── alert/
│   └── incident/
├── faqs/
│   └── faq.md
├── examples/                   # 数据样例
├── tools/                      # 相关工具
│   ├── validators/             # Schema 验证工具
│   └── converters/             # 格式转换工具
├── CHANGELOG.md             	# 更改日志
├── CONTRIBUTING.md             # 贡献指南
├── CODE_OF_CONDUCT.md          # 行为准则
├── dictionaries.json           # 数据字典
├── valid.json        			# 数据校验
├── README.md          			# 项目说明
├── version.json          		# 版本文件
└── LICENSE                     # 开源协议
```

## 使用指南

- 安全工具：SIEM、SOAR、EDR和其他安全平台	# 链接到官网使用指南具体页面
- ...

## 如何贡献

我们欢迎所有形式的贡献！请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详细的贡献指南。

### 贡献方式

1. **报告问题**: 提交 Issue 反馈 bug 或建议新功能
2. **完善文档**: 帮助改进项目文档和示例
3. **提交代码**: 实现新功能或修复 bug
4. **扩展 Schema**: 添加新的安全数据 schema 定义
5. **推广项目**: 在社区中分享和推广 OSIM

### 开发流程

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## 许可证

本项目采用 Apache License 2.0 开源协议，详见 [LICENSE](LICENSE) 文件。

## 联系我们

- 项目主页: [GitHub Repository URL]
- 问题反馈: [GitHub Issues]
- 讨论区: [GitHub Discussions]
- 邮件列表: [Mailing List Address]

## 致谢

感谢所有为这个项目做出贡献的开发者、安全专家和组织！

## 相关项目

- [其他相关开源项目]
- [推荐工具和库]

---

**让我们一起推动中国安全行业的数据标准化和开放共享！**

欢迎 Star ⭐ 和 Fork 本项目，参与建设中国安全开源生态！