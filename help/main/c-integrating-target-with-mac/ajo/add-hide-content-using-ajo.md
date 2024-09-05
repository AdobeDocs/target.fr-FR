---
keywords: optimisation;personnalisation;adobe parcours optimizer;ajo;cas d’utilisation;scénarios;ajouter du contenu;masquer du contenu;ajouter des composants;masquer des composants
description: Découvrez comment ajouter ou masquer des composants sur votre page web à l’aide de  [!DNL Adobe Journey Optimizer].
title: Ajouter ou masquer des composants à votre page web dans [!DNL Adobe Journey Optimizer]
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 000c41efa783889bcb2af20c84956411f73baf40
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---

# Ajouter ou masquer des composants dans votre page web

Ce cas pratique vous aide à déverrouiller les secrets pour les modifications de contenu de test A/B efficaces dans [!DNL Adobe Journey Optimizer].

Ce cas pratique montre comment effectuer des tâches courantes, telles que des tests A/B avec une [activité de test A/B](/help/main/c-activities/t-test-ab/test-ab.md), en utilisant [!DNL Journey Optimizer] au lieu de [!DNL Adobe Target].

Ce cas pratique est conçu pour démontrer comment exécuter des tâches courantes que vous avez pu effectuer à l’aide de [!DNL Adobe Target], de tests A/B à l’aide d’une [ activité de test A/B](/help/main/c-activities/t-test-ab/test-ab.md), mais en utilisant [!DNL Journey Optimizer].

## Avantages et valeur

* **Améliorer l’engagement des utilisateurs** : capturez l’attention des utilisateurs grâce à une conception de page optimisée qui met en évidence des informations pertinentes, telles que les promotions.
* **Améliorer la capacité de découverte** : placez de manière stratégique de nouveaux composants ou contenus sur les applications web ou mobiles pour rationaliser les actions et améliorer la navigation.
* **Augmenter les points de contact supplémentaires** : orientez efficacement les utilisateurs vers les événements de conversion et les objectifs pour accélérer l’impact sur l’entreprise.

## Scénarios possibles

* Une société de services financiers prévoit d’ajouter une nouvelle mosaïque sur sa page d’accueil pour un accès rapide au calculateur de prêt, ce qui réduit le temps de recherche et augmente les demandes de prêt.

* Une société de vêtements a augmenté les conversions en ajoutant un nouveau bouton d’appel à l’action sur sa page web.

## Étapes

>[!NOTE]
>
>Les instructions de cette section mettent en évidence les étapes nécessaires pour modifier une image et utiliser les attributs de profil pour personnaliser les messages texte. Pour plus d’informations sur les options disponibles dans le concepteur web [!DNL Journey Optimizer], voir [Modifier le contenu web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} dans la *documentation Journey Optimizer*.
>
>La vidéo située en bas de la page est particulièrement utile.

Effectuez les étapes suivantes pour ajouter des composants ou masquer des composants sur votre page web :

1. Dans [!DNL Adobe Journey Optimizer], cliquez sur **Campagnes** dans le rail de gauche pour afficher la page [!UICONTROL Campaigns].

   ![Page d’entrée Adobe Journey Optimizer avec l’onglet Campagnes surligné.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Cliquez sur **[!UICONTROL Create Campaign]** dans le coin supérieur droit de la page [!UICONTROL Campaigns].

1. Sélectionnez **[!UICONTROL Scheduled - Marketing]** (valeur par défaut), puis cliquez sur **Créer** pour afficher la page de détails [!UICONTROL Campaign].

   ![Page Détails de la campagne dans Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. Dans la section **[!UICONTROL Properties]** , indiquez un nom descriptif et une description facultative de la campagne.

1. (Conditionnel) Dans la section **[!UICONTROL Audience]** , cliquez sur **[!UICONTROL Select Audience]** et sélectionnez l’audience souhaitée.

   Pour ce cas d’utilisation, vous pouvez activer la campagne pour [!UICONTROL All Visitors] (valeur par défaut).

1. Dans la section **[!UICONTROL Action]** , sélectionnez **[!UICONTROL Web]** dans la liste déroulante **[!UICONTROL Action]** , puis sélectionnez ou créez une configuration web.

   Une configuration web, ou surface de canal, est une configuration définie par un administrateur système. La configuration web contient tous les paramètres techniques pour l’envoi du message, tels que le paramètre d’en-tête, le sous-domaine, les applications mobiles, etc.

   Pour plus d’informations, voir [Configuration des surfaces de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} dans la *documentation de Journey Optimizer*.

1. Dans la section **[!UICONTROL Action]** , cliquez sur **[!UICONTROL Edit Content]** pour ouvrir votre site web dans le concepteur web [!DNL Journey Optimizer].

   ![Landing page Yoga sur le site web LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Pour ajouter un bouton d’appel à l’action, cliquez sur **[!UICONTROL Edit Web Page]** dans le rail de droite.

1. Cliquez sur le bouton

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