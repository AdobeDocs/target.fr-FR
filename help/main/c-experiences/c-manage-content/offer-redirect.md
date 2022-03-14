---
keywords: offre de redirection;créer une offre de redirection;ajouter une offre html;transférer tous les paramètres d’URL dans une offre de redirection;transférer mboxSessionId dans une offre de redirection (disponible uniquement lorsque la redirection est effectuée vers un domaine différent)
description: 'Découvrez comment créer des offres de redirection dans Adobe [!DNL Target] pour provoquer la redirection d’un navigateur vers une nouvelle page. '
title: Comment Créer Des Offres De Redirection ?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 48%

---

# Création d’offres de redirection

Offres de redirection dans [!DNL Adobe Target] de rediriger un navigateur vers une nouvelle page.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez une activité de test A/B avec deux expériences : l’une pointant vers la page par défaut A, l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées dans la variable [!UICONTROL Offres] > [!UICONTROL Offres de code] ou dans le [Compositeur d’expérience d’après Forms](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans le compositeur d’expérience visuelle (VEC). Le contenu sera injecté dans la variable [!DNL Target] emplacements de requête, donc, ils ne sont probablement pas appropriés pour une [!DNL Target] requête.
>
>* Vous ne pouvez pas rediriger les offres dans ajax mbox (`mboxUpdate`).
>
>* Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page d’entrée, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

## Créer une offre de redirection à partir de la page Offres (code)

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.

   ![Onglet Offres (code)](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre de redirection]**.

   ![Boîte de dialogue Créer une offre de redirection](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque Ressources.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** Faites glisser le bouton bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

      Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` sera automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL était `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session de mbox :** Requis pour effectuer une redirection vers un autre domaine. Faites glisser le bouton bascule pour activer cette option si vous souhaitez que la fonction `sessionId` à inclure automatiquement dans la redirection. Cela n’est nécessaire que lorsque vous testez des clics d’un email ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

      Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Création d’une offre de redirection à l’aide du compositeur d’expérience d’après les formulaires

1. Lors de la création d’une activité à l’aide de la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage du **[!UICONTROL Contenu]** .

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur le bouton **[!UICONTROL Contenu par défaut]** liste déroulante, puis cliquez sur **[!UICONTROL Modifier l’offre de redirection]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre de redirection]**.

   ![Boîte de dialogue Créer une offre de redirection](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque Ressources.

1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** Faites glisser le bouton bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

      Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` sera automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL était `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session de mbox :** Requis pour effectuer une redirection vers un autre domaine. Faites glisser le bouton bascule pour activer cette option si vous souhaitez que la fonction `sessionId` à inclure automatiquement dans la redirection. Cela n’est nécessaire que lorsque vous testez des clics d’un email ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

      Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Utilisation des offres de redirection dans les activités

Vous devez appliquer des offres de redirection à l’aide de la variable [!UICONTROL Compositeur d’expérience d’après les formulaires]. Actuellement, vous ne pouvez pas appliquer d’offres de redirection à l’aide du VEC.

Le [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience d’après les formulaires] est une interface de création d’expériences et d’offres non visuelles utile pour créer des expériences à utiliser dans [!UICONTROL Tests A/B], [!UICONTROL Ciblage d’expérience] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] activités lorsque le compositeur d’expérience visuelle n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser la variable [!UICONTROL Compositeur d’expérience d’après les formulaires] pour créer des expériences qui utilisent les offres de redirection.

1. Créez ou modifiez une activité dans le [!UICONTROL Compositeur d’expérience d’après les formulaires].

   Voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement souhaité et ajoutez toute amélioration de l’audience nécessaire.

1. Cliquez sur la liste déroulante du **[!UICONTROL Contenu]** , puis cliquez sur **[!UICONTROL Modifier l’offre de redirection]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Sélectionnez l’offre de redirection souhaitée dans la [!UICONTROL Sélectionner une offre distante] , puis cliquez sur **[!UICONTROL Terminé]**.

1. Terminez la configuration de l’activité.

## Vidéo de formation : Compositeur d’après les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit une démonstration du compositeur d’après les formulaires, que vous pouvez utiliser pour créer des offres de redirection.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
