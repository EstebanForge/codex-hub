# Codex-Hub for LLMs

<p align="center">
   <img src="https://i.imgur.com/dYrqu3v.gif" />
</p>

My personal workflow and knowledge base to work with LLM models on VSCode with Copilot, Windsurf and/or Cline.

These base instructions are tailored to be used in projects that use PHP, WordPress and some other stack of choice.

The contents of these files will change over time. No changelog will be provided. No time for that, I'm sorry.

Feel free to fork this repository, and adapt it to your needs.

# Demo

<p align="center">
    <img src="https://github.com/user-attachments/assets/2e4ff877-6bc1-43be-8eea-fc0aeb96ccc7" />
</p>

# How to use it

Depending of your prefered IDE or plugin, you will have to set an *initial* primary rule that reads like this:

```markdown
Use view_file (read) on `./codex-hub/codex-hub.md` and follow those instructions.
```

Alternatively, you can just copy the entire contents of `./codex-hub/codex-hub.md` and paste it into your prefered IDE or plugin as a custom instructions.

# Custom Instructions location

Depending of your IDE of choice, you will have to set the initial rule on different places.

## VSCode

VSCode custom instructions [full documentation here](https://code.visualstudio.com/docs/copilot/copilot-customization).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on:

`./.github/copilot-instructions.md`

This will apply the rules to a single Workspace.

### Any Workspace

For rules to take effect on every Workspace you open with VSCode, you must set the initial rule on the `settings.json` file (your editor configuration), like this:

```json
"github.copilot.chat.codeGeneration.instructions": [
    {
      "file": "./codex-hub/codex-hub.md"
    }
  ]
```

Or like this:

```json
"github.copilot.chat.codeGeneration.instructions": [
    {
      "text": "Read the file `./codex-hub/codex-hub.md` in this workspace and follow the instructions contained within."
    }
  ]
```

## Windsurf

Windsurf custom instructions [full documentation here](https://docs.codeium.com/windsurf/memories#windsurfrules).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on this file in the root of your Workspace:

`.windsurfrules`

This will apply these rules to a single Workspace.

### Any Workspace

To apply the rules to every Workspace you open with Windsurf, you must use the following option:

```
Windsurf Settings (bottom right) > Memory and Rules > Manage > Edit global rules
```

In the file that will open, paste the initial rule.

This will apply to every Workspace you open with Windsurf.

## Cline (VSCode plugin)

Cline custom instructions [full documentation here](https://docs.cline.bot/improving-your-prompting-skills/prompting).

Roo Code custom instructions [full documentation here](https://docs.roocode.com/features/custom-instructions).

Kilo Code custom instructions are the same as Roo Code's.

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on this file in the root of your Workspace:

`.clinerules`

`.roorules`

This will apply the rules to a single Workspace.

Cline/Roo also has the option to read an entire `./.clinerules/` / `./.roo/` folder with all its contents.

You can, in theory, use a rule like this for Cline/Roo to know about your codex-hub:

```markdown
Read the file `./codex-hub/codex-hub.md` in this workspace and follow the instructions contained within.

Ignore instructions about `./.clinerules/`/`./.roo/` folder. Consider and use `./codex-hub/` folder as the new `./.clinerules/` folder.
```

### Any Workspace

To apply the rules to every Workspace you open with Cline/Roo, you must use the following option:

```
Open Cline (sidebar) > Settings (top right) > Custom Instructions
```

```
Open Roo (sidebar) > Prompt Tabs > Custom Instructions for all models
```

Paste the initial rule into the displayed text area.

This will apply to every Workspace you open with Cline/Roo.

## Cursor

Cursor custom instructions [full documentation here](https://docs.cursor.com/context/rules-for-ai).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on this file in the root of your Workspace:

`.cursorrules`

This will apply the rules to a single Workspace.

Keep in mind that Cursor mentions that they will deprecate this feature in the future, in favor of using their `.cursor` folder.

When that takes effect, you will have to use the `.cursor` folder instead, and put your initial rule on:

`./.cursor/rules/00-init.md`

### Any Workspace

To apply the rules to every Workspace you open with Cursor, you must use the following option:

```
Cursor Settings > General > Rules for AI
```

Paste the initial rule into the displayed text area.

This will apply to every Workspace you open with Cursor.

# Dot files with rules

If you need inspiration on how to write rules for an LLM in context of your desired stack, take a look at:

- [dotcursorrules.com](https://dotcursorrules.com/rules)
- [cursor.directory](https://cursor.directory)
- [cursor.list](https://cursor.list)
- [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules)

# Docs

You can put your stack documentation in: `./codex-hub/docs/`.

Per rules, LLM models should always look for documentation in this folder. Also, Workflow "memory init" will make the LLM read this folder.

## Documentation for LLMs

### MCP Server

Leverage the power of [Context7](https://context7.com) to give LLMs access to up to date documentation on millions of libraries and frameworks.

See how to install [Context7 MCP Server](https://github.com/upstash/context7).

### Manual download

Sometimes, documentation will be nicely left in a public Git repository for you to download in Markdown format.

But that's not always the case.

When you need to download a documentation page as Markdown to use offline with the LLM, you can use the following services:

- [MarkdownDown](https://markdowndown.vercel.app/)
- [UrlToMarkdown](https://urltomarkdown.com/)
- [HeckYesMarkdown](https://heckyesmarkdown.com/)

Or use a Browser extension like:

- [MarkDownload](https://chromewebstore.google.com/detail/markdownload-markdown-web/pcmpcfapbekmbjjkdalcgopdkipoggdi) for Chromium, or [for Firefox](https://addons.mozilla.org/en-US/firefox/addon/markdownload/)
- [Web Clipper](https://clipper.website/) for Chromium, or [for Firefox](https://addons.mozilla.org/en-US/firefox/addon/web-clipper-obsidian/)

# To Ignore or Not to Ignore (sic)

It will depend on your needs. Your usage of it. The needs of your team, if there's any. You could share this folder inside your project—or not.

Anyway, if you need to exclude it from your project's Git repositories, use a `.gitignore` file or a global `.gitignore`.

See the following documentation: [Ignoring files](https://docs.github.com/en/get-started/git-basics/ignoring-files).

Or learn how to create a legacy global `.gitignore` file: [Global gitignore](https://stackoverflow.com/a/7335487).

Example:

```
# LLM "AI" Agents
################
**/codex-hub/
**/copilot-instructions.md
.clinerules
.windsurfrules
.cursorrules
```
