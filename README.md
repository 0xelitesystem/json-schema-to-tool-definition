# JSON Schema to Tool Definition

Paste a JSON Schema and generate a function/tool-calling definition in both the OpenAI function-calling format and the Anthropic tool format. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/json-schema-to-tool-definition/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

- Enter a tool name and a short description.
- Paste the JSON Schema for the tool's parameters (usually an object schema with `properties` and an optional `required` array).
- The tool wraps the schema into two definitions side by side:
  - OpenAI function-calling format: `{ "type": "function", "function": { "name", "description", "parameters" } }`
  - Anthropic tool format: `{ "name", "description", "input_schema" }`
- Copy buttons put either definition on your clipboard.

Invalid input is caught with a clear message: malformed JSON, a non-object schema, a missing `type`, a bad `properties` shape, a non-array `required`, or an out-of-range tool name.

## Why this exists

Both formats wrap the same parameters schema in a slightly different envelope. Rewriting one into the other by hand is error prone. This does the wrapping for you, validates the schema shape, and shows both outputs at once, in a single file with no dependencies.

## Privacy

Everything runs in your browser. The schema you paste and the definitions you generate never leave your machine. Verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/json-schema-to-tool-definition
cd json-schema-to-tool-definition
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It's a single HTML file.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [prompt-cost-across-models](https://github.com/0xelitesystem/prompt-cost-across-models)
- [context-window-gauges](https://github.com/0xelitesystem/context-window-gauges)
- [agent-instructions-file-builder](https://github.com/0xelitesystem/agent-instructions-file-builder)
