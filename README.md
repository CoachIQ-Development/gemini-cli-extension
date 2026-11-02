# CoachIQ extension for Gemini CLI (and Antigravity CLI)

Install:

```bash
gemini extensions install https://github.com/CoachIQ-Development/gemini-cli-extension
```

Or add the server without the extension:

```bash
gemini mcp add --transport http coachiq https://mcp.coachiq.io/mcp
```

On first use Gemini opens the CoachIQ sign-in and consent page. Only CoachIQ Admin and Coach staff
accounts can connect; one connection is bound to one CoachIQ group.

## Publishing this folder (CoachIQ maintainers)

The Gemini CLI extensions gallery (https://geminicli.com/extensions/browse/) indexes public GitHub
repositories automatically; there is no form.

1. Copy the three files in this folder to the root of a **public** GitHub repository, for example
   `CoachIQ-Development/gemini-cli-extension` (the manifest `name` must stay `coachiq`).
2. On the repo's **About** panel add the topic `gemini-cli-extension`.
3. Tag a release (`v1.0.0`) matching the manifest `version`. The crawler checks tagged repos daily;
   if nothing shows after 48 h, confirm GitHub code search sees the manifest:
   `gh api 'search/code?q=repo:CoachIQ-Development/gemini-cli-extension+filename:gemini-extension.json' --jq .total_count`
4. Keep `version` in sync with each release tag; bump it when the server card or listing copy changes.

Source of truth for the listing text: `coachiq-mcp/src/discovery.ts` (`LISTING`).
