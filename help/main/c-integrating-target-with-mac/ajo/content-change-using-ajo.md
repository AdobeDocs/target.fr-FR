---
keywords: optimisation;personnalisation;adobe parcours optimizer;ajo;cas d’utilisation;scénarios;changement de contenu/test ab;attribut de profil;modifier l’image;permuter l’image
description: Déverrouillez les secrets pour effectuer des tests A/B efficaces sur les modifications de contenu dans Adobe Journey Optimizer
title: Modifications de contenu par le biais de tests A/B dans  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités Beta dans  [!DNL Adobe Target] ?"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
TQID: https://experienceleague.adobe.com/IqNBAHefm8J-DEo2fU-Nj19AhcZg-FUPLccs2eC9yPQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: fc314d1d-7cb9-4a38-8dbd-8f9b6478f40d
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 954
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
>Les instructions de cette section mettent en évidence les étapes nécessaires pour modifier une image et utiliser les attributs de profil pour personnaliser les messages texte. Pour plus d’informations sur les options disponibles dans le concepteur web [!DNL Journey Optimizer], consultez [Utilisation du concepteur web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} dans la documentation de *Journey Optimizer*.
>
>La vidéo au bas de la page est particulièrement utile.

Pour optimiser une page web en testant diverses images et en personnalisant les messages avec les prénoms des utilisateurs à l’aide d’un script de profil :

1. Dans [!DNL Journey Optimizer], cliquez sur **Campagnes** dans le rail de gauche pour afficher la page [!UICONTROL Campagnes].

1. Cliquez sur **[!UICONTROL Créer une campagne]** dans le coin supérieur droit de la page [!UICONTROL Campagnes].

1. Sélectionnez **[!UICONTROL Planifié - Marketing]** (valeur par défaut), puis cliquez sur **Créer** pour afficher la page de détails [!UICONTROL Campagne].

1. Dans la section **[!UICONTROL Propriétés]**, fournissez un nom explicite et une description facultative de la campagne.

1. (Conditionnel) Dans la section **[!UICONTROL Audience]**, cliquez sur **[!UICONTROL Sélectionner une audience]** et choisissez l’audience souhaitée.

   Pour ce cas d’utilisation, vous pouvez activer la campagne pour [!UICONTROL Tous les visiteurs] (valeur par défaut).

1. Dans la section **[!UICONTROL Action]**, choisissez **[!UICONTROL Web]** dans la liste déroulante **[!UICONTROL Action]**, puis sélectionnez ou créez une configuration web.

   Une configuration web, ou surface de canal, est une configuration définie par un administrateur système. La configuration web contient tous les paramètres techniques pour l’envoi du message, tels que le paramètre d’en-tête, le sous-domaine, les applications mobiles, etc.

   Pour plus d’informations, voir [Configuration des surfaces de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} dans la documentation de Journey Optimizer **.

1. Dans la section **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Modifier le contenu]** pour ouvrir votre site web dans le concepteur web [!DNL Journey Optimizer].

   Deux expériences ou plus sont nécessaires pour les tests A/B. Vous pouvez utiliser votre page d’accueil existante comme première expérience. Les étapes suivantes expliquent comment configurer une deuxième expérience.

   ![Page de destination du yoga sur le site web de LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Pour créer une expérience afin de déterminer le contenu le plus performant, cliquez sur **[!UICONTROL Créer une expérience]**.

   Les expériences de contenu vous permettent de varier le contenu, l’objet ou l’expéditeur du message afin de définir plusieurs traitements et de déterminer la meilleure combinaison pour vos audiences. Pour plus d’informations, consultez [Création d’une expérience de contenu](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} dans la documentation de *Journey Optimizer*.

1. Sélectionnez une mesure de succès et cliquez sur l’action.

   Cliquez sur les icônes d’aide pour obtenir plus d’informations et des liens vers des articles pertinents.

1. Cliquez sur **[!UICONTROL Ajouter un traitement]**, puis sur **[!UICONTROL Créer]**.

   Pour ce cas d’utilisation, vous pouvez laisser la distribution à 50 % pour chaque expérience.

1. Sur la page de détails [!UICONTROL Campaign], sous **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Modifier le contenu]**.

1. Cliquez sur Web sous Traitement B.

   Pour ce cas d’utilisation, laissez le [!UICONTROL Traitement A] inchangé afin d’utiliser l’expérience originale comme première expérience dans le test A/B.

1. Cliquez sur **[!UICONTROL Modifier la page web]** dans le rail de droite.

   ![Modifier la page de contenu sur la page de destination Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Pour modifier l’image principale, cliquez sur l’image à modifier, puis sur le bouton **[!UICONTROL Choisir une image]**.

   ![Bouton Choisir une image](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Recherchez et sélectionnez l’image souhaitée, puis cliquez sur **[!UICONTROL Utiliser cette image]**.

   ![Nouvelle image de héros sur la page Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Pour personnaliser le message avec les prénoms des utilisateurs à l’aide d’attributs de profil, cliquez sur le texte à personnaliser, puis cliquez sur **[!UICONTROL Ajouter un Personalization]** pour afficher la page [!UICONTROL Ajouter un Personalization].

   ![Bouton Ajouter Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Pour plus d’informations sur les attributs de profil, voir [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la documentation de *Journey Optimizer*.

1. Recherchez et cliquez sur le signe plus pour ajouter l’attribut de profil « prénom », ajustez le texte selon vos besoins, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![Ajouter un attribut de profil pour le nom](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Pour plus d’informations, consultez [Prise en main de l’éditeur de personnalisation](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} dans la documentation de *Journey Optimizer*.

1. Cliquez sur la flèche vers l’arrière dans le coin supérieur gauche pour revenir au concepteur web.

   ![Flèche arrière](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Cliquez sur **[!UICONTROL Vérifier pour activer]**, vérifiez que tout se présente comme prévu, puis cliquez sur **Activer**.

## Afficher les rapports

Cliquez sur le bouton [!UICONTROL Rapports], puis sur la période de création de rapports souhaitée :

* [!UICONTROL Afficher le rapport à toute heure]
* [!UICONTROL Afficher le rapport des dernières 24 heures]

Pour plus d’informations, consultez [Prise en main de la nouvelle interface de création de rapports](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} dans la documentation de *Journey Optimizer*.

>[!MORELIKETHIS]
>
>[Utiliser le concepteur web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} dans la documentation de *Journey Optimizer*
>[Créer une campagne](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} dans les *tutoriels Journey Optimizer*
