# BRANCO connectors

French legal research in your AI assistant. Search legislation and case law, read sources, and check citations through [BRANCO](https://droit.juan-branco.fr), created by Juan Branco, lawyer and doctor of law.

[Get BRANCO](https://droit.juan-branco.fr/offres) · [Installation guide](https://droit.juan-branco.fr/installer) · [Privacy](https://droit.juan-branco.fr/confidentialite)

## Gemini CLI

```sh
gemini extensions install https://github.com/anatolium89/branco-connectors
```

Run `/mcp auth branco` when prompted to connect. Sign in to your BRANCO account in the browser and authorize access to your **Research** subscription. The extension connects directly to BRANCO over HTTPS and adds the French research tool profile. It runs no local server or installation script.

This integration is for **Gemini CLI**. It does not imply availability in the consumer Gemini application or approval by Google.

## Cursor

This repository contains a Cursor plugin manifest and an OAuth `mcp.json`. Add the configuration through Cursor MCP settings, then use its browser authentication action to connect your BRANCO account. No API key is required in these files. See the [installation guide](https://droit.juan-branco.fr/installer). Marketplace publication is separate from using this configuration.

## Kimi Code

Install the plugin in Kimi Code:

```text
/plugins install https://github.com/anatolium89/branco-connectors
```

Reload the session and use `/mcp-config` to select the BRANCO server and log in through your browser. For a manual setup, `examples/kimi-mcp.template.json` contains the OAuth connection configuration. This is a custom installable plugin; it does not imply admission to the Kimi partner catalog.

## GLM / Z.ai

For applications using the Z.ai MCP API, `examples/zai-mcp.template.json` shows a restricted three-tool configuration. Supply your personal credential from a secret store at runtime. This server-side integration sends the credential and returned results to Z.ai; use it only when that provider is appropriate for your data. It is not a listing in the consumer GLM application.

## Other MCP clients

- Transport: Streamable HTTP.
- URL: `https://droit.juan-branco.fr/api/mcp/oauth`
- Authentication: browser-based BRANCO account authorization (OAuth, PKCE S256).
- Documentation and account: [droit.juan-branco.fr/installer](https://droit.juan-branco.fr/installer).

Free-form research requires an active Research subscription. Your subscription rights, shared quotas and service limits apply across clients. OAuth provides research tools only; private university dossiers, account administration and payment tools are excluded.

Clients without OAuth can still use `https://droit.juan-branco.fr/api/mcp` with a personal Research key in `Authorization: Bearer <key>`. That legacy endpoint exposes only three predefined demonstration scenarios when used without a key. The university workspace has its own profile and installation guide.

## Questions to try

- Find the applicable French legal sources for this question and give their dates and references.
- Find case law supporting and contradicting this legal proposition.
- Check this citation against the specified source and show any differences.

Tool availability varies by profile and current coverage. Use the returned references and coverage dates when assessing a result.

## Data and access

These files contain connection metadata and documentation only. They include no credential, corpus, server implementation or private dossier. BRANCO receives the tool requests; your chosen AI application receives the returned results. Its own data-handling rules apply to those results. Never post a personal key or confidential documents in a GitHub issue.

OAuth gives each authorized application a revocable connection, with short-lived access tokens and rotating refresh tokens. Review or revoke connections in [Mon compte → Connexions](https://droit.juan-branco.fr/compte/connexions). Revocation stops future access; it cannot erase results already received by an application. Never share an access or refresh token.

The production endpoint has passed discovery, registration, login-routing and invalid-request checks. End-to-end login with a paid subscriber has not yet been verified separately in each listed client.

## En français

BRANCO relie votre IA aux sources du droit français : textes, jurisprudence et contrôle des références. Installez le connecteur, connectez votre compte BRANCO dans le navigateur et retrouvez les droits de votre abonnement Recherche dans votre logiciel. Chaque connexion peut être révoquée depuis votre compte. Les fichiers de ce dépôt ne contiennent aucune base documentaire ni aucun dossier privé.

## Licence

The MIT licence covers only the connector files and documentation in this repository. It does not license the hosted BRANCO service, grant access to its databases, or change the rights attached to third-party legal materials. Service access remains subject to the [BRANCO terms](https://droit.juan-branco.fr/cgv).

## Upstream configuration references

- [Gemini CLI extensions](https://geminicli.com/docs/extensions/writing-extensions/)
- [Cursor plugins](https://cursor.com/docs/reference/plugins)
- [Kimi Code plugins](https://www.kimi.com/code/docs/en/kimi-code-cli/customization/plugins.html)
- [Kimi Code MCP](https://www.kimi.com/code/docs/en/kimi-code-cli/customization/mcp.html)
- [Z.ai MCP](https://docs.z.ai/guides/capabilities/mcp-call)
