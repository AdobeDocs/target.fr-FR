---
keywords: automated personalization;offre;reporting;groupe;groupe de rapports;ap
description: Découvrez comment utiliser les groupes de génération de rapports d’offres dans les activités  [!DNL Adobe Target] [!UICONTROL Automated Personalization].
title: Puis-je utiliser des groupes de génération de rapports d’offres dans des activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 15%

---

# Offrir des groupes de génération de rapports dans [!UICONTROL Automated Personalization]

Informations sur l’utilisation des groupes de génération de rapports dans [!DNL Adobe Target] activités [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Les groupes de génération de rapports effectuent deux fonctions clés :

* Les groupes de rapports vous permettent de voir vos offres regroupées dans les rapports d’activité AP.
* Les groupes de génération de rapports jouent un rôle clé dans le fonctionnement des modèles de personnalisation [!DNL Target].

Lorsque vous utilisez des groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque groupe de génération de rapports à l’aide des données de toutes les offres de ce groupe. Sans groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque offre de votre activité AP.

Si votre configuration d’activité ne contient pas suffisamment de données pour qu’un modèle de personnalisation soit créé par offre, les groupes de rapports permettent de réduire les exigences en matière de données pour utiliser [!UICONTROL Automated Personalization]. Les groupes de génération de rapports permettent également de résoudre le problème de « démarrage à froid » pour les nouvelles offres en regroupant les offres similaires, de sorte que chaque modèle obtienne davantage de données avec lesquelles se former. Les groupes de modélisation peuvent également être utilisés pour les activités dans lesquelles de nouvelles offres sont introduites régulièrement dans votre activité AP.

Cette approche fonctionne bien si les visiteurs répondent de la même manière à toutes les offres d’un groupe. La bonne pratique consiste à regrouper les offres auxquelles des groupes similaires de visiteurs répondent de la même manière. En d’autres termes, les offres de groupe présentant des taux de conversion similaires. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports. Le regroupement de toutes les offres ou le regroupement d’offres avec des taux de conversion différents réduit probablement l’efficacité des modèles de personnalisation [!DNL Target].

>[!NOTE]
>
>Si une offre est supprimée ou remplacée à partir d’un groupe de modélisation spécifique, le trafic historique qui a vu cette offre spécifique est également supprimé du groupe de modélisation. En d’autres termes, les offres supprimées ne contribuent pas aux données utilisées pour les modèles de personnalisation [!DNL Target] à apprendre.

## Configurer des groupes de génération de rapports

1. Sur la page de **[!UICONTROL Experiences]** d’une activité AP, cliquez sur l’icône **[!UICONTROL Manage Content]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) )
1. Cliquez sur l’onglet **[!UICONTROL Offers]** en haut de la boîte de dialogue [!UICONTROL Manage Content].
1. (Conditionnel) Ajoutez des expériences spécifiques à un groupe de rapports en cliquant sur l’icône [!UICONTROL More Actions] ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) pour l’offre souhaitée, puis sur **[!UICONTROL Reporting Group]**.

1. (Conditionnel) Le lot inclut des expériences dans un groupe de rapports en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur **[!UICONTROL Reporting Group]** au bas de la boîte de dialogue.

1. Pour affecter l’offre sélectionnée à un groupe de rapports existant, sélectionnez **[!UICONTROL Existing]**, sélectionnez le groupe de rapports de votre choix dans la liste déroulante, puis cliquez sur **[!UICONTROL Confirm]**.

   Ou

   Pour créer un groupe de rapports auquel affecter l’offre sélectionnée, sélectionnez **[!UICONTROL New]**, nommez le nouveau groupe de rapports, puis cliquez sur **[!UICONTROL Confirm]**.

Vous pouvez utiliser la liste [!UICONTROL Location] pour filtrer les offres par emplacement. Utilisez la liste [!UICONTROL Report Group] pour filtrer les offres par groupe de rapports. Vous pouvez également utiliser la liste [!UICONTROL Report Group] pour filtrer les [!UICONTROL Unassigned Offers] afin d’affecter un groupe de génération de rapports à une offre qui n’est actuellement affectée à aucun groupe de génération de rapports.

Pour plus d’informations sur le ciblage d’une offre vers des audiences spécifiques, voir [Cibler [!UICONTROL Automated Personalization] offres](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avertissements

* Il est important de comprendre que les groupes de création de rapports influencent la manière dont [!DNL Target] crée ses modèles. Par conséquent, [!DNL Adobe] vous recommande d’utiliser les groupes de génération de rapports uniquement si vous prévoyez de remplacer ou d’ajouter de nouvelles offres pendant qu’une activité est active. Si une nouvelle offre est introduite dans une activité active, la mise en groupe de la nouvelle offre avec des offres similaires existantes permet à la machine d’utiliser les données déjà collectées pour les autres offres de son groupe afin d’en savoir plus sur la nouvelle offre. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports.

* Les activités AP combinent emplacement et offre (variables modèles). Lorsque [!DNL Target] enregistre des données dans des rapports, [!DNL Target] prend en compte ces combinaisons afin de déterminer clairement de quel événement (affichage, clic, etc.) l’offre provient.

  Par exemple, une activité peut avoir plusieurs emplacements et plusieurs offres qui peuvent se chevaucher. Si un visiteur voit plusieurs de ces offres à différents emplacements, [!DNL Target] enregistre les données relatives à ces offres uniquement. Si le même visiteur clique ultérieurement sur une offre, [!DNL Target] enregistre un événement de cette combinaison uniquement (pas pour toutes les combinaisons).

  De même, si le clic provient d’un autre emplacement, présent dans une mesure, mais n’affiche pas d’offre, cet événement est enregistré sous l’activité, mais pas pour toute combinaison offre + emplacement. Par conséquent, cette offre n’apparaît pas dans le groupe de génération de rapports d’offre.

  Ce comportement est dû au fait que le clic peut être effectué à partir d’une mbox différente et non de la mbox qui a diffusé l’offre. Pour cette raison, la mesure est associée à l’activité, mais pas à l’offre.

## Afficher les offres dans un groupe de génération de rapports

1. Cliquez sur **[!UICONTROL Activities]**, puis sur l&#39;activité de [!UICONTROL Automated Personalization] souhaitée dans la liste, et enfin sur l&#39;onglet **[!UICONTROL Reports]** pour afficher le rapport [Niveau de l&#39;offre](/help/main/c-reports/personalization-reports/reports-ap.md).

   Si vous disposez de nombreuses activités, cliquez sur l’icône [!UICONTROL Show Filters] (entonnoir), puis cochez la case [!UICONTROL Automated Personalization] pour filtrer la liste afin de n’afficher que les activités [!UICONTROL Automated Personalization].

1. Cliquez sur **[!UICONTROL Control]** ou **[!UICONTROL Targeted]** dans le tableau pour afficher les offres non regroupées et les offres à l&#39;intérieur des groupes de génération de rapports.

   ![Groupes d’offres : contrôle et ciblé](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Pour plus d’informations sur l’utilisation des rapports [!UICONTROL Automated Personalization] (y compris le rapport [!UICONTROL Offer Level]), consultez [Rapports de synthèse d’Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
