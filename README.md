# bimetrics für Google Gemini CLI

Extension-Manifest für die **Google Gemini CLI** und automatische Aufnahme in die Gemini CLI Extensions Gallery (über ein öffentliches GitHub-Repository mit dem Topic `gemini-cli-extension`).

## Voraussetzung im Backend

In `MCP_CLIENTS_JSON` (Render Produktion) muss der statische Public-PKCE-Client `bimetrics-gemini-cli` (`kind: "gemini-cli"`) mit dem Loopback-Callback `http://localhost:7777/oauth/callback` hinterlegt sein:

```json
{
  "id": "bimetrics-gemini-cli",
  "name": "Gemini CLI",
  "kind": "gemini-cli",
  "redirectUris": ["http://localhost:7777/oauth/callback"]
}
```

## Installation in der Gemini CLI

```sh
gemini extensions install https://github.com/bimetrics1337/gemini-cli-extension
```

Danach in einer Gemini-CLI-Sitzung anmelden:

```text
/mcp auth bimetrics
```
