---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 90%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 25er mai 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Version de la plateforme Target (25 mai 2022)

Cette version comprend les améliorations et correctifs suivants :

* Ajout [Informations sur le client de l’agent utilisateur](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) prise en charge.
* Correction d’un problème qui provoquait par intermittence des dépassements de délai lors du rendu. [!UICONTROL Décisions sur les offres] in [!UICONTROL Ciblage d’expérience] (XT). (TNT-44611)

## at.js version 2.9.0 (27 mai 2022)

* Ajout [Informations sur le client de l’agent utilisateur](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) prise en charge.
* Correction d’un bogue en raison duquel plusieurs requêtes de mbox sur la même page avaient des ID d’impression différents.

## [!DNL Target Standard/Premium] 22.5.1 (sortie échelonnée ; 11-13 mai 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **11 mai** : région Asie-Pacifique (APAC)
* **12 mai**: Région des Amériques
* **13 mai** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème qui provoquait une erreur JavaScript et empêchait certains clients d’accéder aux détails de certaines activités [!UICONTROL Automated Personalization] (AP). (TGT-43526)
* Correction d’un problème qui empêchait certains clients d’ajouter (ou de modifier) une offre spécifique à une activité AP. (TGT-43503)
* Correction d’un problème dans l’interface utilisateur [!DNL Target] qui affichait le message d’erreur suivant : « Votre mbox globale peut ne pas être synchronisée. Réessayez de lʼenregistrer ». Ce problème était un problème de l’interface utilisateur et n’avait aucune incidence sur les implémentations des clients. (TGT-43475)
* Correction d’un problème qui empêchait un client de modifier des ajustements et des audiences au niveau de l’expérience pour une activité si ceux-ci étaient créés avant le déploiement de la nouvelle interface utilisateur [!UICONTROL Audiences]. (TGT-43433)
* Correction d’un problème en raison duquel les clients pouvaient sélectionner des audiences [!DNL Adobe Audience Manager] (AAM) en double lors de la modification des audiences avec création de rapports pour une activité. (TGT-43430)
* Correction d’un problème qui empêchait les clients de créer des audiences en double, mais dans différents espaces de travail. (TGT-43423)
* Correction d’un problème qui empêchait les clients de supprimer les emplacements où des offres ad hoc étaient créées dans les activités créées dans le [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-43315)
* Correction d’un problème qui empêchait les clients d’accéder aux offres de code après avoir cliqué sur des offres d’image, puis avoir actualisé l’interface utilisateur. (TGT-43566)
* Correction d’un problème en raison duquel les modifications apportées aux scripts de profil revenaient au script original non modifié après l’édition, l’activation et la désactivation du script. Le script de profil reste désormais à l’état modifié. (TGT-43249)
* Correction d’un problème qui provoquait l’erreur suivante lors de la tentative de déplacement d’une audience vers un autre espace de travail : « Nous ne pouvons pas terminer votre demande. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-43212)
* Correction d’une erreur qui provoquait une erreur lors du clonage des modifications de code personnalisé pour les pages Application d’une seule page (SPA). (TGT-43137)
* Correction d’un problème en raison duquel la promotion d’origine était affectée après la duplication d’une expérience, puis la modification de la promotion. (TGT-41775)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
