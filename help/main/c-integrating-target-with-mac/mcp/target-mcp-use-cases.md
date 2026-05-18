---
solution: Target
product: target
title: 'Serveur Adobe Target MCP : cas d’utilisation et procédures pas à pas'
description: Explorez les cas d’utilisation courants et les procédures pas à pas des invites pour le serveur Adobe Target MCP.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 53dc7056ca62339a682756fe1b39e6af349f3ae6
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---

# Serveur MCP [!DNL Adobe Target] - cas d’utilisation et procédures pas à pas {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**.

Cette page vous explique tout ce que vous pouvez accomplir avec le serveur MCP [!DNL Adobe Target] à l’aide d’invites en langage naturel, depuis les recherches rapides jusqu’aux tâches d’analyse et de création de rapports en plusieurs étapes.

>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Cas d’utilisation {#mcp-use-cases}

Les exemples suivants montrent comment interagir avec le serveur MCP [!DNL Adobe Target] à l’aide du langage naturel :

| Objectif | Exemple d’invite |
|---|---|
| **Audit du statut de l’expérience** | « Quels tests A/B sont actuellement actifs sur la page d’accueil ? Indiquez-moi le statut, l’affectation du trafic et la durée d’exécution de chacun d’eux. » |
| **Révision des performances** | « Montrez-moi tous les tests actifs qui ont atteint une signification statistique : quelles expériences gagnent ? » |
| **Analyse des revenus** | « Obtenez le rapport des commandes et des recettes pour les AT4821 d’activité et résumez quelle expérience génère le plus de recettes par visiteur. » |
| **Rapports A4T** | « Extrayez le rapport A4T pour mon test d’optimisation du passage en caisse et résumez les données de conversion côté Analytics. » |
| **Informations sur l’activité** | « Obtenez des informations pour mon test &#39;Summer Sale Banner&#39; — à quoi ressemble la performance et y a-t-il des anomalies ? » |
| **Gestion des audiences** | « Répertoriez toutes les audiences ciblant les utilisateurs mobiles et montrez-moi à quelles activités ils sont associés. » |
| **QA et prévisualisation** | « Générer des URL d’aperçu d’AQ pour les 12345 d’activité afin que je puisse examiner toutes les variantes avant l’activation. » |
<!-- | **Recommendations review** | "List all Recommendations criteria configured in this account and summarize the algorithm types in use." | -->
| **Audit de l’implémentation** | « Quelle version d’at.js est configurée et quels jetons de réponse sont actuellement actifs ? » |
| **Audit des modifications** | « Afficher toutes les modifications apportées aux 98765 d’activité au cours des 30 derniers jours et qui les a effectuées. » |

## Cas d’utilisation : présentation {#mcp-use-case-walkthroughs}

Les procédures pas à pas suivantes montrent comment effectuer des tâches courantes à l’aide d’invites en langage naturel avec le serveur MCP [!DNL Adobe Target].

<!--
+++Creating an A/B test

**Prompt:**
"Create an A/B test called 'Homepage Hero Image Test' with two experiences: 'Control' showing the current hero and 'Variant' showing a new summer-themed hero image. Target the homepage mbox."

The AI assistant uses the `create_ab_activity` tool to create the activity with the configuration you described. The tool returns the new activity ID and a confirmation of the created experiences.

+++
-->

+++Vérification des performances de l’activité

**Invite :**
« Affichez-moi les mesures de performances de mon activité « Optimisation du flux de passage en caisse » au cours des 30 derniers jours. »

L’assistant d’IA utilise `get_ab_performance_report` ou `get_xt_performance_report` (selon le type d’activité) pour récupérer les taux de conversion, le nombre de visiteurs et d’autres mesures pour la fenêtre temporelle spécifiée.

+++

<!--
+++Managing offers

**Prompt:**
"Create an HTML offer called 'Summer Sale Banner' with a promotional banner that says '20% off all summer items'."

The AI assistant uses the `create_target_offer` tool to create the offer with your specified HTML content and returns a confirmation with the new offer ID.

+++

+++Building an audience

**Prompt:**
"Create an audience called 'Mobile Visitors from California' that targets users on mobile devices located in California."

The AI assistant uses the `create_target_audience` tool with the appropriate targeting rules derived from your description.

+++
-->

+++Génération des liens d’aperçu de l’AQ

**Invite :**
« Générer des URL d’aperçu pour les 12345 d’activité afin que je puisse tester chaque expérience. »

L’assistant d’IA utilise l’outil `preview_activity` pour générer des URL cliquables qui contournent le ciblage d’audience et vous permettent d’afficher chaque expérience directement dans votre navigateur.

+++

<!--
+++Creating an Experience Targeting activity

**Prompt:**
"Create an Experience Targeting activity called 'Geo Personalization' that shows different hero banners to visitors from different regions."

The AI assistant uses `create_xt_activity` to build the activity with audience-based experience mapping according to the regions you describe.

+++

+++Scheduling an activity

**Prompt:**
"Update the schedule for activity 12345 to start on May 1st and end on May 31st."

The AI assistant uses the `update_activity_schedule` tool to apply the new start and end dates to the activity.

+++
-->

## Ressources connexes {#mcp-use-cases-related}

* [Aperçu](target-mcp.md)
* [Prise en main](target-mcp-get-started.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole ModelContext](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
