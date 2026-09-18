# Canvas Companion

**让 AI 带你连接 Canvas，直接读课程、整理学习任务、辅助完成并提交作业。**

很多同学不知道：具备合适工具并得到授权的 AI Agent，可以直接访问自己的 Canvas，不必每次手动下载课件、再上传给 AI。这个开源 Skill 把接入步骤和连接后的使用方法交给 Agent，让它指导没有技术背景的用户操作。

**版本 0.2.0：连接引导与课程工作流。** 它不是自带登录服务的应用，也不增加账号权限。真实接入需要可用连接器/API 工具，或 Agent 能操作的浏览器；普通聊天窗口不一定具备这些能力。

## 下载后，把这句话交给 AI

下载并解压完整项目，在你的 Agent 中打开该文件夹，然后发：

> 请读取 `skills/canvas-companion/SKILL.md`，带我连接自己的 Canvas。我不懂配置，请检查你当前能用的工具，一步步告诉我需要做什么；能由你完成的配置请直接协助完成。解释需要的授权或 key，但不要让我把密码或 token 发到聊天里。连接后先验证能读到一门课，再告诉我可以怎样使用。

如果 Agent 看不到文件，将完整 `skills/canvas-companion` 文件夹放入它支持的文件环境；只给一个 SKILL.md 会缺少配套指南。支持原生 Skills 的客户端可按其当前安装方式载入同一文件夹。[客户端说明](skills/canvas-companion/references/clients.md)

不想先登录？可以说：“先用虚构资料给我演示一次。”演示是可选项。

## AI 会怎样带你连接

1. **检查环境**：有没有已连接的 Canvas 工具、API 能力或浏览器控制能力；已有可用连接就复用。
2. **确定学校入口**：指导你在官方页面登录并完成 MFA，或走实际提供的连接器 OAuth 授权。
3. **解释 key 和配置**：区分学校网址、个人访问 token、应用 developer key；按实际工具的配置方式操作。个人开发测试用 token 的位置、保管、验证与撤销见[密钥指南](skills/canvas-companion/references/keys.md)。
4. **验证结果**：真正读到课程和一个资源，给出链接；不把“配置保存了”当成连接成功。
5. **遇到阻塞说明具体缺什么**：例如客户端没有浏览器工具、学校未提供服务、权限不足；不让你盲目重复配置。

[完整连接流程](skills/canvas-companion/references/connect.md)。浏览器路线不需要手动生成 key。Canvas 官方把个人开发测试 token 与多人应用授权分开：多人应用须使用 OAuth。本项目不收集用户凭据，也不提供通用 OAuth 服务。[官方说明](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth)

## 连上以后，可以这样用

| 你对 AI 说 | Skill 指导它完成什么 |
|---|---|
| 读一下这门课的全部资料，告诉我学什么 | 建立模块、页面、公告、文件和阅读清单，分批读取内容，说明读完、部分读到和无法访问的材料 |
| 看我这学期所有课，整理待办 | 汇总可访问课程的作业、quiz 截止日期和提交状态，给出来源及缺口 |
| 按老师要求帮我准备这份作业 | 读取题目、rubric、指定阅读及 AI 规则，结合你的观点，辅助大纲、允许的草稿、修改及文件输出 |
| 我不想再手动下载课件给你 | 通过已有授权工具读取或下载到私有工作目录，再使用文档工具处理；外部图书馆可能仍需你登录 |
| 帮我理解阅读，准备 quiz | 根据实际材料解释概念、生成练习；按测验规则协助允许的答题和检查 |
| 把这个最终文件交到这份作业 | 核对课程、作业和文件，在明确授权下上传并提交，检查回执；不把上传成功误报成提交成功 |

这些是 **Agent 操作流程**，不是随包提供的 API 实现。具体能做多少取决于宿主工具、学校权限和课程规则。阅读整门课会分批进行，并报告覆盖情况；不承诺一次获取所有受限内容。开始计时 quiz、提交答案和个人声明可能需要进一步明确的用户操作或授权。

## 项目包含什么

- `skills/canvas-companion/SKILL.md`：Agent 入口，先接入，再按用户目标执行。
- `references/connect.md`、`keys.md`、`clients.md`：连接路线、密钥解释与配置指导。
- `references/course-reading.md`：整门课、跨课程的读取和覆盖记录。
- `references/tasks.md`：作业输出、管理、提交及 quiz 协助流程。
- `references/troubleshooting.md`：连接故障定位。
- `assets/`：不需要账号的虚构演示。

## 价值与边界

它没有发明 Canvas 接口，也没有重新实现 MCP。价值是把“原来能连”变成可交给 AI 执行的引导与工作流程，减少用户自己查配置和反复传文件的负担。熟练用户用完整提示词也能完成类似工作；Skill 的作用是复用这些步骤。

现有社区连接器可作为工具来源，但须核对其当前配置、授权方式与权限。我们研究过 [vishalsachdev/canvas-mcp](https://github.com/vishalsachdev/canvas-mcp)，没有复制或打包其代码。[来源与致谢](THIRD_PARTY.md)

课程允许的 AI 使用范围决定如何协助作业与测验。能登录不等于能把所有材料发给外部 AI。账号的实际权限由平台和连接器控制，Skill 指令不是权限隔离。仅在用户要求提交时执行提交；一次读取不授权其他写入。私人数据、密钥、作业和输出应留在项目之外。

## 验证范围

旧版曾由无聊天背景 Agent 从公开仓库完成虚构演示，识别日期冲突、缺失评分表及上传未提交。本版扩展了接入、整门课读取、产出和提交指导；文件检查不能证明真实连接成功。尚未逐一验证各客户端安装、不同学校登录、真实提交或 quiz 操作，不宣称跨学校即装即用。

报告问题请说明客户端、操作系统及失败阶段，移除密码、token、学生资料和私有课程内容。[排错指南](skills/canvas-companion/references/troubleshooting.md)

## 许可

[MIT](LICENSE)。非 Canvas、Instructure、任何 AI 厂商或学校官方产品。文档与 Skill 使用 AI 辅助起草。

## English summary

Canvas Companion teaches a file-capable AI agent to guide beginners through Canvas connection, then read courses directly, organise work, prepare permitted deliverables and submit explicitly authorised work with receipt checks. It includes credential guidance, course-reading procedures and an optional fictional demo. It supplies no universal connector or login service. Live capabilities depend on client tools, school access and assessment rules; cross-client connections, real submissions and quiz operations are not certified.
