---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1b737f963fe63770cb04d05f3414ed946548d882
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 62%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 19 octobre 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.3 (version échelonnée : 25 - 27 octobre 2022)

Cette version sera disponible selon le planning échelonné suivant :

* **25 octobre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **26 octobre** : région Asie-Pacifique (APAC)
* **27 octobre** : région des Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| [!DNL Recommendations] | Ajout de noms conviviaux dans [!UICONTROL Analytics pour Target] Rapports A4T. Auparavant, [!DNL Target] identifiants d’expérience répertoriés uniquement. Cette amélioration aligne les rapports entre [!DNL Adobe Analytics] et [!DNL Target] et aide les clients à rationaliser la création de rapports dans A4T. (TGT-41853) |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<br>(Disponible pour sélectionner des clients à tester. sera disponible pour tous les clients dans une prochaine version.) | Tenez compte des changements suivants :<ul><li>Ajout de la prise en charge des mesures binaires et de maximisation dans les rapports A4T [!UICONTROL Analytics for Target] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].</li><li>Comportement conservé pour les activités existantes jusqu’en février 2023. À compter de cette date, les activités seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li><li>À compter du 20 février 2023, les mesures `averagetimespentonsite`, `bouncerate` et `entries` dans les activités [!DNL Target] seront obsolètes.</li></ul> |

* Ajout d’info-bulles dans la [!DNL Target] Interface utilisateur pour aider les clients à naviguer plus efficacement dans le créateur d’audiences et à apprendre à utiliser des fonctionnalités qui ne sont pas familières. (TGT-44139)
* Ajout d’une fonctionnalité pour empêcher les clients de modifier une activité désactivée par [!DNL Target] car il utilise des mesures non prises en charge. Un message dans l’interface utilisateur demande aux clients de dupliquer l’activité, puis de mettre à jour la mesure de conversion.

   Avec cette version `averagetimespentonsite`, `bouncerate`, et `entries` mesures dans [!DNL Target] Les activités seront abandonnées pour les nouvelles activités. Les activités existantes peuvent continuer à utiliser ces mesures jusqu’en février 2023. (TGT-43860, TGT-43861, &amp; TGT-43650)

* Ajout d’une info-bulle dans le [!DNL Target] Interface utilisateur pour aider les clients à sélectionner un critère d’optimisation lors de la création ou de la modification d’une [!UICONTROL Ciblage automatique] activité qui utilise A4T. (TGT-43713)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
