---
keywords: optimisation;personnalisation;adobe parcours optimizer;ajo;cas d’utilisation;scénarios;changement de contenu/test ab;attribut de profil;modifier l’image;permuter l’image
description: Déverrouillez les secrets pour effectuer des tests A/B efficaces sur les modifications de contenu dans Adobe Journey Optimizer
title: Modifications de contenu par le biais de tests A/B dans  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b66abe9649f8c257891c1cd8e5736b7f91501c13
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# Modifications de contenu par le biais de tests A/B dans [!DNL Adobe Journey Optimizer]

Ce cas d’utilisation vous aide à déverrouiller les secrets pour des modifications de contenu de test A/B efficaces dans [!DNL Adobe Journey Optimizer].

Ce cas d’utilisation montre comment effectuer des tâches familières, telles que des tests A/B avec une activité de test [A/B](/help/main/c-activities/t-test-ab/test-ab.md) dans [!DNL Adobe Target], en utilisant [!DNL Journey Optimizer] au lieu de [!DNL Adobe Target].

## Avantages et valeur

* **Optimiser l’efficacité du contenu** : découvrez les variations et les éléments de contenu qui interpellent le plus vos clients, ce qui entraîne une augmentation de l’engagement et des conversions.
* **Décisions axées sur les données** : utilisez les données pour prendre des décisions éclairées dans l’ensemble de votre stratégie de contenu, en garantissant un impact maximal.
* **Expérience utilisateur personnalisée** : personnalisez le contenu pour répondre aux préférences et besoins uniques de tous les segments de votre audience.

## Scénarios possibles

* Une société de vêtements a augmenté les conversions en testant diverses images et en personnalisant les pages de destination de la campagne avec les prénoms des utilisateurs dans le texte de call-to-action.

* Une société de commerce électronique a constaté que ses membres fidèles Gold affichaient des taux de conversion plus élevés en testant diverses descriptions de produits et images sur une page de destination de campagne, ce qui a entraîné une augmentation des ventes.

## Étapes

>[!NOTE]
>
>Les instructions de cette section mettent en évidence les étapes nécessaires pour modifier une image et utiliser les attributs de profil pour personnaliser les messages texte. Pour plus d’informations sur les options disponibles dans le concepteur web [!DNL Journey Optimizer], consultez [Utilisation du concepteur web](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} dans la documentation de *Journey Optimizer*.
>
>La vidéo au bas de la page est particulièrement utile.

Pour optimiser une page web en testant diverses images et en personnalisant les messages avec les prénoms des utilisateurs à l’aide d’un script de profil :

1. Dans [!DNL Journey Optimizer], cliquez sur **Campagnes** dans le rail de gauche pour afficher la page [!UICONTROL Campaigns].

1. Cliquez sur **[!UICONTROL Create Campaign]** dans le coin supérieur droit de la page [!UICONTROL Campaigns].

1. Sélectionnez **[!UICONTROL Scheduled - Marketing]** (valeur par défaut), puis cliquez sur **Créer** pour afficher la page des détails du [!UICONTROL Campaign].

1. Dans la section **[!UICONTROL Properties]** , saisissez un nom explicite et une description facultative pour la campagne.

1. (Conditionnel) Dans la section **[!UICONTROL Audience]**, cliquez sur **[!UICONTROL Select Audience]** et sélectionnez l’audience souhaitée.

   Pour ce cas pratique, vous pouvez activer la campagne pour [!UICONTROL All Visitors] (valeur par défaut).

1. Dans la section **[!UICONTROL Action]** , choisissez **[!UICONTROL Web]** dans la liste déroulante **[!UICONTROL Action]** , puis sélectionnez ou créez une configuration web.

   Une configuration web, ou surface de canal, est une configuration définie par un administrateur système. La configuration web contient tous les paramètres techniques pour l’envoi du message, tels que le paramètre d’en-tête, le sous-domaine, les applications mobiles, etc.

   Pour plus d’informations, voir [Configuration des surfaces de canal](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} dans la documentation de Journey Optimizer **.

1. Dans la section **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Edit Content]** pour ouvrir votre site web dans le concepteur web [!DNL Journey Optimizer].

   Deux expériences ou plus sont nécessaires pour les tests A/B. Vous pouvez utiliser votre page d’accueil existante comme première expérience. Les étapes suivantes expliquent comment configurer une deuxième expérience.

   ![Page de destination du yoga sur le site web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Pour créer une expérience afin de déterminer le contenu le plus performant, cliquez sur **[!UICONTROL Create Experiment]**.

   Les expériences de contenu vous permettent de varier le contenu, l’objet ou l’expéditeur du message afin de définir plusieurs traitements et de déterminer la meilleure combinaison pour vos audiences. Pour plus d’informations, consultez [Création d’une expérience de contenu](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} dans la documentation de *Journey Optimizer*.

1. Sélectionnez une mesure de succès et cliquez sur l’action.

   Cliquez sur les icônes d’aide pour obtenir plus d’informations et des liens vers des articles pertinents.

1. Cliquez sur **[!UICONTROL Add Treatment]**, puis sur **[!UICONTROL Create]**.

   Pour ce cas d’utilisation, vous pouvez laisser la distribution à 50 % pour chaque expérience.

1. Sur la page des détails du [!UICONTROL Campaign], sous **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Edit Content]**.

1. Cliquez sur Web sous Traitement B.

   Pour ce cas d’utilisation, ne modifiez [!UICONTROL Treatment A] pour utiliser l’expérience d’origine comme première expérience dans le test A/B.

1. Cliquez sur **[!UICONTROL Edit Web Page]** dans le rail de droite.

   ![Modifier la page de contenu sur la page de destination Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Pour modifier l’image principale, cliquez sur l’image à modifier, puis sur le bouton **[!UICONTROL Choose Image]** .

   ![Bouton Choisir une image](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Recherchez et sélectionnez l’image souhaitée, puis cliquez sur **[!UICONTROL Use This Image]**.

   ![Nouvelle image de héros sur la page Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Pour personnaliser le message avec les prénoms des utilisateurs à l’aide d’attributs de profil, cliquez sur le texte à personnaliser, puis cliquez sur **[!UICONTROL Add Personalization]** pour afficher la page [!UICONTROL Add Personalization].

   ![Bouton Ajouter Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Pour plus d’informations sur les attributs de profil, voir [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la documentation de *Journey Optimizer*.

1. Recherchez et cliquez sur le signe plus pour ajouter l’attribut de profil « prénom », ajustez le texte selon vos besoins, puis cliquez sur **[!UICONTROL Save]**.

   ![Ajouter un attribut de profil pour le nom](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Pour plus d’informations, consultez [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la documentation de *Journey Optimizer*.

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
>&#x200B;>[Créez une campagne &#x200B;](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} dans les *tutoriels Journey Optimizer*
