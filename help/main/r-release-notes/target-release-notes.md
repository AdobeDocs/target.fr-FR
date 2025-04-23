---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ad82d108adc6f5c76b2104f40fb0bb2c66e98a2b
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 33%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : jeudi 23 avril 2025**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.5 (24 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les recommandations ne s’affichaient pas sur le site web du client ou de la cliente après l’activation de l’activité [!DNL Recommendations]. (TGT-52164)
* `OptionLocalIDs` n’incrémente plus incorrectement lorsque l’option reste inchangée. (TGT-52187)
* Les fichiers de rapports téléchargés affichent désormais correctement les données présentes dans l’interface utilisateur de création de rapports. (TGT-52068)
* Les opérations par lots n’échouent plus après l’ajout de règles de diffusion de page. (TGT-52097)
* Correction d’un problème en raison duquel [!DNL Target] supprimait tous les paramètres de requête de l’URL du site web. (TGT-52100)
* Correction d’une erreur de console qui empêchait les clients de créer des activités dans l’interface utilisateur de Target héritée et mise à jour. (TGT-52181)
* Correction d’un problème qui empêchait les clients et clientes d’ajouter de nouvelles pages, provoquant une erreur d’entrée utilisateur non valide. (TGT-52258)
* Correction d’un problème en raison duquel les modifications disparaissaient après l’ajout de pages supplémentaires, puis en revenant à l’onglet [!UICONTROL Experiences] . (TGT-52264)
* Correction d’un problème qui empêchait les clients et clientes de modifier l’audience dans une activité [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Correction d’une erreur qui empêchait la modification d’une activité XT en raison d’une règle d’IU non prise en charge. (TGT-52273)
* Correction d’un problème en raison duquel les modifications d’activité ne s’affichaient pas dans l’interface utilisateur de [!DNL Target], bien qu’elles aient été correctement diffusées sur la page web. (TGT-52192)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) en raison duquel les chemins de navigation n’étaient pas toujours affichés en bas de l’éditeur, ce qui entraînait des difficultés pour sélectionner précisément les éléments. (TGT-51169)
* Correction d’un problème en raison duquel la liste déroulante [!UICONTROL Audience] n’affichait pas toutes les audiences en raison de la pagination. (TGT-52204)
* Correction d’un problème qui entraînait un message d’entrée utilisateur non valide lors de l’ajout de nouvelles offres dans les activités [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Correction d’un problème en raison duquel [!UICONTROL Analytics for Target] (A4T) était incorrectement sélectionné comme source de création de rapports, même si le client n’avait pas accès à A4T. (TGT-52226)
* Correction d’un problème qui empêchait l’enregistrement d’une activité avec la mesure URL [!UICONTROL View a Page]. (TGT-52260)
* Correction d’un problème qui empêchait les clients de sélectionner des espaces de travail lors de la création d’offres dans une activité. (TGT-52289)
* Correction d’un problème où les modifications d’une expérience s’affichaient incorrectement lors du passage à une autre expérience. (TGT-52184)
* Correction d’un problème en raison duquel l’offre par défaut s’affichait incorrectement dans l’interface utilisateur de [!DNL Target] après l’ouverture de l’activité. (TGT-52198)

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
