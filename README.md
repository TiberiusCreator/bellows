# Bellows

Bellows is a single HTML file. Open it, and you get a full three-file code editor (HTML/CSS/JS) with a live preview, an automated test runner, and a genuinely useful local AI assistant — powered by [WebLLM](https://github.com/mlc-ai/web-llm), running on your own GPU via WebGPU. No cloud inference, no data collection, no dependency on anything staying online.

---

## Why

Most "AI code editors" ship your code to someone else's server. Bellows doesn't have a server. The model weights download once, get cached by your browser, and every conversation, every edit, every test run happens locally — genuinely offline-capable once the model is loaded.

It's also built for people who don't want to fight a command palette. You don't type slash commands to get things done in Bellows — you just talk to it. "Fix the bug in my script," "make this look more orange," "test my page" — it figures out what to do.

---

## Features

**Local AI, no strings attached**
- Three models to pick from — **Ember** (balanced, fast), **Flame** (advanced), **Inferno** (smartest) — all [Qwen2.5-Coder](https://github.com/QwenLM/Qwen2.5-Coder), specialized for reading and fixing real code
- No commands required — plain English does everything; a full command palette (25 commands, `/` to browse) is there if you want precision instead
- The AI edits your files directly and shows you a diff of exactly what changed, instead of dumping code in the chat for you to copy
- One-click undo on anything it changes
- Automatically retries its own mistakes — if an edit leaves an error behind, it tries to fix it itself (capped, so it can't loop forever)
- 🌐 Optional image lookup — toggle it on and the AI pulls *real* photos from Wikimedia Commons instead of guessing a URL that 404s

**A real editor, not a toy**
- Three-file project structure (HTML / CSS / JS) with independent, renameable tabs
- CodeMirror-powered editing with a custom syntax theme
- Real find & replace (`Ctrl/Cmd+F`) — not a browser hack
- Resizable panels, a floating preview window you can expand or shrink to a status pill
- The editor locks itself while the AI is actively writing, so nothing gets overwritten mid-edit

**Testing built in**
- One click clicks through every button, link, and field on your page automatically and reports what broke
- Live JavaScript syntax checking (via [Acorn](https://github.com/acornjs/acorn)) with real line and column numbers — not a vague "something's wrong"
- HTML and CSS structural checks (unclosed tags, mismatched braces) that most browsers silently swallow and never tell you about

**Get your work out**
- Download as a single merged `.html` file or a proper `.zip` project
- Everything autosaves locally — code, chat history, layout — and survives a reload

---

## Quick Start

**Option 1 — Just open it**
Download `index.html` and open it in Chrome or Edge. That's the whole install.

**Option 2 — Try it live**
[**bellows-link-here**](#) *(add your GitHub Pages URL here once it's live)*

**Option 3 — Clone it**
```bash
git clone https://github.com/yourusername/bellows.git
cd bellows
open index.html
```

First time you turn the AI on, it downloads the model (a few hundred MB to a few GB depending which one you pick) and caches it in your browser — after that, it loads instantly. Model caching is per-browser, so switching browsers (or using file:// instead of a real server in Safari) means it downloads again.

---

## Requirements

- A WebGPU-capable browser — **Chrome or Edge, recent versions**
- A reasonably capable GPU for the local AI (the editor itself works fine on anything; the AI is the demanding part)

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl/Cmd + F` | Find in current file |
| `Ctrl/Cmd + G` | Find next |
| `Shift + Ctrl/Cmd + G` | Find previous |
| `Ctrl/Cmd + Shift + F` | Replace |
| `Esc` | Close find/replace |
| `Enter` | Send chat message |
| `Shift + Enter` | New line in chat |

---

## Tech Stack

- **[WebLLM](https://github.com/mlc-ai/web-llm)** — in-browser LLM inference via WebGPU
- **[CodeMirror 5](https://codemirror.net/5/)** — the code editor itself, plus its search/dialog addons
- **[Acorn](https://github.com/acornjs/acorn)** — real JavaScript parsing for precise syntax errors
- **[marked](https://github.com/markedjs/marked)** — Markdown rendering in the chat
- **[JSZip](https://github.com/Stuk/jszip)** — project export
- Zero build step. Zero backend. One file.

---

## Use Cases

- Learning HTML/CSS/JS with an AI that actually explains what it changed and why
- Quick prototyping without spinning up a project, installing anything, or paying for API credits
- A private sandbox for experimenting with AI-assisted coding — nothing generated ever touches a server
- Teaching — the diff view and undo make it easy to see exactly what an AI edit does before trusting it

---

## Known Limitations

- WebGPU support is still Chrome/Edge-only in practice — no Safari/Firefox support yet, that's on their end, not this project's
- Small local models are small models — they're good, but a 1.5B–7B model asked for something genuinely large (a full game, a complex multi-system app) will need to be built in pieces, not one shot
- Model downloads don't sync across browsers or devices — that's a browser storage limitation, not something Bellows controls

---

## Roadmap

- [ ] Multi-page projects (beyond the current 3-file structure)
- [ ] Export directly to a GitHub repo
- [ ] More local model options as WebLLM's catalog grows
- [ ] Theming / light mode

---

## License

MIT — do what you want with it.

---

## Credits

Built by me, TiberiusCreator!

If you find a bug (there might be bugs it's in beta for a reason), open an issue please!

---

**If Bellows is useful to you, a star helps other people find it! :)**
