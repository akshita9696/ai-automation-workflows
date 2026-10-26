# Try my AI

The live tool on my portfolio. A visitor pastes their website, and this workflow reads the landing page and suggests 3 AI automation ideas for their business in about 5 seconds.

**Try it:** press "Try my AI" on [my portfolio](https://akshita9696.github.io).

**Built with:** n8n, Firecrawl and Gemini  
**Size:** 1 workflow, 17 steps

## How it works

1. **The portfolio sends the website address.** The webhook only accepts requests from the portfolio itself.
2. **Checks the address and the daily limit.** A badly formed address gets a clear error, and a cap of 100 runs a day keeps costs predictable.
3. **Reads the landing page.** A plain fetch first; if the site blocks it or needs JavaScript, Firecrawl reads it instead.
4. **Gemini suggests 3 ideas.** A strict output format means the portfolio always gets exactly 3 ideas it can show. If the model is busy, it retries and falls back to a second model.
5. **Clear errors, never a broken page.** Each failure (bad address, daily limit, unreadable site, AI unavailable) returns its own message, so the visitor always knows what happened.

## Workflows in this folder

| File | Workflow | Steps |
| --- | --- | --- |
| [`ai-ideas-widget.json`](ai-ideas-widget.json) | Portfolio: AI Ideas Widget | 17 |

## Use it yourself

In n8n, choose **Import from File** and pick a `.json` file. Then attach your own accounts (Gmail, Airtable, Gemini and so on) and replace the placeholders: `you@example.com`, Airtable IDs like `appXXXXXXXXXXXXXX`, and any `YOUR_...` values. No passwords or API keys are included.
