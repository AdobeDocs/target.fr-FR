---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 145f4bd2b3353e429ce968622e47653170a60fda
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

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
| Mesures A4T optimisées pour l’[!UICONTROL affectation automatique] et le [!UICONTROL ciblage automatique]<br> (disponible pour sélectionner des clients pour le test. Sera disponible pour tous les clients dans une prochaine version.) | Tenez compte des changements suivants :<ul><li>Ajout de la prise en charge des mesures binaires et de maximisation dans les rapports A4T [!UICONTROL Analytics for Target] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].</li><li>Comportement conservé pour les activités existantes jusqu’à février 2023. À compter de cette date, les activités seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li><li>À compter du 20 février 2023, les mesures `averagetimespentonsite`, `bouncerate` et `entries` dans les activités [!DNL Target] seront obsolètes.</li></ul> |

* Ajout d’info-bulles dans l’interface utilisateur [!DNL Target] pour aider les clients à accéder plus efficacement au créateur d’audiences et à apprendre à utiliser des fonctionnalités qui ne sont pas familières. (TGT-44139)
* Ajout d’une fonctionnalité pour empêcher les clients de modifier une activité désactivée par [!DNL Target], car il utilise des mesures non prises en charge. Un message dans l’interface utilisateur demande aux clients de dupliquer l’activité, puis de mettre à jour la mesure de conversion.

   Avec cette version, les mesures `averagetimespentonsite`, `bouncerate`, et `entries` dans les activités [!DNL Target] seront abandonnées pour les nouvelles activités. Les activités existantes peuvent utiliser ces mesures jusqu’en mai 2023.

* Ajout d’une info-bulle dans l’interface utilisateur [!DNL Target] pour aider les clients à sélectionner un critère d’optimisation lors de la création ou de la modification d’une activité [!UICONTROL Ciblage automatique] qui utilise A4T.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
