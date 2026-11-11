# doany skills

Agent skills from [doany.ai](https://doany.ai/?utm_source=github&utm_medium=readme&utm_campaign=doany-skills) for building websites and finding customers.

## Skills

| Skill | What it does |
|---|---|
| [`doany-website-builder`](doany-website-builder/) | Ask Annie to build or update a DoAny website from your AI agent. Review the preview and approve when it goes live. |
| [`website-builder`](website-builder/) | Build and preview a business website, add bookings or checkout, and automate reminders and follow-ups after launch. |
| [`reddit-automation`](reddit-automation/) | Find Reddit threads where people are actively shopping for what you sell, and draft replies that read like a helpful community member — not an ad. |

## Install

```bash
npx skills add flowkit-labs/skills --skill doany-website-builder
npx skills add flowkit-labs/skills --skill website-builder
npx skills add flowkit-labs/skills --skill reddit-automation
```

Choose the command for the skill you want. To try Website Builder, ask your agent:

> Use DoAny to build a website for my Austin dog grooming service. Make it easy to request an appointment, and show me a preview before publishing.

Connect your DoAny account through [MCP](https://docs.doany.ai/api-mcp/mcp) or the [DoAny CLI](https://docs.doany.ai/api-mcp/cli) when prompted.

[Explore DoAny](https://doany.ai/?utm_source=github&utm_medium=readme&utm_campaign=doany-website-builder) to see how Annie helps founders turn an idea into a website or web app.

## Security & Privacy

- **Website Builder** sends your brief to Annie through an authorized DoAny connection. Builds and edits use your DoAny credits. Review the preview before approving publication. Sign in through DoAny and keep API keys out of chat.
- **Reddit Automation** requires no DoAny credentials. You review and post each reply yourself.

## License

[MIT](LICENSE)
