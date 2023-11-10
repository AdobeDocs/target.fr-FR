---
keywords: période;date de début;date de fin;dates de début/fin;période;emploi du temps target;partage de la semaine;partage de la journée;partage
description: Découvrez comment utiliser les dates et heures de début et de fin pour cibler les utilisateurs qui visitent votre site pendant une période spécifique.
title: Puis-je cibler les visiteurs qui visitent mon site à des moments spécifiques ?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 1081baa170e8ee979562223c0aa760002d4b9c8c
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 43%

---

# Période

Vous pouvez ajouter des dates et heures de début et de fin dans la variable [!DNL Adobe Target] pour cibler les utilisateurs qui visitent votre site au cours d’une période spécifique. Pour créer des schémas récurrents pour le ciblage des audiences, vous pouvez également définir les options Partage de semaine et de journée.

Par exemple, en utilisant la variable [fonctionnalité d’audiences ad hoc combinées](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), vous pouvez cibler les petits consommateurs à l’aide de contenu spécifique pendant les trois jours précédant Noël et de contenu différent après Noël.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Glisser-déposer **[!UICONTROL Période]** dans le volet audience builder.

   ![target_timeframe_dialog image](assets/target_timeframe_dialog.png)

1. Spécifiez la variable [!UICONTROL Début] et [!UICONTROL Fin] dates et heures pour l’audience.

   Laissez la date de début vide pour lancer le ciblage conformément à la planification de l’activité. Laissez la date de fin vide pour poursuivre le ciblage jusqu’aux date et heure de fin de l’activité.

   Vous pouvez également laisser à la fois les dates de début et de fin vides. Cette fonctionnalité vous permet d’utiliser la même audience dans plusieurs activités (sans en faire une copie) tout en contrôlant les dates de début et de fin au niveau de l’activité.

   >[!NOTE]
   >
   >Tenez compte des points suivants :
   >
   >* Le fuseau horaire des dates de début et de fin s’affiche au format GMT +/- NN:NN, où NN:NN correspond à l’écart par rapport au fuseau horaire GMT et se rapporte au fuseau horaire au niveau du compte et non au niveau du visiteur. Par exemple, le fuseau horaire de la Californie s’affiche comme suit : GMT -08:00.
   >
   >* [!DNL Target] les audiences horaires ne prennent pas en compte les modifications de l’heure d’été. Vous devez mettre à jour manuellement les audiences afin de prendre en compte les modifications DST.

1. (Conditionnel) Cliquez sur **[!UICONTROL Fréquence de définition]** pour définir des schémas récurrents, y compris les jours de la semaine et les heures.

   ![Partage de semaine et de journée](assets/week_and_day_parting.png)

   Vous pouvez utiliser [!UICONTROL Fréquence] par exemple, pour afficher une option &quot;Chat Now&quot; aux visiteurs uniquement pendant les jours et heures où votre centre d’appel est en service.

   Sélectionnez un ou plusieurs jours de la semaine, puis définissez les heures de début et de fin. Cliquez sur **[!UICONTROL Ajouter une fréquence]** pour spécifier d’autres modèles, suivant vos besoins.

   >[!NOTE]
   >
   >Le fuseau horaire pour le [!UICONTROL Partage de semaine et de journée] s’affiche au format GMT +/- NN:NN, où NN:NN correspond à l’écart par rapport au fuseau horaire GMT et se rapporte au fuseau horaire au niveau du compte plutôt qu’à celui du visiteur. Par exemple, le fuseau horaire de la Californie pour l’heure d’été du Pacifique s’affiche au format GMT -07:00.

1. (Facultatif) Configurez des règles supplémentaires pour l’audience.

   Si vous le souhaitez, vous pouvez répéter l’étape 5 pour chaque règle.

1. Cliquez sur **[!UICONTROL Terminé]**.

## Vidéo de formation : création d’audiences ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
