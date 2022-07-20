---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bc4b04ae0be1fade2456eb42ade7ee87c0f14b16
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 40%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 20 juillet 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] version de Platform (20 juillet 2022)

Cette version comprend les fonctionnalités, les améliorations et correctifs suivants :

| Fonctionnalité | Description |
| --- | --- |
| Amélioration de la précision de l’évaluation des audiences et réduction de la latence des utilisateurs finaux grâce à la prise en charge du protocole IPv6 (TNT-43364, TNT-44692) | La géolocalisation des visiteurs est désormais déterminée par les adresses IPv6, le cas échéant, et non par les adresses IPv4 uniquement. Les API de diffusion prennent également en charge les paramètres d’entrée IPv6. Le filtrage et le liste autorisée prennent en charge les adresses IPv4 et IPv6. La prise en charge d’IPv6 dans cette version signifie que les visiteurs seront inclus plus précisément dans les audiences (plus adaptés aux activités ou inclus dans les critères de filtrage). Il améliore également la latence des données, car les clients IPv6 acheminent directement, évitant ainsi la surcharge de la passerelle IPv6 vers IPv4. |
| Correction d’un problème de gestion de la charge utile côté client d’A4T (TNT-44926). | Avec l’intégration côté serveur A4T, si Adobe Target identifie une demande comme provenant d’un robot, il ne transmet pas la charge utile à Analytics et aucun événement mod_stats n’est enregistré dans la variable [!DNL Target] journaux. Avec cette version, la journalisation côté client d’A4T a été améliorée de sorte que le comportement concernant la payload A4T soit le même que pour A4T côté serveur : Les visiteurs identifiés comme des robots sont exclus de [!DNL Target] comptage/reporting. (Notez que le problème en question se limitait aux mises en oeuvre qui utilisaient la gestion de la charge utile côté client ; côté serveur n’a pas été affecté. Avec cette version, le comportement est désormais cohérent pour la gestion de la charge utile côté serveur et côté client.) |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
