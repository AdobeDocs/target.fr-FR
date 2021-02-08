---
keywords: Target Standard, at.js, implémentation
description: Découvrez comment migrer vers at.js, la nouvelle bibliothèque d’implémentation pour Adobe Target conçue à la fois pour les implémentations Web classiques et pour les applications d’une seule page (SPA).
title: Comment migrer de mbox.js vers at.js ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 91%

---


# Migration de mbox.js vers at.js

La bibliothèque at.js est une nouvelle bibliothèque d’implémentation pour [!DNL Adobe Target] qui a été conçue pour les implémentations web classiques et les applications d’une seule page.

Autres avantages : [!DNL at.js] réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page.

[!DNL at.js] remplace [!DNL mbox.js] les [!DNL Target] implémentations. La bibliothèque [!DNL at.js] contient les composants qui étaient inclus dans [!DNL target.js]. Il n’y a donc plus d’appel à [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 et FP-11577 (ou version ultérieure) prend en charge les implémentations d’at.js et son intégration des services de cloud d’Adobe Target. Pour plus d’informations, voir [Feature Packs (Packs de fonctionnalités)](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) et [Integrating with Adobe Target (Intégration à Adobe Target)](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) de la documentation d’*Adobe Experience Manager 6.2*.

## Avantages d’at.js {#benefits}

Le tableau suivant explique les différences entre les deux bibliothèques :

| Référence de bibliothèque | Description |
|--- |--- |
| at.js | at.js remplace mbox.js pour les implémentations de [!DNL Target].<br>Autres avantages : at.js optimise les délais de chargement des pages pour les mises en œuvre web, renforce la sécurité, bloque les avertissements document.write dans Google Chrome et fournit de meilleures options d’implémentation pour les applications d’une seule page.<br>Pour plus d’informations, consultez [Implémentation de at.js](#implement). |
| mbox.js | Avant la version [!DNL Target]16.3.1 (mars 2016), [!DNL Target] devait appeler mbox.js pour créer la mbox globale nécessaire pour que [!DNL Target] puisse assurer les activités, suivre les clics ainsi que la plupart des mesures de succès. Ce fichier contient les bibliothèques nécessaires pour toutes vos activités. Vous n’avez ainsi pas à conserver différentes versions spécifiques à une activité du fichier.<br>Si vos pages contiennent déjà des mbox d’encapsulation issues d’un ancien style de mise en œuvre de [!DNL Target], vous pouvez continuer à les utiliser dans la nouvelle interface. Le fichier mbox.js mis à jour reste requis ; toutefois, il est possible de sélectionner ces mbox pour des activités et de les modifier à l’aide du compositeur d’expérience visuelle.<br>[!DNL Target] Standard et Target Premium mettent à jour et complètent mbox.js avec une référence à un fichier target.js. Ce fichier target.js est hébergé par Adobe. Il permet de modifier le contenu sur n’importe quelle page à l’aide du compositeur d’expérience visuelle, et ce même si la page ne contient pas de mbox prédéfinies. Vous devez référencer ce fichier sur chaque page de votre site.<br>Pour plus d’informations, consultez [Implémentation de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Important** : la bibliothèque mbox.js est toujours prise en charge, mais ses fonctionnalités ne seront plus mises à jour. Tous les clients doivent migrer vers at.js. Pour plus d’informations, voir [Migration vers at.js à partir de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md) |

## Implémentation d’at.js {#implement}

Pour utiliser [!DNL at.js], remplacez la référence à [!DNL mbox.js] dans les pages où vous souhaitez implémenter la bibliothèque. Vous ne pouvez pas utiliser [!DNL mbox.js] et [!DNL at.js] dans une même page. Vous pouvez en revanche utiliser une des deux bibliothèques sur chaque page de votre site.

La bibliothèque [!DNL at.js] fonctionne pour les implémentations existantes qui utilisent les fonctions `mboxCreate()`, `mboxDefine()` et `mboxUpdate()`. Elle prend aussi en charge les nouvelles fonctionnalités axées sur les implémentations basées sur les applications d’une seule page.

Vous pouvez utiliser [!DNL at.js] aux emplacements où vous utilisez actuellement [!DNL mbox.js].

La bibliothèque [!DNL at.js] propose plusieurs améliorations par rapport à la bibliothèque [!DNL mbox.js], notamment :

* Communications entièrement asynchrones via AJAX interdomaine

   >[!IMPORTANT]
   >
   >Bien que la bibliothèque [!DNL at.js] communique avec les serveurs [!DNL Target] de manière asynchrone, le fichier [!DNL at.js] doit être chargé de manière synchrone dans la section `<head>` de la page. Dans l’idéal, il doit être l’un des premiers scripts chargés. Une fois chargé, le fichier [!DNL at.js] exécute les appels de mbox de manière asynchrone via `XMLHttpRequest` et ne bloque pas le rendu des pages.

* Plus d’appels de blocage
* Aucun `document.write()` utilisé
* Pas d’exécution immédiate de JavaScript dans les réponses de [!DNL Target]
* Amélioration du délai d’attente et de la gestion des erreurs

   * Une [expiration](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) personnalisable par appel
   * Pas de rechargements à l’expiration

* Des fonctions conçues spécifiquement pour les applications d’une seule page/les infrastructures MVC

## Vidéo de formation : at.js - Bonnes pratiques sur les privilèges et l’implémentation  ![badge Aperçu](/help/assets/overview.png)

Cette vidéo est un enregistrement de « [Heures de bureau](/help/cmp-resources-and-contact-information.md) », initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Fonctionnement de la bibliothèque at.js
* Avantages d’at.js par rapport à mbox.js
* Gestion du scintillement par at.js
* Gestion des erreurs dans at.js
* Méthodologies de débogage
* Problèmes connus et feuille de route future

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
