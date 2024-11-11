---
keywords: optimisation;personnalisation;adobe parcours optimizer;ajo;cas d’utilisation;scénarios;changement de contenu/test;attribut de profil;modifier une image;changer une image
description: Déverrouillez les secrets des modifications efficaces du contenu des tests A/B dans Adobe Journey Optimizer.
title: Modifications du contenu par le biais de tests A/B dans  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# Modifications du contenu par le biais de tests A/B dans [!DNL Adobe Journey Optimizer]

Ce cas pratique vous aide à déverrouiller les secrets pour les modifications de contenu de test A/B efficaces dans [!DNL Adobe Journey Optimizer].

Ce cas pratique montre comment effectuer des tâches courantes, telles que des tests A/B avec une [activité de test A/B](/help/main/c-activities/t-test-ab/test-ab.md) dans [!DNL Adobe Target], en utilisant [!DNL Journey Optimizer] au lieu de [!DNL Adobe Target].

## Avantages et valeur

* **Optimiser l’efficacité du contenu** : découvrez les variations et les éléments de contenu qui résonnent le plus chez vos clients, ce qui entraîne un engagement et des conversions plus élevés.
* **Décisions pilotées par les données** : utilisez les données pour prendre des décisions éclairées dans votre stratégie de contenu, ce qui garantit un impact maximum.
* **Expérience utilisateur personnalisée** : personnalisez le contenu pour répondre aux préférences et aux besoins uniques de tous vos segments d’audience.

## Scénarios possibles

* Une société d’habillement a augmenté les conversions en testant diverses images et en personnalisant les landing pages de campagne avec les prénoms des utilisateurs dans le texte d’appel à l’action.

* Une société de commerce électronique a constaté que les membres du programme de fidélité Gold avaient des taux de conversion plus élevés en testant diverses descriptions et images de produits sur une page d’entrée de campagne, ce qui a entraîné une augmentation des ventes.

## Étapes

>[!NOTE]
>
>Les instructions de cette section mettent en évidence les étapes nécessaires pour modifier une image et utiliser les attributs de profil pour personnaliser les messages texte. Pour plus d’informations sur les options disponibles dans le concepteur web [!DNL Journey Optimizer], voir [Modifier le contenu web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} dans la *documentation Journey Optimizer*.
>
>La vidéo située en bas de la page est particulièrement utile.

Pour optimiser une page web en testant différentes images et en personnalisant les messages avec les prénoms des utilisateurs à l’aide d’un script de profil :

1. Dans [!DNL Journey Optimizer], cliquez sur **Campagnes** dans le rail de gauche pour afficher la page [!UICONTROL Campaigns].

1. Cliquez sur **[!UICONTROL Create Campaign]** dans le coin supérieur droit de la page [!UICONTROL Campaigns].

1. Sélectionnez **[!UICONTROL Scheduled - Marketing]** (valeur par défaut), puis cliquez sur **Créer** pour afficher la page de détails [!UICONTROL Campaign].

1. Dans la section **[!UICONTROL Properties]** , indiquez un nom descriptif et une description facultative de la campagne.

1. (Conditionnel) Dans la section **[!UICONTROL Audience]** , cliquez sur **[!UICONTROL Select Audience]** et sélectionnez l’audience souhaitée.

   Pour ce cas d’utilisation, vous pouvez activer la campagne pour [!UICONTROL All Visitors] (valeur par défaut).

1. Dans la section **[!UICONTROL Action]** , sélectionnez **[!UICONTROL Web]** dans la liste déroulante **[!UICONTROL Action]** , puis sélectionnez ou créez une configuration web.

   Une configuration web, ou surface de canal, est une configuration définie par un administrateur système. La configuration web contient tous les paramètres techniques pour l’envoi du message, tels que le paramètre d’en-tête, le sous-domaine, les applications mobiles, etc.

   Pour plus d’informations, voir [Configuration des surfaces de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} dans la *documentation de Journey Optimizer*.

1. Dans la section **[!UICONTROL Action]** , cliquez sur **[!UICONTROL Edit Content]** pour ouvrir votre site web dans le concepteur web [!DNL Journey Optimizer].

   Deux ou plusieurs expériences sont nécessaires pour les tests A/B. Vous pouvez utiliser votre page d’accueil existante comme première expérience. Les étapes suivantes expliquent comment configurer une deuxième expérience.

   ![Landing page Yoga sur le site web LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Pour créer une expérience afin de déterminer quel contenu est le plus performant, cliquez sur **[!UICONTROL Create Experiment]**.

   Les expériences de contenu vous permettent de varier le contenu du message, l’objet ou l’expéditeur afin de définir plusieurs traitements et de déterminer la meilleure combinaison pour vos audiences. Pour plus d’informations, voir [Création d’une expérience de contenu](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} dans la *documentation Journey Optimizer*.

1. Sélectionnez une mesure de succès et cliquez sur l’action.

   Cliquez sur les icônes d’aide pour plus d’informations et des liens vers les articles pertinents.

1. Cliquez sur **[!UICONTROL Add Treatment]**, puis sur **[!UICONTROL Create]**.

   Pour ce cas d’utilisation, vous pouvez laisser la distribution à 50 % pour chaque expérience.

1. Sur la page de détails [!UICONTROL Campaign], sous **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Edit Content]**.

1. Cliquez sur Web sous Traitement B.

   Pour ce cas d’utilisation, ne modifiez pas [!UICONTROL Treatment A] afin d’utiliser l’expérience d’origine comme première expérience dans le test A/B.

1. Cliquez sur **[!UICONTROL Edit Web Page]** dans le rail de droite.

   ![Modifier la page de contenu sur la page d’entrée Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Pour modifier l’image principale, cliquez sur l’image que vous souhaitez modifier, puis cliquez sur le bouton **[!UICONTROL Choose Image]** .

   ![Bouton Choisir l’image](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Recherchez et sélectionnez l’image souhaitée, puis cliquez sur **[!UICONTROL Use This Image]**.

   ![Nouvelle image à forte identification sur la page Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Pour personnaliser le message avec les prénoms des utilisateurs à l’aide des attributs de profil, cliquez sur le texte que vous souhaitez personnaliser, puis cliquez sur **[!UICONTROL Add Personalization]** pour afficher la page [!UICONTROL Add Personalization].

   ![Bouton Ajouter Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Pour plus d’informations sur les attributs de profil, voir [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la *documentation de Journey Optimizer*.

1. Recherchez et cliquez sur le signe plus pour ajouter l’attribut de profil &quot;prénom&quot;, ajustez le texte comme vous le souhaitez, puis cliquez sur **[!UICONTROL Save]**.

   ![Ajouter un attribut de profil pour name](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Pour plus d’informations, voir [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la *documentation de Journey Optimizer*.

1. Cliquez sur la flèche Précédent dans le coin supérieur gauche pour revenir au concepteur web.

   ![Flèche vers l’arrière](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Cliquez sur **[!UICONTROL Review to Activate]**, assurez-vous que tout se présente comme prévu, puis cliquez sur **Activer**.

## Affichage des rapports

Cliquez sur le bouton [!UICONTROL Reports] , puis sur la période de création de rapports souhaitée :

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

Pour plus d’informations, voir [Prise en main de la nouvelle interface de création de rapports](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} dans la *documentation de Journey Optimizer*.

>[!MORELIKETHIS]
>
>[Modifier le contenu web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} dans la *documentation Journey Optimizer*
>[Vidéo pratique ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content#video){target=_blank} dans la *documentation Journey Optimizer*
>[Créez une campagne ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} dans *Journey Optimizer Tutorials*
