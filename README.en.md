<div align="center">

<img src="assets/logo.svg" width="88" alt="Oh My Browser logo">

# Oh My Browser · OMB

### Give your AI agent access to the real web you are signed into

**Read private pages · Observe async content · Act on websites · Verify UI changes**

[Website](https://omb.org.cn/en) · [Install](https://omb.org.cn/en/install) · [Chrome Web Store Lite](https://chromewebstore.google.com/detail/oh-my-browser-lite/akoahoncmadanincjkcgajofianmbbon) · [简体中文](README.md)

</div>

---

Your browser shows the document, but your agent gets a login page. Your build passes, but the layout still breaks. Your PDF preview is loading, but the first read looks empty.

**OMB connects local AI agents to your existing Chrome session.** Agents can read rendered pages, inspect elements, perform authorized actions, capture screenshots and observe explicit readiness conditions for delayed content.

Use it for web debugging with Codex or Claude Code, and for research and work across websites you are already signed into. Ordinary websites need no SDK integration. Developers can optionally add WebMCP tools and a diagnostics SDK for business context.

## When to use OMB

| Your task | What the agent can do |
| --- | --- |
| Read internal documents, CRM, OA or subscription content | Read pages available under your existing browser identity |
| curl fails or retrieves a shell/login page | Inspect the rendered page and its actual access/loading state |
| Obtain a delayed preview, image or list | Retain the tab and observe the target's readiness conditions |
| Verify a frontend change | Combine DOM measurements, screenshots and actual interactions |
| Investigate a web app failure | Inspect available page diagnostics, bounded request/error evidence and DOM state |
| Complete a multi-step workflow | Discover elements, act within your authorization and verify the result |

Ordinary search remains useful for simple public facts. Choose OMB when identity, rendering or actual interaction matters.

## Get started

### 1. Install the CLI and agent connection

Run in a macOS or Linux terminal:

```bash
curl -fsSL https://api-browser.getohmy.com/install.sh | sh
```

China endpoint:

```bash
curl -fsSL https://api.omb.org.cn/install.sh | sh
```

The installer downloads the CLI, configures detected agents and prepares the Full Chrome extension. Follow its account and browser setup instructions.

### 2. Load the extension

Open `chrome://extensions`, enable **Developer mode**, choose **Load unpacked**, then select the extension directory shown by the installer. On macOS the default is `~/Downloads/oh-my-browser-extension`. Complete extension sign-in. Reload the extension after updating its files.

Alternatively, install [Lite from the Chrome Web Store](https://chromewebstore.google.com/detail/oh-my-browser-lite/akoahoncmadanincjkcgajofianmbbon). Lite still requires the CLI and agent connection. Choose one edition.

### 3. Give your agent a real task

```text
Use OMB to read this page in my signed-in browser and summarize the key points:
<URL>
```

In Codex, `/mcp` shows loaded MCP connections. If an existing session has not loaded a newly installed tool connection, follow the installer's reload/new-session guidance.

## Copyable task prompts

**Delayed content**

```text
Use OMB to open this page and retain its tab. I need the preview content.
If it is loading, observe explicit readiness: the loading indicator disappears
and the image decodes or expected text appears. Summarize only after checking
the content. A timeout should be reported as an observation, not a site defect.
URL: <URL>
```

**Frontend verification**

```text
Use OMB to verify this local page at desktop and narrow widths.
Check layout, scroll containers, controls and error states using DOM measurements
and screenshots. A successful build or healthy diagnostic is insufficient.
Keep the browser in the background; explain any capability needing visibility.
URL: http://localhost:<port>/<path>
```

**Web debugging**

```text
Reproduce this issue with OMB. First inspect available WebMCP diagnostic tools,
then gather DOM, request and runtime-error evidence. Separate observations
from hypotheses, verify the fix on the page, and close your test tabs.
Issue: <description>
URL: <URL>
```

## Full or Lite?

**We recommend Full** for development and multi-page work. Both editions share foundational reading and action functionality.

| Capability | Full | Lite |
| --- | --- | --- |
| Installation | Installer prepares files; load unpacked in Chrome | Chrome Web Store |
| Signed-in page reading | Yes | Yes |
| Basic page actions and generic diagnostics | Yes | Yes |
| Site memory / selector cache | Yes | No |
| Concurrent tab operations | Up to 8 | 1 |
| Updates | Download updated files and reload | Chrome updates after store review/publication |

Store and server releases can differ while review is pending.

## Tools your agent uses

| Tool | Purpose |
| --- | --- |
| `omb_read` | Read rendered pages or a specific tab/frame |
| `omb_page_watch` | Observe delayed content against explicit conditions |
| `omb_map` | Discover interactive elements and page-provided WebMCP tools |
| `omb_action` | Click, fill, select, evaluate, screenshot and other actions |
| `omb_snapshot` | Obtain a page snapshot for element targeting |
| `omb_search` | Search the web |
| `omb_status` | Inspect client/authentication state |
| `omb_guide` | Obtain detailed tool contracts and recovery guidance |
| `omb_report` | Submit authorized tool feedback or feature suggestions |

A default read closes its OMB-owned tab. Multi-step work starts with `keepForChain:true`, reuses the explicit `tabId`, and ends with explicit closure. Installed skills and `omb_guide` teach agents the detailed workflow.

## Practical boundaries

- OMB uses your browser's existing access; it does not grant missing permissions or guarantee bypassing access challenges.
- No target-site password needs to be shared merely to use an existing session. Page reads and screenshots can contain private data; scope agent access to the task.
- Localhost pages work when accessible from Chrome. Start your app first.
- Embedded content may require explicit frame discovery and reading. Browser permissions can limit access.
- Page watch returns bounded observations, not every browser event. `ready` proves the declared conditions only; `timeout` does not prove a broken website.
- Supported tasks can run in the background. Some screenshot or browser-native paths require visibility; agents should explain actual limits.
- Healthy page diagnostics do not prove correct layout or successful business outcomes. Verify the task's acceptance conditions.
- An interrupted action may already have applied. Inspect the exact target before retrying consequential operations.

Developers can optionally expose business context and diagnostics through WebMCP/SDK integration. See the [web debugging guide](https://omb.org.cn/en/guide/web-debugging).

## Help us improve OMB

Ask your agent to prepare a minimal reproduction with expected/observed behavior, exact errors, verified versions/time and the relevant invocation `request_id` values. After you authorize submission, it can use `omb_report`. Missing evidence should be labeled unknown; do not include credentials or private page contents.

Public suggestions and issues are also welcome in [this repository](https://github.com/getohmy/oh-my-browser-omb/issues).

---

[Install Full](https://omb.org.cn/en/install) · [Get Lite](https://chromewebstore.google.com/detail/oh-my-browser-lite/akoahoncmadanincjkcgajofianmbbon) · [Website](https://omb.org.cn/en)

This repository contains the OMB product introduction and user guide. Consult the website and current tool responses for installation details and capabilities.
