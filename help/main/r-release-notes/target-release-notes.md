---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 6058ebcf8150f9161d591a1c1c315af40babc6ef
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 85%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 9 septembre 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.9.1 (version échelonnée : 13 - 15 septembre 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **13 septembre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **14 septembre** : région des Amériques
* **15 septembre** : région Asie-Pacifique (APAC)

Cette version comprend les améliorations et correctifs suivants :

* Ajout d’une option [!UICONTROL interdomaines] lors du téléchargement d’at.js 2.10.0 (et versions ultérieures) pour autoriser ou désactiver la définition des cookies tiers. (TGT-43674)
* Notifications mises à jour dans le [!DNL Target] Interface utilisateur pour informer les clients si l’importation de [!DNL Recommendations] les flux échouent. (TGT-35811)
* Correction d’un problème en raison duquel [!UICONTROL Offres de décision] ne fonctionnait pas correctement dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC). (TGT-43866)
* Correction d’un problème en raison duquel un message d’erreur s’affichait lors de la sélection de l’objectif de conversion [!UICONTROL Clic sur un élément] pendant la création d’une activité de [!UICONTROL test multivarié] (MVT). (TGT-43842)
* Correction d’un problème en raison duquel la variable [!UICONTROL Impressions] ne s’affichait pas dans le fichier de rapport CSV téléchargé pour les activités de [!UICONTROL ciblage automatique] (AP). (TGT-43780)
* Correction d’un problème qui empêchait les clients de modifier les offres de HTML/JSON après avoir dupliqué des expériences lors de l’utilisation de la variable [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-43633)
* Correction d’un problème en raison duquel les clients ne pouvait pas copier une activité de [!UICONTROL Test A/B] d’un espace de travail non par défaut vers un autre espace de travail non par défaut. (TGT-41910)
* Correction d’un problème pour s’assurer que les clients peuvent afficher correctement les utilisations de [!DNL Recommendations] objets (conceptions, critères, collections, etc.) dans [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) activités qui contiennent des recommandations et qui suppriment également les objets de critère qui ne sont plus utilisés depuis [!DNL Target] Interface utilisateur et [!DNL Recommendations] back-end. (TGT-42331)
* Correction d’un problème qui entraînait l’affichage d’une alerte de délai d’expiration réseau dans l’interface utilisateur [!DNL Target] lors de la récupération des paramètres. (TGT-43737)
* Mise à jour de l’interface utilisateur pour garantir que certaines actions de glisser-déposer sont accessibles par le biais du clavier. (TGT-42969)
* Mise à jour de l’interface utilisateur pour garantir que les chaînes de texte sont correctement localisées.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
