---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de  [!DNL Target]  ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 14 mars 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.15.1 (8 et 9 mars 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **8 mars** : région Amériques
* **9 mars** : région Europe, Moyen-Orient et Afrique (EMEA)
* **9 mars** : région Asie-Pacifique (APAC)

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

* Correction d’un problème en raison duquel la fonction `trackEvent` renvoyait toujours une erreur.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
