---
keywords: offre de redirection;créer une offre de redirection;ajouter une offre HTML;Transmettre tous les paramètres d’URL dans la redirection
description: Découvrez comment créer des offres de redirection pour guider facilement les navigateurs vers de nouvelles pages.
title: Comment Créer Des Offres De Redirection ?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
TQID: 'https://experienceleague.adobe.com/-kFkgCCbzb34aNAxW-Q1CqmyK9rETL0qVMQeEP9JtrY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: ef98a6e0-f26c-4870-9bd4-e6b72e9cc699
    internal-label: Experiences and offers
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 24%
---
# Création d’offres de redirection

Découvrez comment créer des offres de redirection pour guider facilement les navigateurs vers de nouvelles pages.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A à la page B. Configurez une activité [!UICONTROL Test A/B] avec deux expériences : l’une pointant vers la page A par défaut, l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une autre page.

>[!NOTE]
>
> * Les offres de redirection peuvent être créées sur la page [!UICONTROL Offres] > [!UICONTROL Offres de code] ou dans le [Compositeur d’expérience basé sur Forms](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres de redirection dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). Le contenu est injecté dans les emplacements de requête [!DNL Target]. Ces emplacements ne sont donc probablement pas appropriés pour une requête [!DNL Target] globale.
>
>* Vous ne pouvez pas utiliser d’offres de redirection dans les mbox AJAX (`mboxUpdate`).
>
>* Pour les offres de redirection dans les activités utilisant [[!UICONTROL Analytics comme source de création de rapports]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), votre implémentation doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Voir la FAQ sur les [offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#redirect-to-url).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Ce processus permet aux visiteurs et visiteuses d’utiliser le bouton Précédent dans leur navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur référente de la landing page, utilisez une offre HTML plutôt qu&#39;une offre de redirection.

## Créez une offre de redirection à partir de la page [!UICONTROL Offres de code]

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.
1. Cliquez Sur **[!UICONTROL Créer Une Offre]** > **[!UICONTROL Offre De Redirection]**.
1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Ressources].

1. (Conditionnel) Si vous disposez d’un compte [Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez l’[espace de travail](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) souhaité.

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger. Cette URL doit être absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Pour éviter cela, ajoutez un paramètre de requête à l’URL de redirection (par exemple, `?redirect=true`). Ensuite, dans l’audience de l’activité ou dans la règle de modèle, vérifiez que ce paramètre de requête n’est pas présent. Cela permet de s’assurer que l’utilisateur ou l’utilisatrice ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **[!UICONTROL Inclure tous les paramètres d’URL]:** Activez cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous souhaitez également que les paramètres dynamiques de l’URL soient transmis, car cette méthode permet de suivre si des personnes ont accédé à votre site par e-mail, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone d’URL était `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Transmettez l’ID de session mbox] :** Obligatoire pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que `sessionId` soit automatiquement inclus dans la redirection. Cette option est requise uniquement lorsque vous testez des clics depuis un e-mail ou des clics depuis un domaine vers un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Créer]**.

>[!IMPORTANT]
>
>Adressez-vous à votre consultant en implémentation avant de lancer ces tests.

## Créez une offre de redirection à l’aide du [!UICONTROL compositeur d’expérience d’après les formulaires]

1. Lors de la création d’une activité à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage de la section **[!UICONTROL Contenu]**.
1. Cliquez sur la liste déroulante **[!UICONTROL Contenu]**, sur l&#39;icône **[!UICONTROL Liste]** ( ![Liste](/help/main/assets/icons/MoreSmallList.svg) ), puis sur **[!UICONTROL Modifier l&#39;offre de redirection]**.
1. Cliquez Sur **[!UICONTROL Créer Une Offre]** > **[!UICONTROL Offre De Redirection]**.
1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Ressources].

1. Spécifiez l’URL du contenu ou de la destination unique vers lequel vous souhaitez rediriger. Cette URL doit être absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Pour éviter cela, ajoutez un paramètre de requête à l’URL de redirection (par exemple, `?redirect=true`). Ensuite, dans l’audience de l’activité ou dans la règle de modèle, vérifiez que ce paramètre de requête n’est pas présent. Cela permet de s’assurer que l’utilisateur ou l’utilisatrice ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

   * **[!UICONTROL Inclure tous les paramètres d’URL]:** Faites glisser le bouton pour activer cette option si vous souhaitez que tous les paramètres d’URL présents sur la page précédente soient propagés à la page redirigée.

     Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous souhaitez également que les paramètres dynamiques de l’URL soient transmis, car cette méthode permet de suivre si des personnes ont accédé à votre site par e-mail, bannière publicitaire, publicité de recherche ou de manière organique. En activant cette option, votre offre de redirection sur la page `https://www.mycompany.com/mens.html?emailId=123` devient automatiquement `https://www.mycompany.com/mensShirts.html?emailId=123` lorsque tout ce que vous avez saisi dans la zone d’URL était `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Transmettez l’ID de session mbox] :** Obligatoire pour la redirection vers un autre domaine. Faites glisser le bouton (bascule) pour activer cette option si vous souhaitez que `sessionId` soit automatiquement inclus dans la redirection. Cette option est requise uniquement lorsque vous testez des clics depuis un e-mail ou des clics depuis un domaine vers un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

     Si vous utilisez la configuration des cookies propriétaires et tiers, il n’est pas nécessaire de transmettre l’ID de session mbox lors du changement de domaine. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

1. Cliquez sur **[!UICONTROL Créer]**.

>[!IMPORTANT]
>
>Adressez-vous à votre consultant en implémentation avant de lancer ces tests.

## Utilisation des offres de redirection dans les activités

Appliquez des offres de redirection à l’aide du [[!UICONTROL compositeur d’expérience d’après les formulaires]](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez actuellement pas appliquer d’offres de redirection à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC).

Le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience d’après les formulaires] est une interface de création d’offres et d’expériences non visuelles qui est utile pour créer des expériences à utiliser dans des activités de [!UICONTROL tests A/B], [!UICONTROL ciblage d’expérience] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL recommandations] lorsque le [!UICONTROL compositeur d’expérience visuelle] n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le [!UICONTROL Compositeur d’expérience d’après les formulaires] pour créer des expériences qui utilisent des offres de redirection.

1. Créez ou modifiez une activité dans le [!UICONTROL Compositeur d’expérience d’après les formulaires].

   Consultez [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées.

1. Spécifiez l’emplacement souhaité et ajoutez des améliorations d’audience si nécessaire.

1. Cliquez sur la liste déroulante **[!UICONTROL Contenu]**, sur l&#39;icône **[!UICONTROL Liste]** ( ![Liste](/help/main/assets/icons/MoreSmallList.svg) ), puis sur **[!UICONTROL Modifier l&#39;offre de redirection]**.
1. Sélectionnez l’offre de redirection souhaitée dans la boîte de dialogue [!UICONTROL Sélectionner l’offre de redirection], puis cliquez sur **[!UICONTROL Ajouter]**.
1. Terminez la configuration de l’activité.
