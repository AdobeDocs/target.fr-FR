---
solution: Target
product: target
title: Présentation du serveur MCP Adobe Target
description: Découvrez ce qu’est le serveur Adobe Target MCP, ses fonctionnalités essentielles et comment il se connecte à votre assistant d’IA.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
role: User, Developer
level: Beginner, Intermediate
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 8fd1b8e05c92c3e0b49f61b17fbf5fba522a8410
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 0%
---
# [!DNL Adobe Target] Serveur MCP {#target-mcp}

L&#39;intégration MCP [!DNL Adobe Target] vous permet d&#39;inspecter, d&#39;analyser et de gérer des tests A/B et des activités de personnalisation directement à partir de votre assistant d&#39;IA. Transformer les données d’expérimentation et de personnalisation de [!DNL Target] en workflows en langage clair : auditez votre portfolio d’expériences, examinez les rapports de performances, explorez les audiences et les offres, créez des activités et effectuez des mises à jour sans parcourir l’interface utilisateur ni écrire d’appels API.

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. La prise en charge d’autres applications compatibles avec MCP sera ajoutée dans les prochaines versions.


## Qu’est-ce que le protocole de contexte de modèle ? {#mcp-overview}

Les équipes de marketing et d’optimisation s’appuient de plus en plus sur des applications de chat et des outils de développement tels qu’Anthropic Claude, OpenAI ChatGPT, Cursor et Microsoft Copilot Studio pour rationaliser leur travail quotidien. Ces applications prennent en charge le **Model Context Protocol (MCP)**, un standard ouvert qui permet aux applications d&#39;exposer les outils back-end à des modèles de langage de grande taille (LLM) de manière uniforme.

[!DNL Adobe Target] fournit désormais un serveur MCP qui surfacie les opérations d’expérimentation et de personnalisation directement dans toute application compatible MCP. [!DNL Adobe Target] joue le rôle de couche de prise de décision et d’exécution, tandis que l’assistant d’IA gère le raisonnement et l’explication, ce qui permet aux équipes d’accéder plus rapidement aux informations d’optimisation sans avoir à parcourir plusieurs écrans de produit ni à écrire des requêtes sur l’API REST [!DNL Adobe Target].


