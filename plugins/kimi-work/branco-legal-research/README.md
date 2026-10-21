# BRANCO - Droit français pour Kimi

BRANCO réunit la recherche en droit français, la confrontation des autorités et la vérification des citations. Le plugin contient trois méthodes et un connecteur MCP distant avec autorisation OAuth du compte Recherche BRANCO.

## Installation dans Kimi Work

Télécharger le paquet `branco-kimi-1.0.0.zip` depuis la publication `kimi-v1.0.0` de ce dépôt. Importer le paquet avec le Plugin Builder de Kimi Work, puis installer BRANCO dans la rubrique des plugins personnels. Suivre l’autorisation BRANCO dans le navigateur.

## Exemples de demandes

- Avec BRANCO, lis l’article 1240 du Code civil et indique sa source et sa version.
- Recherche les décisions qui soutiennent et limitent cet argument, puis compare les passages pertinents.
- Vérifie cette citation dans sa source et explique la portée du passage.

## Connexion

Le connecteur utilise `https://droit.juan-branco.fr/api/mcp/oauth`. Chaque utilisateur connecte son propre compte Recherche BRANCO. Les droits et quotas du compte s’appliquent aux appels du connecteur. Les connexions peuvent être retirées dans le compte BRANCO.

## Validation

Le paquet a passé le validateur officiel inclus dans Kimi Work : aucune erreur et aucun avertissement. L’installation locale et la connexion OAuth ont été vérifiées le 21 octobre 2026.

## Licence

La licence MIT couvre les fichiers de ce plugin. Le service BRANCO et les sources consultées conservent leurs conditions et droits respectifs.
