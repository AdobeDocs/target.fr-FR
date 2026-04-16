---
solution: Target
product: target
title: Utiliser les clients MCP
description: Découvrez comment connecter Adobe Target aux clients MCP à l’aide du serveur MCP
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: 75f0dddcf65e9708aa564335974de1b6c3fd58ca
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# Utiliser les clients MCP {#target-mcp}

>[!BEGINSHADEBOX]

Table des matières :

* **[Utiliser des clients MCP](target-mcp.md)**
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Auto-hébergement du serveur MCP](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est actuellement disponible en **Claude Web**, **Claude Desktop**, **Claude Code** et **Cursor**. La prise en charge d’autres applications compatibles avec MCP sera ajoutée dans les prochaines versions.

L’intégration MCP [!DNL Adobe Target] vous permet d’inspecter, d’analyser et de gérer des tests A/B, des activités de personnalisation et des critères de recommandations directement à partir de votre assistant d’IA. Transformez les API de lecture et d’écriture d’[!DNL Target] en workflows en langage clair : vérifiez votre portfolio d’expériences, examinez les rapports de performances, gérez les audiences et les offres, et prenez les mesures gouvernées sans parcourir l’interface utilisateur ni écrire d’appels d’API. Cette page explique le fonctionnement de l’intégration, ce que vous pouvez en faire et comment commencer.

## Qu’est-ce que le protocole de contexte de modèle ? {#mcp-overview}

Les équipes de marketing et d’optimisation s’appuient de plus en plus sur des applications de chat et des outils de développement tels qu’Anthropic Claude, OpenAI ChatGPT, Cursor et Microsoft Copilot Studio pour rationaliser leur travail quotidien. Ces applications prennent en charge le **Model Context Protocol (MCP)**, une norme ouverte qui permet aux applications d’exposer de manière uniforme les outils back-end à des modèles de langage (LLM) volumineux.

[!DNL Adobe Target] fournit désormais un serveur MCP qui surfacie les opérations d’expérimentation, de personnalisation et de recommandations directement dans toute application compatible MCP. [!DNL Adobe Target] agit comme couche de prise de décision et d’exécution, tandis que l’assistant d’IA gère le raisonnement et l’explication, ce qui permet aux équipes d’accéder plus rapidement aux informations d’optimisation sans avoir à parcourir plusieurs écrans de produit ni à écrire des requêtes sur l’API REST [!DNL Adobe Target].

## Fonctionnalités clés {#mcp-capabilities}

Le serveur MCP [!DNL Adobe Target] permet d’accéder en lecture et en écriture aux activités, audiences, offres, recommandations et à la configuration de l’implémentation. Avec l’intégration , vous pouvez :

* **Inspecter et auditer les expériences** - Obtenez des liens d’aperçu de statut, de performances, d’historique des modifications et d’assurance qualité pour toute activité sans avoir à naviguer dans l’interface utilisateur.
* **Analyser les résultats** - Récupérez les rapports de performances, de chiffre d’affaires et A4T pour les activités A/B, XT, AP et de ciblage automatique.
* **Gérer les activités** - Créer, mettre à jour et activer les activités A/B et XT ; ajuster les fractionnements de trafic, les variantes, les plannings et les priorités.
* **Gérer les audiences et les offres** - Répertoriez, examinez et créez des audiences, des offres HTML et des offres JSON.
* **Explorer les critères de Recommendations** - Répertoriez et examinez les critères et les algorithmes basés sur le panier.
* **Implémentation d’audit** - Examinez les paramètres at.js, les jetons de réponse et l’historique des révisions par entité.

>[!NOTE]
>
>Les opérations d’écriture (création, mise à jour, activation, désactivation) incluent des annotations de sécurité. Aucune modification n’est exécutée sans confirmation explicite de l’utilisateur.

## Outils disponibles {#mcp-tools}

Le serveur MCP [!DNL Adobe Target] contient 52 outils. Les outils de lecture sont disponibles pour tous les utilisateurs connectés avec des autorisations d’affichage ; les outils d’écriture nécessitent un rôle Éditeur ou Approbateur.

### Outils d’activité - lecture

| Outil | Description |
|---|---|
| `list_target_activities` | Liste des activités avec filtrage côté serveur par état, type, nom, date, priorité, mbox et espace de travail |
| `list_all_target_activities` | Récupérer toutes les activités correspondant aux filtres, pagination automatique à travers les résultats |
| `get_ab_activity` | Obtenir des détails complets sur une activité A/B spécifique |
| `get_xt_activity` | Obtenez des détails complets sur une activité de ciblage d’expérience (XT) spécifique |
| `get_abt_activity` | Obtenez des détails complets sur une activité Automated Personalization (AP) spécifique |

### Outils d’activité - écriture

| Outil | Description |
|---|---|
| `create_ab_activity` | Créer une activité de test A/B |
| `create_xt_activity` | Créer une activité de ciblage d’expérience (XT) |
| `create_activity_from_modifications` | Création d’une activité XT à partir de modifications JavaScript |
| `update_ab_activity` | Mettre à jour une activité A/B existante |
| `update_xt_activity` | Mettre à jour une activité XT existante |
| `update_abt_activity` | Mettre à jour une activité Automated Personalization existante |
| `update_activity_state` | Activer, désactiver, mettre en pause ou archiver une activité |
| `update_activity_schedule` | Mettre à jour les dates de début et de fin d’une activité |
| `update_activity_priority` | Mettre à jour la priorité d’une activité |
| `update_activity_name` | Renommer une activité |
| `add_activity_variant` | Ajouter une nouvelle variante (expérience) à une activité |
| `update_traffic_split` | Mettre à jour l’affectation du trafic entre les variantes |
| `update_variant_offer` | Modification de l’offre ou des modifications du compositeur d’expérience visuelle pour une variante |
| `remove_activity_variant` | Supprimer une variante d’une activité |

### Outils d’offre

| Outil | Description |
|---|---|
| `list_target_offers` | Liste des offres avec filtrage et tri côté serveur |
| `list_all_target_offers` | Récupérer toutes les offres correspondant aux filtres, pagination automatique |
| `get_target_offer` | Obtenir les détails d’une offre spécifique |
| `create_target_offer` | Création d’une offre HTML |
| `create_target_json_offer` | Créer une offre JSON |
| `update_target_offer` | Mettre à jour une offre HTML existante |

### Outils Audience

| Outil | Description |
|---|---|
| `list_target_audiences` | Liste des audiences avec filtrage et tri côté serveur |
| `create_target_audience` | Créer une audience avec des règles de ciblage facultatives |

### Outils de mbox et d’emplacement

| Outil | Description |
|---|---|
| `list_target_mboxes` | Mbox de liste avec filtrage et tri |
| `list_all_target_mboxes` | Récupérer toutes les mbox correspondant aux filtres, pagination automatique |
| `get_target_mbox` | Obtention des détails d’une mbox spécifique par nom |
| `list_target_mbox_profile_attributes` | Liste de tous les attributs de profil associés aux mbox |

### Propriétés

| Outil | Description |
|---|---|
| `list_target_properties` | Liste de toutes les propriétés de Target |

### Outils de création de rapports et d’informations

| Outil | Description |
|---|---|
| `get_ab_performance_report` | Obtention du rapport de performances pour une activité A/B, d’affectation automatique ou de ciblage automatique |
| `get_ab_orders_report` | Obtention de l&#39;état des commandes et du chiffre d&#39;affaires pour une activité A/B ou de ciblage automatique |
| `get_xt_performance_report` | Obtention du rapport de performances pour une activité XT |
| `get_xt_orders_report` | Obtention de l&#39;état des commandes et des revenus pour une activité XT |
| `get_apt_performance_report` | Obtention du rapport de performances pour une activité de AP ou de ciblage automatique |
| `get_activity_insights` | Recherchez une activité par nom et obtenez des informations détaillées sur les performances |
| `get_a4t_report` | Obtention du rapport Analytics for Target (A4T) pour une activité |

### Outils de recommandations

| Outil | Description |
|---|---|
| `list_target_criteria` | Répertorier tous les critères de Recommendations |
| `get_target_criteria` | Obtention de détails sur un critère Recommendations spécifique |
| `update_target_criteria_cart` | Mise à jour d’un critère basé sur le panier Recommendations |

### Outils d’implémentation et de configuration

| Outil | Description |
|---|---|
| `get_atjs_settings` | Obtenir les paramètres et la configuration d’AT.js |
| `get_atjs_versions` | Obtention des versions d’AT.js disponibles |
| `list_target_response_tokens` | Répertorier tous les jetons de réponse de votre client Target |
| `create_target_response_token` | Créer un jeton de réponse personnalisé |

### Outils d’audit et de révision

| Outil | Description |
|---|---|
| `get_target_revisions` | Obtention du journal d’audit pour un type de ressource, filtré par auteur |
| `get_target_entity_revisions` | Obtention de toutes les révisions d’une entité spécifique par ID |

### Utilitaires

| Outil | Description |
|---|---|
| `preview_activity` | Générer des URL d’aperçu d’assurance qualité pour une activité Target |
| `create_page_delivery_segment` | Créer un segment de diffusion de page pour le ciblage d’activité du compositeur d’expérience visuelle |
| `list_target_templates` | Répertorier les ressources et modèles MCP disponibles |
| `debug_token_info` | Inspecter les portées et les revendications actuelles des jetons OAuth |

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
> « Créez un test A/B appelé « Test d’image du héros de la page d’accueil » avec deux expériences : « Contrôle » montrant le héros actuel et « Variante » montrant une nouvelle image du héros sur le thème de l’été. Ciblez la mbox de la page d’accueil. »

L’assistant d’IA utilise l’outil `create_ab_activity` pour créer l’activité avec la configuration que vous avez décrite. L’outil renvoie le nouvel identifiant d’activité et une confirmation des expériences créées.

+++

+++Vérification des performances de l’activité

**Invite:**
> « Affichez-moi les mesures de performances de mon activité « Optimisation du flux de passage en caisse » au cours des 30 derniers jours. »

L’assistant d’IA utilise `get_ab_performance_report` ou `get_xt_performance_report` (selon le type d’activité) pour récupérer les taux de conversion, le nombre de visiteurs et d’autres mesures pour la fenêtre temporelle spécifiée.

+++

+++Gestion des offres

**Invite:**
> « Créez une offre HTML appelée « Bannière de vente d’été » avec une bannière promotionnelle indiquant « 20 % de réduction sur tous les articles d’été ». »

L’assistant d’IA utilise l’outil `create_target_offer` pour créer l’offre avec le contenu HTML spécifié et renvoie une confirmation avec le nouvel identifiant d’offre.

+++

+++Création d’une audience

**Invite:**
> « Créez une audience appelée « Visiteurs mobiles de Californie » qui cible les utilisateurs sur les appareils mobiles situés en Californie. »

L’assistant d’IA utilise l’outil `create_target_audience` avec les règles de ciblage appropriées dérivées de votre description.

+++

+++Génération des liens d’aperçu de l’AQ

**Invite:**
> « Générer des URL d’aperçu pour les 12345 d’activité afin que je puisse tester chaque expérience. »

L’assistant d’IA utilise l’outil `preview_activity` pour générer des URL cliquables qui contournent le ciblage d’audience et vous permettent d’afficher chaque expérience directement dans votre navigateur.

+++

+++Création d&#39;une activité de ciblage d&#39;expérience

**Invite:**
> « Créez une activité de ciblage d’expérience appelée « Geo Personalization » qui présente différentes bannières principales aux visiteurs de différentes régions. »

L’assistant d’IA utilise `create_xt_activity` pour créer l’activité avec un mappage d’expérience basé sur les audiences en fonction des régions que vous décrivez.

+++

+++Planification d’une activité

**Invite:**
> « Mettez à jour le planning des 12345 d’activité pour qu’elles commencent le 1er mai et se terminent le 31 mai. »

L’assistant d’IA utilise l’outil `update_activity_schedule` pour appliquer les nouvelles dates de début et de fin à l’activité.

+++

## Conditions préalables {#mcp-prerequisites}

Avant de connecter le serveur MCP [!DNL Adobe Target] à votre client MCP, vérifiez les points suivants :

* Vous disposez d’une licence [!DNL Adobe Target] active (abonnement Adobe Experience Cloud) avec une organisation Adobe Experience Platform.
* Vous disposez d’une application compatible avec MCP prise en charge (actuellement Claude Web, Claude Desktop, Claude Code ou Cursor).
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

## Questions fréquentes {#mcp-faq}

+++Quels clients MCP sont pris en charge ?

Le serveur MCP [!DNL Adobe Target] est actuellement disponible pour **Claude Web**, **Claude Desktop**, **Claude Code** et **Cursor**. Il est possible que la prise en charge d’autres applications compatibles avec MCP soit ajoutée dans les prochaines versions.
+++

+++À quels objets de [!DNL Adobe Target] puis-je accéder via MCP ?

Vous pouvez accéder aux activités (A/B, XT, AP), aux audiences, aux offres, aux propriétés, aux mbox, aux critères de recommandations, aux jetons de réponse, à la configuration d’at.js, aux rapports A4T et à l’historique de révision des entités. Les opérations de lecture et d’écriture sont toutes deux prises en charge dans 52 outils. Les opérations d’écriture nécessitent le rôle approprié et une confirmation explicite.
+++

+++Le serveur MCP peut-il créer ou modifier des activités ?

Oui. Outre les opérations de lecture, le serveur expose les opérations d’écriture qui vous permettent de créer des activités, de les mettre en pause, de mettre à jour les priorités, d’ajuster les divisions de trafic, etc. Les opérations d’écriture suivent le même modèle d’autorisation que l’interface utilisateur de [!DNL Adobe Target]. Vous avez besoin du rôle approprié pour apporter des modifications, et aucune action n’est exécutée sans confirmation explicite de l’utilisateur.
+++

+++Ai-je besoin d’un accès développeur pour utiliser le serveur MCP ?

Non. Le serveur MCP est conçu à la fois pour les professionnels du marketing et pour les techniciens. Les marketeurs peuvent interagir avec celui-ci à l’aide d’invites en langage naturel dans n’importe quel client MCP pris en charge, tandis que les développeurs peuvent l’utiliser dans des outils tels que Claude Code ou Cursor.
+++

+++Mes données [!DNL Adobe Target] sont-elles envoyées au fournisseur du client MCP ?

Lorsque vous envoyez une invite, le client MCP peut envoyer le contexte approprié (y compris [!DNL Adobe Target] données renvoyées par le serveur MCP) à son modèle pour traitement. Consultez les politiques de confidentialité et de gestion des données de votre fournisseur client MCP avant de vous connecter aux données de production. La gestion des données d’Adobe est régie par la [Politique de confidentialité d’Adobe](https://www.adobe.com/fr/privacy.html) et les [Conditions de protection des données](https://www.adobe.com/go/dpt-ww).
+++

+++Les opérations d’écriture peuvent-elles entraîner des modifications involontaires des activités en direct ?

Les outils d’écriture incluent des annotations de sécurité et des points de contrôle de confirmation. Avant toute action de changement d’état, telle que l’activation d’une activité, la modification de la priorité ou la mise à jour de l’affectation du trafic, le serveur présente une confirmation structurée montrant l’objet affecté, l’impact estimé du trafic et une étape d’approbation explicite requise. Aucune modification n’est apportée avant confirmation.
+++

+++De quelles autorisations ai-je besoin dans [!DNL Adobe Target] ?

Au minimum, le rôle **Observateur** accorde l’accès à tous les outils de lecture. Le rôle **Éditeur** permet de créer des activités, des audiences et des offres. Le rôle **Approbateur** est requis pour activer, désactiver ou archiver des activités. Contactez votre administrateur [!DNL Adobe Target] si vous n’êtes pas sûr de votre niveau d’accès actuel.
+++

+++Puis-je utiliser le serveur MCP sur plusieurs organisations ou propriétés Target ?

Le serveur MCP étend les opérations à l’organisation associée à vos informations d’identification Adobe IMS authentifiées. Si vous avez accès à plusieurs propriétés au sein de cette organisation, vous pouvez effectuer une requête par propriété à l’aide de l’outil `list_target_properties` et filtrer les requêtes suivantes en conséquence.
+++

## Ressources connexes {#mcp-related}

* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Auto-hébergement du serveur  [!DNL Adobe Target]  MCP](target-mcp-self-hosted.md)
* [Documentation du protocole Model Context](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] Référence de l’API Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentation du curseur](https://docs.cursor.com/){target="_blank"}
