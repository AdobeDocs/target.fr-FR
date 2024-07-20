---
keywords: personnalisation automatisée;offre;création de rapports;groupe;groupe de génération de rapports;ap
description: Découvrez comment utiliser des groupes de génération de rapports d’offres dans les activités  [!DNL Adobe Target] [!UICONTROL Automated Personalization].
title: Puis-je utiliser des groupes de génération de rapports d’offres dans les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 15%

---

# Offrir des groupes de génération de rapports dans [!UICONTROL Automated Personalization]

Informations sur l&#39;utilisation des groupes de génération de rapports dans les activités [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Les groupes de génération de rapports effectuent deux fonctions clés :

* Les groupes de génération de rapports vous permettent de voir vos offres regroupées dans les rapports d’activité AP.
* Les groupes de génération de rapports jouent un rôle clé dans le fonctionnement des modèles de personnalisation [!DNL Target].

Lorsque vous utilisez des groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque groupe de génération de rapports à l’aide des données de toutes les offres de ce groupe. Sans groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque offre de votre activité AP.

Si la configuration de votre activité ne dispose pas de suffisamment de données pour qu’un modèle de personnalisation soit créé par offre, les groupes de génération de rapports aident à réduire les exigences de données à utiliser [!UICONTROL Automated Personalization]. Les groupes de génération de rapports permettent également de résoudre le problème de « démarrage à froid » pour les nouvelles offres en regroupant les offres similaires, de sorte que chaque modèle obtienne davantage de données avec lesquelles se former. Les groupes de modélisation peuvent également être utilisés pour les activités où de nouvelles offres sont introduites régulièrement dans votre activité AP.

Cette approche fonctionne bien si les visiteurs répondent de la même manière à toutes les offres d’un groupe. La bonne pratique consiste à regrouper les offres auxquelles des groupes similaires de visiteurs répondent de la même manière. En d’autres termes, les offres de groupe présentant des taux de conversion similaires. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports. Le regroupement de toutes les offres ou le regroupement d’offres avec des taux de conversion différents réduit probablement l’efficacité des modèles de personnalisation [!DNL Target].

>[!NOTE]
>
>Si une offre est supprimée ou remplacée à partir d’un groupe de modélisation spécifique, le trafic historique qui a vu cette offre spécifique est également supprimé du groupe de modélisation. En d’autres termes, les offres supprimées ne contribuent pas aux données utilisées pour que les modèles de personnalisation [!DNL Target] puissent apprendre.

## Configuration des groupes de génération de rapports

1. Sur la page **[!UICONTROL Experiences]** d’une activité AP, cliquez sur l’icône **[!UICONTROL Manage Content]**.

   ![Icône Gérer le contenu](/help/main/c-reports/assets/ap_manage_content.png)

1. Cliquez sur l’onglet **[!UICONTROL Offers]** en haut de la boîte de dialogue [!UICONTROL Manage Content].
1. (Conditionnel) Ajoutez des expériences spécifiques à un groupe de génération de rapports en faisant glisser le curseur sur l’offre souhaitée, puis en cliquant sur l’icône de dossier **[!UICONTROL Reporting Group]**.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Conditionnel) Incluez par lots des expériences dans un groupe de génération de rapports en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur l’icône de dossier **[!UICONTROL Reporting Group]** dans le coin supérieur droit de la boîte de dialogue.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Pour attribuer l’offre sélectionnée à un groupe de génération de rapports existant, sélectionnez **[!UICONTROL Existing]**, sélectionnez le groupe de génération de rapports de votre choix dans la liste déroulante, puis cliquez sur **[!UICONTROL Apply]**.

   Ou

   Pour créer un groupe de génération de rapports auquel affecter l’offre sélectionnée, sélectionnez **[!UICONTROL New]**, nommez le nouveau groupe de génération de rapports, puis cliquez sur **[!UICONTROL Apply]**.

   ![Nouvelle icône pour créer un groupe de génération de rapports](/help/main/c-reports/assets/ap_reporting_groups.png)

Vous pouvez utiliser la liste [!UICONTROL Location] pour filtrer les offres par emplacement. Utilisez la liste [!UICONTROL Report Group] pour filtrer les offres par groupes de génération de rapports. Vous pouvez également utiliser la liste [!UICONTROL Report Group] pour filtrer [!UICONTROL Unassigned Offers] afin d’affecter un groupe de génération de rapports à une offre qui n’est actuellement affectée à aucun groupe de génération de rapports.

Pour plus d’informations sur le ciblage d’une offre sur des audiences spécifiques, voir [Offres [!UICONTROL Automated Personalization] Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avertissements

* Il est important de comprendre que les groupes de génération de rapports affectent la manière dont [!DNL Target] crée ses modèles. Par conséquent, [!DNL Adobe] vous recommande d’utiliser les groupes de génération de rapports uniquement si vous prévoyez de remplacer ou d’ajouter de nouvelles offres pendant qu’une activité est active. Si une nouvelle offre est introduite dans une activité en direct, le fait de la placer dans un groupe avec des offres similaires existantes permet à la machine d’utiliser les données déjà collectées pour les autres offres de son groupe afin d’en savoir plus sur la nouvelle offre. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports.

* Les activités AP comportent des combinaisons de position + offre (modèles). Lorsque [!DNL Target] enregistre des données dans les rapports, [!DNL Target] prend en compte de telles combinaisons afin qu’il soit clair à partir de quel événement (affichage, clic, etc.) l’offre est venue.

  Par exemple, une activité peut avoir plusieurs emplacements et plusieurs offres, qui peuvent se chevaucher. Si un visiteur voit plusieurs de ces offres à des emplacements différents, [!DNL Target] n’enregistre que les données de ces offres. Si le même visiteur clique ensuite sur une offre, [!DNL Target] enregistre un événement de cette combinaison uniquement (pas pour toutes les combinaisons).

  De même, si le clic provient d’un autre emplacement, qui est présent dans une mesure, mais n’affiche pas d’offre, cet événement est consigné sous l’activité, mais pas pour une combinaison offre+emplacement. Par conséquent, cette offre n’apparaît pas dans le groupe de génération de rapports des offres.

  Ce comportement est dû au fait que le clic peut être effectué à partir d’une autre mbox et non de la mbox qui a servi l’offre. Pour cette raison, la mesure est associée à l’activité, mais pas à l’offre.

## Affichage des offres dans un groupe de génération de rapports

1. Cliquez sur **[!UICONTROL Activities]**, cliquez sur l’activité [!UICONTROL Automated Personalization] souhaitée dans la liste, puis sur l’onglet **[!UICONTROL Reports]** pour afficher le rapport [Niveau d’offre](/help/main/c-reports/personalization-reports/reports-ap.md).

   Si vous avez beaucoup d&#39;activités, cliquez sur l&#39;icône [!UICONTROL Show Filters] (entonnoir), puis cochez la case [!UICONTROL Automated Personalization] pour filtrer la liste afin de n&#39;afficher que les activités [!UICONTROL Automated Personalization].

1. Cliquez sur **[!UICONTROL Control]** ou **[!UICONTROL Targeted]** dans le tableau pour afficher les offres et les offres non regroupées dans des groupes de génération de rapports.

   ![Groupes d’offres : contrôle et ciblage](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Pour plus d’informations sur l’utilisation des rapports [!UICONTROL Automated Personalization] (y compris le rapport [!UICONTROL Offer Level]), voir [Rapports récapitulatifs Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


