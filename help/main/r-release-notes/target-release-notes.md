---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd12d615b784b26e2b5a7b9e391f3e7d5a9cc8c5
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 31%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 27 septembre 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.1 (version échelonnée du 4 au 6 octobre 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **4 octobre**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **5 octobre**: Région Asie-Pacifique (APAC)
* **6 octobre**: Région des Amériques

Cette version contient les nouvelles fonctionnalités, améliorations et correctifs suivants :

| Fonctionnalité | Détails |
| --- | --- |
| Nouveau [!UICONTROL Compositeur d’expérience visuelle] extension pour Google Chrome | Une nouvelle [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour Chrome est disponible dans Chrome Web Store.<br>À compter de janvier 2023, la variable [!DNL Target] L’extension d’assistance de VEC cessera de fonctionner dans Google Chrome, car Google n’autorise pas les extensions utilisant Manifest V2. Téléchargez la nouvelle extension pour continuer à créer visuellement vos sites web dans [!DNL Target] à partir de la nouvelle année. |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<br>(Date exacte de publication à déterminer.) | Tenez compte des modifications suivantes :<ul><li>Ajout de la prise en charge des mesures binaires et de maximisation dans [!UICONTROL Analytics pour Target] Rapports A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités</li><li>Suppression du message d’avertissement des mesures binaires pour [!UICONTROL Ciblage automatique] activités</li><li>Comportement conservé pour les activités existantes jusqu’au 20 février 2023. À compter de cette date, les activités seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li><li>À compter du 20 février 2023, la prise en charge de `averagetimespentonsite`, `bouncerate`, et `entries` mesures dans [!DNL Target] Les activités seront obsolètes.</li></ul> |

* Correction d’un problème qui empêchait l’affichage correct des informations des règles d’audience dans la variable [!UICONTROL Amélioration des audiences] fenêtre d’informations. (TGT-43917)
* Amélioration des performances de la fonction [!DNL Target] de l’interface utilisateur lors du chargement d’audiences approchant la variable [limite recommandée des règles de ciblage](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Correction d’un problème en raison duquel certains composants ne s’affichaient pas correctement dans la variable [!UICONTROL Modifications] du panneau [!UICONTROL Expériences] lors de la création ou de la modification d’activités dans le compositeur d’expérience visuelle après le passage de [!UICONTROL Composer] to [!UICONTROL Parcourir] mode . (TGT-43300)
* Correction d’un problème qui empêchait certains clients d’archiver [!UICONTROL Test A/B] activités qui utilisent [!UICONTROL Ciblage automatique]. (TGT-40978)
* Ajout de la possibilité d’utiliser automatiquement une seule offre à plusieurs emplacements au sein d’un seul groupe de génération de rapports. (TGT-43974)
* Ajout de la possibilité de filtrer les fragments d’expérience par type (HTML ou JSON) dans le [!UICONTROL Offres] liste. (TGT-43121)
* Correction d’un problème en raison duquel les clients pouvaient insérer JSON. [!UICONTROL Fragment d’expérience] offres lors de l’utilisation du VEC, qui n’est pas pris en charge. Les offres JSON ne peuvent être insérées que lors de l’utilisation de la variable [!UICONTROL Expérience d’après les formulaires] compositeur. (TGT-43846)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
