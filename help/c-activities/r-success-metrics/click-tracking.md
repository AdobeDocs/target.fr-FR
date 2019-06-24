---
description: Target permet d’effectuer le suivi des clics sur un élément en tant que mesure de succès.
keywords: suivi des clics;suivre les clics;clics;AppMeasurement
seo-description: Target permet d’effectuer le suivi des clics sur un élément en tant que mesure de succès.
seo-title: Suivi des clics
solution: Target
subtopic: Prise en main
title: Suivi des clics
topic: Standard
uuid: 4a8fbb23-93d8-49f3-aca3-dbbdd6da0178
translation-type: tm+mt
source-git-commit: e96730720a07a599b2c77fbf93d3660e8198eea1

---


# Suivi des clics{#click-tracking}

Target permet d’effectuer le suivi des clics sur un élément en tant que mesure de succès.

>[!NOTE]
>
>Le suivi des clics n’est pas pris en charge sur la mbox globale cible lorsqu’il est utilisé comme emplacement dans une activité basée sur les formulaires.

## Setting Up click tracking {#section_5540C5A533114E57BAE022A600B02E72}

1. Lorsque vous définissez vos objectifs sur la page [!UICONTROL Objectifs et paramètres] pour votre activité, sélectionnez la mesure de succès **[!UICONTROL Conversion]**.
1. Pour l’action, sélectionnez **[!UICONTROL A cliqué sur un élément]**, puis cliquez sur **[!UICONTROL Sélectionner un élément]**.

   La page s’ouvre dans le [!UICONTROL compositeur d’expérience visuelle] (VEC).

1. Sélectionnez l’élément pour lequel vous souhaitez effectuer le suivi.

   Pour des conseils sur la sélection des éléments, voir Points à prendre en compte.

1. Cliquez sur la coche située dans la partie supérieure de l’écran pour enregistrer vos sélections.

Lorsqu’un participant à une activité clique sur un élément sélectionné, le clic est comptabilisé comme une conversion.

## Selected Elements panel {#selected-elements}

For A/B Test, Experience Targeting (XT), Automated Personalization (AP), and Multivariate Test (MVT) activities, a [!UICONTROL Selected Elements] panel lists all of the selected elements for click tracking on the right side.

![Panneau Eléments sélectionnés](/help/c-activities/r-success-metrics/assets/selected-elements.png)

There are a several actions that can be applied when you hover over an element in the [!UICONTROL Selected Elements] panel. Le tableau suivant décrit chaque action pouvant être exécutée sur un élément :

| Action | Description |
| --- | --- |
| Informations | Affiche le type d&#39;élément et le chemin DOM complet du sélecteur. |
| Modifier | Permet de modifier le sélecteur CSS. |
| Supprimer | Supprime l&#39;élément. |

### Ajouter un élément

Si vous connaissez déjà le chemin DOM vers le sélecteur, vous pouvez l&#39;ajouter manuellement en cliquant sur l&#39;icône Plus située en haut du panneau.

![Icône Ajouter un élément](/help/c-activities/r-success-metrics/assets/add-element.png)

### Menu déroulant des éléments sélectionnés

After selecting multiple elements for click tracking, you can click the [!UICONTROL Elements Selected] link on the activity&#39;s [!UICONTROL Goals &amp; Settings] step to see the full list of elements selected for click tracking. La liste contient le chemin DOM complet de l&#39;élément pour vous aider à vérifier que l&#39;élément sélectionné doit être utilisé pour le suivi des clics.

