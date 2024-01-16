---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 78bedce2134061edc48baf7023107e1dd48da2a1
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 50%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : mardi 16 janvier 2023**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Abandon de l’attribut d’audience iPad et iPhone du navigateur (30 avril 2024)

| Obsolescence | Détails |
|--- |--- |
| [!DNL iPad] et [!DNL iPhone] à être obsolète de la fonction [Attribut du navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) utilisé lors de la création d’audiences.<p>Date d’obsolescence :<P>mercredi 30 avril 2024 | [!DNL Adobe Target] vous permet de [cibler sur l’un des attributs de catégorie les plus courants](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les utilisateurs qui utilisent une variable [options de navigateur ou de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) lorsqu’ils visitent votre page.<P><B>À compter du 30 avril 2024, iPad et iPhone seront retirés de la [!UICONTROL Navigateur] type liste déroulante lors de la création de catégories pour les audiences.</b><P>Si des audiences ciblent des iPad ou des iPhones à l’aide de la variable [!UICONTROL Navigateur] , vous devez modifier ces paramètres avant le 30 avril 2024 pour vous assurer que ces audiences continuent à fonctionner comme prévu.<P>Les paramètres suivants doivent être utilisés à l’avenir :<ul><li>[!UICONTROL Mobile] > [!UICONTROL is Tablet]<P>![mobile est une tablette](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 et 25 janvier 2024)

Cette version est programmée pour les jours suivants :

* **22 janvier** : région Europe, Moyen-Orient et Afrique (EMEA)
* **23 janvier** : région Asie-Pacifique (APAC)
* **25 janvier** : région des Amériques

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel les intervalles de date de création de rapports ne fonctionnaient pas correctement. (TGT-47396)
* Correction d’un problème en raison duquel un état incorrect s’affichait sur le [!UICONTROL Toutes les activités] après que les clients ont activé ou désactivé une activité à l’aide de la variable [!UICONTROL Autres actions] Icône (TGT-47367)
* Correction d’un problème en raison duquel la variable [!UICONTROL Attributs importants] ne s’affichera pas pour un seul client. (TGT-47272)
* Correction d’un problème en raison duquel un message &quot;Payload non valide&quot; s’affichait lorsqu’un client tentait d’activer l’option &quot;Authentification requise&quot;. (TGT-47195)
* Mise à jour de nombreuses chaînes localisées dans le [!DNL Target] Interface utilisateur.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
