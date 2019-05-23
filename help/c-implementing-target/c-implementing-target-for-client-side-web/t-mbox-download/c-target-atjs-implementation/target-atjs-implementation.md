---
description: La bibliothèque at.js est une nouvelle bibliothèque d’implémentation pour Adobe Target qui a été conçue pour les implémentations web classiques et les applications d’une seule page.
keywords: Target Standard, at.js, implémentation
seo-description: La bibliothèque at.js est une nouvelle bibliothèque d’implémentation pour Adobe Target qui a été conçue pour les implémentations web classiques et les applications d’une seule page.
seo-title: Migration de mbox.js vers at.js
solution: Target
title: Migration de mbox.js vers at.js
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: ffa6585834b271838629d65ceb00d1770b37e80c

---


# Migration de mbox.js vers at.js{#migrate-from-mbox-js-to-at-js}

La bibliothèque at.js est une nouvelle bibliothèque d’implémentation pour [!DNL Adobe Target] qui a été conçue pour les implémentations web classiques et les applications d’une seule page.

Autres avantages : [!DNL at.js] réduit les délais de chargement des pages pour les implémentations web et offre des options d’implémentation optimisées pour les applications d’une seule page.

[!DNL at.js] remplace [!DNL mbox.js] les [!DNL Target] implémentations. La bibliothèque [!DNL at.js] contient les composants qui étaient inclus dans [!DNL target.js]. Il n’y a donc plus d’appel à [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 et FP-11577 (ou version ultérieure) prend en charge les implémentations d’at.js et son intégration des services de cloud d’Adobe Target. Pour plus d’informations, voir [Feature Packs (Packs de fonctionnalités)](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) et [Integrating with Adobe Target (Intégration à Adobe Target)](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) de la documentation d’*Adobe Experience Manager 6.2*.

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

## Vidéo de formation : at.js - Bonnes pratiques sur les privilèges et l’implémentation

Cette vidéo est un enregistrement de « [Heures de bureau](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Fonctionnement de la bibliothèque at.js
* Avantages d’at.js par rapport à mbox.js
* Gestion du scintillement par at.js
* Gestion des erreurs dans at.js
* Méthodologies de débogage
* Problèmes connus et feuille de route future

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
