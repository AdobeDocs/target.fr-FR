---
keywords: automated personalization;offre;reporting;groupe;groupe de rapports;ap
description: Découvrez comment utiliser les groupes de génération de rapports d’offre dans les activités  [!DNL Adobe Target] .
title: Puis-je utiliser les groupes de génération de rapports d’offres dans les activités  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 25%

---

# Offrir des groupes de génération de rapports dans 

Informations sur l’utilisation des groupes de génération de rapports dans [!DNL Adobe Target] activités [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Les groupes de génération de rapports effectuent deux fonctions clés :

* Les groupes de rapports vous permettent de voir vos offres regroupées dans les rapports d’activité AP.
* Les groupes de génération de rapports jouent un rôle clé dans le fonctionnement des modèles de personnalisation [!DNL Target].

Lorsque vous utilisez des groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque groupe de génération de rapports à l’aide des données de toutes les offres de ce groupe. Sans groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque offre de votre activité AP.

Si la configuration de votre activité ne contient pas suffisamment de données pour qu’un modèle de personnalisation soit créé par offre, les groupes de rapports permettent de réduire les exigences en matière de données pour utiliser . Les groupes de génération de rapports permettent également de résoudre le problème de « démarrage à froid » pour les nouvelles offres en regroupant les offres similaires, de sorte que chaque modèle obtienne davantage de données avec lesquelles se former. Les groupes de modélisation peuvent également être utilisés pour les activités dans lesquelles de nouvelles offres sont introduites régulièrement dans votre activité AP.

Cette approche fonctionne bien si les visiteurs répondent de la même manière à toutes les offres d’un groupe. La bonne pratique consiste à regrouper les offres auxquelles des groupes similaires de visiteurs répondent de la même manière. En d’autres termes, les offres de groupe présentant des taux de conversion similaires. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports. Le regroupement de toutes les offres ou le regroupement d’offres avec des taux de conversion différents réduit probablement l’efficacité des modèles de personnalisation [!DNL Target].

>[!NOTE]
>
>Si une offre est supprimée ou remplacée à partir d’un groupe de modélisation spécifique, le trafic historique qui a vu cette offre spécifique est également supprimé du groupe de modélisation. En d’autres termes, les offres supprimées ne contribuent pas aux données utilisées pour les modèles de personnalisation [!DNL Target] à apprendre.

## Configurer des groupes de génération de rapports

1. Sur la page **[!UICONTROL Expériences]** d’une activité AP, cliquez sur l’icône **[!UICONTROL Gérer le contenu]**.

   ![Icône Gérer le contenu](/help/main/c-reports/assets/ap_manage_content.png)

1. Cliquez sur l’onglet **[!UICONTROL Offres]** dans la partie supérieure de la boîte de dialogue [!UICONTROL Gérer le contenu].
1. (Conditionnel) Ajoutez des expériences spécifiques à un groupe de génération de rapports en faisant glisser le curseur sur l’offre souhaitée, puis en cliquant sur l’icône de dossier **[!UICONTROL Groupe de génération de rapports]**.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Conditionnel) Le lot inclut des expériences dans un groupe de rapports en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur l’icône de dossier **[!UICONTROL Groupe de rapports]** dans le coin supérieur droit de la boîte de dialogue.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Pour attribuer l’offre sélectionnée à un groupe de génération de rapports existant, sélectionnez **[!UICONTROL Existant]**, sélectionnez le groupe de génération de rapports voulu dans la liste déroulante, puis cliquez sur **[!UICONTROL Appliquer]**.

   OU

   Pour créer un groupe de rapports auquel affecter l’offre sélectionnée, sélectionnez **[!UICONTROL Nouveau]**, nommez le nouveau groupe de rapports, puis cliquez sur **[!UICONTROL Appliquer]**.

   ![Nouvelle icône pour créer un groupe de rapports](/help/main/c-reports/assets/ap_reporting_groups.png)

Vous pouvez utiliser la liste [!UICONTROL Emplacement] pour filtrer les offres par emplacement. Utilisez la liste [!UICONTROL Groupe de rapports] pour filtrer les offres par groupe de génération de rapports. Vous pouvez également utiliser la liste [!UICONTROL Groupe de rapports] pour filtrer les [!UICONTROL Offres non assignées] et ainsi assigner un groupe de génération de rapports à une offre jusque là assignée à aucun groupe.

Pour plus d’informations sur le ciblage d’une offre vers des audiences spécifiques, consultez [Cibler les offres [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avertissements

* Il est important de comprendre que les groupes de création de rapports influencent la manière dont [!DNL Target] crée ses modèles. Par conséquent, [!DNL Adobe] vous recommande d’utiliser les groupes de génération de rapports uniquement si vous prévoyez de remplacer ou d’ajouter de nouvelles offres pendant qu’une activité est active. Si une nouvelle offre est introduite dans une activité active, la mise en groupe de la nouvelle offre avec des offres similaires existantes permet à la machine d’utiliser les données déjà collectées pour les autres offres de son groupe afin d’en savoir plus sur la nouvelle offre. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports.

* Les activités AP combinent emplacement et offre (variables modèles). Lorsque [!DNL Target] enregistre des données dans des rapports, [!DNL Target] prend en compte ces combinaisons afin de déterminer clairement de quel événement (affichage, clic, etc.) l’offre provient.

  Par exemple, une activité peut avoir plusieurs emplacements et plusieurs offres qui peuvent se chevaucher. Si un visiteur voit plusieurs de ces offres à différents emplacements, [!DNL Target] enregistre les données relatives à ces offres uniquement. Si le même visiteur clique ultérieurement sur une offre, [!DNL Target] enregistre un événement de cette combinaison uniquement (pas pour toutes les combinaisons).

  De même, si le clic provient d’un autre emplacement, présent dans une mesure, mais n’affiche pas d’offre, cet événement est enregistré sous l’activité, mais pas pour toute combinaison offre + emplacement. Par conséquent, cette offre n’apparaît pas dans le groupe de génération de rapports d’offre.

  Ce comportement est dû au fait que le clic peut être effectué à partir d’une mbox différente et non de la mbox qui a diffusé l’offre. Pour cette raison, la mesure est associée à l’activité, mais pas à l’offre.

## Afficher les offres dans un groupe de génération de rapports

1. Cliquez sur **[!UICONTROL Activités]**, cliquez sur l’activité [!UICONTROL Automated Personalization] souhaitée dans la liste, puis cliquez sur l’onglet **[!UICONTROL Rapports]** pour afficher le rapport [Niveau de l’offre](/help/main/c-reports/personalization-reports/reports-ap.md).

   Si vous avez de nombreuses activités, cliquez sur l’icône [!UICONTROL Afficher les filtres] (funnel), puis cochez la case [!UICONTROL Automated Personalization] pour filtrer la liste afin d’afficher uniquement les activités [!UICONTROL Automated Personalization].

1. Cliquez sur **[!UICONTROL Contrôle]** ou **[!UICONTROL Ciblé]** dans le tableau pour afficher les offres et les offres non groupées dans les groupes de génération de rapports.

   ![Groupes d’offres : contrôle et ciblé](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Pour plus d’informations sur l’utilisation des rapports  (y compris le rapport [!UICONTROL Offer Level]), consultez [Rapports de synthèse d’Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


