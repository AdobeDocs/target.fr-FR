---
keywords: personnalisation automatisée;offre;création de rapports;groupe;groupe de génération de rapports;ap
description: Découvrez comment utiliser les groupes de génération de rapports d’offres dans [!DNL Adobe Target] [!UICONTROL Automated Personalization] activités.
title: Puis-je utiliser des groupes de génération de rapports d’offres dans [!UICONTROL Automated Personalization] Activités ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 26%

---

# Offrir des groupes de génération de rapports dans [!UICONTROL Automated Personalization]

Informations sur l’utilisation des groupes de génération de rapports dans [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Les groupes de génération de rapports effectuent deux fonctions clés :

* Les groupes de génération de rapports vous permettent de voir vos offres regroupées dans les rapports d’activité AP.
* Les groupes de génération de rapports jouent un rôle clé dans la manière dont la variable [!DNL Target] fonction de modèles de personnalisation.

Lorsque vous utilisez des groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque groupe de génération de rapports en utilisant les données de toutes les offres de ce groupe. Sans groupe de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque offre de votre activité AP.

Si la configuration de votre activité ne dispose pas de suffisamment de données pour qu’un modèle de personnalisation soit créé par offre, les groupes de génération de rapports réduisent les exigences de données à utiliser. [!UICONTROL Automated Personalization]. Les groupes de génération de rapports permettent également de résoudre le problème de « démarrage à froid » pour les nouvelles offres en regroupant les offres similaires, de sorte que chaque modèle obtienne davantage de données avec lesquelles se former. Les groupes de modélisation peuvent également être utilisés pour les activités où de nouvelles offres sont introduites régulièrement dans votre activité AP.

Cette approche fonctionne bien si les visiteurs répondent de la même manière à toutes les offres d’un groupe. La bonne pratique consiste à regrouper les offres auxquelles des groupes similaires de visiteurs répondent de la même manière. En d’autres termes, les offres de groupe présentant des taux de conversion similaires. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports. Le regroupement de toutes les offres ou le regroupement d’offres avec des taux de conversion différents réduit probablement l’efficacité de la variable [!DNL Target] modèles de personnalisation.

>[!NOTE]
>
>Si une offre est supprimée ou remplacée à partir d’un groupe de modélisation spécifique, le trafic historique qui a vu cette offre spécifique est également supprimé du groupe de modélisation. En d’autres termes, les offres supprimées ne contribuent pas aux données utilisées pour la variable [!DNL Target] modèles de personnalisation à apprendre.

## Configuration des groupes de génération de rapports

1. Sur le **[!UICONTROL Expériences]** d’une activité AP, cliquez sur **[!UICONTROL Gestion du contenu]** Icône

   ![Icône Gérer le contenu](/help/main/c-reports/assets/ap_manage_content.png)

1. Cliquez sur l’onglet **[!UICONTROL Offres]** dans la partie supérieure de la boîte de dialogue [!UICONTROL Gérer le contenu].
1. (Conditionnel) Ajoutez des expériences spécifiques à un groupe de génération de rapports en faisant glisser le curseur sur l’offre souhaitée, puis en cliquant sur l’icône de dossier **[!UICONTROL Groupe de génération de rapports]**.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Conditionnel) Incluez par lots des expériences dans un groupe de génération de rapports en cochant les cases correspondant aux expériences pertinentes, puis en cliquant sur le bouton **[!UICONTROL Groupe de rapports]** icône de dossier dans le coin supérieur droit de la boîte de dialogue.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Pour attribuer l’offre sélectionnée à un groupe de génération de rapports existant, sélectionnez **[!UICONTROL Existant]**, sélectionnez le groupe de génération de rapports voulu dans la liste déroulante, puis cliquez sur **[!UICONTROL Appliquer]**.

   Ou

   Pour créer un groupe de génération de rapports auquel affecter l’offre sélectionnée, sélectionnez **[!UICONTROL Nouveau]**, nommez le nouveau groupe de génération de rapports, puis cliquez sur **[!UICONTROL Appliquer]**.

   ![Nouvelle icône pour créer un groupe de génération de rapports](/help/main/c-reports/assets/ap_reporting_groups.png)

Vous pouvez utiliser la variable [!UICONTROL Emplacement] liste pour filtrer les offres par emplacement. Utilisez la liste [!UICONTROL Groupe de rapports] pour filtrer les offres par groupe de génération de rapports. Vous pouvez également utiliser la liste [!UICONTROL Groupe de rapports] pour filtrer les [!UICONTROL Offres non assignées] et ainsi assigner un groupe de génération de rapports à une offre jusque là assignée à aucun groupe.

Pour plus d’informations sur le ciblage d’une offre pour des audiences spécifiques, voir [Cible [!UICONTROL Automated Personalization] offres](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avertissements

* Il est important de comprendre que les groupes de génération de rapports affectent la manière dont [!DNL Target] crée ses modèles. Par conséquent, [!DNL Adobe] recommande d’utiliser des groupes de génération de rapports uniquement si vous envisagez de remplacer ou d’ajouter de nouvelles offres lorsqu’une activité est active. Si une nouvelle offre est introduite dans une activité en direct, le fait de la placer dans un groupe avec des offres similaires existantes permet à la machine d’utiliser les données déjà collectées pour les autres offres de son groupe afin d’en savoir plus sur la nouvelle offre. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports.

* Les activités AP comportent des combinaisons de position + offre (modèles). When [!DNL Target] enregistre les données dans les rapports, [!DNL Target] considère ces combinaisons de sorte qu’il soit clair de quel événement (affichage, clic, etc.) l’offre est issue.

  Par exemple, une activité peut avoir plusieurs emplacements et plusieurs offres, qui peuvent se chevaucher. Si un visiteur voit plusieurs de ces offres à des emplacements différents, [!DNL Target] enregistre des données pour ces offres uniquement. Si le même visiteur clique ultérieurement sur une offre, [!DNL Target] enregistre un événement de cette combinaison uniquement (et non pour toutes les combinaisons).

  De même, si le clic provient d’un autre emplacement, qui est présent dans une mesure, mais n’affiche pas d’offre, cet événement est consigné sous l’activité, mais pas pour une combinaison offre+emplacement. Par conséquent, cette offre n’apparaît pas dans le groupe de génération de rapports des offres.

  Ce comportement est dû au fait que le clic peut être effectué à partir d’une autre mbox et non de la mbox qui a servi l’offre. Pour cette raison, la mesure est associée à l’activité, mais pas à l’offre.

## Affichage des offres dans un groupe de génération de rapports

1. Cliquez sur **[!UICONTROL Activités]**, cliquez sur le [!UICONTROL Automated Personalization] dans la liste, puis cliquez sur le bouton **[!UICONTROL Rapports]** pour afficher la variable [Niveau de l’offre](/help/main/c-reports/personalization-reports/reports-ap.md) rapport.

   Si vous avez de nombreuses activités, cliquez sur le bouton [!UICONTROL Afficher les filtres] (entonnoir), puis sélectionnez la variable [!UICONTROL Automated Personalization] pour filtrer la liste à afficher uniquement [!UICONTROL Automated Personalization] activités.

1. Cliquez sur **[!UICONTROL Contrôle]** ou **[!UICONTROL Ciblés]** dans le tableau pour afficher les offres et les offres dissociées au sein des groupes de génération de rapports.

   ![Groupes d’offres : contrôle et ciblage](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Pour plus d’informations sur l’utilisation de [!UICONTROL Automated Personalization] rapports (y compris la variable [!UICONTROL Niveau de l’offre] report), voir [Rapports de synthèse Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


