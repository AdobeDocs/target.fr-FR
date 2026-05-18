---
solution: Target
product: target
title: Présentation du serveur MCP Adobe Target
description: Découvrez ce qu’est le serveur Adobe Target MCP, ses fonctionnalités essentielles et comment il se connecte à votre assistant d’IA.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 53dc7056ca62339a682756fe1b39e6af349f3ae6
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 0%

---

# Serveur MCP [!DNL Adobe Target] {#target-mcp}

L’intégration MCP [!DNL Adobe Target] vous permet d’inspecter et d’analyser les tests A/B et les activités de personnalisation directement depuis votre assistant d’IA. Transformez les données d’expérimentation et de personnalisation de [!DNL Target] en workflows en langage clair : auditez votre portfolio d’expériences, examinez les rapports de performances et explorez les audiences et les offres sans parcourir l’interface utilisateur ni écrire d’appels API.

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. La prise en charge d’autres applications compatibles avec MCP sera ajoutée dans les prochaines versions.


## Qu’est-ce que le protocole de contexte de modèle ? {#mcp-overview}

Les équipes de marketing et d’optimisation s’appuient de plus en plus sur des applications de chat et des outils de développement tels qu’Anthropic Claude, OpenAI ChatGPT, Cursor et Microsoft Copilot Studio pour rationaliser leur travail quotidien. Ces applications prennent en charge le **Model Context Protocol (MCP)**, une norme ouverte qui permet aux applications d’exposer de manière uniforme les outils back-end à des modèles de langage (LLM) volumineux.

[!DNL Adobe Target] fournit désormais un serveur MCP qui surface les opérations d’expérimentation et de personnalisation directement dans toute application compatible MCP. [!DNL Adobe Target] agit comme couche de prise de décision et d’exécution, tandis que l’assistant d’IA gère le raisonnement et l’explication, ce qui permet aux équipes d’accéder plus rapidement aux informations d’optimisation sans avoir à parcourir plusieurs écrans de produit ni à écrire des requêtes sur l’API REST [!DNL Adobe Target].


