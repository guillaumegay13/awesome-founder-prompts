# awesome-founder-prompts

> A minimalist collection of system prompts from famous founders, investors, and builders. Drop them into your OpenAI/Anthropic SDK and code like they would.

## Why

Great operators have a way of thinking. When they share the system prompts they actually use, that thinking becomes a drop-in tool. This repo collects those prompts, verbatim, with sources.

No metadata, no plugins, no taxonomy. Each file is just the raw prompt.

## Available prompts

| Person | Role | Source | File |
|---|---|---|---|
| Marc Andreessen | Co-founder, a16z | [@pmarca](https://x.com/pmarca/status/2051374498994364529) | [marc-andreessen.md](prompts/marc-andreessen.md) |

## Install

Every file under `prompts/` is the raw system prompt — no headers, no fences, no metadata. Fetch it as plain text.

### Python

```python
import requests

system_prompt = requests.get(
    "https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md"
).text

# OpenAI
# client.responses.create(model="gpt-5", instructions=system_prompt, input="...")

# Anthropic
# client.messages.create(model="claude-opus-4-7", system=system_prompt, messages=[...])
```

### Node

```js
const systemPrompt = await fetch(
  "https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md"
).then(r => r.text());
```

### curl

```bash
curl -s https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md
```

## Contributing

Open a PR adding `prompts/<slug>.md` containing **only** the verbatim prompt text — no front-matter, no fences. In the PR description, include:

1. A direct link to the public source (tweet, blog, podcast transcript, etc.).
2. The date the prompt was captured.
3. One sentence of context.

Attribution then goes into the table in this README.

No paraphrasing, no "inspired by" prompts, no leaks. Public, attributable, verbatim.

## License

[MIT](LICENSE). Prompt text remains the property of its respective author and is reproduced here under fair-use quotation for commentary and reference.
