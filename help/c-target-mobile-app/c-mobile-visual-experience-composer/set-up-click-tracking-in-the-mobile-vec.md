---
description: Le compositeur d'expérience visuelle mobile (VEC) prend en charge le paramétrage des objectifs de suivi des clics pour les activités Target.
keywords: Compositeur d'expérience visuelle pour mobile ; compositeur d'expérience visuelle mobile ; options du compositeur d'expérience mobile ; options d'expérience mobile ; vue cible ; clics ; suivi des clics ; track
seo-description: Le compositeur d'expérience visuelle mobile (VEC) prend en charge le paramétrage des objectifs de suivi des clics pour les activités Adobe Target.
seo-title: Configuration du suivi des clics dans le compositeur d'expérience visuelle
solution: Target
title: Configuration du suivi des clics dans le compositeur d'expérience visuelle
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: aa729a8972547be065008c6504bb36dce9cd6e65

---


# Configuration du suivi des clics dans le compositeur d&#39;expérience visuelle{#set-up-click-tracking-in-the-mobile-vec}

L&#39;application Mobile App VEC prend en charge le paramétrage des objectifs de suivi des clics pour [!DNL Target] les activités.

1. Lorsque vous définissez vos objectifs sur la page Objectifs et paramètres pour votre activité, sélectionnez la mesure de succès [!UICONTROL Conversion].

   ![](assets/mobile-vec-clicktrack1.png)

1. Pour l’action, sélectionnez **[!UICONTROL A cliqué sur un élément]**, puis cliquez sur **[!UICONTROL Sélectionner un élément]**.

   L’application mobile s’ouvre dans le compositeur d’expérience visuelle (VEC) mobile.

   ![](assets/mobile-vec-clicktrack2.png)

1. Sélectionnez l’élément pour lequel vous souhaitez effectuer le suivi.

   Pour des conseils sur la sélection des éléments, voir [!UICONTROL Points à prendre en compte].

   ![](assets/mobile-vec-clicktrack3.png)

1. Cliquez sur la coche située dans la partie supérieure de l’écran pour enregistrer vos sélections.

Vous pouvez aussi modifier et changer vos sélections de clics, voire les supprimer si vous voulez repartir de zéro.

![](assets/mobile-vec-clicktrack4.png)

Lorsqu’un participant à une activité clique sur un élément sélectionné, le clic est comptabilisé comme une conversion.

## Considérations {#considerations}

Vous devez tenir compte de plusieurs points lors de la sélection des éléments :

* Lorsque plusieurs éléments sont sélectionnés et si un visiteur clique sur l&#39;un de ces éléments, le clic est comptabilisé. Pour comptabiliser chaque clic séparément, configurez les mesures de succès individuelles pour chaque élément.
* Les événements de clic sont envoyés à Target aussitôt que l’utilisateur a cliqué sur un événement.
* Dans le compositeur d&#39;expérience visuelle, seuls les éléments auxquels un gestionnaire de clics est attaché sont autorisés à être sélectionnés.
* Vous pouvez naviguer dans n’importe quelle section de l’application, mais assurez-vous que les [vues](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views) de la section dans laquelle vous sélectionnez des éléments sont définies pour le suivi des clics.
* Lorsque vous modifiez une activité, si l’appareil a déjà été sélectionné à l’étape 1, il n’est pas nécessaire de le sélectionner à nouveau. Toutefois, si vous atterrissez directement sur la page de suivi des clics, l&#39;écran de sélection de l&#39;appareil s&#39;affiche pour sélectionner un périphérique autorisé.
