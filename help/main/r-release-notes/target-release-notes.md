---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 872e56662e04e3fabda7ff38233adfea32efbe48
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 47%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : vendredi 17 avril 2025**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.5 (24 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel plusieurs audiences d’expérience s’affichaient lors de la modification ou de l’enregistrement d’une activité. (TGT-52134)
* Correction d’un problème en raison duquel les recommandations ne s’affichaient pas sur le site web du client ou de la cliente après l’activation de l’activité [!DNL Recommendations]. (TGT-52164)
* `OptionLocalIDs` n’incrémente plus incorrectement lorsque l’option reste inchangée. (TGT-52187)
* Les fichiers de rapports téléchargés affichent désormais correctement les données présentes dans l’interface utilisateur de création de rapports. (TGT-52068)
* Correction d’un problème qui empêchait Target de reconnaître le caractère « # » dans l’URL d’un site web. (TGT-52093)
* Les opérations par lots n’échouent plus après l’ajout de règles de diffusion de page. (TGT-52097)
* Correction d’un problème en raison duquel [!DNL Target] supprimait tous les paramètres de requête de l’URL du site web. (TGT-52100)
* Correction d’un problème en raison duquel les affinements d’audience et les audiences d’activité étaient inversés dans l’interface utilisateur mise à jour. (TGT-52158)

## Mise à jour des autorisations Target (22 avril 2025)

Cette future mise à jour améliore le contrôle organisationnel sur les configurations d’instance de [!DNL Target], empêchant les mises à jour accidentelles qui pourraient affecter la diffusion des activités entre différentes équipes de test et de personnalisation.

À compter du 22 avril 2025, seuls les administrateurs [!UICONTROL Product] et [!UICONTROL Solutions] pourront mettre à jour les paramètres des sections [!UICONTROL Administration], quels que soient leurs rôles dans les espaces de travail [!DNL Target]. Les utilisateurs ne disposant pas de cette autorisation auront un accès en lecture seule aux sections [!UICONTROL Administration].

Pour plus d’informations, voir [ Administration de Target ](/help/main/administrating-target/start-target.md).

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
