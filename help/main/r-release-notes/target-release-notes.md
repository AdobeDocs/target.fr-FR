---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 22 janvier 2024**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Obsolescence de l’iPad et de l’iPhone dans l’attribut d’audience Navigateur (30 avril 2024)

| Retrait | Détails |
|--- |--- |
| Les [!DNL iPad] et [!DNL iPhone] sont retirés de l’[attribut de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md), qui est utilisé lors de la création d’audiences.<p>Date de retrait :<P>30 avril 2024 | [!DNL Adobe Target] vous permet de [cibler n’importe quel attribut de catégorie](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les personnes qui utilisent un [navigateur ou des options de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) spécifiques lorsqu’elles consultent votre page.<P><B>À compter du 30 avril 2024, iPad et iPhone seront retirés de la liste déroulante [!UICONTROL Navigateur] disponible lors de la création de catégories pour les audiences.</b><P>Si vous avez des audiences qui ciblent les iPad ou les iPhone à l’aide de l’attribut [!UICONTROL Navigateur], vous devez modifier ces paramètres avant le 30 avril 2024 pour assurer leur bon fonctionnement.<p>Pour des exemples de paramètres alternatifs, consultez [Obsolescence de l’iPad et de l’iPhone dans l’attribut d’audience Navigateur (30 avril 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 et 25 janvier 2024)

Cette version est programmée pour les jours suivants :

* **22 janvier** : région Europe, Moyen-Orient et Afrique (EMEA)
* **23 janvier** : région Asie-Pacifique (APAC)
* **25 janvier** : région des Amériques

Cette version comprend les améliorations et correctifs suivants :

* Les activités [!UICONTROL Analytics for Target] (A4T) avec des mesures d’objectif de revenus n’affichaient pas « Revenus » comme nom de colonne et la mesure des revenus ne s’affichait pas au format ($) dans les rapports. Il s’agissait d’un problème d’ordre cosmétique qui a été corrigé. (TGT-46995)
* Correction d’un problème en raison duquel les périodes des rapports ne fonctionnaient pas correctement. (TGT-47396)
* Correction d’un problème qui entraîne l’affichage d’un statut incorrect sur la page [!UICONTROL Toutes les activités] après l’activation ou la désactivation d’une activité à l’aide de l’icône [!UICONTROL Plus d’actions]. (TGT-47367)
* Correction d’un problème en raison duquel le rapport [!UICONTROL Attributs importants] ne s’affichait pas pour un seul client ou une seule cliente. (TGT-47272)
* Correction d’un problème en raison duquel le message « Payload non valide » s’affichait lorsqu’un seul client ou une seule cliente tentait d’activer l’option « Authentification obligatoire ». (TGT-47195)
* Mise à jour de plusieurs chaînes localisées dans l’interface utilisateur de [!DNL Target].

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
