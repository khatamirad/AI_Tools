# AI Tools

A growing, public collection of small AI/LLM tools I build for myself and end up finding useful enough to share.

Most of these start as practice projects (from courses, work, or just curiosity) in a private dev repo. When one is polished enough and worth sharing with colleagues, it moves here — so this repo is less "in progress" and more "here's a thing that works, try it."

## Tools

| Tool | Description | Status |
|---|---|---|
| [`literature-radar`](./literature-radar) | Searches Nature for a keyword and uses an LLM (OpenAI or local via Ollama) to summarize and rank how relevant each result is. | 🚧 in progress |

More will be added over time — check back now and then.

## Structure

Each tool lives in its own folder with its own README (what it does, setup, how to run it):

```
ai-tools/
├── README.md
├── literature-radar/
│   ├── README.md
│   └── ...
└── <next-tool>/
    ├── README.md
    └── ...
```

## Using these

Each tool folder is meant to be self-contained — its own README, its own dependencies/requirements. General notes:

- API keys (OpenAI, etc.) are never committed — each tool expects its own `.env` file (see its README for which variables it needs).
- Where a tool can run against a local model (e.g. via [Ollama](https://ollama.com)) instead of a paid API, that's noted in its README.

## License

MIT — use, fork, adapt freely. If something here is useful to you, I'd love to hear about it.
