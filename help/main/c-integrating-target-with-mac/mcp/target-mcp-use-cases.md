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
hide: true
source-git-commit: ecb51d828807735b990b8f3a52102feb005bc61b
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Serveur MCP [!DNL Adobe Target] - cas d’utilisation et procédures pas à pas {#target-mcp-use-cases}

>[!BEGINSHADEBOX]

Table des matières :

* [Aperçu](target-mcp.md)
* [Prise en main](target-mcp-get-started.md)
* **[Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md)**
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

Cette page vous explique tout ce que vous pouvez accomplir avec le serveur MCP [!DNL Adobe Target] à l’aide d’invites en langage naturel, des recherches rapides aux tâches de gestion d’activités en plusieurs étapes.

## Cas d’utilisation {#mcp-use-cases}

Les exemples suivants montrent comment interagir avec le serveur MCP [!DNL Adobe Target] à l’aide du langage naturel :

| Objectif | Exemple d’invite |
|---|---|
| **Audit du statut de l’expérience** | « Quels tests A/B sont actuellement actifs sur la page d’accueil ? Indiquez-moi le statut, l’affectation du trafic et la durée d’exécution de chacun d’eux. » |
| **Révision des performances** | « Montrez-moi tous les tests actifs qui ont atteint une signification statistique : quelles expériences gagnent ? » |
| **Analyse des revenus** | « Obtenez le rapport des commandes et des recettes pour les AT4821 d’activité et résumez quelle expérience génère le plus de recettes par visiteur. » |
| **Rapports A4T** | « Extrayez le rapport A4T pour mon test d’optimisation du passage en caisse et résumez les données de conversion côté Analytics. » |
| **Gestion des activités** | « Suspendre l’activité 98765 et mettre à jour la priorité de l’activité 11111 sur 200. » |
| **Informations sur l’activité** | « Obtenez des informations pour mon test &#39;Summer Sale Banner&#39; — à quoi ressemble la performance et y a-t-il des anomalies ? » |
| **Gestion des audiences** | « Répertoriez toutes les audiences ciblant les utilisateurs mobiles et montrez-moi à quelles activités ils sont associés. » |
| **QA et prévisualisation** | « Générer des URL d’aperçu d’AQ pour les 12345 d’activité afin que je puisse examiner toutes les variantes avant l’activation. » |
| **Révision des recommandations** | « Répertoriez tous les critères de recommandations configurés dans ce compte et résumez les types d’algorithmes utilisés. » |
| **Audit de la mise en œuvre** | « Quelle version d’at.js est configurée et quels jetons de réponse sont actuellement actifs ? » |
| **Modifier l’audit** | « Montrez-moi toutes les modifications apportées aux 98765 d’activité au cours des 30 derniers jours et qui les a effectuées. » |

## Cas d’utilisation : présentation {#mcp-use-case-walkthroughs}

Les procédures pas à pas suivantes montrent comment effectuer des tâches courantes à l’aide d’invites en langage naturel avec le serveur MCP [!DNL Adobe Target].

+++Création d’un test A/B

**Invite:**
« Créez un test A/B appelé « Test d’image du héros de la page d’accueil » avec deux expériences : « Contrôle » montrant le héros actuel et « Variante » montrant une nouvelle image du héros sur le thème de l’été. Ciblez la mbox de la page d’accueil. »

L’assistant d’IA utilise l’outil `create_ab_activity` pour créer l’activité avec la configuration que vous avez décrite. L’outil renvoie le nouvel identifiant d’activité et une confirmation des expériences créées.

+++

+++Vérification des performances de l’activité

**Invite:**
« Affichez-moi les mesures de performances de mon activité « Optimisation du flux de passage en caisse » au cours des 30 derniers jours. »

L’assistant d’IA utilise `get_ab_performance_report` ou `get_xt_performance_report` (selon le type d’activité) pour récupérer les taux de conversion, le nombre de visiteurs et d’autres mesures pour la fenêtre temporelle spécifiée.

+++

+++Gestion des offres

**Invite:**
« Créez une offre HTML appelée « Bannière de vente d’été » avec une bannière promotionnelle indiquant « 20 % de réduction sur tous les articles d’été ». »

L’assistant d’IA utilise l’outil `create_target_offer` pour créer l’offre avec le contenu HTML spécifié et renvoie une confirmation avec le nouvel identifiant d’offre.

+++

+++Création d’une audience

**Invite:**
« Créez une audience appelée « Visiteurs mobiles de Californie » qui cible les utilisateurs sur les appareils mobiles situés en Californie. »

L’assistant d’IA utilise l’outil `create_target_audience` avec les règles de ciblage appropriées dérivées de votre description.

+++

+++Génération des liens d’aperçu de l’AQ

**Invite:**
« Générer des URL d’aperçu pour les 12345 d’activité afin que je puisse tester chaque expérience. »

L’assistant d’IA utilise l’outil `preview_activity` pour générer des URL cliquables qui contournent le ciblage d’audience et vous permettent d’afficher chaque expérience directement dans votre navigateur.

+++

+++Création d&#39;une activité de ciblage d&#39;expérience

**Invite:**
« Créez une activité de ciblage d’expérience appelée « Geo Personalization » qui présente différentes bannières principales aux visiteurs de différentes régions. »

L’assistant d’IA utilise `create_xt_activity` pour créer l’activité avec un mappage d’expérience basé sur les audiences en fonction des régions que vous décrivez.

+++

+++Planification d’une activité

**Invite:**
« Mettez à jour le planning des 12345 d’activité pour qu’elles commencent le 1er mai et se terminent le 31 mai. »

L’assistant d’IA utilise l’outil `update_activity_schedule` pour appliquer les nouvelles dates de début et de fin à l’activité.

+++

## Ressources connexes {#mcp-use-cases-related}

* [Aperçu](target-mcp.md)
* [Prise en main](target-mcp-get-started.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole Model Context](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] Référence de l’API Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
