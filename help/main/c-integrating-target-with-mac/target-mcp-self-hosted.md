---
solution: Target
product: target
title: Auto-hébergement du serveur MCP Adobe Target
description: Découvrez comment exécuter votre propre instance du serveur MCP Adobe Target à l’aide de Python, de Docker ou d’un environnement de développement local.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer
level: Experienced
hide: true
source-git-commit: 75f0dddcf65e9708aa564335974de1b6c3fd58ca
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 2%

---

# Auto-hébergement du serveur MCP [!DNL Adobe Target] {#target-mcp-self-hosted}

>[!BEGINSHADEBOX]

Table des matières :

* [Utiliser les clients MCP](target-mcp.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* **[Auto-hébergement du serveur MCP](target-mcp-self-hosted.md)**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Le déploiement auto-hébergé est destiné aux développeurs et aux utilisateurs avancés qui ont besoin d’un contrôle total sur l’exécution du serveur MCP [!DNL Adobe Target]. Pour la plupart des utilisateurs, le point d’entrée hébergé (`https://targetmcp.adobe.io/mcp`) est recommandé. Voir [&#x200B; Utilisation de clients MCP &#x200B;](target-mcp.md).

Cette page explique comment cloner, configurer et exécuter votre propre instance du serveur MCP [!DNL Adobe Target]. L’auto-hébergement est utile lorsque vous avez besoin d’un environnement de développement local, d’une configuration réseau personnalisée ou que vous souhaitez contribuer à la base de code du serveur.

## Conditions préalables {#self-hosted-prereqs}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Python 3.13 ou version ultérieure**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** — Package Python rapide et gestionnaire de projets

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* Licence [!DNL Adobe Target] active avec accès à Adobe Experience Cloud
* **Informations d’identification d’usine** (utilisateurs internes d’Adobe uniquement) - requises pour installer des dépendances internes

## Installation {#self-hosted-install}

**1. Clonez le référentiel :**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2. Créer et activer un environnement virtuel :**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3. Configurez les variables d’environnement :**

```bash
cp env.example .env
```

Ouvrez `.env` et remplacez les valeurs d’espace réservé par vos informations d’identification et paramètres d’organisation.

**4. Installer les dépendances :**

```bash
make uv-install
```

**5. Démarrez le serveur :**

Choisissez le mode qui correspond à votre cas d’utilisation :

| Mode | Commande | Utiliser lorsque |
|---|---|---|
| StreamableHTTP (serveur API) | `make run-api-server` | Connexion d’un client MCP via HTTP |
| STDIO (client MCP local) | `make run-mcp-stdio` | Utilisation de la communication de processus directe |

## Connexion d’un client MCP à un serveur local {#self-hosted-connect}

### Curseur

Ajoutez les éléments suivants à la configuration MCP du curseur. Remplacez les valeurs d’espace réservé par votre jeton IMS et votre ID d’organisation réels :

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### Claude Code

Ajoutez une entrée à votre fichier de configuration MCP Claude Code pointant vers le serveur local :

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>Lors de la connexion à un serveur local, les en-têtes d’authentification doivent être transmis manuellement (comme illustré dans l’exemple Cursor ci-dessus). Le flux de navigateur OAuth n’est disponible qu’avec le point d’entrée `https://targetmcp.adobe.io/mcp` hébergé.

## Déploiement Docker {#self-hosted-docker}

Le référentiel inclut une configuration Docker Compose pour les déploiements en conteneur.

**Exécuter avec la composition Docker :**

```bash
make run-dc
```

**Créez et exécutez directement l’image Docker :**

```bash
make build
make run-docker
```

## Points d’entrée de l’API {#self-hosted-endpoints}

Le serveur auto-hébergé expose les points d’entrée HTTP suivants :

| Point d&#39;entrée | Description |
|---|---|
| `/mcp` | Point d’entrée du protocole MCP pour les clients d’IA |
| `/ping` | Vérification de l&#39;activité — renvoie `"Pong"` |
| `/health` | Contrôle de l’intégrité — renvoie `{"status": "healthy"}` |
| `/validate` | Point d’entrée de validation |
| `/authorize` | Point d’entrée d’autorisation OAuth |
| `/token` | Point d’entrée du jeton OAuth |

**Exemple de contrôle de l’intégrité :**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## Résolution des problèmes {#self-hosted-troubleshoot}

+++Le serveur ne démarre pas

1. Vérifiez que Python 3.13+ est installé : `python --version`
1. Vérifiez que l’environnement virtuel est activé : `source .venv/bin/activate`
1. Vérifiez que toutes les variables d’environnement dans `.env` sont correctement définies.
1. Exécutez `make uv-install` nouveau pour vous assurer que toutes les dépendances sont présentes.

+++

+++Impossible de se connecter à partir du client MCP

1. Vérifiez que le serveur est en cours d’exécution et que le port est accessible : `curl http://localhost:8080/ping`
1. Vérifiez que l’URL du serveur dans la configuration du client MCP correspond à l’adresse du serveur en cours d’exécution.
1. Pour Cursor, assurez-vous que l’en-tête `Authorization` contient un jeton IMS valide et non expiré.

+++

+++Échec de l’installation des dépendances (utilisateurs et utilisatrices internes d’Adobe)

1. Vérifiez que vos informations d’identification Artifactory sont correctement configurées.
1. Vérifiez votre connexion réseau à l’instance Artifactory interne.
1. Contactez le responsable des opérations de développement ou de l’ingénierie de plateforme de votre équipe pour obtenir un accès Artifactory.

+++

## Ressources connexes {#self-hosted-related}

* [Utiliser des clients MCP](target-mcp.md) — Configuration de point d&#39;entrée hébergé et référence d&#39;outil
* [Documentation du protocole Model Context](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] Référence de l’API Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
