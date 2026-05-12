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
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 0%

---

# Serveur MCP [!DNL Adobe Target] {#target-mcp}


L’intégration MCP [!DNL Adobe Target] vous permet d’inspecter, d’analyser et de gérer des tests A/B, des activités de personnalisation et des critères de recommandations directement à partir de votre assistant d’IA. Transformez les API de lecture et d’écriture d’[!DNL Target] en workflows en langage clair : vérifiez votre portfolio d’expériences, examinez les rapports de performances, gérez les audiences et les offres, et prenez les mesures gouvernées sans parcourir l’interface utilisateur ni écrire d’appels d’API.

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. La prise en charge d’autres applications compatibles avec MCP sera ajoutée dans les prochaines versions.


## Qu’est-ce que le protocole de contexte de modèle ? {#mcp-overview}

Les équipes de marketing et d’optimisation s’appuient de plus en plus sur des applications de chat et des outils de développement tels qu’Anthropic Claude, OpenAI ChatGPT, Cursor et Microsoft Copilot Studio pour rationaliser leur travail quotidien. Ces applications prennent en charge le **Model Context Protocol (MCP)**, une norme ouverte qui permet aux applications d’exposer de manière uniforme les outils back-end à des modèles de langage (LLM) volumineux.

[!DNL Adobe Target] fournit désormais un serveur MCP qui surfacie les opérations d’expérimentation, de personnalisation et de recommandations directement dans toute application compatible MCP. [!DNL Adobe Target] agit comme couche de prise de décision et d’exécution, tandis que l’assistant d’IA gère le raisonnement et l’explication, ce qui permet aux équipes d’accéder plus rapidement aux informations d’optimisation sans avoir à parcourir plusieurs écrans de produit ni à écrire des requêtes sur l’API REST [!DNL Adobe Target].


>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

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

Le serveur MCP [!DNL Adobe Target] expose 52 outils répartis dans 10 catégories, de la gestion des activités et des rapports à la création d’audiences et aux aperçus d’assurance qualité. Pour consulter la référence complète des paramètres, voir [Référence des outils du serveur MCP](target-mcp-tools-reference.md).

Pour découvrir ce que vous pouvez faire avec le serveur MCP [!DNL Adobe Target], y compris les procédures pas à pas d’invites, consultez [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md).

Pour connecter le serveur MCP [!DNL Adobe Target] à votre assistant d’IA, notamment les conditions préalables, la configuration spécifique au client et le dépannage, consultez [Prise en main](target-mcp-get-started.md).

## Questions fréquentes {#mcp-faq}

+++Quels clients MCP sont pris en charge ?

Le serveur MCP [!DNL Adobe Target] est actuellement disponible pour **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**. Il est possible que la prise en charge d’autres applications compatibles avec MCP soit ajoutée dans les prochaines versions.
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

Lorsque vous envoyez une invite, le client MCP peut envoyer le contexte approprié (y compris [!DNL Adobe Target] données renvoyées par le serveur MCP) à son modèle pour traitement. Consultez les politiques de confidentialité et de gestion des données de votre fournisseur client MCP avant de vous connecter aux données de production. La gestion des données d’Adobe est régie par la [Politique de confidentialité d’Adobe](https://www.adobe.com/privacy.html) et les [Conditions de protection des données](https://www.adobe.com/go/dpt-ww).
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

* [Prise en main](target-mcp-get-started.md)
* [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md)
* [Référence des outils du serveur MCP](target-mcp-tools-reference.md)
* [Documentation du protocole ModelContext](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentation du curseur](https://docs.cursor.com/){target="_blank"}
