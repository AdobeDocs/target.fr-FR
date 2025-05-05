---
keywords: offre de redirection;créer une offre de redirection;ajouter une offre HTML;Transmettre tous les paramètres d’URL dans la redirection
description: Découvrez comment créer des offres de redirection pour guider facilement les navigateurs vers de nouvelles pages.
title: Comment Créer Des Offres De Redirection ?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 25%

---

# Création d’offres de redirection

Découvrez comment créer des offres de redirection pour guider facilement les navigateurs vers de nouvelles pages.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez une activité [!UICONTROL A/B Test] avec deux expériences : l’une pointant vers la page A par défaut, et l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées sur la page [!UICONTROL Offers] > [!UICONTROL Code Offers] ou dans le compositeur d’expérience Forms [&#128279;](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans le [!UICONTROL Visual Experience Composer] (VEC). Le contenu est injecté dans les emplacements de requête [!DNL Target]. Ces emplacements ne sont donc probablement pas appropriés pour une requête de [!DNL Target] globale.
>
>* Vous ne pouvez pas utiliser d’offres de redirection dans les mbox AJAX (`mboxUpdate`).
>
>* Pour les offres de redirection dans les activités utilisant [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), votre implémentation doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Voir la [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Ce processus permet aux visiteurs et visiteuses d’utiliser le bouton Précédent dans leur navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur référente de la landing page, utilisez une offre d&#39;HTML plutôt qu&#39;une offre de redirection.

## Créer une offre de redirection à partir de la page [!UICONTROL Code Offers]

1. Cliquez sur **[!UICONTROL Offers]**, puis sélectionnez l’onglet **[!UICONTROL Code Offers]** .
1. Cliquez sur **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Attribuez un nom explicite à l’offre.

   Un nom descriptif vous permet, ainsi qu’à d’autres personnes, de trouver rapidement l’offre dans la bibliothèque [!UICONTROL Assets].

1. (Conditionnel) Si vous disposez d’un compte [Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez l’espace de travail [ souhaité](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger. Cette URL doit être absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Assurez-vous que l’utilisateur ou l’utilisatrice ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **[!UICONTROL Include all URL parameters]:** activez cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous souhaitez également que les paramètres dynamiques de l’URL soient transmis, car cette méthode permet de suivre si des personnes ont accédé à votre site par e-mail, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL a été `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Obligatoire pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que le `sessionId` soit automatiquement inclus dans la redirection. Cette option est requise uniquement lorsque vous testez des clics depuis un e-mail ou des clics depuis un domaine vers un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Adressez-vous à votre consultant en implémentation avant de lancer ces tests.

## Créer une offre de redirection à l’aide de l’[!UICONTROL Form-Based Experience Composer]

1. Lors de la création d’une activité à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage de la section **[!UICONTROL Content]**.
1. Cliquez sur la liste déroulante **[!UICONTROL Content]** , sur l&#39;icône **[!UICONTROL List]** ( ![Liste](/help/main/assets/icons/MoreSmallList.svg) ), puis sur **[!UICONTROL Change Redirect Offer]**.
1. Cliquez sur **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Attribuez un nom explicite à l’offre.

   Un nom descriptif vous permet, ainsi qu’à d’autres personnes, de trouver rapidement l’offre dans la bibliothèque [!UICONTROL Assets].

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger. Cette URL doit être absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Assurez-vous que l’utilisateur ou l’utilisatrice ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **[!UICONTROL Include all URL parameters]:** faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous souhaitez également que les paramètres dynamiques de l’URL soient transmis, car cette méthode permet de suivre si des personnes ont accédé à votre site par e-mail, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL a été `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Obligatoire pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que le `sessionId` soit automatiquement inclus dans la redirection. Cette option est requise uniquement lorsque vous testez des clics depuis un e-mail ou des clics depuis un domaine vers un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Adressez-vous à votre consultant en implémentation avant de lancer ces tests.

## Utilisation des offres de redirection dans les activités

Appliquez des offres de redirection à l’aide de l’[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) . Vous ne pouvez actuellement pas appliquer d’offres de redirection à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

Le [!UICONTROL Form-Based Experience Composer] [!DNL Adobe Target] est une interface de création d’offres et d’expériences non visuelles qui est utile pour créer des expériences à utiliser dans des activités [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] lorsque le [!UICONTROL Visual Experience Composer] n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le [!UICONTROL Form-Based Experience Composer] pour créer des expériences qui utilisent des offres de redirection.

1. Créez ou modifiez une activité dans le [!UICONTROL Form-Based Experience Composer].

   Consultez [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées.

1. Spécifiez l’emplacement souhaité et ajoutez des améliorations d’audience si nécessaire.

1. Cliquez sur la liste déroulante **[!UICONTROL Content]** , sur l&#39;icône **[!UICONTROL List]** ( ![Liste](/help/main/assets/icons/MoreSmallList.svg) ), puis sur **[!UICONTROL Change Redirect Offer]**.
1. Sélectionnez l’offre de redirection souhaitée dans la boîte de dialogue [!UICONTROL Select Redirect Offer], puis cliquez sur **[!UICONTROL Add]**.
1. Terminez la configuration de l’activité.
