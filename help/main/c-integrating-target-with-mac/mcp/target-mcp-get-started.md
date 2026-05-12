---
solution: Target
product: target
title: Prise en main du serveur Adobe Target MCP
description: Découvrez comment connecter le serveur Adobe Target MCP à votre assistant d’IA, notamment les conditions préalables, la configuration du client et le dépannage.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Prise en main du serveur [!DNL Adobe Target] MCP {#target-mcp-get-started}

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**.

Cette page vous explique tout ce dont vous avez besoin pour connecter le serveur MCP [!DNL Adobe Target] à votre assistant d’IA et vérifier votre configuration.

>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Conditions préalables {#mcp-prerequisites}

Avant de connecter le serveur MCP [!DNL Adobe Target] à votre client MCP, vérifiez les points suivants :

* Vous disposez d’une licence [!DNL Adobe Target] active (abonnement Adobe Experience Cloud) avec une organisation Adobe Experience Platform.
* Vous disposez d&#39;une application compatible avec MCP prise en charge (actuellement Claude Web, Claude Desktop, Claude Code, Cursor ou ChatGPT).
* Vous disposez d’autorisations [!DNL Adobe Target] configurées dans Adobe Admin Console :
   * **Observateur** rôle : outils en lecture seule
   * **Éditeur** rôle : lecture + création d’outils
   * **Approbateur** rôle : lecture + création + activation/désactivation des outils

## Connexion du serveur MCP [!DNL Adobe Target] {#mcp-connect}

>[!NOTE]
>
>Le serveur MCP [!DNL Adobe Target] utilise OAuth 2.0 pour l’authentification. Lorsque vous utilisez un outil MCP pour la première fois, vous êtes redirigé vers Adobe Experience Cloud pour vous connecter, sélectionner votre organisation et accorder les autorisations demandées. Aucune information d’identification statique n’est requise.

**Pour vous connecter depuis Claude Desktop ou Claude Web:**

1. Ouvrez les paramètres de votre client MCP et ajoutez un nouveau serveur MCP.
1. Saisissez l’URL du serveur : `https://targetmcp.adobe.io/mcp`
1. Lorsque vous y êtes invité, saisissez la connexion OAuth Adobe IMS avec vos informations d’identification Adobe Experience Cloud.
1. Une fois authentifiés, tous les outils sont immédiatement disponibles. Essayez de « Répertorier toutes les activités Target actives » pour vérifier la connexion.

**Pour vous connecter depuis Claude Code :**

Ajoutez les éléments suivants à votre configuration MCP de code Claude :

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

Terminez le flux du navigateur OAuth lorsque vous y êtes invité lors de la première utilisation.

**Pour vous connecter à partir du curseur :**

1. Ouvrez **Cursor** et accédez à **Settings** → **MCP** → **Add New Global MCP Server**.
1. Ajoutez la configuration suivante :

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. Enregistrez la configuration. Le serveur MCP [!DNL Target] apparaîtra dans les serveurs MCP disponibles.

>[!TIP]
>
>Si des activités ou des données provenant de la mauvaise organisation apparaissent, déconnectez-vous complètement de Adobe Experience Cloud, reconnectez le serveur MCP et sélectionnez soigneusement l’organisation appropriée pendant la réauthentification.

## Résolution des problèmes {#mcp-troubleshooting}

+++Le flux OAuth échoue ou ne redirige pas correctement

1. Fermez complètement la session Adobe Experience Cloud.
1. Effacez les cookies de navigateur pour les domaines adobe.com.
1. Réessayez le flux d’authentification.
1. Veillez à sélectionner l’organisation appropriée lorsque vous y êtes invité.
+++

+++Les activités ou les données de la mauvaise organisation s’affichent

1. Fermez complètement la session Adobe Experience Cloud.
1. Déconnectez et reconnectez le serveur MCP dans les paramètres de votre client.
1. Sélectionnez l’organisation appropriée avec soin lors de la réauthentification.
+++

+++Un outil renvoie un message d’erreur

1. Vérifiez que vous disposez des autorisations requises dans [!DNL Adobe Target] pour l’opération (voir [Conditions préalables](#mcp-prerequisites)).
1. Vérifiez que les ressources référencées (activités, offres, audiences) existent dans votre organisation.
1. Vérifiez que les identifiants d’activité et d’autres identifiants sont corrects.
+++

+++Impossible de se connecter au serveur MCP

1. Vérifiez votre connexion Internet.
1. Vérifiez que l’URL du serveur MCP est saisie correctement dans votre configuration client.
1. Essayez de supprimer et de rajouter le serveur dans les paramètres de votre client MCP.
+++

## Sécurité et autorisations {#mcp-security}

Le serveur MCP [!DNL Adobe Target] peut uniquement accéder aux données que votre compte utilisateur Adobe est autorisé à afficher ou à modifier. Toutes les opérations respectent vos [!DNL Target] affectations de rôles et autorisations d’espace de travail.

Le serveur demande les portées OAuth suivantes :

* `AdobeID` — Identité Adobe de base
* `openid` : authentification OpenID Connect
* `additional_info.projectedProductContext` — Découverte client
* `read_organizations` — Opérations au niveau de l&#39;organisation
* `additional_info.roles` — Contrôle d&#39;accès en fonction du rôle

Les jetons OAuth sont validés par rapport à Adobe IMS à chaque requête, ne sont pas stockés de manière persistante par le serveur MCP et toutes les communications utilisent HTTPS.

## Ressources connexes {#mcp-get-started-related}

* [Aperçu](target-mcp.md)
* [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole ModelContext](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
