# Share Artifacts for Gemini CLI

Publish HTML reports, slide decks, and visual documents to shareable URLs using
the hosted [Share Artifacts](https://shareartifacts.dev) MCP service.

## Install and connect

Install the extension with [Gemini CLI](https://geminicli.com/docs/get-started/installation/):

```sh
gemini extensions install https://github.com/arunai30/share-artifacts-gemini
```

Review the extension details when prompted, then start a new Gemini CLI session.
Inside the interactive session, run:

```text
/mcp auth share-artifacts
/mcp list
```

Complete sign-in to your Share Artifacts account and approve the requested access
in the browser, then return to Gemini CLI. This extension uses the hosted MCP
service with OAuth; it does not require a personal API token or a local MCP server.
The connection requests access to read and manage your pages, reusable templates,
and artifact style, with offline access to keep the connection signed in.

Try asking:

> Create a one-page HTML project brief with a goal, three milestones, and next
> steps. Save it privately with Share Artifacts and give me its URL.

Then ask Gemini to update that same page. Publishing defaults to private; request
public sharing explicitly when you want anyone with the link to view it. Published
content is static HTML: scripts, forms, external API calls, and embedded frames
are disabled.

To update or uninstall the extension:

```sh
gemini extensions update share-artifacts
gemini extensions uninstall share-artifacts
```

If you already configured an MCP server named `share-artifacts` in Gemini CLI's
settings, that configuration takes precedence over this extension. Keep only the
connection you intend to use. For a connection that needs sign-in again, run
`/mcp auth share-artifacts` in a fresh interactive session.

The extension manifest is [`gemini-extension.json`](./gemini-extension.json).
This integration is for Gemini CLI; it does not install an app in the consumer
Gemini website.

## Support

See the [connection guide](https://shareartifacts.dev/connect) or
[report an extension issue](https://github.com/arunai30/share-artifacts-gemini/issues).

This extension is distributed under the [MIT license](./LICENSE).
