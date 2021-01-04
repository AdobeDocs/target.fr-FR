---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Adobe Target peut être intégré à l’Adobe Dynamic Media Classic (anciennement Scene7) afin de fournir la gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
title: Intégration de la configuration de l’intégration Dynamic Media Classic
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 29%

---


# Configuration de Scene7

[!DNL Adobe Target] peut être intégré à  [!DNL Adobe Dynamic Media Classic] (anciennement Scene7) afin de fournir la gestion des actifs numériques (DAM) dans la bibliothèque [!UICONTROL  de ]contenu.

>[!NOTE]
>
>L&#39;intégration de [!DNL Target] à [!DNL Dynamic Media Classic] permet la diffusion de ressources (dans le cadre d&#39;activités) téléchargées dans le dossier [!DNL Adobe Experience Cloud] ressources. Cette intégration ne permet pas d&#39;accéder à tous les actifs chargés dans [!DNL Dynamic Media Classic] pour diffusion dans les activités [!DNL Target].

Si vous possédez déjà un compte [!DNL Dynamic Media], vous pouvez fournir vos informations d’identification existantes. Si vous n&#39;avez pas de compte, vous pouvez demander un compte à usage restreint [!DNL Dynamic Media Classic] sans frais supplémentaires auprès de votre représentant [!DNL Adobe]. Ce compte peut uniquement être utilisé à des fins limitées pour une utilisation dans [!DNL Target]. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si ce paramètre n’est pas configuré, l’option [!UICONTROL Permuter l’offre d’image] dans le processus de création d’activités n’est pas disponible. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite exploiter des offres d’image avec des images qui ont été téléchargées à partir de [!DNL Adobe Experience Cloud] pour les utiliser dans les activités [!DNL Target].

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image téléchargée dans [!DNL Experience Cloud] pour consommer directement ou en dehors des workflows de ciblage utilisant [!DNL Target]. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Notez que l’URL de l’enregistrement et les URL de publication finales des images de [!DNL Dynamic Media] sont différentes et que *NOT* doivent créer des offres à l’aide du lien d’enregistrement des images, car la diffusion ne fonctionnera pas dans de tels cas. Vous devez utiliser la fonctionnalité d’offres d’image, comme expliqué dans notre documentation d’aide.

Pour intégrer [!DNL Dynamic Media Classic] ([!DNL Scene7]), vous devez spécifier les informations suivantes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Configuration de Scene7]**.

   ![Page Scene7](/help/administrating-target/assets/scene7.png)

1. Spécifiez les informations de compte [!DNL Dynamic Media Classic] suivantes :

   **Région :**[!DNL Dynamic Media] région de votre compte  (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers [!DNL Dynamic Media].

   **Adresse électronique :** adresse électronique utilisée pour se connecter à  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Mot de passe :** mot de passe utilisé pour se connecter à  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Cliquez sur **[!UICONTROL Envoyer]**.
