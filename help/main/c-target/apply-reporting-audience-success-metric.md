---
keywords: Ciblage;audience;rapports;mesure de succès
description: Découvrez comment choisir une mesure de succès dans  [!DNL Adobe Target]  qui qualifie l’utilisateur pour l’audience de rapport.
title: Puis-Je Appliquer Une Audience De Rapport À Une Mesure De Succès ?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
TQID: https://experienceleague.adobe.com/n3iyCzlY5oDOrCEqvo6nO51PvknlySPCMasQZ0JfIEM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 43%

---

# Application d’une audience de rapport à une mesure de succès

Choisissez une mesure de succès qui qualifie l’utilisateur pour l’audience de rapport dans [!DNL Adobe Target].

Pour toutes les activités, la liste déroulante [!UICONTROL S’applique à] permet d’appliquer une audience à une mesure de succès pour visualiser les nombres présentés dans les rapports une fois la mesure atteinte et pour les actions ultérieures.

![image success_metric](assets/success_metric.png)

Imaginons, par exemple, que vous avez créé une activité pour tous les visiteurs qui entrent sur votre page d’accueil et qui accèdent ensuite à la page de conversion, mais que vous voulez également analyser plus en détails les visiteurs qui ont ajouté dans leur panier des produits pour un montant supérieur à 50 USD avant la conversion.

La liste déroulante [!UICONTROL Appliqué à] peut se diviser en trois catégories :

* Tout visiteur ou visiteuse de l’activité
* Seuls les visiteurs qui atteignent une certaine étape de l’activité
* Uniquement les visiteurs qui atteignent la conversion

Autrement dit, vous pouvez spécifier qu’un visiteur doit avoir atteint une mbox sur la page d’entrée de l’activité, une mbox qui définit un point donné au cours de l’activité, ou encore la mbox de conversion à la fin de l’activité.

>[!NOTE]
>
>[Les mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) sont disponibles uniquement si vous les avez configurées pour votre activité. Si vous n’avez pas défini de mesures de succès, vous ne voyez que deux options dans la liste déroulante : [!UICONTROL Entrée de campagne] et [!UICONTROL Conversion].


## Considérations

Prenez en compte les points suivants lorsque vous appliquez une audience de rapport à une mesure de succès :

* Seules les mesures de succès commençant par celle à laquelle l’audience est appliquée affichent les données de rapports segmentées par l’audience
* Les mesures de succès précédant celles auxquelles l’audience est appliquée ne seront pas segmentées par l’audience et afficheront toutes les données du visiteur
* Les mesures sont prises en compte en fonction de leur ordre dans la définition de l’activité, l’objectif de Principal  étant le dernier.

## Afficher la segmentation dans les rapports

Pour afficher la segmentation dans les rapports, sélectionnez l’audience souhaitée dans la liste déroulante [!UICONTROL Audience] du rapport de l’activité.

![image reporting_audience_dropdown](assets/reporting_audience_dropdown.png)

## Exemple

Prenons l’exemple d’une activité qui a la mesure de succès 1, la mesure de succès 2, la mesure de succès 3 et l’objectif du Principal.

Supposons que l’Audience1 de création de rapports soit définie sur « Entrée » et que l’Audience2 de création de rapports soit définie sur la Mesure de succès 2. Les audiences filtreront les données de rapport comme suit :

|  | Visiteurs | Mesure De Succès 1 | Mesure de succès 2 | Mesure De Succès 3 | Objectif du Principal |
| --- | --- | --- | --- | --- | --- |
| Audience1 | Appliqué | Appliqué | Appliqué | Appliqué | Appliqué |
| Audience2 | Non appliqué | Non appliqué | Appliqué | Appliqué | Appliqué |
