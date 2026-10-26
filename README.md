# thumbs: an iPhone for your AI agent (MCP)

**thumbs** gives Claude Code, or any MCP client, an iPhone to see, tap and type on, through one remote MCP server URL with Google sign-in. Nothing to install on your side: no Mac, no Xcode, no cable.

```
https://mcp.usethumbs.com/mcp
```

> **Status: early access, by waitlist.** Free early access runs on the **iOS Simulator** (Safari and Apple's built-in apps), shared between testers and let in one at a time. A real iPhone of your own is planned; it is **not available yet and has no date or price**.
>
> **[Join the waitlist →](https://www.usethumbs.com/?utm_source=github&utm_medium=docs&utm_campaign=directories_oct26&utm_content=readme_top)**

This repository holds the **documentation only**. The server's source code is not published here. Docs are MIT licensed (see [LICENSE](LICENSE)).

## What an agent can do

An agent gets a screenshot of the phone and a numbered list of everything it can tap, with labels and positions, so it can say "tap 4" instead of guessing pixels. It can tap, type, swipe, scroll, open apps and links, press the home button and answer system alerts.

## What you can use it for

- **Check your web app on iOS** (works in early access): open your pages in Safari on an iPhone Simulator and see what a phone shows, such as the keyboard covering a form. Guide: [How to test your web app on an iPhone with an AI agent](https://www.usethumbs.com/guides/test-ios-web-app-with-ai-agent).
- **Test your own app, map other apps, use apps with no API** (these need your own iPhone, which is planned and not available yet).

More: [How to give an AI agent an iPhone with MCP](https://www.usethumbs.com/guides/ai-agent-iphone-mcp).

## Connect

Only accounts that have been let in from the waitlist can use a phone. [Join the waitlist](https://www.usethumbs.com/?utm_source=github&utm_medium=docs&utm_campaign=directories_oct26&utm_content=readme_connect) if you aren't in yet.

| Client | How |
|---|---|
| **Claude Code** | `claude mcp add --transport http thumbs https://mcp.usethumbs.com/mcp`, then run `/mcp` and sign in with Google. Finish the sign-in in a browser on the same computer while Claude Code waits. |
| **Claude app** | Settings › Connectors › Add custom connector, and paste the URL above. |
| **Cursor** | [Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=thumbs&config=eyJ1cmwiOiJodHRwczovL21jcC51c2V0aHVtYnMuY29tL21jcCJ9), or add the generic config below to `~/.cursor/mcp.json`. |
| **VS Code** | [Install in VS Code](vscode:mcp/install?%7B%22name%22%3A%22thumbs%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//mcp.usethumbs.com/mcp%22%7D), or add `{ "servers": { "thumbs": { "type": "http", "url": "https://mcp.usethumbs.com/mcp" } } }` to `.vscode/mcp.json`. |
| **Any other MCP client** | Any client that supports remote servers over Streamable HTTP with OAuth 2.1 sign-in connects the same way. |

Generic config for clients that take a URL:

```json
{ "mcpServers": { "thumbs": { "url": "https://mcp.usethumbs.com/mcp" } } }
```

### Server details

| | |
|---|---|
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 with Google sign-in (dynamic client registration, PKCE S256) |
| Endpoint | `https://mcp.usethumbs.com/mcp` |
| Access | Allowlist: accounts let in from the waitlist |
| Registry name | `com.usethumbs/thumbs` (see [server.json](server.json)) |

An unauthenticated request gets `401` with a `WWW-Authenticate` header pointing to the OAuth metadata. That is expected.

## Measured

On a real iPhone 17 Pro, 23 October 2026, run by the maker (not on the Simulator that early access uses today): a screenshot in about 63 ms; a tap in 0.4 to 0.8 s depending on the app; 296 commands in 20 minutes with no failures; a language app's 19-screen onboarding walked to its paywall in 3.2 minutes.

## Limits

- Early access is the **iOS Simulator**: Safari and Apple's built-in apps, not App Store apps. It is not a real device.
- The Simulator is **shared between testers**, in turns of up to 30 minutes. Don't sign in to personal accounts on it; anything left on it may be seen by us and the next tester, and may be deleted.
- No banking apps, no Apple Pay, nothing behind Face ID.
- It may be slow, unavailable or change at any time. Early access is provided as it is, without warranty.

## Usage policy

Use thumbs for your own apps, your own accounts and your own research. Don't use it to spam, make fake accounts, get around an app's rules or security, harm others, or anything illegal. Don't try to break, overload or reverse-engineer the service. You are responsible for what your agent does and for having the right to test the apps you point it at. Full text: [Terms](https://www.usethumbs.com/terms) · [Privacy](https://www.usethumbs.com/privacy).

## Links

- Website and waitlist: [usethumbs.com](https://www.usethumbs.com/?utm_source=github&utm_medium=docs&utm_campaign=directories_oct26&utm_content=readme_links)
- Guides: [usethumbs.com/guides](https://www.usethumbs.com/guides/)
- Contact: [hello@usethumbs.com](mailto:hello@usethumbs.com)
- Maker: [Jorge García González](https://github.com/jorchg).

## License

The documentation in this repository is released under the [MIT License](LICENSE). "thumbs" and the thumbs logo are not covered by it.
