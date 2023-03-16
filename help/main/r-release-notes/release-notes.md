---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 207095a1db483abcc59f7806a67e559ee8694397
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 64%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 22.15.1 (8 et 9 mars 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **8 mars**: Région des Amériques
* **9 mars**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **9 mars**: Région Asie-Pacifique (APAC)

>[!NOTE]
>
>En raison de problèmes qui ont été corrigés depuis, les mesures &quot;Optimized A4T&quot; pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]&quot;La fonctionnalité qui a été publiée les 8 et 9 mars a été temporairement supprimée. Après d’autres tests internes, la fonctionnalité sera de nouveau disponible au cours des prochaines semaines.

Cette version comprend les correctifs suivants :

* Mises à jour pour la création de composants web personnalisés avec le [!UICONTROL Compositeur d’expérience visuelle] (VEC) :

   * Correction de la sélection des éléments DOM fantômes dans le VEC en améliorant le processus de création afin qu’il n’y ait aucune dépendance sur la variable [!DNL Target] type d’implémentation lors de la création de la racine fantôme. Désormais, la sélection des éléments DOM fantômes dans le VEC doit fonctionner pour n’importe quel site web.
   * Correction d’un problème qui empêchait le chargement des éléments de HTML à l’aide de #Shadow DOM dans le VEC. (TGT-35801)
   * Correction de problèmes du compositeur d’expérience visuelle avec SPA sites web à l’aide de ShadowDOM. (TGT-43169)
   * Correction d’un problème lié à l’objectif d’optimisation : &quot;clic sur un élément&quot; qui n’identifiait pas correctement le sélecteur CSS dans ShadowDOM.

>[!NOTE]
>
>Pour garantir la diffusion des modifications créées dans le compositeur d’expérience visuelle, assurez-vous que vous utilisez une [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) avec une version supérieure à 2.8.

**Problème connu**: Suivi des clics sur un élément racine fantôme lors de l’utilisation de [!DNL Adobe Experience Platform Web SDK] ne fonctionne pas correctement. (TNT-47012)

## at.js version 2.10.2 (7 mars 2023)

* Correction d’un problème en raison duquel la variable `trackEvent` pour toujours renvoyer une erreur.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/main/r-release-notes/target-release-notes.md). |