![Lien Eléments sélectionnés](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Considérations {#considerations}

Vous devez tenir compte de plusieurs points lors de la sélection des éléments :

* La fonction de chemin d’accès DOM est disponible lorsque vous définissez le suivi des clics. Lorsque vous cliquez sur un élément de la page, le menu des options du VEC s’affiche. En outre, le chemin d’accès DOM correspondant s’affiche au bas de la page. Vous pouvez utiliser le chemin d’accès DOM pour afficher rapidement les informations sur l’élément sélectionné (type, ID et classe). Vous pouvez monter ou descendre le chemin d’accès DOM pour sélectionner l’élément souhaité.

   ![Illustration du chemin d’accès DOM](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Tout comme lors de la création d’expériences à l’étape 1 dans le workflow de création de l’activité, le sélecteur de chemin d’accès DOM au bas de la page vous permet de choisir un élément. Lorsque vous sélectionnez un élément dans le chemin d’accès DOM, l’élément correspondant dans le VEC s’affiche sous la forme « Sélectionné ». Pour désélectionner un élément sélectionné, vous pouvez de nouveau cliquer sur l’élément dans le sélecteur de chemin d’accès DOM ou cliquer sur la case « Sélectionné » dans le VEC.

   Pour plus d’informations, voir [Navigation dans les éléments à l’aide du chemin d’accès DOM](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) dans *Options du compositeur d’expérience visuelle*.

* Vous pouvez accéder à une autre page pour effectuer le suivi des clics sur une page pour laquelle vous ne modifiez pas le contenu. Cette page différente doit être incluse dans l’activité en utilisant la [fonction multi-page](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) et [!DNL at.js] ou [!DNL mbox.js] doivent y être inclus.
* Si vous sélectionnez plusieurs éléments et si un participant clique sur l’un d’entre eux, le clic est comptabilisé. Pour comptabiliser séparément chaque élément, configurez des mesures de succès distinctes pour chacun d’entre eux.
* Veillez à sélectionner le niveau de l’élément dont vous souhaitez effectuer le suivi. Par exemple, lorsque vous spécifiez un bouton, veillez à sélectionner le lien et non le texte du bouton.
* Les événements de clic sont envoyés à [!DNL Target] sur la même page que le clic.
* Si la mesure de suivi des clics est la mesure de l’objectif d’une activité A4T, le visiteur doit cliquer sur cet élément dans les 60 secondes suivant le chargement de la page pour que la mesure puisse être suivie.
* Le suivi des clics ne fonctionne pas pour des éléments dont les sélecteurs contiennent des caractères d’échappement, y compris pour les éléments suivants :

   | Caractère | Description |
   |---|---|
   | # | Croisillon ou dièse |
   | : | Deux-points |
   | . | Point |
   | $ | Symbole du dollar |
   | [ ] | Crochets |

* Si vous utilisez le suivi des clics [!DNL at.js] et Analytics AppMeasurement, le suivi des clics [!DNL at.js] annule tous les autres gestionnaires d’événements de clics. En conséquence, le gestionnaire de clics AppMeasurement ne s’exécute jamais.

   [!DNL at.js] une façon particulière de gérer le suivi des clics lorsque l’élément sous-jacent est une balise (lien) `A`A (link) ou `FORM`.

   Lorsque l’événement de suivi des clics est associé à une balise (lien) [!DNL at.js] ou `A`, `FORM` effectue les étapes suivantes :

   1. Invoquez `event.preventDefault()`.

   1. Il déclenche la requête Target.

   1. En cas de succès de la requête Target ou de rappel d’erreur, il applique le comportement par défaut :

      * Balise (lien) `A` : le comportement par défaut consiste à accéder à l’URL définie par l’attribut HREF.
      * Balise `FORM` : le comportement par défaut consiste à soumettre le formulaire.
   Ce comportement par défaut peut interférer avec le suivi des clics d’Analytics. Si vous utilisez Analytics, fiez-vous à lui pour le suivi des clics plutôt qu’à Target.

* Le suivi des clics n’est pas enregistré sur les pages où l’URL de page et d’activité appartient à des propriétés différentes. Les autorisations utilisateur d’entreprise sont une fonctionnalité Target Premium. Pour plus d’informations, voir [Autorisations utilisateur d’Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

## Vidéo de formation {#section_36607204DAE146E3B8E2C609D244EDB1}

Cette vidéo comporte des informations sur la création de mesures de suivi des clics.

* Comprendre les mesures d’« objectif »
* Comprendre et créer des mesures de conversion, de recettes et d’engagement
* Créer une mesure de suivi des clics

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=fre_fr)