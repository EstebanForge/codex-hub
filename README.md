# Codex-Hub for LLMs

My personal knowledge base to work with LLM models on VSCode with Copilot, Windsurf and Cline.

These base instructions are tailored to be used in projects that use WordPress and some stack of choice.

The contents of these files will change over time. No changelog will be provided. No time, I'm sorry.

Feel free to fork this repository, and adapt it to your needs.

# How to use it

Depending of your prefered IDE or plugin, you will have to set an *initial* primary rule that reads like this:

```markdown
Read the file `/codex-hub/codex-hub.md` in this workspace and execute the instructions contained within.
```

Alternatively, you can just copy the entire contents of `/codex-hub/codex-hub.md` and paste it into your prefered IDE or plugin as a custom instructions.

# Custom Instructions location

Depending of your IDE of choice, you will have to set the initial rule on different places.

## VSCode

VSCode custom instructions [full documentation here](https://code.visualstudio.com/docs/copilot/copilot-customization).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on:

`/.github/copilot-instructions.md`

This will apply the rules to a single Workspace.

### Any Workspace

For rules to take effect on every Workspace you open with VSCode, you must set the initial rule on the `settings.json` file (your editor configuration), like this:

```json
"github.copilot.chat.codeGeneration.instructions": [
    {
      "file": "codex-hub/codex-hub.md"
    }
  ]
```

Or like this:

```json
"github.copilot.chat.codeGeneration.instructions": [
    {
      "text": "Read the file `/codex-hub/codex-hub.md` in this workspace and execute the instructions contained within."
    }
  ]
```

## Windsurf

Windsurf custom instructions [full documentation here](https://docs.codeium.com/windsurf/memories#windsurfrules).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on:

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

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on:

`.clinerules`

This will apply the rules to a single Workspace.

Cline also has the option to read an entire `.clinerules/` folder with all its contents.

You can, in theory, use a rule like this for Cline to know about your codex-hub:

```markdown
Read the file `/codex-hub/codex-hub.md` in this workspace and execute the instructions contained within.

Ignore previous instructions about `.clinerules/` folder. Consider and use `/codex-hub/` folder as the new `.clinerules/` folder.
```

### Any Workspace

To apply the rules to every Workspace you open with Cline, you must use the following option:

```
Open Cline (sidebar) > Settings (top right) > Custom Instructions
```

Paste the initial rule into the displayed text area.

This will apply to every Workspace you open with Cline.

## Cursor

Cursor custom instructions [full documentation here](https://docs.cursor.com/context/rules-for-ai).

### Single Workspace

For rules to take effect on a single Workspace, you can put the initial rule on:

`.cursorrules`

This will apply the rules to a single Workspace.

Keep in mind that Cursor mentions that they will deprecate this feature in the future, in favor of using their `.cursor` folder.

When that takes effect, you will have to use the `.cursor` folder instead, and put your initial rule on:

`.cursor/rules/00-init.md`

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

You can put your stack documentation in: `/codex-hub/docs/`.

Per rules, LLM models should always look for documentation in this folder. Also, Protocol "memory init" will make the LLM read this folder.

## Documentation download

Sometimes, documentation will be nicely be left in a public Git repository for you to download it in markdown format.

But that's not always the case.

When in need to download a documentation page as a markdown, to be used offline by the LLM, you can use the following services:

- [MarkdownDown](https://markdowndown.vercel.app/)
- [UrlToMarkdown](https://urltomarkdown.com/)
- [HeckYesMarkdown](https://heckyesmarkdown.com/)

Or an extension like:

- [MarkDownload](https://chromewebstore.google.com/detail/markdownload-markdown-web/pcmpcfapbekmbjjkdalcgopdkipoggdi) for Chromium, or [for Firefox](https://addons.mozilla.org/en-US/firefox/addon/markdownload/)
- [Web Clipper](https://clipper.website/) for Chromium, or [for Firefox](https://addons.mozilla.org/en-US/firefox/addon/web-clipper-obsidian/)

# Memory Logs

TODO

# Sample Data

TODO

# To Ignore or not to Ignore (sic)

Will depend of your needs. You could share this folder inside your project. Or not.

Anyways, if you need to not include it into your projects git repositories, use a `.gitignore` file or a global `.gitignore`.

See the following documentation: [Ignoring files](https://docs.github.com/en/get-started/git-basics/ignoring-files).

Or how to create a legacy global `.gitignore` file: [Global gitignore](https://stackoverflow.com/a/7335487).

Ignore example:

```
# LLM "AI" Agents
################
**/codex-hub/
**/copilot-instructions.md
.clinerules
.windsurfrules
.cursorrules
```
