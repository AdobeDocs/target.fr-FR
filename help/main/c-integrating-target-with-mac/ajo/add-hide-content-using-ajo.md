---
keywords: optimisation;personnalisation;adobe parcours optimizer;ajo;cas d’utilisation;scénarios;ajouter du contenu;masquer du contenu;ajouter des composants;masquer des composants
description: Découvrez comment ajouter ou masquer des composants sur votre page web à l’aide de  [!DNL Adobe Journey Optimizer].
title: Ajoutez ou masquez des composants à votre page web dans  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités Beta dans  [!DNL Adobe Target] ?"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
source-git-commit: 122484056e73f8f679312a3e776e623d905701d5
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 2%

---

# Ajouter ou masquer des composants à votre page web

Ce cas d’utilisation vous aide à déverrouiller les secrets pour des modifications de contenu de test A/B efficaces dans [!DNL Adobe Journey Optimizer].

Ce cas pratique montre comment effectuer des tâches familières, telles que des tests A/B avec une activité de test [A/B](/help/main/c-activities/t-test-ab/test-ab.md), en utilisant [!DNL Journey Optimizer] au lieu de [!DNL Adobe Target].

Ce cas d’utilisation est conçu pour montrer comment effectuer des tâches familières que vous avez peut-être effectuées à l’aide de [!DNL Adobe Target], des tests A/B à l’aide d’une activité de test [A/B](/help/main/c-activities/t-test-ab/test-ab.md), mais en utilisant [!DNL Journey Optimizer].

## Avantages et valeur

* **Améliorer l’interaction client** : captez l’attention des utilisateurs et utilisatrices à l’aide d’une conception de page optimisée qui met en évidence les informations pertinentes, telles que les promotions.
* **Améliorer la visibilité** : placez stratégiquement de nouveaux composants ou contenus sur des applications web ou mobiles pour rationaliser les actions et améliorer la navigation.
* **Augmenter les points de contact supplémentaires** : guider efficacement les utilisateurs vers les événements et les objectifs de conversion afin d’accélérer l’impact commercial.

## Scénarios possibles

* Une société de services financiers prévoit d’ajouter une nouvelle vignette sur sa page d’accueil pour accéder rapidement au calculateur de prêt, ce qui réduira le temps de recherche et stimulera les demandes de prêt.

* Une société de vêtements a augmenté les conversions en ajoutant un nouveau bouton call-to-action sur sa page web.

## Étapes

>[!NOTE]
>
>Les instructions de cette section mettent en évidence les étapes nécessaires pour modifier une image et utiliser les attributs de profil pour personnaliser les messages texte. Pour plus d’informations sur les options disponibles dans le concepteur web [!DNL Journey Optimizer], consultez [Utilisation du concepteur web](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} dans la documentation de *Journey Optimizer*.
>
>La vidéo au bas de la page est particulièrement utile.

Pour ajouter des composants ou masquer des composants sur votre page web, procédez comme suit :

1. Dans [!DNL Adobe Journey Optimizer], cliquez sur **Campagnes** dans le rail de gauche pour afficher la page [!UICONTROL Campaigns].

   ![Page de destination Adobe Journey Optimizer avec l’onglet Campagnes en surbrillance.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Cliquez sur **[!UICONTROL Create Campaign]** dans le coin supérieur droit de la page [!UICONTROL Campaigns].

1. Sélectionnez **[!UICONTROL Scheduled - Marketing]** (valeur par défaut), puis cliquez sur **Créer** pour afficher la page des détails du [!UICONTROL Campaign].

   ![Page de détails de la campagne dans Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. Dans la section **[!UICONTROL Properties]** , saisissez un nom explicite et une description facultative pour la campagne.

1. (Conditionnel) Dans la section **[!UICONTROL Audience]**, cliquez sur **[!UICONTROL Select Audience]** et sélectionnez l’audience souhaitée.

   Pour ce cas pratique, vous pouvez activer la campagne pour [!UICONTROL All Visitors] (valeur par défaut).

1. Dans la section **[!UICONTROL Action]** , choisissez **[!UICONTROL Web]** dans la liste déroulante **[!UICONTROL Action]** , puis sélectionnez ou créez une configuration web.

   Une configuration web, ou surface de canal, est une configuration définie par un administrateur système. La configuration web contient tous les paramètres techniques pour l’envoi du message, tels que le paramètre d’en-tête, le sous-domaine, les applications mobiles, etc.

   Pour plus d’informations, voir [Configuration des surfaces de canal](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} dans la documentation de Journey Optimizer **.

1. Dans la section **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Edit Content]** pour ouvrir votre site web dans le concepteur web [!DNL Journey Optimizer].

   ![Page de destination du yoga sur le site web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Pour ajouter un élément masqué, cliquez sur **[!UICONTROL Edit Web Page]** dans le rail de droite.

1. Cliquez sur l’élément à masquer, puis sur le bouton [!UICONTROL Hide] dans le rail de droite.

   Le rail de droite affiche l’option que vous pouvez exécuter sur l’élément sélectionné. Ces options varient en fonction de l’élément sélectionné.

   ![bouton Masquer l’élément](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

1. Cliquez sur la flèche vers l’arrière dans le coin supérieur gauche pour revenir au concepteur web.

   ![Flèche arrière](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Cliquez sur **[!UICONTROL Review to Activate]**, vérifiez que tout se présente comme prévu, puis cliquez sur **Activer**.

## Afficher les rapports

Cliquez sur le bouton [!UICONTROL Reports] , puis sur la période de reporting souhaitée :

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

Pour plus d’informations, consultez [Prise en main de la nouvelle interface de création de rapports](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} dans la documentation de *Journey Optimizer*.

>[!MORELIKETHIS]
>
>[Utiliser le concepteur web](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} dans la documentation de *Journey Optimizer*
>[Créez une campagne &#x200B;](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} dans les *tutoriels Journey Optimizer*
