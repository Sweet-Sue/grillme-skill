# grill-me：Codex 中文深度访谈 Skill

一个面向 Codex 的中文技能，让 Codex 暂时不急着给答案，而是通过一次一个问题的访谈，帮助你把计划、产品想法、技术设计或实施方案讲清楚。

它会持续检查目标、范围、依赖、风险、边界情况和验收标准，直到双方对方案形成共同理解。

> 这是社区技能，不是 OpenAI 官方项目。

## 功能

- 每轮只问一个最重要的问题，避免一次抛出大量问题。
- 优先解决会影响后续决策的关键前置条件。
- 在可以检查工作区、文件、代码或配置时，先自行检查再提问。
- 主动追问范围、非目标、约束、边界情况、失败处理和验收标准。
- 区分已经确认的信息、仍未验证的假设和需要处理的风险。
- 访谈结束后输出目标、决策、假设、风险、验收标准和下一步建议。
- 默认使用中文交流，同时保留 `grill me` 英文触发语。

## 适用场景

- 产品方案评审
- 软件架构和数据库设计
- 数据分析项目规划
- 工作流程设计
- 实施计划和需求澄清
- 个人决策与方案比较

## 安装

### 方法一：Git 克隆

把下面地址中的 `YOUR_GITHUB_USERNAME` 替换成实际 GitHub 用户名：

```powershell
git clone https://github.com/YOUR_GITHUB_USERNAME/grill-me-codex-skill.git "$env:USERPROFILE\.codex\skills\Grill-Me"
```

如果设置了自定义 `CODEX_HOME`，请把仓库放入对应的 `skills\Grill-Me` 目录。

### 方法二：手动安装

1. 下载仓库 ZIP 文件并解压。
2. 将文件夹重命名为 `Grill-Me`。
3. 把它放入 `C:\Users\你的用户名\.codex\skills\`。
4. 确认 `Grill-Me` 文件夹根目录中存在 `SKILL.md`。
5. 新建 Codex 对话；如果技能没有出现，请重启 Codex。

安装后的结构应当类似：

```text
C:\Users\你的用户名\.codex\skills\Grill-Me\
├── README.md
├── SKILL.md
└── agents\
    └── openai.yaml
```

`README.md` 用于 GitHub 项目介绍；Codex 实际执行的规则来自 `SKILL.md`。

## 使用方法

在 Codex 输入框中显式调用：

```text
$grill-me
请用中文逐题检查我的项目计划，找出风险和遗漏。
```

也可以直接使用自然语言触发：

```text
请压力测试这个数据库设计，一次只问我一个问题。
```

```text
挑战一下我的方案，直到实施需求和验收标准都明确。
```

## 工作方式

1. 明确目标，以及方案服务的用户或对象。
2. 明确范围和不准备处理的内容。
3. 按依赖关系逐一解决设计或实施选择。
4. 检查风险、边界情况、运行限制和失败处理。
5. 定义完成条件和验收方式。
6. 输出共同理解总结和建议的下一步。

## 仓库内容

```text
grill-me-codex-skill/
├── README.md             # GitHub 项目说明
├── SKILL.md              # Codex 技能规则
└── agents/
    └── openai.yaml       # Codex 技能列表中的名称和提示语
```

## 致谢

本项目的核心想法参考了 [RobMitt/grill-me-skill](https://github.com/RobMitt/grill-me-skill)，README 组织方式参考了 [Jekudy/grillme-skill](https://github.com/Jekudy/grillme-skill)，并针对 Codex、本地技能发现和中文使用场景进行了改写。

## 许可
MIT许可证
