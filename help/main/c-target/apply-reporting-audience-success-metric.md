---
keywords: Ciblage;audience;rapports;mesure de succès
description: Découvrez comment choisir une mesure de succès dans  [!DNL Adobe Target] qui qualifie l’utilisateur pour l’audience de rapport.
title: Puis-je appliquer une audience de rapport à une mesure de succès ?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: bcbb6dec9d6add07c109b07bf125c1356ad2a8b9
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 36%

---

# Application d’une audience de rapport à une mesure de succès

Sélectionnez une mesure de succès qui qualifie l’utilisateur pour l’audience de création de rapports dans [!DNL Adobe Target].

Pour toutes les activités, la liste déroulante [!UICONTROL Applied At] vous permet d’appliquer une audience à une mesure de succès afin que vous puissiez afficher les nombres de rapports une fois la mesure atteinte et pour les actions suivantes.

![image_success_metric](assets/success_metric.png)

Imaginons, par exemple, que vous avez créé une activité pour tous les visiteurs qui entrent sur votre page d’accueil et qui accèdent ensuite à la page de conversion, mais que vous voulez également analyser plus en détails les visiteurs qui ont ajouté dans leur panier des produits pour un montant supérieur à 50 USD avant la conversion.

La liste déroulante [!UICONTROL Applied At] propose potentiellement trois catégories :

* Tout visiteur de l’activité
* Uniquement les visiteurs qui atteignent une certaine étape de l’activité
* Uniquement les visiteurs qui atteignent la conversion

Autrement dit, vous pouvez spécifier qu’un visiteur doit avoir atteint une mbox sur la page d’entrée de l’activité, une mbox qui définit un point donné au cours de l’activité, ou encore la mbox de conversion à la fin de l’activité.

>[!NOTE]
>
>[Les mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) sont disponibles uniquement si vous les avez configurées pour votre activité. Si vous n’avez pas défini de mesures de succès, vous ne voyez que deux options dans la liste déroulante : [!UICONTROL Campaign Entry] et [!UICONTROL Conversion].


## Considérations

Prenez en compte les points suivants lorsque vous appliquez une audience de rapport à une mesure de succès :

* Seules les mesures de succès commençant par celle à laquelle l’audience est appliquée affichent les données de rapport segmentées par l’audience.
* Les mesures de succès antérieures à celles auxquelles l’audience est appliquée ne sont pas segmentées par audience et affichent toutes les données du visiteur.
* Les mesures sont prises en compte en fonction de leur ordre dans la définition de l’activité, [!UICONTROL Primary Goal] étant le dernier.

## Afficher la segmentation dans les rapports

Pour afficher la segmentation dans les rapports, sélectionnez l’audience souhaitée dans la liste déroulante [!UICONTROL Audience] du rapport de l’activité.

![image de menu déroulant de reporting_audience_1&rbrace;](assets/reporting_audience_dropdown.png)

## Exemple

Prenons l’exemple d’une activité qui comprend les éléments Mesure de succès 1, Mesure de succès 2, Mesure de succès 3 et Objectif Principal.

Supposons que vous ayez défini Audience1 sur &quot;Entrée&quot; et Audience2 sur la mesure de succès 2 de la création de rapports. Les audiences filtreront les données du rapport comme suit :

|  | Visiteurs | Mesure de succès 1 | Mesure de succès 2 | Mesure de succès 3 | Objectif Principal |
| --- | --- | --- | --- | --- | --- |
| Audience1 | Appliqué | Appliqué | Appliqué | Appliqué | Appliqué |
| Audience2 | Non appliqué | Non appliqué | Appliqué | Appliqué | Appliqué |
