---
keywords: Objectif et paramètres;objectif;priorité;durée
description: Découvrez comment utiliser les paramètres d’activité dans Adobe  [!DNL Target]  gérer l’objectif, la priorité et la durée de vos activités.
title: Comment Spécifier Les Paramètres D’Activité ?
feature: Activities
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
TQID: https://experienceleague.adobe.com/tCKQJJOfsU1XkeHwFHNF33XP4tYvxlE0Hv01u0CBr7o
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 432
ht-degree: 77%

---

# Paramètres d’activité

Utilisez les [!UICONTROL &#x200B; Paramètres d’activité &#x200B;] dans [!DNL Adobe Target] pour gérer l’objectif, la priorité et la durée de vos activités.

1. Saisissez des remarques sur l’objectif de l’activité.

   Entrez des informations sur l’activité qui soient utiles pour vous et d’autres membres de l’équipe. Faites glisser le curseur pour redimensionner le champ [!UICONTROL Objectif].
1. Définissez le niveau de priorité de l’activité.

   En fonction de vos paramètres, l’interface utilisateur et les options pour [!UICONTROL Priorité] peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

   Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

   Si cette option n’est pas activée dans [!UICONTROL Administration] > [!UICONTROL Rapports] (valeur par défaut), spécifiez une priorité : Faible, Medium ou Élevée.

   Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Rapports], puis activez l’option [!UICONTROL Activer les priorités affinées] sur la position « Activé ».

   Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

   * 0 = Faible
   * 999 = Élevé

   Pour les activités créées dans les anciennes versions de [!DNL Target Standard/Premium], la priorité Faible correspond à 0, Moyen à 5 et Élevé à 10. Vous pouvez ajuster ces valeurs si besoin.

   >[!NOTE]
   >
   >Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

1. Définissez la durée de l’activité.

   Vous pouvez activer et désactiver manuellement l’activité ou spécifier une date et une heure pour la diffusion de l’activité. Le contrôle de l’heure utilise une horloge de 24 heures, 00:00 correspondant à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

   >[!NOTE]
   >
   >La planification d’une activité contrôle le créneau de diffusion de l’activité. Toutefois, celle-ci doit être explicitement activée avant qu’elle puisse être diffusée selon la planification spécifiée.

La page [!UICONTROL Objectif et paramètres] comprend d’autres paramètres qui dépendent du type d’activité en cours de création. Pour plus d’informations sur ces paramètres, reportez-vous au type d’activité :

* [Test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Test multivarié](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommandations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Vidéo de formation : Paramètres des activités ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

  >[!VIDEO](https://video.tv.adobe.com/v/17381)
