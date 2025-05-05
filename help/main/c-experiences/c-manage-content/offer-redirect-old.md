---
keywords: offre de redirection;créer une offre de redirection;ajouter une offre html;transférer tous les paramètres d’URL dans une offre de redirection;transférer mboxSessionId dans une offre de redirection (disponible uniquement lorsque la redirection est effectuée vers un domaine différent)
description: Découvrez comment créer des offres de redirection dans l [!DNL Target] Adobe pour qu’un navigateur redirige vers une nouvelle page.
title: Comment Créer Des Offres De Redirection ?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 45%

---

# Création d’offres de redirection

Les offres de redirection dans [!DNL Adobe Target] entraînent la redirection par un navigateur vers une nouvelle page.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez des activités de test A/B avec deux expériences : l’une pointant vers la page A par défaut, l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées sur la page [!UICONTROL Offers] > [!UICONTROL Code Offers] ou dans le compositeur d’expérience Forms [&#128279;](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans le Compositeur d’expérience visuelle (VEC). Le contenu sera injecté dans les emplacements de requête [!DNL Target]. Il est donc peu probable qu’ils soient appropriés pour une requête de [!DNL Target] globale.
>
>* Vous ne pouvez pas utiliser d’offres de redirection dans les mbox ajax (`mboxUpdate`).
>
>* Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page de destination, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

## Créer une offre de redirection à partir de la page Offres de code

1. Cliquez sur **[!UICONTROL Offers]**, puis sélectionnez l’onglet **[!UICONTROL Code Offers]** .

   ![Onglet Offres de code](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![ Boîte de dialogue Créer une offre de redirection ](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite permet, à vous et aux autres personnes, de trouver rapidement l’offre dans la bibliothèque Assets.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** faites glisser le bouton pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` sera automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL aura été `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session mbox :** requis pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que le `sessionId` soit automatiquement inclus dans la redirection. Cela n’est nécessaire que lorsque vous testez des clics depuis un e-mail ou des clics d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Save]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Créer une offre de redirection à l’aide du compositeur d’expérience d’après les formulaires

1. Lors de la création d’une activité à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage de la section **[!UICONTROL Content]**.

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur la liste déroulante **[!UICONTROL Default Content]**, puis sur **[!UICONTROL Change Redirect Offer]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![ Boîte de dialogue Créer une offre de redirection ](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite permet, à vous et aux autres personnes, de trouver rapidement l’offre dans la bibliothèque Assets.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** faites glisser le bouton pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` sera automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL aura été `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session mbox :** requis pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que le `sessionId` soit automatiquement inclus dans la redirection. Cela n’est nécessaire que lorsque vous testez des clics depuis un e-mail ou des clics d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Save]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Utilisation des offres de redirection dans les activités

Vous devez appliquer les offres de redirection à l’aide de l’[!UICONTROL Form-Based Experience Composer] . Vous ne pouvez actuellement pas appliquer d’offres de redirection à l’aide du VEC.

Le [!UICONTROL Form-Based Experience Composer] [!DNL Adobe Target] est une interface de création d’offres et d’expériences non visuelles qui est utile pour créer des expériences à utiliser dans des activités [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] lorsque le compositeur d’expérience visuelle n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le [!UICONTROL Form-Based Experience Composer] pour créer des expériences qui utilisent des offres de redirection.

1. Créez ou modifiez une activité dans le [!UICONTROL Form-Based Experience Composer].

   Consultez [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées.

1. Spécifiez l’emplacement souhaité et ajoutez des améliorations d’audience si nécessaire.

1. Cliquez sur la liste déroulante de la section **[!UICONTROL Content]**, puis sur **[!UICONTROL Change Redirect Offer]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Sélectionnez l’offre de redirection souhaitée dans la boîte de dialogue [!UICONTROL Select Remote Offer], puis cliquez sur **[!UICONTROL Done]**.

1. Terminez la configuration de l’activité.

## Vidéo de formation : compositeur basé sur les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo présente une démonstration du compositeur basé sur les formulaires, que vous pouvez utiliser pour créer des offres de redirection.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
