---
keywords: personnalisation automatisée;offre;création de rapports;groupe;groupe de génération de rapports;ap
description: Découvrez comment utiliser des groupes de génération de rapports d’offres dans Adobe [!DNL Target] [!UICONTROL Automated Personalization] activités.
title: Puis-je utiliser des groupes de génération de rapports d’offres dans les activités Automated Personalization ?
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 60655a93b515095bd8c67a4af2193d36789ab96e
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 52%

---

# ![PREMIUM](/help/main/assets/premium.png)[!UICONTROL  Groupes de rapports d’offres dans la personnalisation automatisée]

Informations sur l’utilisation des groupes de génération de rapports dans [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Les groupes de génération de rapports effectuent deux fonctions clés :

* Les groupes de génération de rapports vous permettent de voir vos offres regroupées dans les rapports d’activité AP.
* Les groupes de génération de rapports jouent un rôle clé dans la manière dont la variable [!DNL Target] fonction de modèles de personnalisation.

Lorsque vous utilisez des groupes de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque groupe de génération de rapports en utilisant les données de toutes les offres de ce groupe. Sans groupe de génération de rapports, [!DNL Target] crée un modèle de personnalisation pour chaque offre de votre activité AP.

Si la configuration de votre activité ne dispose pas de suffisamment de données pour qu’un modèle de personnalisation soit créé par offre, les groupes de génération de rapports peuvent contribuer à réduire les exigences de données à utiliser. [!UICONTROL Automated Personalization]. Les groupes de génération de rapports permettent également de résoudre le problème de « démarrage à froid » pour les nouvelles offres en regroupant les offres similaires, de sorte que chaque modèle obtienne davantage de données avec lesquelles se former. Les groupes de modélisation peuvent également être utilisés pour les activités où de nouvelles offres sont introduites régulièrement dans votre activité AP.

Cette approche fonctionne bien si les visiteurs répondent de la même manière à toutes les offres d’un groupe. La bonne pratique consiste à regrouper les offres auxquelles des groupes similaires de visiteurs répondent de la même manière. En d’autres termes, les offres de groupe présentant des taux de conversion similaires. Il convient de ne jamais placer toutes les offres dans un seul groupe de génération de rapports. Le regroupement de toutes les offres ou le regroupement d’offres avec des taux de conversion très différents réduit probablement l’efficacité de la variable [!DNL Target] modèles de personnalisation.

>[!NOTE]
>
>Si une offre est supprimée ou remplacée à partir d’un groupe de modélisation spécifique, le trafic historique qui a vu cette offre spécifique est également supprimé du groupe de modélisation. En d’autres termes, les offres supprimées ne contribuent pas aux données utilisées pour la variable [!DNL Target] modèles de personnalisation à apprendre.

**Pour configurer des groupes de génération de rapports** :

1. Sur le **[!UICONTROL Expériences]** d’une activité AP, cliquez sur **[!UICONTROL Gestion du contenu]** icône .

   ![Icône Gérer le contenu](/help/main/c-reports/assets/ap_manage_content.png)

1. Cliquez sur l’onglet **[!UICONTROL Offres]** dans la partie supérieure de la boîte de dialogue [!UICONTROL Gérer le contenu].
1. (Conditionnel) Ajoutez des expériences spécifiques à un groupe de génération de rapports en faisant glisser le curseur sur l’offre souhaitée, puis en cliquant sur l’icône de dossier **[!UICONTROL Groupe de génération de rapports]**.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Conditionnel) Incluez par lots des expériences dans un groupe de génération de rapports en cochant la case correspondant aux expériences pertinentes, puis en cliquant sur l’icône de dossier **[!UICONTROL Groupe de génération de rapports]** dans le coin supérieur droit de la boîte de dialogue.

   ![Icône Groupe de rapports](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Pour attribuer l’offre sélectionnée à un groupe de génération de rapports existant, sélectionnez **[!UICONTROL Existant]**, sélectionnez le groupe de génération de rapports voulu dans la liste déroulante, puis cliquez sur **[!UICONTROL Appliquer]**.

   Ou

   Pour créer un groupe de génération de rapports auquel attribuer l’offre sélectionnée, sélectionnez **[!UICONTROL Nouveau]**, nommez le nouveau groupe de génération de rapports, puis cliquez sur **[!UICONTROL Appliquer]**.

   ![Nouvelle icône pour créer un groupe de génération de rapports](/help/main/c-reports/assets/ap_reporting_groups.png)