>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Fonctionnalités clés {#mcp-capabilities}

Le serveur MCP [!DNL Adobe Target] fournit un accès en lecture et en écriture aux activités, audiences, offres et à la configuration d’implémentation. Avec l’intégration , vous pouvez :

* **Inspecter et auditer les expériences** - Obtenez le statut, les performances, l’historique des modifications et les liens d’aperçu de l’assurance qualité pour toute activité sans naviguer dans l’interface utilisateur.
* **Analyser les résultats** - Récupérez les rapports de performances, de chiffre d’affaires et d’A4T pour les activités A/B, XT, AP et de ciblage automatique.
* **Explorer les activités** - Répertoriez, inspectez et analysez les activités A/B et XT.
* **Créer et mettre à jour des activités** - Créez de nouvelles activités A/B et de ciblage d’expérience, mettez à jour des configurations, gérez les divisions de trafic, ajoutez ou supprimez des variantes et contrôlez l’état de l’activité (activer, mettre en pause, désactiver).
* **Explorer et gérer les audiences et les offres** - Répertoriez, inspectez, créez et mettez à jour des audiences, des offres HTML et des offres JSON.
* **Gérer les recommandations** - Répertoriez, inspectez, créez et mettez à jour des critères, des collections, des conceptions, des promotions et des exclusions, et recherchez dans le catalogue de produits. Nécessite un droit Target Premium.
* **Implémentation d’audit** - Examinez les paramètres at.js, les jetons de réponse et l’historique des révisions par entité.

Le serveur MCP [!DNL Adobe Target] expose 62 outils dans 11 catégories, de la création d’activités et de rapports à la gestion de l’audience, en passant par les aperçus d’AQ et la configuration de Recommendations. Pour consulter la référence complète des paramètres, voir [Référence des outils du serveur MCP](target-mcp-tools-reference.md).

Pour découvrir ce que vous pouvez faire avec le serveur MCP [!DNL Adobe Target], y compris les procédures pas à pas des invites, consultez [Cas d&#39;utilisation et procédures pas à pas](target-mcp-use-cases.md).

Pour connecter le serveur MCP [!DNL Adobe Target] à votre assistant AI, y compris les conditions préalables, la configuration spécifique au client et le dépannage, consultez [Prise en main](target-mcp-get-started.md).

## Questions fréquentes {#mcp-faq}

+++Quels clients MCP sont pris en charge ?

Le serveur MCP [!DNL Adobe Target] est actuellement disponible pour **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. Il est possible que la prise en charge d’autres applications compatibles avec MCP soit ajoutée dans les prochaines versions.
+++

+++À quels [!DNL Adobe Target] objets puis-je accéder via MCP ?

Vous pouvez accéder aux activités (A/B, XT, AP), aux audiences, aux offres, aux propriétés, aux mbox, aux jetons de réponse, à la configuration d’at.js, aux rapports A4T, à l’historique des révisions d’entité et à la configuration de Recommendations (critères, collections, conceptions, promotions, exclusions et recherche de catalogue), et les gérer. Le serveur MCP expose 62 outils couvrant les opérations de lecture et d’écriture. Les outils de recommandations nécessitent un droit Target Premium et ne sont pas disponibles sur les comptes non Premium.
+++

+++Le serveur MCP peut-il créer ou modifier des activités ?

Oui. Le serveur MCP prend en charge les opérations d’écriture, notamment la création d’activités A/B et de ciblage d’expérience, la mise à jour des configurations d’activité, la gestion des divisions de trafic, l’ajout ou la suppression de variantes, l’activation, la suspension et la désactivation d’activités. Le rôle Éditeur ou supérieur est requis pour les opérations d’écriture ; le rôle Approbateur est requis pour l’activation et la désactivation.
+++

+++Ai-je besoin d’un accès développeur pour utiliser le serveur MCP ?

Non. Le serveur MCP est conçu à la fois pour les professionnels du marketing et pour les techniciens. Les marketeurs peuvent interagir avec celui-ci à l’aide d’invites en langage naturel dans n’importe quel client MCP pris en charge, tandis que les développeurs peuvent l’utiliser dans des outils tels que Claude Code ou Cursor.
+++

+++Mes données [!DNL Adobe Target] sont-elles envoyées au fournisseur client MCP ?

Lorsque vous envoyez une invite, le client MCP peut envoyer le contexte approprié (y compris les données [!DNL Adobe Target] renvoyées par le serveur MCP) à son modèle pour traitement. Consultez les politiques de confidentialité et de gestion des données de votre fournisseur client MCP avant de vous connecter aux données de production. La gestion des données d’Adobe est régie par la [Politique de confidentialité d’Adobe](https://www.adobe.com/fr/privacy.html) et les [Conditions de protection des données](https://www.adobe.com/go/dpt-ww).
+++

+++Les opérations d’écriture peuvent-elles entraîner des modifications involontaires des activités en direct ?

Les outils d’écriture incluent des annotations de sécurité et des points de contrôle de confirmation afin qu’aucune action de changement d’état ne soit exécutée sans confirmation explicite de l’utilisateur. Adobe recommande de tester les intégrations dans un environnement sandbox avant d’utiliser des outils d’écriture en production et d’examiner attentivement toutes les actions déclenchées par MCP avant de les confirmer.
+++

+++De quelles autorisations ai-je besoin dans [!DNL Adobe Target] ?

Le rôle **Observateur** ou supérieur accorde l&#39;accès à tous les outils en lecture seule. Le rôle **Éditeur** ou supérieur est requis pour les outils d’écriture (créer, mettre à jour). Le rôle **Approbateur** est requis pour les outils de changement d&#39;état (activer, désactiver). Contactez votre administrateur [!DNL Adobe Target] si vous n’êtes pas sûr de votre niveau d’accès actuel.
+++

+++Puis-je utiliser le serveur MCP sur plusieurs organisations ou propriétés Target ?

Le serveur MCP étend les opérations à l’organisation associée à vos informations d’identification Adobe IMS authentifiées. Si vous avez accès à plusieurs propriétés au sein de cette organisation, vous pouvez effectuer une requête par propriété à l’aide de l’outil `list_target_properties` et filtrer les requêtes suivantes en conséquence.
+++

## Ressources connexes {#mcp-related}

* [Prise en main](target-mcp-get-started.md)
* [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole ModelContext](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Référence de l’API d’administration [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentation du curseur](https://docs.cursor.com/){target="_blank"}
