# BRANCO connectors

French legal research in your AI assistant. Search legislation and case law, read sources, and check citations through [BRANCO](https://droit.juan-branco.fr), created by Juan Branco, lawyer and doctor of law.

[Get BRANCO](https://droit.juan-branco.fr/offres) · [Installation guide](https://droit.juan-branco.fr/installer) · [Privacy](https://droit.juan-branco.fr/confidentialite)

## Gemini CLI

```sh
gemini extensions install https://github.com/anatolium89/branco-connectors
```

Enter your personal **Research** API key when prompted. Gemini CLI marks this setting as sensitive and stores it in your system keychain. The extension connects directly to BRANCO over HTTPS and adds the French research tool profile. It runs no local server or installation script.

This integration is for **Gemini CLI**. It does not imply availability in the consumer Gemini application or approval by Google.

## Cursor

This repository contains a Cursor plugin manifest and `mcp.json`. In a plugin installation, configure `BRANCO_API_KEY` with your personal Research key. For a manual MCP connection, follow the [installation guide](https://droit.juan-branco.fr/installer). Marketplace publication is separate from installing this repository.

## Kimi Code

Use `/mcp-config` to add an HTTP server with the URL below, an `Authorization: Bearer <your personal key>` header, and `X-Branco-Tool-Profile: france`. `examples/kimi-mcp.template.json` shows the structure. Keep the completed configuration in your private user settings, outside shared repositories.

## GLM / Z.ai

For applications using the Z.ai MCP API, `examples/zai-mcp.template.json` shows a restricted three-tool configuration. Supply your personal credential from a secret store at runtime. This server-side integration sends the credential and returned results to Z.ai; use it only when that provider is appropriate for your data. It is not a listing in the consumer GLM application.

## Other MCP clients

- Transport: Streamable HTTP.
- URL: `https://droit.juan-branco.fr/api/mcp`
- Authentication: your personal BRANCO key in the `Authorization` bearer header.
- Documentation and account: [droit.juan-branco.fr/installer](https://droit.juan-branco.fr/installer).

Without a key, BRANCO exposes only three predefined demonstration scenarios. Free-form research requires a Research subscription. Your subscription rights, shared quotas and service limits apply in every client. The university workspace uses its own profile and installation guide.

## Questions to try

- Find the applicable French legal sources for this question and give their dates and references.
- Find case law supporting and contradicting this legal proposition.
- Check this citation against the specified source and show any differences.

Tool availability varies by profile and current coverage. Use the returned references and coverage dates when assessing a result.

## Data and access

These files contain connection metadata and documentation only. They include no credential, corpus, server implementation or private dossier. BRANCO receives the tool requests; your chosen AI application receives the returned results. Its own data-handling rules apply to those results. Never post a personal key or confidential documents in a GitHub issue.

Your subscription does not become a general-purpose public key. You can replace a compromised key through [Mon compte](https://droit.juan-branco.fr/compte).

## En français

BRANCO relie votre IA aux sources du droit français : textes, jurisprudence et contrôle des références. Installez le connecteur, renseignez votre clé personnelle Recherche et retrouvez les droits de votre abonnement dans votre logiciel. Les fichiers de ce dépôt ne contiennent aucune base documentaire ni aucun dossier privé.

## Licence

The MIT licence covers only the connector files and documentation in this repository. It does not license the hosted BRANCO service, grant access to its databases, or change the rights attached to third-party legal materials. Service access remains subject to the [BRANCO terms](https://droit.juan-branco.fr/cgv).

## Upstream configuration references

- [Gemini CLI extensions](https://geminicli.com/docs/extensions/writing-extensions/)
- [Cursor plugins](https://cursor.com/docs/reference/plugins)
- [Kimi Code MCP](https://www.kimi.com/code/docs/en/kimi-code-cli/customization/mcp.html)
- [Z.ai MCP](https://docs.z.ai/guides/capabilities/mcp-call)
