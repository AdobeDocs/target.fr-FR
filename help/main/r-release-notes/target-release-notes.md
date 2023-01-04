---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 92851dc763f9bc6bb5a26a449d0f08bceceb583f
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 52%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 4 janvier 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.1.1 (23 janvier 2023)

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| AEM fragments de contenu<br>(Date exacte de publication de cette fonctionnalité à déterminer.) | Utiliser les fragments de contenu créés dans [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target] activités pour faciliter l’optimisation ou la personnalisation.<br>Utilisation de fragments de contenu créés dans AEM dans [!DNL Target] Les activités vous permettent de combiner la facilité d’utilisation et la puissance de l’AEM avec de puissantes fonctionnalités d’ intelligence artificielle (AI) et d’ apprentissage automatique (ML) dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle. |

* Ajout de la prise en charge des offres JSON dans [!UICONTROL Automated Personalization] (AP) à l’aide du compositeur d’expérience d’après les formulaires. (TGT-41460)
* Ajout de la possibilité de rechercher et de filtrer les offres par balises AEM. (TGT-43837)
* Renommé &quot;[!UICONTROL Fragment d’expérience]&quot; dans le workflow du compositeur d’expérience visuelle. L’option est désormais &quot;[!UICONTROL HTML XF].&quot; (TGT-44132)
* Ajout de la possibilité d’afficher les métadonnées de l’offre de fragments d’expérience dans l’info-bulle de l’offre. (TGT-43838)
* Suppression des options de calendrier de 45 jours et de 90 jours de l’API et [!UICONTROL Ciblage automatique] [!UICONTROL Informations sur la personnalisation] et [!UICONTROL Attributs importants] dans les [!DNL Target] Interface utilisateur. En raison des schémas d’utilisation et pour améliorer les performances, ces plages de dates sont obsolètes. L’interface utilisateur a été mise à jour pour prendre en compte les plages actuellement autorisées : 15, 30 et 60 jours. (TGT-39357)
* Suppression de la possibilité de modifier la variable [!UICONTROL Identique à l’objectif d’optimisation] sur le [!UICONTROL Objectifs et paramètres] une fois l’activité activée. (TGT-43923)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
