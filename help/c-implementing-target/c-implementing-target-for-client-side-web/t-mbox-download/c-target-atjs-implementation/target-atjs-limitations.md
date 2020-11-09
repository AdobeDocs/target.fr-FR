---
keywords: visual experience composer limitations;browser support;integrations;plugins;asynchronous considerations
description: Il existe des différences entre at.js et mbox.js. Cette section répertorie certaines des différences et limites pour que vous puissiez tirer parti d’at.js.
title: Limites d’at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# Limites d’at.js{#at-js-limitations}

Il existe des différences entre at.js et mbox.js. Cette section répertorie certaines des différences et limites pour que vous puissiez tirer parti d’at.js.

## Limites connues du compositeur d’expérience visuelle {#section_4B63C97169DE4C93B22944E880FD3DF1}

* Dans le compositeur d’expérience visuelle, les options Insérer l’élément et Réorganiser doivent être évitées dans les applications d’une seule page.

   Comme le modèle DOM n’est pas effacé lors des événements de chargement de page dans les applications d’une seule page, les manipulations Insérer l’élément et Réorganiser peuvent être réappliquées plusieurs fois selon la navigation du visiteur dans le SPA.

## Intégrations et modules externes {#section_D92E31170176406AAC7B5005F03D3425}

Certaines fonctions de [!DNL mbox.js] ne sont pas disponibles dans [!DNL at.js]. Les [objets et méthodes mbox.js](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) internes (tels que `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories`, etc.) ne sont plus pris en charge par [!DNL at.js] (exemple : `mboxFactoryDefault`). Cette fin de prise en charge est liée à la conception de la bibliothèque et a pour but de vous empêcher d’utiliser [!DNL at.js] pour développer des fonctionnalités qui peuvent détruire une implémentation et rendre impossible sa mise à niveau. Les seules méthodes exposées sont abordées dans les pages sur les API de cette documentation. Pour cette raison :

* Les [intégrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) héritées, basées sur des pages, avec d’autres solutions Adobe pourraient ne pas fonctionner et devraient être mises à niveau vers des intégrations plus récentes côté serveur.
* [Les modules externes développés pour mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) peuvent ne pas fonctionner à moins qu’ils ne soient mis à jour pour [!DNL at.js].

   Veillez à inclure les [modules externes](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) dans le cadre de vos tests.

## Points à prendre en compte concernant le caractère asynchrone des mbox {#section_B586360A3DD34E2995AE25A18E3FB953}

Étant donné que toutes les mbox sont désormais asynchrones, elles ne bloquent pas le rendu des pages et ne sont pas renvoyées dans l’ordre dans lequel elles sont déclenchées.

* Si vous utilisez une mbox globale dans le [compositeur d’expérience d’après les formulaires](/help/c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22), sachez que les offres HTML ne doivent contenir que les balises `<script>`, `<style>` et `<link>`.

   Lors de la livraison, [!DNL at.js] filtre toutes les autres balises HTML pendant l’application des offres mbox globales. Les offres mbox globales sont appliquées à HTML HEAD, ce qui n’autorise pas DIV, SPAN, etc. Par exemple, `<div>test</div>` ne peut pas être appliqué car la balise `<div>` ne peut être utilisée que dans HTML BODY.

* Les intégrations héritées basées sur des pages de [!DNL Target] vers [!DNL Analytics] ne fonctionneront pas.

   Cette intégration requiert que l’appel de [!DNL Target] soit effectué avant celui d’[!DNL Analytics].

* Méfiez-vous des dépendances JavaScript entre l’offre et la page.

   Vous ne devez pas supposer que le code JavaScript de l’offre s’exécutera avant le code JavaScript codé en dur en dessous la mbox.

* Méfiez-vous des dépendances JavaScript entre plusieurs offres sur la page.

   Vous ne pouvez plus supposer que l’offre diffusée par la première mbox s’exécutera avant celle diffusée par la seconde mbox.

* Les offres de redirection et de manipulation du modèle DOM doivent être diffusées via le type auto-created global mbox dans [!DNL at.js] et fournies dans la section `<head>`.

   Une fonction `mboxCreate()` située en haut de la section `<body>` entraînera probablement un scintillement du contenu par défaut.

