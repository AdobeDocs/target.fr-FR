---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Puis-je utiliser des offres de redirection pour pousser un navigateur à rediriger vers une nouvelle page ?
title: Création d’offres de redirection
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 15eb3050b4263358d0747b09a8afd2b4c102294c
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 48%

---


# Création d’offres de redirection

Les offres de redirection dans [!DNL Adobe Target] entraînent la redirection d’un navigateur vers une nouvelle page.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez une activité de test A/B avec deux expériences : l’une pointant vers la page A par défaut, l’autre pointant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées sur la page [!UICONTROL Offres] > [!UICONTROL Offres de code] ou dans le [compositeur d’expérience basé sur Forms](/help/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans le compositeur d’expérience visuelle. Le contenu sera injecté dans les emplacements de requête [!DNL Target], de sorte qu’ils ne sont probablement pas appropriés pour une requête globale [!DNL Target].
   >
   >
* Vous ne pouvez pas rediriger les offres dans ajax mbox (`mboxUpdate`).
   >
   >
* Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
   >
   >
* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page d’entrée, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

## Création d’une offre de redirection à partir de la page Offres du code

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.

   ![Onglet Offres de code](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre de redirection]**.

   ![Créer une Offre de redirection, boîte de dialogue](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque Ressources.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** faites glisser la bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

      Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` deviendra automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL est `https://www.mycompany.com/mensShirts.html`.

   * **Transmettez l’ID de session de la mbox :** Obligatoire pour rediriger vers un autre domaine. Faites glisser la bascule pour activer cette option si vous souhaitez que `sessionId` soit automatiquement inclus dans la redirection. Ceci n’est nécessaire que lorsque vous testez des clics d’un courrier électronique ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

      Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session de la mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Création d’une offre de redirection à l’aide du compositeur d’expérience d’après les formulaires

1. Lors de la création d’une activité à l’aide du compositeur d’expérience d’après les formulaires ](/help/c-experiences/form-experience-composer.md), sélectionnez l’emplacement où afficher la section **[!UICONTROL Contenu]**.[

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur la liste déroulante **[!UICONTROL Contenu par défaut]**, puis sur **[!UICONTROL Modifier l’Offre de redirection]**.

   ![Modifier l’Offre de redirection](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre de redirection]**.

   ![Créer une Offre de redirection, boîte de dialogue](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque Ressources.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** faites glisser la bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

      Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` deviendra automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL est `https://www.mycompany.com/mensShirts.html`.

   * **Transmettez l’ID de session de la mbox :** Obligatoire pour rediriger vers un autre domaine. Faites glisser la bascule pour activer cette option si vous souhaitez que `sessionId` soit automatiquement inclus dans la redirection. Ceci n’est nécessaire que lorsque vous testez des clics d’un courrier électronique ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

      Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session de la mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Utiliser les offres de redirection dans les activités

Vous devez appliquer des offres de redirection à l’aide du [!UICONTROL compositeur d’expérience d’après les formulaires]. Actuellement, vous ne pouvez pas appliquer d’offres de redirection à l’aide du compositeur d’expérience visuelle.

Le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience d’après les formulaires] est une interface de création d’offres et d’expériences non visuelles qui permet de créer des expériences à utiliser dans les [!UICONTROL tests A/B], [!UICONTROL ciblage d’expérience] (XT), [!UICONTROL Automated Personalization] (AP) et &lt;a9/ ] activités lorsque le compositeur d’expérience visuelle n’est pas disponible ou n’est pas pratique à utiliser. [!UICONTROL  Par exemple, vous pouvez utiliser le compositeur d’expérience d’après les formulaires ] pour créer des expériences qui utilisent des offres de redirection.[!UICONTROL 

1. Créez ou modifiez une activité dans le [!UICONTROL compositeur d’expérience d’après les formulaires].

   Voir [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement de votre choix et ajoutez les affinements d’audience nécessaires.

1. Cliquez sur la liste déroulante de la section **[!UICONTROL Contenu]**, puis sur **[!UICONTROL Modifier l’Offre de redirection]**.

   ![Modifier l’Offre de redirection](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Sélectionnez l’offre de redirection souhaitée dans la boîte de dialogue [!UICONTROL Sélectionner l’Offre distante], puis cliquez sur **[!UICONTROL Terminé]**.

1. Terminez la configuration de l’activité.

## Vidéo de formation : Balise de présentation du référentiel de contenu (4:56) ![Aperçu](/help/assets/overview.png)

Cette vidéo fournit des informations sur la gestion du contenu.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387)
