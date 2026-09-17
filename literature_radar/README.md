# Literature Radar

Turn a search keyword into an AI-annotated reading list from Nature.

Given a keyword, it searches [nature.com](https://www.nature.com), pulls the matching articles, and uses an LLM to read each one and tell you: publication year, first author, journal, article type, a short summary, and — the useful part — *why it's actually relevant to your keyword*. Results are saved to an Excel file you can skim or filter.

Built while practicing ideas from Ed Donner's *LLM Engineering* course; scratches a real itch — keeping up with self-driving-lab / catalysis literature without reading 50 abstracts by hand.

## What it does

1. Searches Nature for a keyword and collects the article links from the results page.
2. Fetches the full text of each article page.
3. Sends each article to an LLM (your choice of a frontier model via the OpenAI API, or a local model via [Ollama](https://ollama.com)) with a prompt asking for year, first author, journal, article type, a 2–3 sentence summary, and relevance to the keyword.
4. Collects everything into a table and saves it as `<keyword>.xlsx`.

## Setup

```bash
pip install -r requirements.txt
cp .env.example .env   # then add your OpenAI API key
```

To use a local model instead of OpenAI, install [Ollama](https://ollama.com), pull a model (e.g. `ollama pull llama3.2`), and make sure it's running on `localhost:11434`.

## Usage

Open `lit_radar.ipynb` and:

1. Set `keyword` to whatever you want to search for.
2. Set `provider` to `"openai"` or `"ollama"`, and `model` to the model name.
3. Run all cells.

Results are saved as `<keyword>.xlsx` in the same folder.

## Known limitations

- Nature only — no other publishers/search engines yet.
- Scraping depends on Nature's current page markup; if they change their HTML, the link-extraction step will need updating.

## Possible next steps

- Support more sources beyond Nature (arXiv, Google Scholar, etc.).
- Turn `keyword` / `provider` / `model` into command-line arguments or a simple config file.
