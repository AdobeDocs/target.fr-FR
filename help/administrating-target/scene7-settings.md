---
keywords: scene7;dynamic media classic;gestion des ressources numériques;ressources;dam;bibliothèque de contenu;changer une image
description: Découvrez comment intégrer Adobe [!DNL Target] à Adobe Dynamic Media Classic (anciennement Scene7) pour offrir la gestion des ressources numériques (DAM) dans la bibliothèque de contenu.
title: Comment configurer l’intégration de Dynamic Media Classic (Scene7) ?
feature: Administration et configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 28%

---

# Configuration de Dynamic Media Classic (anciennement Scene7)

[!DNL Adobe Target] peut être intégré à  [!DNL Adobe Dynamic Media Classic] (anciennement  [!DNL Scene7]) afin de fournir la gestion des ressources numériques (DAM) dans la  [!UICONTROL bibliothèque de contenu].

>[!NOTE]
>
>L’intégration de [!DNL Target] à [!DNL Dynamic Media Classic] permet la diffusion de ressources (dans le cadre d’activités) chargées dans le dossier [!DNL Adobe Experience Cloud] ressources. Cette intégration ne permet pas d’accéder à toutes les ressources chargées dans [!DNL Dynamic Media Classic] pour une diffusion dans les activités [!DNL Target].

Si vous disposez déjà d’un compte [!DNL Dynamic Media], vous pouvez fournir vos informations d’identification existantes. Si vous ne disposez pas d’un compte, vous pouvez demander un compte à usage restreint [!DNL Dynamic Media Classic] sans frais supplémentaires auprès de votre représentant [!DNL Adobe]. Ce compte ne peut être utilisé qu’à des fins limitées dans [!DNL Target]. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si ce paramètre n’est pas configuré, l’option [!UICONTROL Permuter l’offre d’image] dans le workflow de création de l’activité n’est pas disponible. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite exploiter les offres d’image avec des images qui ont été téléchargées à partir de [!DNL Adobe Experience Cloud] pour les utiliser dans les activités [!DNL Target].

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image téléchargée dans la balise [!DNL Experience Cloud] pour consommer directement ou en dehors des workflows de ciblage utilisant la balise [!DNL Target]. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Notez que l’URL de stockage et les URL de publication finales des images de [!DNL Dynamic Media] sont différentes et qu’il faut *NE PAS* créer des offres à l’aide du lien de stockage des images, car la diffusion ne fonctionnera pas dans de tels cas. Vous devez utiliser la fonctionnalité d’offres d’images comme expliqué dans notre documentation d’aide.

Pour l’intégration à [!DNL Dynamic Media Classic] ([!DNL Scene7]), vous devez spécifier les informations suivantes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Configuration Scene7]**.

   ![Page Scene7](/help/administrating-target/assets/scene7.png)

1. Indiquez les informations de compte [!DNL Dynamic Media Classic] suivantes :

   **Région :**[!DNL Dynamic Media] région de votre compte  (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers [!DNL Dynamic Media].

   **Adresse électronique :** adresse électronique utilisée pour la connexion à  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Mot de passe :** mot de passe utilisé pour la connexion à  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Cliquez sur **[!UICONTROL Envoyer]**.
