# Code Workspace

本项目用于存放 VS Code 的 **多根工作区（Multi-root Workspace）** 配置文件，便于按业务或技术域组织和管理多个相关项目。

## 什么是 Code Workspace？

`.code-workspace` 是 VS Code 的多根工作区文件，允许在同一个编辑器中同时打开多个文件夹，并共享统一的配置。适合：

- 同时开发前后端关联项目
- 按业务域组织相关微服务
- 统一管理工作区级别的设置

## 工作区列表

| 工作区文件 | 说明 | 包含项目 |
|-----------|------|----------|
| `central_web.code-workspace` | Central 前端 Web 项目 | central-content-web, central-mkt-web, central-sns-web |
| `central_service.code-workspace` | Central 后端服务 | central-im-service, central-mkt-service, central-content-service |
| `ec.code-workspace` | EC 业务相关服务 | ec-item-service, ec-prebff-service, ec-mkt-service, ec-content-service |
| `mkt.code-workspace` | MKT 营销业务全栈 | ec-mkt-service, central-mkt-service, central-mkt-web |
| `sns.code-workspace` | SNS 社交业务全栈 | ec-sns-service, central-sns-service, central-sns-web |
| `prebff_item.code-workspace` | PreBFF 与 Item 服务 | ec-item-service, ec-prebff-service |

## 使用方法

1. **打开工作区**：在 VS Code 中通过 `文件 > 打开工作区` 选择对应的 `.code-workspace` 文件
2. **命令行打开**：`code sns.code-workspace` 或 `code central_web.code-workspace`
3. **最近使用**：VS Code 会记录最近打开的工作区，可从欢迎页快速进入

## 工作区配置

各工作区采用统一的排除规则，在文件树中隐藏以下目录以提升浏览效率：

- `node_modules`
- `bower_components`
- `.idea`
- `.vscode`
- `dist`

## 项目路径约定

工作区中引用的项目路径基于 `D:/git/` 目录，例如：

- `D:/git/ec/` - EC 相关服务
- `D:/git/central-service/` - Central 后端服务
- `D:/git/central-web/` - Central 前端项目

克隆或移动项目时，需确保路径与工作区配置一致，或手动编辑 `.code-workspace` 中的 `path` 字段。
