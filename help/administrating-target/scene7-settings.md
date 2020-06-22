---
description: Target Standard peut être intégré à Adobe Dynamic Media Classic (anciennement Scene7) pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
title: Intégration de Dynamic Media Classic intégration de configuration
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 0736f6f777f9f3d64706541bf5ef8265615e9082
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 32%

---


# Configuration de Scene7 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Les informations de cette rubrique ont été mises à jour afin de vous donner un pic de dénivellement lors des modifications de l’interface utilisateur qui se produisent dans la version Target Standard/Premium 20.6.1 (juillet 2020). La plupart des informations présentées dans cette rubrique s’appliquent à l’interface utilisateur actuelle ; toutefois, les options peuvent se trouver à des emplacements légèrement différents.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. Vous devez utiliser la fonctionnalité d’offres d’image, comme expliqué dans notre documentation d’aide.

To integrate with [!DNL Dynamic Media Classic] ([!DNL Scene7]), you need to specify the following information.

1. Cliquez sur **[!UICONTROL Administration]** > Configuration **** Scene7.

   ![Page Scene7](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **Région :**[!DNL Dynamic Media] région de votre compte  (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers [!DNL Dynamic Media].

   **Adresse électronique :** Adresse électronique utilisée pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Mot de passe :** Mot de passe utilisé pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Cliquez sur **[!UICONTROL Envoyer]**.
