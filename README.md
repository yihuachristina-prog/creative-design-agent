# 创意与设计 Agent

面向 Codex 的中文创意与设计工作流。简单任务直接比较可用成品，复杂项目先用提案和代表性样稿确定方向，再组织制作与验收。

## 自创 Agent 和配套 Skill

| 组件 | 用途 |
| --- | --- |
| Agent 角色 `creative-design` | 主会话可以把创意任务交给这个角色，由它调用配套 Skill 来组织制作。 |
| 配套 Skill `creative-design`（1.0.0） | 指导如何澄清需求、比较创意方向、选择制作工具，并按文案、图像、网页、演示或视频的要求验收成品。 |

[下载 Agent 和配套 Skill 1.0.0](creative-design-agent-v1.0.0.zip?raw=true)

### 安装与使用

1. 下载并解压压缩包，打开其中的 `creative-design-agent` 文件夹。
2. 将 `skills/creative-design` 目录复制到 `~/.agents/skills/`，将 `agents/creative-design.toml` 复制到 `~/.codex/agents/`。自定义 `CODEX_HOME` 的用户将角色文件放入该目录的 `agents/`。已有同名文件时先核对版本。
3. 新开 Codex 会话，用 `$creative-design` 调用工作流程，或要求“调用 creative-design 子智能体”。

包内含角色配置、完整 Skill 源码、三份工作参考和只读能力盘点脚本。盘点脚本的依赖 PyYAML 6.0.3 随包提供，原作者署名与 MIT 许可保存在包内。第三方设计和文案 Skills 可按任务另行安装。

## 第三方 Skill 清单

以下 25 项由各自的上游维护，可按任务独立安装。前 18 项用于创意制作与验收，另有 4 项品牌策略工具和 3 项飞书创作工具。

GitHub 链接指向已核对的具体版本。安装时可将名称和链接交给 Codex 的 `skill-installer`。其中 `ui-ux-pro-max` 使用作者的 CLI，归藏的 `guizang-ppt-skill` 从仓库根目录（`.`）安装。

### 创意制作与验收（18 项）

#### 营销文案

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `copywriting` | 从产品事实和受众出发，写标题、落地页与行动号召。 | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/0cd9b3a0ef4c411a1d690419ce843f2a1da32cce/skills/copywriting) |
| `copy-editing` | 保留品牌口吻，逐段改清楚卖点、证据和行动号召。 | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/0cd9b3a0ef4c411a1d690419ce843f2a1da32cce/skills/copy-editing) |

