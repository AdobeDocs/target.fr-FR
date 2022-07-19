---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d0b6f81507cc5d5bc17d029c3d8f5b36c2c71a29
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 18 juillet 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.7.1 (20 juillet 2022)

Cette version comprend les fonctionnalités, les améliorations et correctifs suivants :

| Fonctionnalité | Description |
| --- | --- |
| Amélioration de la précision de l’évaluation des audiences et de la latence des utilisateurs finaux grâce à la prise en charge d’IPv6 | La géolocalisation des visiteurs est désormais déterminée par les adresses IPv6, le cas échéant, et non par les adresses IPv4 uniquement. Les API de diffusion prennent également en charge les paramètres d’entrée IPv6. Le filtrage et le liste autorisée prennent en charge les adresses IPv4 et IPv6. Cette prise en charge d’IPv6 dans cette version signifie que les visiteurs seront inclus plus précisément dans les audiences (plus adaptés aux activités ou inclus dans les critères de filtrage). Il améliore également la latence des données, car les clients IPv6 acheminent directement, évitant ainsi la surcharge de la passerelle IPv6 vers IPv4. |
| Amélioration de la gestion de la charge utile côté client d’A4T | Avec l’intégration côté serveur A4T, si Adobe Target identifie une requête comme provenant d’un robot, il ne transmet pas la charge utile à Analytics et aucun événement mod_stats n’est enregistré dans les journaux de Target. Avant cette version, les intégrations côté client d’A4T transmettaient la charge utile à Analytics, même lorsqu’elle avait été identifiée comme trafic de robots. Cette incohérence entre le côté serveur et le côté client entraînerait des incohérences, dans la mesure où les rapports A4T pour ce dernier incluaient le trafic de robots. De plus, le trafic de robots n’était pas nécessairement identifié ni marqué, ce qui signifie qu’il n’était pas possible de déambigüer ou de supprimer le trafic de robots du reste du trafic. Et même si un client comptabilisait lui-même le trafic de robots, il ne correspondrait pas nécessairement à l’ensemble du trafic identifié et exclu par Target en tant que trafic de robots, ce qui entraînerait une division des incohérences ou d’autres problèmes. Avec cette version, la journalisation côté client d’A4T a été améliorée de sorte que le comportement concernant la payload A4T soit le même que pour A4T côté serveur : Les visiteurs identifiés comme des robots sont exclus du comptage/reporting de Target, pour les mises en oeuvre côté serveur et côté client. |

## [!DNL Target Standard/Premium] 22.6.2 (30 juin 2022)

Cette version comprend les fonctionnalités, les améliorations et correctifs suivants :

| Fonctionnalité | Description |
| --- | ---  |
| Notifications intégrées au produit | Obtenez les notifications intégrées au produit appropriées suivantes :<ul><li>**Activités** : notifications pour tous les types d’activité lorsqu’une activité est approuvée ou désactivée, manuellement ou lorsqu’elle atteint sa date de début ou de fin. La notification inclut le nom de l’activité avec un lien vers sa page de présentation.</li><li>**Scripts de profil** : notifications lorsqu’un script de profil est activé ou désactivé, manuellement ou par Target.</li><li>**Flux de recommandations** : notifications lorsqu’un flux de recommandations est activé ou désactivé, manuellement ou par Target. Des notifications sont également envoyées lorsqu’un flux de recommandations échoue.</li></ul> Par défaut, les administrateurs de produit, les éditeurs et les approbateurs reçoivent les notifications. Vous pouvez configurer les notifications dans les préférences d’Experience Cloud.<br>Pour plus d’informations, consultez [Notifications et annonces](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guide du développeur d’Adobe Target* | Le *Guide du développeur d’Adobe Target* consolide tout le contenu développeur [!DNL Target] dans un guide pratique. Ce guide contient des informations sur l’implémentation de [!DNL Target] et [!DNL Recommendations], des SDK [!DNL Target] et des API [!DNL Target].<br>Pour plus d’informations, consultez la section [Guide du développeur d’Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Les utilisateurs dotés du rôle [!UICONTROL Éditeur] ne peuvent plus modifier les audiences dans les activités dynamiques. (TGT-43582)
* Un message d’avertissement s’affiche si un client tente d’enregistrer une audience sous un nom comportant un point d’exclamation (!) comme premier caractère du nom de l’audience (par exemple, !Londres). (TGT-43643)
* Correction d’un problème en raison duquel les cartes de définition des audiences de certains clients indiquaient qu’une activité terminée était toujours active. (TGT-43527)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
