# Food Lab Cook · 从食材到做法

简体中文 | [English](README.md)

一个根据手头食材推荐家常做法的 Codex skill：先问口味和口感，再给出用量、火候、时间与熟度判断，让建议能直接用于下厨。

本项目参考 J. Kenji López-Alt 的《料理实验室》（*The Food Lab*）所讨论的烹饪原理，自行组织交互流程和家庭应用方案。它是独立项目，非作者或出版社的官方配套产品，也未获其背书。技能正文和参考资料目前为中文；英文 README 提供安装与使用说明。

## 快速使用

下载仓库，保留完整的 `skills/food-lab-cook` 文件夹，包括 `references/` 和 `agents/`。

首次安装到个人技能目录时，在下载后的仓库根目录运行：

```sh
mkdir -p ~/.agents/skills
cp -R skills/food-lab-cook ~/.agents/skills/
```

如果已安装 `food-lab-cook`，请检查后更新原有副本，避免在多个位置安装同名技能。当前 [OpenAI 官方文档](https://learn.chatgpt.com/docs/build-skills)列出的个人目录为 `~/.agents/skills`，项目目录为 `.agents/skills`；以当前环境配置为准。技能未出现时可重启 Codex。

显式调用示例：

```text
使用 $food-lab-cook。我有鸡腿和蘑菇，先问我的口味，再推荐做法。
```

交互示意：

> **你：** 有鸡腿和蘑菇。  
> **助手：** 想吃蒜香酱油、微辣下饭，还是清淡鲜香？更喜欢嫩滑还是焦香？  
> **你：** 蒜香酱油、焦香。两个人，只有平底锅，30 分钟。  
> **助手：** 推荐一道合适的菜，说明备料前提，给出用量、编号步骤、火力与时间范围、鸡肉安全中心温度，以及最影响成败的两点原理。

如果已经说明口味，技能会直接沿用；也可以说「随你推荐」。

## 能做什么

- 根据当前食材提供合适的口味选择。
- 围绕焦香、嫩度、水分和口感，结合厨具与时间选择方法。
- 使用克、毫升和摄氏度，配合可观察的结束信号。
- 提供替代调料，并根据「太咸、太柴、不脆」等反馈调整。

使用需要支持本地技能的 Codex 环境；无需原书文件、额外脚本或额外 API 凭据。已确认的偏好在本次对话内沿用，不自动写入全局技能。

## 文件结构

```text
README.md
README.zh-CN.md
.gitignore
skills/food-lab-cook/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── core-insights.md
    ├── ingredient-playbook.md
    ├── taste-and-sauces.md
    └── food-safety.md
```

[技能入口](skills/food-lab-cook/SKILL.md)按需要读取核心决策、食材处理、调味酱汁与家庭食品安全参考。资料中的书籍页序是整理时的版本定位记录，不要求用户取得某个特定 PDF。

## 来源与验证

主要参考：J. Kenji López-Alt，*The Food Lab: Better Home Cooking Through Science*，W. W. Norton，2015；中文版《料理实验室：科学创造美味》。书目信息见[作者的书籍页面](https://www.kenjilopezalt.com/books)。

食品安全另据 [FoodSafety.gov](https://www.foodsafety.gov/food-safety-charts/safe-minimum-internal-temperatures)及[香港食物安全中心](https://www.cfs.gov.hk/sc_chi/multimedia/multimedia_pub/multimedia_pub_fsf_139_04.html)整理，核对日期为 2026-10-11；其用途与书中追求特定口感的温度参数不同。

技能格式已通过验证。三组模拟回答检查了先问口味、遵守明确限制及区分食材处理方法的行为。这属于回答场景检查，尚非真实下厨测试；生成的配方仍需结合实际食材和设备判断。

## 版权与发布范围

**在以下边界内，当前纯文本技能可以作为公开到 GitHub 的候选。这是有条件的判断，不代表已取得权利人许可，也不能保证没有争议。**

版权区分原理、方法与具体表达。烹饪原理可以用于设计做法，但原书的解释文字、照片、插图和具有独创性的内容选择或编排仍可能受保护。依据：[WIPO 说明](https://www.wipo.int/en/web/copyright/protection)、[美国版权局 Circular 33](https://www.copyright.gov/circs/circ33.pdf)。

所审查的技能以重新撰写的原理说明和自行组织的家庭应用为主，未发现书页扫描、插图、长段摘录或完整原书食谱。本次审查覆盖技能文件及发布范围，未与原书逐句比对。改写、署名都不自动等于不侵权。[《中华人民共和国著作权法》第十三至十六条、第二十四条](https://zscqj.beijing.gov.cn/zscqj/zwgk/flfg18/436481084/index.html)要求整理、改编和汇编尊重原作品权利；个人学习的例外也不能直接用于公开传播原书。

公开范围仅限上方列出的文件。原书、封面图片、扫描页、OCR 全文及未经授权的下载链接均不属于发布内容。项目用于辅助下厨，不替代原书。

本项目首次发布应使用仅含干净发布文件的新目录，在那里初始化新仓库。不要复制当前工作项目的 `.git`，其中的本地快照对象包含参考资料。`.gitignore` 只能防止常规新增，不能清除已有 Git 对象或历史。

## 许可证状态

当前尚未选择明确的开源许可证。GitHub 公开仓库允许依平台条款查看和 fork，但这不自动赋予对受保护仓库文本的无限制复用权。参见 [GitHub 许可证说明](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository)。

项目不主张独占烹饪事实或方法。未来的许可证只能覆盖发布者有权许可的内容，不能为原书、中文译本或其他第三方作品授予使用权。