>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Fonctionnalités clés {#mcp-capabilities}

Le serveur MCP [!DNL Adobe Target] fournit un accès en lecture aux activités, audiences, offres et à la configuration de l’implémentation. Avec l’intégration , vous pouvez :

* **Inspecter et auditer les expériences** - Obtenez des liens d’aperçu de statut, de performances, d’historique des modifications et d’assurance qualité pour toute activité sans avoir à naviguer dans l’interface utilisateur.
* **Analyser les résultats** - Récupérez les rapports de performances, de chiffre d’affaires et A4T pour les activités A/B, XT, AP et de ciblage automatique.
* **Explorer les activités** - Répertorier, inspecter et analyser les activités A/B et XT.
* **Explorer les audiences et les offres** - Répertoriez et examinez les audiences, les offres HTML et les offres JSON.
<!-- * **Explore Recommendations criteria** - List and inspect criteria and cart-based algorithms. -->
* **Implémentation d’audit** - Examinez les paramètres at.js, les jetons de réponse et l’historique des révisions par entité.

>[!NOTE]
>
>Les outils d’écriture (création, mise à jour, activation, désactivation) ne sont pas exposés via le catalogue public MCP dans **Public Beta**. Tous les outils actuellement disponibles sont en lecture seule. L’accès en écriture sera disponible dans une version ultérieure.

Le serveur MCP [!DNL Adobe Target] présente 23 outils en lecture seule répartis sur 10 catégories, depuis l’inspection des activités et la création de rapports jusqu’à l’exploration des audiences et les aperçus d’assurance qualité. Pour consulter la référence complète des paramètres, voir [Référence des outils du serveur MCP](target-mcp-tools-reference.md).

Pour découvrir ce que vous pouvez faire avec le serveur MCP [!DNL Adobe Target], y compris les procédures pas à pas d’invites, consultez [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md).

Pour connecter le serveur MCP [!DNL Adobe Target] à votre assistant d’IA, notamment les conditions préalables, la configuration spécifique au client et le dépannage, consultez [Prise en main](target-mcp-get-started.md).

## Questions fréquentes {#mcp-faq}

+++Quels clients MCP sont pris en charge ?

Le serveur MCP [!DNL Adobe Target] est actuellement disponible pour **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. Il est possible que la prise en charge d’autres applications compatibles avec MCP soit ajoutée dans les prochaines versions.
+++

+++À quels objets de [!DNL Adobe Target] puis-je accéder via MCP ?

Vous pouvez accéder aux activités (A/B, XT, AP), aux audiences, aux offres, aux propriétés, aux mbox, aux jetons de réponse, à la configuration d’at.js, aux rapports A4T et à l’historique des révisions d’entités. Les 23 outils actuellement disponibles sont en lecture seule.
+++

+++Le serveur MCP peut-il créer ou modifier des activités ?

Pas dans le Beta public. Le catalogue MCP public contient actuellement 23 outils en lecture seule. Les opérations d’écriture (création, mise à jour, activation, désactivation) ne sont pas encore disponibles via le serveur MCP public. L’accès en écriture sera disponible dans une version ultérieure.
+++

+++Ai-je besoin d’un accès développeur pour utiliser le serveur MCP ?

Non. Le serveur MCP est conçu à la fois pour les professionnels du marketing et pour les techniciens. Les marketeurs peuvent interagir avec celui-ci à l’aide d’invites en langage naturel dans n’importe quel client MCP pris en charge, tandis que les développeurs peuvent l’utiliser dans des outils tels que Claude Code ou Cursor.
+++

+++Mes données [!DNL Adobe Target] sont-elles envoyées au fournisseur du client MCP ?

Lorsque vous envoyez une invite, le client MCP peut envoyer le contexte approprié (y compris [!DNL Adobe Target] données renvoyées par le serveur MCP) à son modèle pour traitement. Consultez les politiques de confidentialité et de gestion des données de votre fournisseur client MCP avant de vous connecter aux données de production. La gestion des données d’Adobe est régie par la [Politique de confidentialité d’Adobe](https://www.adobe.com/privacy.html) et les [Conditions de protection des données](https://www.adobe.com/go/dpt-ww).
+++

+++Les opérations d’écriture peuvent-elles entraîner des modifications involontaires des activités en direct ?

Les outils d’écriture ne sont pas disponibles via le catalogue public MCP dans Public Beta : les 23 outils actuellement exposés sont en lecture seule. Lorsque les outils d’écriture seront introduits dans une version ultérieure, ils incluront des annotations de sécurité et des points de contrôle de confirmation afin qu’aucune action de changement d’état ne soit exécutée sans confirmation explicite de l’utilisateur.
+++

+++De quelles autorisations ai-je besoin dans [!DNL Adobe Target] ?

Le rôle **Observateur** ou une valeur supérieure accorde l’accès à l’ensemble des 23 outils en lecture seule disponibles dans Public Beta. Les outils d’écriture ne sont pas encore exposés via le catalogue MCP public. Par conséquent, les privilèges des rôles Éditeur et Approbateur ne déverrouillent pas d’autres outils MCP pour le moment. Contactez votre administrateur [!DNL Adobe Target] si vous n’êtes pas sûr de votre niveau d’accès actuel.
+++

+++Puis-je utiliser le serveur MCP sur plusieurs organisations ou propriétés Target ?

Le serveur MCP étend les opérations à l’organisation associée à vos informations d’identification Adobe IMS authentifiées. Si vous avez accès à plusieurs propriétés au sein de cette organisation, vous pouvez effectuer une requête par propriété à l’aide de l’outil `list_target_properties` et filtrer les requêtes suivantes en conséquence.
+++

## Ressources connexes {#mcp-related}

* [Prise en main](target-mcp-get-started.md)
* [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole ModelContext](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentation du curseur](https://docs.cursor.com/){target="_blank"}
