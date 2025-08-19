---
keywords: période;date de début;date de fin;dates de début/fin;période;emploi du temps target;partage de la semaine;partage de la journée;partage
description: Découvrez comment utiliser les dates et heures de début et de fin pour cibler les utilisateurs et utilisatrices qui visitent votre site au cours d’une période spécifique.
title: Puis-Je Cibler Les Visiteurs Et Visiteuses Qui Visitent Mon Site À Des Heures Spécifiques ?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 25%

---

# [!UICONTROL Time Frame]

Vous pouvez ajouter des dates et heures de début et de fin dans [!DNL Adobe Target] pour cibler les utilisateurs et utilisatrices qui visitent votre site au cours d’une période spécifique. Pour créer des schémas récurrents pour le ciblage des audiences, vous pouvez également définir les options Partage de semaine et de journée.

Par exemple, à l’aide de la fonction d’audiences ad hoc [combinées](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), vous pouvez cibler les utilisateurs et utilisatrices qui dépensent peu avec un contenu spécifique au cours des trois jours précédant le Vendredi noir et d’autres contenus après le Vendredi noir.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Faites glisser et déposez **[!UICONTROL Time Frame]** dans le volet du Créateur d’audiences.

   ![image target_timeframe_dialog](assets/target_timeframe_dialog.png)

1. Spécifiez les dates et heures [!UICONTROL Start] et [!UICONTROL End] de l’audience.

   Laissez la date de début vide pour lancer le ciblage conformément à la planification de l’activité. Laissez la date de fin vide pour poursuivre le ciblage jusqu’aux date et heure de fin de l’activité.

   Vous pouvez également laisser à la fois les dates de début et de fin vides. Cette fonctionnalité vous permet d’utiliser la même audience dans plusieurs activités (sans faire de copie de l’audience) tout en contrôlant les dates de début et de fin au niveau de l’activité.

   >[!NOTE]
   >
   >Tenez compte des points suivants :
   >
   >* Le fuseau horaire des dates de début et de fin s’affiche sous la forme GMT +/- NN:NN, où NN:NN correspond au décalage par rapport à GMT et reflète le fuseau horaire au niveau du compte plutôt que le fuseau horaire du visiteur. Par exemple, le fuseau horaire de la Californie s’affiche sous la forme GMT -08:00.
   >
   >* Les audiences d’heure d’[!DNL Target] ne prennent pas en compte les modifications de l’heure d’été. Vous devez réenregistrer manuellement les audiences pour tenir compte des modifications de l’heure d’été.

1. (Conditionnel) Cliquez sur **[!UICONTROL Set frequency]** pour définir des modèles récurrents, y compris les jours des semaines et les heures.

   ![Partage de semaine et de journée](assets/week_and_day_parting.png)

   Vous pouvez utiliser [!UICONTROL Frequency] options, par exemple, pour afficher une option « Chat Now » aux visiteurs et visiteuses uniquement pendant les jours et les heures où votre centre d’appels dispose de personnel.

   Sélectionnez un ou plusieurs jours de la semaine, puis définissez les heures de début et de fin. Cliquez sur **[!UICONTROL Add frequency]** pour spécifier des modèles supplémentaires, selon vos besoins.

   >[!NOTE]
   >
   >Le fuseau horaire de [!UICONTROL Week and Day Parting] s’affiche sous la forme GMT +/- NN:NN, où NN:NN correspond au décalage par rapport à GMT et reflète le fuseau horaire au niveau du compte plutôt que le fuseau horaire du visiteur. Par exemple, le fuseau horaire de la Californie pour l’heure d’été du Pacifique s’affiche sous la forme GMT -07:00.

1. (Facultatif) Configurez des règles supplémentaires pour l’audience.

   Si vous le souhaitez, vous pouvez répéter l’étape 5 pour chaque règle.

1. Cliquez sur **[!UICONTROL Done]**.

## Vidéo de formation : création d’audiences ![badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
