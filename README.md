# Codex Skills

一组可在 Codex 中使用的技能。每个技能放在自己的目录中，入口文件为 `SKILL.md`。

| 技能 | 调用名 | 用途 |
| --- | --- | --- |
| [Find Picture](skills/find-picture/SKILL.md) | `$find-picture` | 根据参考图、号码布、拍摄时间或装备线索，从本地相册筛选候选照片并整理原片。 |

## 安装 Find Picture

在 GitHub 打开本仓库的 [Find Picture 目录](skills/find-picture/)，复制该目录的网址。在 Codex 中输入：

```text
用 $skill-installer 安装这个 GitHub 目录：<刚才复制的网址>
```

安装完成后重启 Codex，然后调用 `$find-picture`。参见 [OpenAI 的技能安装说明](https://github.com/openai/skills/blob/main/README.md)。

## 使用示例

```text
用 $find-picture 检查本地相册。我会提供几张已确认的参考图，号码布是 07 队 023。
请补查合照和相邻连拍，把确认的原片复制到我指定的文件夹，并报告扫描和复核范围。
```

使用时请提供源相册位置、参考图或其他线索，以及你希望保存结果的目录。此前已确认或排除的照片也可以作为线索。

Find Picture 依赖 Codex 访问本地照片。大批量识别可按需使用 [RapidOCR](https://github.com/RapidAI/RapidOCR) 等本地工具。号码布被挡住或人物离镜头较远时，结果可能需要人工复核。技能会说明检查到的范围和仍待确认的照片。
