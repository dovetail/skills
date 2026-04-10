# Dovetail Skills

Reusable skills for AI coding agents to work with [Dovetail](https://dovetail.com) and the `dt` CLI.

## Installation

```bash
npx skills add dovetail/skills
```

## Skills

| Skill | Description |
|-------|-------------|
| [install-dt](./install-dt/SKILL.md) | Install the `dt` CLI via npm or npx and run initial workspace setup |
| [migrate-to-dovetail](./migrate-to-dovetail/SKILL.md) | Migrate data from Notion, Confluence, Google Drive, Airtable, Marvin, Condens, EnjoyHQ, Productboard, or local files into Dovetail |
| [create-dovetail-doc](./create-dovetail-doc/SKILL.md) | Create a Dovetail doc from a local markdown file or a title using `dt doc` |

## About the dt CLI

`dt` is the Dovetail command-line tool for importing content into your Dovetail workspace. Install it with:

```bash
npm install -g @heydovetail/dt
```
