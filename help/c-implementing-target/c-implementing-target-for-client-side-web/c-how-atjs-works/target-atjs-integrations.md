---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: Informations sur les intégrations courantes de Target et leur état de prise en charge avec at.js.
title: Intégrations d’at.js
feature: client-side
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 90%

---


# Intégrations d’at.js{#at-js-integrations}

Informations sur les intégrations courantes de [!DNL Target] et la prise en charge avec at.js.

Si vous sentez le besoin irrépressible d’une intégration, mais qu’elle n’est pas prise en charge, ni même mentionnée ici, veuillez contacter votre gestionnaire de compte ou votre consultant.

## Intégrations prises en charge {#section_3B44A970D3FB42D1973701452C868B55}

| Intégration | Détails |
|--- |--- |
| Analytics for Target (A4T) | Voir [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) |
| Profils et audiences | Consultez [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) dans le Guide *de l’utilisateur des services* principaux. |
| Service Experience Cloud ID | Voir la [documentation du Service Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/home.html). |
| Adobe Launch | Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. Voir [Implémentation de Target avec Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25). |
| Dynamic Tag Management | See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html).   Remarque importante : [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) est la dernière méthode en date, préconisée pour la mise en œuvre de Target et de la bibliothèque at.js. Désormais, utilisez Launch pour implémenter Target. Le guide suivant s’adresse aux clients déjà existants qui utilisent DTM pour l’implémentation. Tenez compte de ce qui suit lors de l’utilisation d’une intégration DTM : <ul><li>Gestion de la bibliothèque : servez-vous de l’option d’hébergement personnalisé pour l’utilisation d’at.js. La gestion automatique n’est actuellement pas prise en charge. </li></ul> |
| Services cloud Adobe Experience Manager (AEM) | Les services cloud Adobe Experience Manager (AEM) permettent la création de tests A/B et d’activités de ciblage d’expérience au sein du workflow d’AEM. Prend en charge at.js avec Adobe Experience Manager 6.2 avec FP-11577 (ou une version supérieure). Pour plus d’informations, voir [Intégration à Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) et sélectionnez votre version d’AEM. |
| Fragments d’expérience AEM | Les fragments d’expérience créés dans AEM dans les activités Target permet d’associer la facilité d’utilisation et la puissance d’AEM à de puissantes fonctionnalités d’intelligence artificielle (AI) et d’apprentissage automatique (ML) dans Target, permettant de tester et de personnaliser des expériences à grande échelle. AEM rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. AEM permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil : AEM ajuste automatiquement chaque expérience en utilisant votre contenu. Voir [fragments d’expérience AEM](../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Intégrations non prises en charge {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Intégration | Détails |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Il s’agit de l’intégration qui envoyait des ID de recette et de campagne à [!DNL SiteCatalyst] via l’appel de page pour que vous puissiez créer des rapports dans l’interface utilisateur de [!DNL SiteCatalyst]. Cette fonctionnalité est remplacée par A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Il s’agit de l’intégration qui effectuait des appels de mbox appelés `"SiteCatalyst: Event"` et `"SiteCatalyst: Purchase"` qui vous permettaient de créer des mesures de succès et des profils d’utilisateur basés sur les evar et les prop. Cette fonctionnalité est remplacée par A4T et Profils et audiences. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Il s’agit de l’intégration qui effectuait un appel d’API principal pour récupérer des segments AAM et les envoyer ensuite en tant que paramètres de mbox à chaque appel de mbox sur la page. |

## Intégrations tierces {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Intégration | Détails |
|--- |--- |
| Autres gestionnaires de balises | at.js doit fonctionner avec des plates-formes de gestion de balises autres qu’Adobe. Soyez toutefois prudent lorsque vous utilisez des fonctionnalités d’intégration développées par d’autres éditeurs. Leur intégration peut être dépendante de fonctions mbox.js internes qui n’existent plus dans at.js. |
| Fournisseurs de données tiers (Demandbase, BlueKai, API de météo, par exemple) | De nombreux fournisseurs de données tiers habitués à compléter la création de profils utilisateur de Target peuvent être intégrés grâce à l’utilisation de la fonctionnalité d’at.js [Fournisseurs de données.](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers). |