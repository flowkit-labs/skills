# doany skills

Agent skills from [doany.ai](https://doany.ai/?utm_source=github&utm_medium=readme&utm_campaign=doany-skills) for building websites and finding customers.

## Skills

| Skill | What it does |
|---|---|
| [`ai-website-builder`](ai-website-builder/) | Turn a business idea into a hosted website or web app. Review the preview, launch it, and automate recurring work. |
| [`reddit-automation`](reddit-automation/) | Find Reddit threads where people are actively shopping for what you sell, and draft replies that read like a helpful community member — not an ad. |

## Install

```bash
npx skills add flowkit-labs/skills --skill ai-website-builder
npx skills add flowkit-labs/skills --skill reddit-automation
```

Choose the command for the skill you want. Try asking your agent to build a site from an everyday business brief.

> Build a website for my mobile dog grooming business in Austin. Let customers request an appointment, show me a preview before launch, and help me set up automatic booking confirmations.

Connect your DoAny account through [MCP](https://docs.doany.ai/api-mcp/mcp) or the [DoAny CLI](https://docs.doany.ai/api-mcp/cli) when prompted.

[AI website builder](https://doany.ai/?utm_source=github&utm_medium=readme&utm_campaign=ai-website-builder)

## Security & Privacy

- **AI Website Builder** sends your brief to Annie through an authorized DoAny connection. Builds, edits, and automation setup tasks use your DoAny credits. Review the preview before approving publication and check the trigger and recipients before enabling customer-facing automations. Sign in through DoAny and keep API keys out of chat.
- **Reddit Automation** requires no DoAny credentials. You review and post each reply yourself.

## License

[MIT](LICENSE)
