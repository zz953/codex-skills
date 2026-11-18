# Codex Skills

A collection of skills for Codex. Each skill has its own directory with a `SKILL.md` entry point.

| Skill | Command | What it does |
| --- | --- | --- |
| [Find Picture](skills/find-picture/SKILL.md) | `$find-picture` | Search local photo collections using reference images, bib numbers, capture times, or clothing and gear. Review candidates and copy matching originals. |

## Install Find Picture

Open the [Find Picture directory](skills/find-picture/) on GitHub and copy its URL. Enter the following in Codex:

```text
Use $skill-installer to install this skill from GitHub: <paste the directory URL here>
```

Restart Codex after installation, then invoke `$find-picture`. See [OpenAI's skill installation instructions](https://github.com/openai/skills/blob/main/README.md).

## Example

```text
Use $find-picture to search my local photo collection. I'll provide a few confirmed
reference photos. The bib reads Team 07, number 023. Check group photos and nearby
frames, copy confirmed originals to the folder I specify, and report what you
scanned automatically and what you reviewed manually.
```

Provide the source folder, reference photos or other clues, and the destination folder. Mention any photos you have already confirmed or ruled out.

Codex needs access to the local photo files. For large batches, it can use a local tool such as [RapidOCR](https://github.com/RapidAI/RapidOCR). Obscured bibs and distant subjects may require manual review. Find Picture reports what it checked and which candidates still need confirmation.
