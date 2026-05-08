# Edge Browser Control Skill

Edge Browser Control Skill teaches Codex how to inspect and operate Microsoft Edge through the local Codex Edge Access Bridge.

After installation, Codex can respond to requests such as listing current Edge tabs, reading the active page, opening URLs, clicking page elements, typing into fields, and taking screenshots through the local bridge.

## Companion Bridge

This skill is designed to work with the Edge bridge repository:

- Browser bridge: [CoderYTY/codex-edge-access-bridge](https://github.com/CoderYTY/codex-edge-access-bridge)

Use them together:

- The bridge repository provides the Microsoft Edge extension, Native Messaging host, and CLI.
- This skill gives Codex the operating instructions and safety model for using that bridge naturally.

## Capabilities

With the bridge running, this skill guides Codex to:

- Check the local bridge status.
- List open Edge tabs.
- Read visible page text, links, headings, and HTML.
- Query, click, type, scroll, reload, and navigate pages.
- Capture screenshots from Edge tabs.
- Keep automation scoped to user-requested browser tasks.

## Installation

Install and verify the browser bridge first:

1. Follow the setup guide in [CoderYTY/codex-edge-access-bridge](https://github.com/CoderYTY/codex-edge-access-bridge).
2. Open the `Codex Edge Bridge` extension dashboard.
3. Confirm the dashboard shows `connected`.

Then install this skill into Codex:

```powershell
git clone https://github.com/CoderYTY/edge-browser-control-skill.git "$env:USERPROFILE\.codex\skills\edge-browser-control"
```

Restart Codex after installation so the skill index refreshes.

## Usage Examples

```text
操控 Edge 浏览器，看看我有哪些标签页
访问我的 Edge，读取当前页面内容
打开这个网页，然后帮我点击搜索框
读取当前 B 站页面里显示的关注列表
```

## Files

- `SKILL.md`: main skill instructions for Codex.
- `agents/openai.yaml`: display metadata for Codex UI and agent indexing.

## Privacy Model

This skill routes browser work through the local bridge on the user's machine. Codex should inspect and operate only the pages requested by the user, and leave account verification, payment confirmation, CAPTCHA, and other sensitive checkpoints under direct user control.
