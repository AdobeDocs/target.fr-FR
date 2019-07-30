---
description: Liste des questions fréquentes sur la création de rapports dans Target.
keywords: résolution des problèmes;divergences entre les mesures;Forum aux questions;rapports
seo-description: Liste des questions fréquentes sur la création de rapports dans Adobe Target.
seo-title: FAQ sur les rapports pour Adobe Target
solution: Target
title: FAQ sur la création de rapports
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# FAQ sur la création de rapports{#reporting-faq}

Liste des questions fréquentes sur la création de rapports dans [!DNL Target].

## Why do my [!UICONTROL Experience Targeting] (XT) reports contain metrics for control experiences?

Les activités de ciblage d'expérience doivent toujours avoir une expérience de contrôle. If you are using an XT activity in a similar manner to an [!UICONTROL A/B Test] activity, which is a fairly common scenario, the control experience data is useful. Vous pouvez ignorer les données de contrôle des expériences si elles ne sont pas utiles dans vos rapports.

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

Les chiffres de mesure signalés par [!DNL Target], par exemple le nombre de visites, seront toujours inférieurs aux chiffres signalés dans les autres solutions [!DNL Experience Cloud] pour plusieurs raisons :

* [!DNL Target] comptabilise uniquement les visites des visiteurs qui remplissent les critères de l’activité. Les autres solutions comptabilisent les visites des visiteurs qui affichent la page, indépendamment de l’activité qui les a amenés à la page.
* Dans certains cas, différentes activités sont en compétition pour le même emplacement (mutuellement exclusif). Les visiteurs voient donc des contenus différents sur une même page web, ce qui affecte les chiffres de mesure signalés par [!DNL Target].

## Pourquoi n’existe-t-il pas de données disponibles pour le rapport de mon activité ?{#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

Si un environnement de développement est sélectionné, le message suivant peut s’afficher : « Aucune donnée n’est disponible pour les paramètres des rapports sélectionnés. »

Pour modifier l’environnement pour le rapport d’une activité :

1. Cliquez sur **[!UICONTROL Activités]**, sélectionnez l’activité souhaitée dans la liste, puis cliquez sur l’onglet ]**Rapports[!UICONTROL **.
1. Cliquez sur l’engrenage pour configurer les paramètres des rapports.

   ![Boîte de dialogue Paramètres A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. Dans la liste déroulante **[!UICONTROL Environnement]**, sélectionnez **[!UICONTROL Production]**.

   Les données de rapport peuvent ne pas être disponibles si vous avez sélectionné un environnement de développement.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour plus d’informations sur les environnements, voir [Hôtes](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
