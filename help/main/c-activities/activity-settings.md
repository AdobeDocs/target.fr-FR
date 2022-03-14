---
keywords: Objectif et paramètres;objectif;priorité;durée
description: Découvrez comment utiliser les paramètres d’activité dans Adobe [!DNL Target] pour gérer l’objectif, la priorité et la durée de vos activités.
title: Comment puis-je spécifier les paramètres d’activité ?
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 79%

---

# Paramètres d’activité

Utilisation [!UICONTROL Paramètres d’activité] in [!DNL Adobe Target] pour gérer l’objectif, la priorité et la durée de vos activités.

1. Saisissez des remarques sur l’objectif de l’activité.

   Entrez des informations sur l’activité qui soient utiles pour vous et d’autres membres de l’équipe. Faites glisser le curseur pour redimensionner le champ [!UICONTROL Objectif].
1. Définissez le niveau de priorité de l’activité.

   En fonction de vos paramètres, l’interface utilisateur et les options pour [!UICONTROL Priorité] peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

   Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

   Si cette option n’est pas activée dans [!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : Faible, Moyen ou Élevé.

   Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez la fonction [!UICONTROL Activation des priorités affinées] à la position &quot;Activé&quot;.

   Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

   * 0 = Faible
   * 999 = Élevé

   Pour les activités créées dans les anciennes versions de [!DNL Target Standard/Premium], la priorité Faible correspond à 0, Moyen à 5 et Élevé à 10. Vous pouvez ajuster ces valeurs si besoin.

   >[!NOTE]
   >
   >Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

1. Définissez la durée de l’activité.

   Vous pouvez activer et désactiver manuellement l’activité ou spécifier une date et une heure pour la diffusion de l’activité. La commande de l’heure utilise une horloge de 24 heures (00:00 correspond à minuit). Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

   >[!NOTE]
   >
   >La planification d’une activité contrôle le créneau de diffusion de l’activité. Toutefois, celle-ci doit être explicitement activée avant qu’elle puisse être diffusée selon la planification spécifiée.

La page [!UICONTROL Objectif et paramètres] comprend d’autres paramètres qui dépendent du type d’activité en cours de création. Pour plus d’informations sur ces paramètres, reportez-vous au type d’activité :

* [Test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Test multivarié](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Vidéo de formation : Paramètres d’activité ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

   >[!VIDEO](https://video.tv.adobe.com/v/17381)
