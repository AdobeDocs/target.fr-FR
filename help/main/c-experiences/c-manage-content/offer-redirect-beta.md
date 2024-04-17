---
keywords: offre de redirection;créer une offre de redirection;ajouter une offre html;transférer tous les paramètres d’URL dans une offre de redirection;transférer mboxSessionId dans une offre de redirection (disponible uniquement lorsque la redirection est effectuée vers un domaine différent)
description: Découvrez comment créer des offres de redirection dans [!DNL Target] pour qu’un navigateur redirige vers une nouvelle page.
title: Comment Créer Des Offres De Redirection ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
source-git-commit: bd19686d2aa716af64f520fb0be798a300ed9fa3
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# Création d’offres de redirection

Création d’offres de redirection dans [!DNL Adobe Target] pour qu’un navigateur redirige vers une nouvelle page.

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à la variable [!DNL Target] interface utilisateur qui fait actuellement partie d’un programme bêta. La variable [!DNL Adobe Target] L’équipe active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités seront activées pour tous les clients à l’avenir. [!DNL Target Standard/Premium] versions et annoncées dans les notes de mise à jour.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez une [!UICONTROL A/B Test] activité avec deux expériences : l’une pointant vers la page par défaut A, l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées dans la variable [!UICONTROL Offers] > [!UICONTROL Code Offers] ou dans le [Compositeur d’expérience d’après Forms](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans la variable [!UICONTROL Visual Experience Composer] (VEC). Le contenu est injecté dans la variable [!DNL Target] emplacements de requête, de sorte que ces emplacements ne sont probablement pas appropriés pour une [!DNL Target] requête.
>
>* Vous ne pouvez pas utiliser les offres de redirection dans AJAX mbox (`mboxUpdate`).
>
>* Pour les offres de redirection dans les activités utilisant Analytics comme source de création de rapports (A4T), votre mise en oeuvre doit respecter certaines exigences minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Ce processus permet aux visiteurs d’utiliser le bouton Précédent dans leur navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référent de la landing page, utilisez une offre de HTML plutôt qu’une offre de redirection.

## Créez une offre de redirection à partir du [!UICONTROL Code Offers] page

1. Cliquez sur **[!UICONTROL Offers]**, puis sélectionnez la variable **[!UICONTROL Code Offers]** .

   ![Onglet Offres (code)](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Cliquez sur **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![Boîte de dialogue Créer une offre de redirection](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la variable [!UICONTROL Assets] bibliothèque .

1. (Conditionnel) Si vous avez un événement [Compte Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez une [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Assurez-vous que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** Faites glisser le bouton bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL était `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session de mbox :** Requis pour rediriger vers un autre domaine. Faites glisser le bouton bascule pour activer cette option si vous souhaitez que la fonction `sessionId` à inclure automatiquement dans la redirection. Cette option est requise uniquement lorsque vous testez des clics d’un email ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Create]**.

>[!NOTE]
>
>Avant de lancer ces tests, contactez votre conseiller en mise en oeuvre.

## Créez une offre de redirection à l’aide du [!UICONTROL Form-Based Experience Composer]

1. Lors de la création d’une activité à l’aide de la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage du **[!UICONTROL Content]** .

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur le bouton **[!UICONTROL Default Content]** liste déroulante, puis cliquez sur **[!UICONTROL Change Redirect Offer]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Boîte de dialogue Créer une offre de redirection](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la variable [!UICONTROL Assets] bibliothèque .

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Assurez-vous que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **Inclure tous les paramètres d’URL :** Faites glisser le bouton bascule pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page de redirection.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone URL était `https://www.mycompany.com/mensShirts.html`.

   * **Transmettre l’ID de session de mbox :** Requis pour rediriger vers un autre domaine. Faites glisser le bouton bascule pour activer cette option si vous souhaitez que la fonction `sessionId` à inclure automatiquement dans la redirection. Cette option est requise uniquement lorsque vous testez des clics d’un email ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Save]**.

>[!NOTE]
>
>Avant de lancer ces tests, contactez votre conseiller en mise en oeuvre.

## Utilisation des offres de redirection dans les activités

Vous devez appliquer des offres de redirection à l’aide de la variable [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). Actuellement, vous ne pouvez pas appliquer d’offres de redirection à l’aide de la variable [!UICONTROL Visual Experience Composer] (VEC).

La variable [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] est une interface de création d’offres et d’expériences non visuelles utile pour créer des expériences à utiliser dans [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] activités lorsque le compositeur d’expérience visuelle n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser la variable [!UICONTROL Form-Based Experience Composer] pour créer des expériences qui utilisent les offres de redirection.

1. Créez ou modifiez une activité dans le [!UICONTROL Form-Based Experience Composer].

   Voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement souhaité et ajoutez toute amélioration de l’audience nécessaire.

1. Cliquez sur la liste déroulante du **[!UICONTROL Content]** , puis cliquez sur **[!UICONTROL Change Redirect Offer]**.

   ![Option Modifier l’offre de redirection](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Sélectionnez l’offre de redirection souhaitée dans la [!UICONTROL Select Remote Offer] , puis cliquez sur **[!UICONTROL Done]**.

1. Terminez la configuration de l’activité.

## Vidéo de formation : compositeur d’après les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo présente une démonstration de la fonction [!UICONTROL Form-Based Experience Composer], à utiliser pour créer des offres de redirection.

* Créez une activité à l’aide du [!UICONTROL Form-Based Experience Composer]
* Comprendre à quel moment utiliser la variable [!UICONTROL Form-Based Experience Composer] par rapport à la valeur [!UICONTROL Visual Experience Composer]
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)