# claude-mods

Eight Claude Code mods from the RoboNuggets "9 Claude Mods" guide, packaged as one plugin marketplace. Needs Claude Code 2.1.287 or newer. Mods work in the terminal and the desktop app Code tab, not in cloud sessions or the VS Code extension.

## Install

```
/plugin marketplace add dandeppert/claude-mods
/plugin install skins@claude-mods
```

Swap `skins` for any name below. Then start a new session or run `/reload-plugins`.

| Plugin | What it does | Use it |
| --- | --- | --- |
| savvy-progress | Live panel of every subagent, its model and estimated cost | `/agents-info` |
| skins | Themes for tool rows and diffs | `/skin dracula` |
| filetree | File tree that lights up files Claude touches | `/tui fullscreen` |
| cache-tax | Holds one send when the prompt cache is cold, shows the cost | `/keepwarm 90m` |
| blast-radius | Holds risky shell commands, lists what they would delete | automatic |
| reflect-mod | Turns your corrections into CLAUDE.md rules | automatic |
| terminal-browser | Real browser pane. Needs the `terminal-browser` binary. Mac and Linux terminal only | `/browser` |
| replay-theater | Step through each edit Claude made | `/replay` |

The ninth mod, You Should Know, is built in: `/plugin enable cc-plugin-you-should-know@builtin`.

## Safety

Mods are not sandboxed. They run with your permissions. Check one first with `claude plugin validate ./plugins/<name>`.

Things to know before you enable:
- cache-tax makes small model calls to keep the cache warm, which costs tokens.
- reflect-mod sends your short prompts to Haiku to check for corrections.
- skins checks for updates over the network and registers a `design` tool.
- blast-radius is a safety net, not a permission system.

## Sources and licenses

Vendored unchanged from the original repos. Each plugin folder keeps its license.

- savvy-progress: JohnnyVizz/claude-kit (MIT)
- skins: hellosverre/claude-skins (MIT)
- filetree: data-goblin/claude-code-filetree (MIT)
- cache-tax: karanb192/cache-tax (MIT)
- reflect-mod: BayramAnnakov/claude-reflect, `mod/` (MIT)
- terminal-browser: zenbu-labs/terminal-browser, `claude-code-plugin/` (MIT)
- blast-radius, replay-theater: anthropics/claude-code-playground (Apache-2.0)
