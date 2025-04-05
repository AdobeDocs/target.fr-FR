---
keywords: scene7;dynamic media classic;gestion des ressources numériques;ressources;dam;bibliothèque de contenu;permuter l’image
description: Découvrez comment intégrer Adobe  [!DNL Target]  à Adobe Dynamic Media Classic (anciennement Scene7) pour offrir le module de gestion des ressources numériques (DAM) dans la bibliothèque de contenu.
title: Comment dois-je procéder pour configurer l’intégration de Dynamic Media Classic (Scene7) ?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 85%

---

# Configuration de Dynamic Media Classic (anciennement Scene7)

[!DNL Adobe Target] peut être intégré à [!DNL Adobe Dynamic Media Classic] (anciennement [!DNL Scene7]) pour offrir la gestion des ressources numériques (DAM) dans le [!UICONTROL Content Library].

{{permissions-update}}

>[!NOTE]
>
>L’intégration de [!DNL Target] à [!DNL Dynamic Media Classic] permet la diffusion de ressources (intégrées à des activités) chargées vers le dossier des ressources [!DNL Adobe Experience Cloud]. Cette intégration ne permet pas d’accéder à toutes les ressources chargées vers [!DNL Dynamic Media Classic] pour la diffusion dans des activités [!DNL Target].

Si vous disposez déjà d’un compte [!DNL Dynamic Media], vous pouvez fournir vos informations d’identification existantes. Si vous n’avez pas de compte, vous pouvez demander un compte [!DNL Dynamic Media Classic] à utilisation restreinte sans frais supplémentaires auprès de votre représentant [!DNL Adobe]. Ce compte peut être utilisé à des fins limitées pour un usage dans [!DNL Target] uniquement. Ce service est mis à la disposition des clients pour les workflows nécessitant une fonctionnalité de permutation d’image.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Si ce paramètre n’est pas configuré, l’option [!UICONTROL Swap Image offer] n’est pas disponible dans le workflow de création d’activité. Une fois ce paramètre configuré, l’option de permutation/modification d’offres d’image est disponible dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite utiliser les offres d’images avec des images qui ont été chargées depuis [!DNL Adobe Experience Cloud] en vue de les utiliser dans des activités [!DNL Target].

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image chargée dans [!DNL Experience Cloud] pour la consommation directe ou à l’extérieur des workflows de ciblage utilisant [!DNL Target]. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Veuillez noter que l’URL de stockage et les URL de publications finales des images depuis [!DNL Dynamic Media] sont différentes et qu’il ne faut *PAS* créer d’offres à l’aide du lien de stockage des images. En effet, dans de tels cas, la livraison ne fonctionne pas. Vous devez utiliser la capacité des offres d’images, comme expliqué dans notre documentation d’aide.

Pour une intégration avec [!DNL Dynamic Media Classic] ([!DNL Scene7]), vous devez spécifier les informations suivantes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

1. Indiquez les informations de compte [!DNL Dynamic Media Classic] suivantes :

   **Région :** région de votre compte [!DNL Dynamic Media] (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers [!DNL Dynamic Media].

   **Adresse e-mail :** adresse e-mail utilisée pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Mot de passe :** mot de passe utilisé pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Cliquez sur **[!UICONTROL Submit]**.
