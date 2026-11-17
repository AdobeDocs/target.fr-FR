---
keywords: expérience;contrôle;personnalisation automatisée;ciblage automatique
description: Découvrez comment sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une activité de [!UICONTROL ciblage automatique] dans Automated Personalization] (AP) ou [!UICONTROL ciblage automatique[!DNL Adobe Target].
title: Comment puis-je utiliser une expérience spécifique en tant que contrôle dans une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: 'https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 3%
---
# Sélectionner l’expérience de contrôle {#experience-as-control}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment choisir le contrôle d’une activité de **[!UICONTROL Automated Personalization]** ou de **[!UICONTROL ciblage automatique]** et ce qu’il faut prendre en compte lorsque vous utilisez une expérience spécifique comme contrôle.

>[!ENDSHADEBOX]

Vous pouvez sélectionner une expérience diffusée de manière aléatoire ou une expérience spécifique à utiliser comme contrôle lors de la création d’une activité de [**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP) ou de [**[!UICONTROL ciblage automatique]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT). Le trafic de contrôle est acheminé vers les expériences pertinentes en fonction du pourcentage d’affectation du trafic configuré dans l’activité, de sorte que vous puissiez évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle.

Dans un **[!UICONTROL test A/B]** manuel, vous pouvez modifier ce que les rapports affichent comme contrôle, et l’effet élévateur est calculé à partir de cette expérience, car le trafic est diffusé de manière aléatoire à toutes les expériences, quel que soit le contrôle. Dans les activités **[!UICONTROL Automated Personalization]** et **[!UICONTROL Ciblage automatique]**, le contrôle a une incidence sur la manière dont le trafic des visiteurs est diffusé. Choisissez-le avec soin.

Deux options sont disponibles pour le contrôle :

* **Diffusion aléatoire :** le pourcentage de contrôle du trafic diffuse aléatoirement toutes les expériences de l’activité, sans tenir compte du profil du visiteur. Cela fonctionne comme un **[!UICONTROL test A/B]** au sein de votre activité et affiche le taux de conversion non personnalisé de chaque expérience ou offre, ce qui vous aide à analyser les résultats.

* **Expérience spécifique :** Le pourcentage de contrôle du trafic diffuse aléatoirement uniquement cette expérience. Cette option vous permet de comparer le trafic généré par les modèles de personnalisation [!DNL Target] à une expérience spécifique que vous définissez, par exemple, votre page d’accueil par défaut.

## Considérations {#considerations}

Gardez les points suivants à l’esprit lorsque vous utilisez une expérience spécifique comme contrôle :

* Il n’est pas conseillé de modifier l’expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports, même si les rapports plus anciens sont basés sur une autre expérience.

* La suppression de l’expérience de contrôle n’est pas recommandée.

* Il est déconseillé d’ajouter de nombreuses nouvelles offres ou expériences à une activité en direct avec une expérience spécifique, car le contrôle n’est pas conseillé.

* Dans les activités **[!UICONTROL Automated Personalization]**, y compris le ciblage sur l’expérience de contrôle qui pourrait contraindre davantage les personnes pouvant voir que cette expérience n’est pas recommandée.

* Dans les **[!UICONTROL activités Automated Personalization]**, les informations sur l’effet élévateur et le degré de confiance ne sont *pas* disponibles dans le rapport au niveau de l’offre si une expérience spécifique est sélectionnée. En effet, la comparaison du taux de conversion d’une expérience spécifique au taux de conversion d’une offre n’est pas logique en raison de la différence d’unités. Les informations d’effet élévateur et de confiance sont disponibles au niveau du trafic global « ciblé » par rapport au niveau de trafic de « contrôle » pour l’activité, et à tous les niveaux si « aléatoire » est sélectionné comme contrôle. Les informations disponibles dans une activité de **[!UICONTROL ciblage automatique]** sont les mêmes, quel que soit le type de contrôle sélectionné.

* Lorsque vous sélectionnez une expérience spécifique comme contrôle, tout le trafic de contrôle est dirigé vers une seule expérience ou un seul ensemble d’offres. Avec un contrôle aléatoire, le trafic de contrôle est réparti sur le nombre d’expériences ou d’offres dans votre activité. Par conséquent, vous n’avez généralement pas besoin d’autant de trafic pour acheminer vers le contrôle avec une expérience spécifique. 10 % est un bon point de départ.

* Si vous effectuez l’une des opérations suivantes sur une activité active avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l’expérience spécifique sélectionnée précédemment) :

  * Supprimer une expérience.
  * Supprimer un emplacement ou une offre (**[!UICONTROL Automated Personalization]** uniquement).
  * Exclure une expérience manuellement, en supprimant les offres en double ou par le biais d’un groupe d’exclusion (**[!UICONTROL Automated Personalization]** uniquement).


## Définition d’une expérience spécifique comme contrôle {#specify-control}

La spécification d’une expérience spécifique en tant que contrôle donne au trafic personnalisé une expérience connue à comparer, telle que votre expérience par défaut actuelle, dans les rapports de l’activité.

1. Lors de la création ou de la modification d’une activité [**[!UICONTROL Automated Personalization ]**](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity) ou d’une activité de [**[!UICONTROL ciblage automatique]**](/help/main/c-activities/auto-target/create-auto-target.md#create-auto-target-activity), configurez les expériences selon vos besoins.

1. Sur la page **[!UICONTROL Ciblage]** (étape 2 du workflow en trois parties), cliquez sur l’expérience de contrôle pour afficher les options **[!UICONTROL Contrôle]** dans le volet de droite.

   ![Panneau de contrôle](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Dans la liste déroulante **[!UICONTROL Contrôle]**, sélectionnez **[!UICONTROL Expérience aléatoire]** ou sélectionnez l’expérience que vous souhaitez utiliser comme contrôle.

1. Cliquez sur le contrôle **[!UICONTROL Affectation du trafic]**, puis spécifiez l’affectation du trafic pour l’expérience de contrôle et les autres expériences.

   ![Rail d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   Pour un contrôle d’expérience spécifique, 10 à 30 % sont conseillés.

1. Continuez avec la page **[!UICONTROL Objectifs et paramètres]**.

Une fois l’activité activée, ses rapports comparent le trafic personnalisé à l’expérience de contrôle que vous avez sélectionnée. Passez en revue les [considérations](#considerations) avant de modifier une activité active, car certaines modifications réinitialisent automatiquement le contrôle sur des expériences diffusées de manière aléatoire.