#### 品牌视觉

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `brandkit` | 构思 Logo、品牌规范板、包装样机与品牌形象图，需配合图像生成能力。 | [Leonxlnx/imagegen-skills](https://github.com/Leonxlnx/imagegen-skills/tree/beb16b0d0f4dae9a6f5cb04ea41e97b93a54ab8e/skills/brandkit) |
| `brand-to-design-md` | 从现有品牌网站和公开素材提炼颜色、字体、组件规则，输出 DESIGN.md。 | [shaom/brand-to-design-md-skill](https://github.com/shaom/brand-to-design-md-skill/tree/f7fe99e7a2985d4457d44bfab8399bb1cf1896c0/skills/brand-to-design-md) |
| `better-colors` | 生成与检查配色、语义色和文字对比度。 | [jakubkrehel/skills](https://github.com/jakubkrehel/skills/tree/592aedc44d7d5b3e29740984252902f3e5402a1c/skills/better-colors) |
| `better-typography` | 设置字体层级、字距、行距、断行与可读性规则。 | [jakubkrehel/skills](https://github.com/jakubkrehel/skills/tree/592aedc44d7d5b3e29740984252902f3e5402a1c/skills/better-typography) |

#### 网页与界面

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `frontend-design` | 为网站和应用选择视觉方向并实现页面。 | [anthropics/skills](https://github.com/anthropics/skills/tree/dbd4588f9e1033efb41dad4bef2f7947c8993d44/skills/frontend-design) |
| `design-taste-frontend` | 把版式、字体、动效和交互细节落实到前端。上游目录名为 taste-skill。 | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill/tree/12af471f627f866411b4bd785b19646d3672784c/skills/taste-skill) |
| `ui-ux-pro-max` | 搜索界面风格、配色、排版和技术栈建议。作者用 CLI 生成 Codex 版本。 | [CLI 安装说明](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/28b3b8dee8c976df4fa3e94aed4e092ad43fcb03/README.md#installation) |
| `impeccable` | 审视界面质量，调整布局、层级、视觉强度和一致性。 | [pbakaus/impeccable](https://github.com/pbakaus/impeccable/tree/6743a347db6229848348024388033e830ae4af42/.agents/skills/impeccable) |
| `variant` | 在同一页面比较组件备选方案。使用时需明确点名。 | [jakubkrehel/skills](https://github.com/jakubkrehel/skills/tree/592aedc44d7d5b3e29740984252902f3e5402a1c/skills/variant) |
| `web-design-guidelines` | 按 Web 界面准则检查可访问性、表单、导航等。 | [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills/tree/063bee94c3f4df8453406c830b0a7df0f2860278/skills/web-design-guidelines) |
| `vercel-react-best-practices` | 检查 React / Next.js 页面的加载和渲染性能。 | [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills/tree/063bee94c3f4df8453406c830b0a7df0f2860278/skills/react-best-practices) |

#### 演示与提案

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `ppt-design-skill` | 制作可编辑 PowerPoint，检查幻灯片结构和渲染效果。 | [sunchaokun/PPT-Design-Skill](https://github.com/sunchaokun/PPT-Design-Skill/tree/cbf7ef1324a026b29e2b77b71e2034554ddd3e22/skill) |
| `frontend-slides` | 制作带动画的网页演示，也支持把 PowerPoint 转为网页。 | [zarazhangrui/frontend-slides](https://github.com/zarazhangrui/frontend-slides/tree/9906a34d640d2111f724544cbc50f7f130569ae1/plugins/frontend-slides/skills/frontend-slides) |
| `guizang-ppt-skill` | 以电子杂志或瑞士风格做单文件、横向翻页的网页演示。 | [op7418/guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill/tree/c91369c449d34755d320a8b81d0734000d99d1ab) |

#### 动效与视频

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `motion-design` | 设计界面动效的节奏、缓动与状态过渡。 | [LottieFiles/motion-design-skill](https://github.com/LottieFiles/motion-design-skill/tree/f9a8a041b85185ee4881b3471d3415e939aac772/skills/motion-design) |
| `remotion-best-practices` | 用 React / Remotion 编排视频、字幕和动画，渲染需要相应项目环境。 | [remotion-dev/skills](https://github.com/remotion-dev/skills/tree/30d4553ecd46fbc5212fd0ff006ae43af522158b/skills/remotion-best-practices) |

### 品牌策略辅助（4 项）

用于撰写创意简报、确定品牌表达和评估品牌表现。

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `brand-context` | 建立品牌背景、目标受众、品牌价值和语气档案，供后续简报复用。 | [arnabbagxd/Brand-building-skills](https://github.com/arnabbagxd/Brand-building-skills/tree/4a0a8b5b7a0f64bf0fc551978a18a591670a5223/skills/brand-context) |
| `brand-positioning` | 明确目标心智、品牌差异和支撑理由。 | [arnabbagxd/Brand-building-skills](https://github.com/arnabbagxd/Brand-building-skills/tree/4a0a8b5b7a0f64bf0fc551978a18a591670a5223/skills/brand-positioning) |
| `brand-architecture` | 梳理母品牌、子品牌及产品线的命名与层级。 | [arnabbagxd/Brand-building-skills](https://github.com/arnabbagxd/Brand-building-skills/tree/4a0a8b5b7a0f64bf0fc551978a18a591670a5223/skills/brand-architecture) |
| `brand-measurement` | 定义品牌认知、偏好等指标，帮助创意简报写清衡量方式。 | [arnabbagxd/Brand-building-skills](https://github.com/arnabbagxd/Brand-building-skills/tree/4a0a8b5b7a0f64bf0fc551978a18a591670a5223/skills/brand-measurement) |

### 飞书创作工具（3 项）

链接指向飞书官方安装包。使用这些工具需要飞书 CLI 和相应的文档权限。

| Skill 名称 | 用途 | 安装链接 |
| --- | --- | --- |
| `lark-slides` | 创建和编辑飞书演示。 | [飞书下载](https://open.feishu.cn/lark-cli/skills/regular/.well-known/agent-skills/lark-slides.tar.gz) |
| `lark-whiteboard` | 绘制或编辑流程图、架构图和文档内画板。 | [飞书下载](https://open.feishu.cn/lark-cli/skills/regular/.well-known/agent-skills/lark-whiteboard.tar.gz) |
| `lark-apps` | 制作妙搭应用的界面原型、线框图和可交互页面。 | [飞书下载](https://open.feishu.cn/lark-cli/skills/regular/.well-known/agent-skills/lark-apps.tar.gz) |
