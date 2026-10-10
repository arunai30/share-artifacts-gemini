# Share Artifacts for Antigravity and Gemini CLI

Publish HTML reports, slide decks, and visual documents to shareable URLs using
the hosted [Share Artifacts](https://shareartifacts.dev) MCP service.

## Antigravity

Google ended Gemini CLI access for individual free, Google AI Pro, and Google AI
Ultra accounts on June 18, 2026. Use
[Antigravity](https://antigravity.google/docs/cli/install/) for these accounts.
See [Google's transition announcement](https://github.com/google-gemini/gemini-cli/discussions/28017).

With Antigravity CLI installed, run:

```sh
agy plugin install https://github.com/arunai30/share-artifacts-gemini
agy plugin list
agy
```

Complete Antigravity's Google sign-in, then open `/mcp` and use its authentication
action for `share-artifacts`. Follow the browser sign-in and consent flow for your
Share Artifacts account, then complete any callback step shown by Antigravity.

The native plugin uses [`plugin.json`](./plugin.json) and
[`mcp_config.json`](./mcp_config.json). The remote server uses OAuth discovery and
dynamic client registration; no personal API token or local MCP server is needed.

## Gemini CLI for supported accounts

Gemini CLI remains available with supported enterprise accounts and API-key
authentication. Individual Google sign-in is no longer supported in Gemini CLI;
updating or reinstalling it does not restore that access.

Install the extension with [Gemini CLI](https://geminicli.com/docs/get-started/installation/):

```sh
gemini extensions install https://github.com/arunai30/share-artifacts-gemini
```

Review the extension details when prompted, authenticate Gemini CLI using a
supported method, then start a new Gemini CLI session.
Inside the interactive session, run:

```text
/mcp auth share-artifacts
/mcp list
```

Complete sign-in to your Share Artifacts account and approve the requested access
in the browser, then return to Gemini CLI.

## Publish and update artifacts

Both integrations use the hosted Share Artifacts MCP service with OAuth.
The connection requests access to read and manage your pages, reusable templates,
and artifact style, with offline access to keep the connection signed in.

Try asking:

> Create a one-page HTML project brief with a goal, three milestones, and next
> steps. Save it privately with Share Artifacts and give me its URL.

Then ask your agent to update that same page. Publishing defaults to private; request
public sharing explicitly when you want anyone with the link to view it. Published
content is static HTML: scripts, forms, external API calls, and embedded frames
are disabled.

## Manage the integration

To disable or uninstall the Antigravity plugin:

```sh
agy plugin disable share-artifacts
agy plugin uninstall share-artifacts
```

To update or uninstall the Gemini CLI extension:

```sh
gemini extensions update share-artifacts
gemini extensions uninstall share-artifacts
```

If you already configured an MCP server named `share-artifacts` in Gemini CLI's
settings, that configuration takes precedence over this extension. Keep only the
connection you intend to use. For a connection that needs sign-in again, run
`/mcp auth share-artifacts` in a fresh interactive session.

The Gemini CLI extension manifest is [`gemini-extension.json`](./gemini-extension.json).
These integrations do not install an app in the consumer Gemini website.

## Verification status

The Gemini CLI extension passed a fresh installation test with version 0.63.0.
Antigravity CLI 1.3.3 validated and installed the native plugin with its hosted MCP
server. Share Artifacts OAuth and an authenticated publish/update test remain
pending. This repository does not imply an approved Antigravity Marketplace listing.

## Support

See the [connection guide](https://shareartifacts.dev/connect) or
[report an extension issue](https://github.com/arunai30/share-artifacts-gemini/issues).

This extension is distributed under the [MIT license](./LICENSE).
