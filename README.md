# finagent

个人金融研究 agent：本地优先、可扩展、可自定义。

## 设计思路

- **插件与 agent 解耦**：能力以 MCP server（数据、搜索、抓取、Python 沙箱）和 Skills（分析流程、术语口径）的形式提供，任何支持 MCP 的 agent 都能使用。
- **agent 内核**：基于 [pi](https://github.com/earendil-works/pi) SDK，通过扩展钩子（`context` 等）注入个人上下文、裁剪大结果、加数字护栏。
- **数据层是核心**：统一表结构 + 可插拔数据源适配器（AKShare / Tushare / BaoStock ...），本地 DuckDB 存储。
- **数字靠代码算**：财务指标一律由代码计算，每个数字标注来源。

## 目录

| 目录 | 内容 |
|---|---|
| `mcp/` | MCP servers（Python）：数据、搜索、抓取、沙箱 |
| `agent/` | 基于 pi 的 agent 与扩展（TypeScript） |
| `skills/` | 分析流程与术语口径 |
| `docs/` | 设计文档 |

## 许可协议

本项目采用 [Functional Source License 1.1, MIT Future License (FSL-1.1-MIT)](LICENSE.md)：

- ✅ 个人使用、公司内部使用、学习、非商业研究、修改：都可以
- ❌ 不得将本软件用于与本项目竞争的商业产品或服务
- ⏳ 每个版本发布满 **2 年**后，自动转为 MIT 协议

如需商业授权，请联系作者。

依赖的第三方组件（如 [pi](https://github.com/earendil-works/pi)，MIT）遵循各自的协议。

## 免责声明

本项目仅用于个人研究与学习，不构成任何投资建议。
