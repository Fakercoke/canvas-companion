# Canvas Companion

**让你的 AI 帮你找到 Canvas 作业要求、截止时间和指定阅读。**

这是一个给学生和 AI Agent 一起使用的开源 Skill 包：先检查怎样连接，再用有来源的结果完成学习任务。你不需要先学会写 MCP。

**当前版本：0.1.0 试用版。** 需要能读取本地文件的 Agent；真实连接还需要客户端能力、学校权限和用户授权。本项目不提供通用 Canvas 登录服务，不包含账号、密钥或课程资料。

## 下载后，先把这句话发给 Agent

将下载的文件夹解压并放到 Agent 能读取的位置，然后复制：

> 请读取这个项目的 `skills/canvas-companion/SKILL.md`。先用其中的虚构演示资料，展示你能怎样整理作业；不要访问真实账号。然后检查你当前是否有 Canvas 连接器或可操作的浏览器，告诉我可以采用哪种连接方式。不要让我把密码或 token 发到聊天里。

如果 Agent 看不到文件夹，请先在客户端打开该文件夹，或把 Skill 及其 references、assets 一起放入它支持的文件环境。**只上传一个 SKILL.md，可能会丢失配套说明。** 普通聊天窗口未必能安装 MCP 或操作浏览器。

## 它能帮你做什么

| 你问 | 它应该交付 | 不会凭空承诺 |
|---|---|---|
| 我这周有什么要交？ | 作业、截止时间、提交状态和来源链接 | 数据不完整时不说“没有作业” |
| 这份作业到底要求什么？ | 硬性要求、评分标准、AI 规则、待确认项 | 找不到评分表时不编造评分表 |
| 我应该先看哪些阅读？ | 指定阅读入口与建议顺序 | 只有摘要时不声称读过全文 |
| 我交上去了吗？ | 已提交、仅上传或状态未知的证据 | 附件已上传不等于最终提交成功 |
| 给我排一个学习计划 | 基于真实截止时间与用户空闲时间的建议 | 不自动写作业、考试、发消息或提交 |

本包默认工作流只做读取与整理；这是一条使用约定，**不是对底层账号权限的技术隔离**。

## 它怎样连接

1. **已有可用连接器**：先检查工具和权限，再读取你选定的一门课。
2. **学校认可的 MCP 服务**：按学校或服务提供方的说明完成 OAuth 授权。[客户端接入说明](skills/canvas-companion/references/clients.md)
3. **没有连接器，但 Agent 有浏览器操作能力**：由你在学校官方页面登录，然后按需读取页面。[浏览器流程](skills/canvas-companion/references/connect.md)
4. **两者都没有**：明确说明缺少什么；可以先用演示资料体验，或整理你获准提供的材料。

Canvas 普通网址不是 MCP 服务地址。不要把账号密码交给仓库作者。官方 API 文档要求多人使用的应用通过 OAuth 获取令牌；本项目不会把“让所有同学手工交 token”包装成通用登录方案。[Canvas 授权说明](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth)

## 谁适合用

- 不熟悉配置，但已经在使用有文件和工具能力的 Agent 的同学。
- 想让 Agent 按固定流程核对任务，而不是每次重新解释要求的人。
- 愿意帮助测试不同客户端、学校和课程场景的维护者。

已经熟练连接 Canvas、会核对来源的用户，直接提示 AI 可能就够了。本项目对这类用户的额外价值有限。

## 和现有工具是什么关系

Canvas MCP 连接器已经有多个社区实现。本项目提供的是入门引导、连接选择、任务工作流和演示资料，**没有重新实现 MCP 服务，也不声称发明了 AI 连接 Canvas**。

我们研究了 [vishalsachdev/canvas-mcp](https://github.com/vishalsachdev/canvas-mcp)，没有复制或打包它的代码。它的配置方式、适用权限和维护状态应由使用者单独核对。详情见 [来源与致谢](THIRD_PARTY.md)。

## 能力与测试范围

| 内容 | 本版状态 |
|---|---|
| Skill 文件、相对链接、演示资料结构 | 已完成文件格式、相对链接和解压检查 |
| 虚构数据中的日期冲突、上传未提交、缺失评分表 | 提供示例与预期输出；不等于真实账号测试 |
| Codex、Cursor、Claude Code 的 MCP 配置路径 | 对照官方文档编写，尚未逐客户端安装实测 |
| Claude Desktop | 引导检查其当前连接器功能；不承诺自动读取本地 Skill |
| 不同学校的 OAuth、SSO、阅读平台 | 未验证通用兼容性；逐校确认 |

## 数据与学术使用

只选择当前任务需要的课程和材料。本地连接器取得的数据仍可能发送到你所用的 AI 服务；“本地运行”不等于“内容绝不离开电脑”。遵守学校对课程材料和 AI 使用的要求；不得把可以登录理解为可以把所有资料交给外部 AI。

不要在 GitHub Issue、截图或聊天中贴 token、密码、学生资料、私有作业或原始日志。报告问题前先脱敏。[排错说明](skills/canvas-companion/references/troubleshooting.md)

## 项目与许可

项目地址：[Fakercoke/canvas-companion](https://github.com/Fakercoke/canvas-companion)。

反馈时请提供客户端、操作系统和失败阶段，先移除私人资料和凭据。

本项目文件采用 [MIT 许可证](LICENSE)。不代表 Canvas、Instructure、OpenAI、Anthropic、Cursor 或任何学校的官方产品。文档与 Skill 使用 AI 辅助起草。

## English summary

Canvas Companion is a student-oriented onboarding and workflow skill, not a Canvas MCP server. Ask your file-capable agent to read `skills/canvas-companion/SKILL.md`, try the fictional demo, and inspect available connection methods. It prefers an existing authorized connector, an institution-approved OAuth service, or a user-authenticated browser when supported. It does not collect credentials or promise universal compatibility. Client setup instructions are documented, not end-to-end certified. Replies should separate verified requirements, recommendations and unavailable evidence. File structure and relative links have been checked; fresh-user installations and live cross-client connections have not been tested.
