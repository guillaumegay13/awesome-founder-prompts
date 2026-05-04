# awesome-founder-prompts

> A minimalist collection of system prompts from famous founders, investors, and builders. Drop them into your OpenAI/Anthropic SDK and code like they would.

## Why

Great operators have a way of thinking. When they share the system prompts they actually use, that thinking becomes a drop-in tool. This repo collects those prompts, verbatim, with sources.

No skills metadata, no plugin manifests, no taxonomy. Just markdown files you can read, copy, or fetch.

## Available prompts

| Person | Role | File |
|---|---|---|
| Marc Andreessen | Co-founder, a16z | [prompts/marc-andreessen.md](prompts/marc-andreessen.md) |

## Install

Every prompt lives in a fenced code block inside its `.md` file. Fetch the raw markdown and slice out the block, or just copy-paste.

### Python

```python
import re, requests

url = "https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md"
md = requests.get(url).text
system_prompt = re.search(r"```text\n(.*?)\n```", md, re.DOTALL).group(1)

# Use with OpenAI / Anthropic SDK
# client.responses.create(model="gpt-5", instructions=system_prompt, input="...")
```

### Node

```js
const url = "https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md";
const md = await fetch(url).then(r => r.text());
const systemPrompt = md.match(/```text\n([\s\S]*?)\n```/)[1];
```

### curl

```bash
curl -s https://raw.githubusercontent.com/guillaumegay13/awesome-founder-prompts/main/prompts/marc-andreessen.md
```

## Contributing

Open a PR adding `prompts/<slug>.md`. Each entry must include:

1. The prompt text the person actually published, verbatim, in a fenced ```` ```text ```` block.
2. A direct link to the public source (tweet, blog, podcast transcript, etc.).
3. The date the prompt was captured.
4. One sentence of context.

No paraphrasing, no "inspired by" prompts, no leaks. Public, attributable, verbatim.

## License

[MIT](LICENSE). Prompt text remains the property of its respective author and is reproduced here under fair-use quotation for commentary and reference.
