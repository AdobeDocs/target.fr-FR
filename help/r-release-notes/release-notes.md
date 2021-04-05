---
keywords: Notes de mise à jour ; nouvelles fonctionnalités ; versions ; mises à jour ; mise à jour ; mise à jour ; amélioration ; améliorations ; correctifs ; correctifs ; mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Notes de mise à jour
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: 60c3dfe28f3618113d4d03da538e4d0e4ac2feb8
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 36%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour fournissent des informations sur les fonctionnalités, les améliorations et les correctifs de chaque version [!DNL Adobe Target Standard] et [!DNL Target Premium]. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : A compter du 31 mars 2021, la bibliothèque mbox.js  [!DNL Adobe Target] ne sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Migrez vers la dernière version de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel sur vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## at.js 2.4.1 (23 mars 2021)

Cette version d’at.js est une version de maintenance qui comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel `targetPageParams` était inclus dans les requêtes de mbox. `targetPageParams` doit être incluse dans les  `pageLoad` requêtes uniquement. (TNT-40247)
* Correction d’un problème lié aux objets globaux document et fenêtre dans l’extension [!DNL Adobe Experience Platform Launch] en remplaçant les dépendances d’objet global Platform launch par des références directes à ces objets. (TNT-37124)

## Modifications de l’adresse IP pour les serveurs de traitement des flux Recommendations (16 mars 2021)

Les [!DNL Target Recommendations] adresses IP du serveur de traitement de flux ont été mises à jour le 16 mars 2021. Pour plus d’informations, voir [Adresses IP utilisées par les serveurs de traitement de flux de Recommendations](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

## Target Standard/Premium 21.2.1 (9 mars 2021)

Cette version de maintenance comprend les améliorations, correctifs et modifications suivants.

Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

* Augmentation de la taille d’offre autorisée (TGT-38304) :

   | Type | Limite précédente | Nouvelle limite |
   | --- | --- | --- |
   | HTML | 256 Ko | 1024 Ko |
   | Offres visuelles de l’interface utilisateur de Cible | 64 Ko | 1 024 Ko pour chaque expérience |
   | Via l’API | 512 Ko | 1024 Ko |

* [!UICONTROL Les rapports ] d’analyse de la personnalisation pour les activités de la Cible  automatique (AT) et de l’ [!UICONTROL Automated Personalization] (AP) sont désormais générés quotidiennement. Vous pouvez choisir un rapport qui fournit [!UICONTROL Segments automatisés] ou [!UICONTROL Attributs importants] pour les 15, 30 et 60 derniers jours. Les options 45 et 90 jours ont été supprimées pour permettre aux autres paramètres de fenêtre de recherche de s’exécuter quotidiennement. (TGT-39472)
* Correction d’un problème en raison duquel la dépendance actuelle ne s’affichait pas lorsque les clients cliquaient sur [!UICONTROL Modifier la dépendance] sur une page [!UICONTROL Objectifs et paramètres] d’une activité. (TGT-39340)
* Correction d’un problème lors de l’actualisation de la [!UICONTROL bibliothèque d’Audiences] d’un espace de travail. Avant l’actualisation, les audiences de l’espace de travail actuellement sélectionné s’affichaient. Après l’actualisation, l’[!UICONTROL espace de travail par défaut] et ses audiences s’affichaient. L’espace de travail actuel et ses audiences persistent après l’actualisation. (TGT-38871)
* Correction d’un problème lors de la copie d’une activité [!UICONTROL Recommendations] et de la modification ultérieure de l’activité d’origine en modifiant sa séquence de critères. La modification de la séquence de critères dans l’activité d’origine a également été incorrectement appliquée à l’activité copiée. (TGT-39155)
* Correction d’un problème en raison duquel un nombre incorrect de produits s’affichait pour les exclusions [!UICONTROL Recommendations]. (TGT-39599)

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la Bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Vue des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans ces notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [ de mise à jour des ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour du produit prioritaire Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
