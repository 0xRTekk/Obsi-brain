---
tags:
  - Dev
  - IA
---

## Description
Le MCP (Model Context Protocol) est un cadre conceptuel utilisé pour structurer et gérer les interactions entre différents modèles dans un système. Il permet de définir comment les modèles peuvent communiquer et échanger des informations tout en tenant compte du contexte dans lequel ils opèrent.

## Objectifs principaux
- Standardisation : Établir des normes pour l'interaction entre modèles.
- Flexibilité : Permettre l'adaptation des modèles à différents contextes.
- Interopérabilité : Faciliter la collaboration entre divers systèmes et modèles.

## Domaines d'utilisation
- Intelligence artificielle
- Simulation
- Ingénierie des systèmes

## Avantages pour les agents IA
C'est une avancée importante qui permet aux modèles d'IA de se connecter facilement à différents outils et données.

## Analogie
Pensez au MCP comme à un port USB-C pour les applications d'IA. Tout comme l'USB-C offre une méthode standardisée pour connecter vos appareils à divers périphériques et accessoires, MCP fournit une manière standardisée de connecter les modèles d'IA à différentes sources de données et outils.

---

## Architecture du MCP
- Basé sur **json-rpc 2.0**
- Spécification disponible ici
- Schéma :
```json
{
  "jsonrpc": "2.0",
  "id": "string | number",
  "method": "string",
  "params": {
    "[key: string]": "unknown"
  }
}
```
- Ne remplace pas les API, mais s'adapte selon le besoin/contexte.

## Composants
- **Client** : Applications de modèles de langage (LLM) qui initient des connexions.
- **Serveur** : Services fournissant le contexte et les capacités.
- **Transport** : HTTP, WebSocket ou stdio.
- **Framework d'autorisation** : OAuth2.
- **Architecture** : Client/serveur, étatful.

---

## Workflow MCP
Utilisation d'un serveur MCP existant pour faciliter l'intégration.

### Serveur MCP utilisé
- `@modelcontextprotocol/server-filesystem`
- Fonction : opérations sur le système de fichiers.
- Documentation officielle disponible.

### Étapes du workflow
1. L'agent IA (MCP Client) initie une requête.
2. La requête est formatée selon JSON-RPC 2.0.
3. La requête est transportée via HTTP, stdio ou WebSocket.
4. Le serveur MCP traite la requête et fournit le contexte et les capacités.

---

## Intégration avec Ollama
- Modèle choisi : **Qwen 2.5** (ou autre compatible).
- Étapes pour l'installation et la configuration :
  - Installer Ollama.
  - Récupérer le modèle.
  - Vérifier les capacités du modèle.
  - Préparer le fichier de configuration (`ollama_mcp_config.json`).
  - Installer Go si nécessaire.
  - Installer `mcphost`.
  - Démarrer le serveur MCP avec la configuration.
  - Lister les serveurs MCP et outils disponibles.
  - Utiliser les outils pour créer des fichiers, répertoires, etc.

---

## Annexe : Autres serveurs MCP
- Plusieurs autres serveurs MCP sont disponibles selon les besoins.
- Plus d'informations et options disponibles sur [GitHub](https://github.com/modelcontextprotocol/servers).

---

## Ressources complémentaires
- [DZone - MCP vs API](https://dzone.com/articles/mcp-vs-traditional-apis-ai-integration)
- [DZone - Architecture et implémentation](https://dzone.com/articles/mcp-client-agent-architecture-amp-implementation)
- [DZone - Test automation avec LLM](https://dzone.com/articles/modern-test-automation-ai-llm-playwright-mcp)
- [Tuto Medium](https://medium.com/data-science-in-your-pocket/model-context-protocol-mcp-using-ollama-e719b2d9fd7a)
