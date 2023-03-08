---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de  [!DNL Target]  ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 55%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 8er mars 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.15.1 (8 et 9 mars 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **8 mars**: Région des Amériques
* **9 mars**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **9 mars**: Région Asie-Pacifique (APAC)

Cette version contient les nouvelles fonctionnalités et améliorations suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] | [!DNL Target] vous permet de choisir des mesures en fonction d’événements binaires ou de mesures en fonction d’événements continus lors de l’utilisation de la variable [!UICONTROL A4T] pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.<P>Gardez à l’esprit les changements suivants au niveau des mesures prises en charge :<ul><li>[!DNL Target] a conservé le comportement précédent des activités existantes jusqu’à (DATE À DÉTERMINER). À compter de cette date, les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers le nouveau comportement.</li></ul>Pour plus d’informations, voir [Mesures d’objectif prises en charge](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique*. |
| [!UICONTROL Affectation automatique] using [!UICONTROL Analytics pour Target] (A4T) | Nouveau tutoriel :<ul><li>[Configuration de rapports A4T dans [!DNL Analysis Workspace] pour [!UICONTROL Affectation automatique] activités](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL Ciblage automatique] using [!UICONTROL Analytics pour Target] (A4T) | Nouveau tutoriel :<ul><li>[Configuration de rapports A4T dans [!DNL Analysis Workspace] pour [!UICONTROL Ciblage automatique] activités](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

## at.js version 2.10.2 (7 mars 2023)

* Correction d’un problème en raison duquel la variable `trackEvent` pour toujours renvoyer une erreur.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
