# libtv识图转化专业视频提示词v1

将参考首帧与简短创意转为专业中文视频生成提示词。支持 LibTV 等自然语言视频工作流，也可用于接受类似提示词的视频模型。技能只编写提示词，不自动生成媒体或消费生成额度。

本技能已上架 Agensi AI Skills Marketplace，提供免费下载与安装。
在 Agensi 查看 LibTV Image to Video Prompts
本项目也可以直接通过 GitHub 获取。遵循 MIT 开源许可证，为独立开发项目，并非 LibTV 官方产品。

## 能做什么

- 先查看首帧，核对人物数量、道具接触、动作起点、空间与光线。
- 按指定时长编排分阶段动作，区分一镜到底与多镜头剪切。
- 设计连续运镜、自然对白、人物反应、环境声和拟音。
- 检查重力、手部操作、道具归属、口型目标与首尾连续性。
- 默认只输出专业提示词，不附精简版、风险表或额外报告。

不限古风、美食或人物场景；也适用于村景、日常生活、产品及其他参考画面。

## 安装到 Codex

需要可读取图片、支持 Skills 的运行环境。克隆此仓库，再将整个目录放入用户技能目录；已存在同名技能时先比较内容，不直接覆盖。

Windows PowerShell（默认用户目录）：

```powershell
git clone https://github.com/Traveller06/libtv-image-to-video-prompts-v1.git
New-Item -ItemType Directory -Force "$HOME/.codex/skills" | Out-Null
Copy-Item -Recurse ./libtv-image-to-video-prompts-v1 "$HOME/.codex/skills/image-to-video-prompts"
```

macOS / Linux（默认用户目录）：

```bash
git clone https://github.com/Traveller06/libtv-image-to-video-prompts-v1.git
mkdir -p ~/.codex/skills
cp -R libtv-image-to-video-prompts-v1 ~/.codex/skills/image-to-video-prompts
```

若你的环境自定义了技能目录，请放入实际目录；重新打开会话后检查技能是否被发现。其他支持 SKILL.md 的工具可按各自的导入方式安装；没有技能加载功能时，也可以直接阅读 SKILL.md 并将其作为工作说明使用。

## 使用示例

上传参考图片后输入：

> 使用 $image-to-video-prompts，分阶段一镜到底，时长7秒，三句对白。

> 使用 $image-to-video-prompts，5秒，大胆连续运镜，有环境音和烟火气，无人声。

> 使用 $image-to-video-prompts，继承首帧，两镜，总长8秒，不要改变人物服装。

可补充：不可改变的内容、指定台词、角色对应、画幅、声音参考、动作结果与字符上限。缺失关键参考图片时，技能会请求附件，而不是猜测画面。

## 默认输出

【首帧与视觉】、【动作与表演】、【时间轴】、【镜头】、【声音】、【物理与连续性】、【关键锁定】、【负面约束】、【最终画面】。

## 能力边界

- 时间节点是生成引导，不能保证逐帧执行。
- 图片不包含声音；保持音色需要实际配音设置、音色ID或参考音频。
- 口型和多角色一致性取决于所选模型及后期流程。
- 本仓库不绑定模型接口、不提供视频生成服务、不包含 API 密钥或用户媒体。
- 安装技能不等于获得 LibTV 或其他平台授权。

## 文件结构

```text
SKILL.md                 核心规则与输出流程
agents/openai.yaml       技能名称与默认调用提示
references/patterns.md   短对白、运镜与边界处理示例
```

## 贡献

欢迎通过 Issues 或 Pull Requests 提交改进。反馈时请附可公开的输入要求、实际输出和期望差异；使用示例图片或音频前请确认有相应权限，不提交隐私或密钥。

## 许可证

MIT License，见 [LICENSE](LICENSE)。本项目为独立提示词技能，与 LibTV 等平台不存在官方隶属关系。
