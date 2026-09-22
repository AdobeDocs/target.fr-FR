---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ[!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’[!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’[!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e7d752d7b77f6c167878f1b3679d118c2b44a31f
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 36%
---
# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 26.9.5 (21 septembre 2026)

**[!UICONTROL Analytics for Target]**

+++Afficher les détails

* **Lien de rapport A4T non généré dans [!DNL Target]’interface utilisateur**. Pour les activités [!DNL A4T], le lien du rapport n’a pas été généré dans la section **[!UICONTROL Rapports]**, même si les données du rapport sous-jacent étaient visibles dans les deux interfaces utilisateur [!DNL Target] et [!DNL Adobe Analytics]. (TGT-56247)

+++

## [!DNL Target Standard/Premium] 26.9.4 (17 septembre 2026)

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* Contrôle **[!UICONTROL Insérer avant] inaccessible pour les [!DNL Experience Fragments] sur l’élément de page le plus haut**. Dans le compositeur d’expérience visuelle, la sélection de l’élément le plus haut sur une page a fait défiler la page vers le haut, ce qui a provoqué le rendu du contrôle **[!UICONTROL Insérer avant]** au-dessus de la fenêtre visible, à un endroit où il n’a pas pu être sélectionné. (TGT-55829)

+++

## [!DNL Target Standard/Premium] 26.9.3 (16 septembre 2026)

**[!UICONTROL Création de rapports]**

+++Afficher les détails

* **Valeurs [!UICONTROL Lift] et [!UICONTROL Confiance] manquantes dans certains [!DNL A4T Auto-Target] rapports**. Pour les activités [!DNL A4T Auto-Target] utilisant l’objectif d’optimisation **[!UICONTROL Maximiser le taux de conversion des visites]**, la mesure de rapport **[!UICONTROL Ma mesure de Principal]** par défaut n’a pas été résolue correctement, laissant **[!UICONTROL Effet élévateur]** et **[!UICONTROL Degré de confiance]** vides. (TGT-56137)

+++

**[!UICONTROL Analytics for Target]**

+++Afficher les détails

* Le champ **[!UICONTROL Reporting Source] est désormais en lecture seule pour les activités en direct sans accès [!DNL Analytics]**. Auparavant, lorsque le propriétaire d’une activité active n’avait pas accès à [!DNL Adobe Analytics], le champ **[!UICONTROL Source de création de rapports]** et son champ associé restaient modifiables. (TGT-56089)

+++

## [!DNL Target Standard/Premium] 26.9.2 (8 septembre 2026)


**[!UICONTROL Recommandations]**

+++Afficher les détails

* **[!DNL New]’interface utilisateur code incorrectement les URL de flux**. Lors de la création d’un flux de recommandations à partir d’une URL dans la nouvelle interface [!DNL Target], l’URL du flux était codée de manière incorrecte, ce qui entraînait l’échec de la création du flux avec une erreur inconnue. (TGT-56084)

+++

**[!UICONTROL Création de rapports]**

+++Afficher les détails

* **Le rapport Segments automatisés n’affiche pas systématiquement les valeurs d’attribut**. Le rapport Segments automatisés affiche de manière incohérente les valeurs d’attribut et les plages pour les activités [!DNL Automated Personalization] et [!DNL Auto-Target]. Certains segments automatisés n’affichaient que le nom de l’attribut au lieu de la valeur ou de la plage associée. (TGT-55855)

+++

## [!DNL Target Standard/Premium] 26.9.1 (1er septembre 2026)

**[!UICONTROL Audience]**

+++Afficher les détails

* **L’enregistrement d’une activité en cours de copie avec une audience d’activité unique échoue**. Lorsqu’une activité A/B utilise une règle d’audience d’activité seule (étendue localement) et une modification du code personnalisé, sa copie et son enregistrement échouent avec un message d’erreur « ID d’audience non valides ». (TGT-55785)

+++

Serveur MCP **[!DNL Adobe Target]- Outils de recommandations (Beta publique)**

+++Afficher les détails

Le serveur MCP [!DNL Adobe Target] expose désormais des outils de recommandations. Vous pouvez ainsi répertorier, inspecter, créer et mettre à jour des critères, des collections, des conceptions, des promotions et des exclusions, et rechercher le catalogue de produits directement depuis votre assistant d’IA.

Cette fonctionnalité nécessite un client compatible avec Recommendations avec **** ; elle n’est pas disponible sur les comptes non Premium.

Pour plus d’informations, voir [Référence des outils de serveur MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md).

+++

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour et une documentation détaillées via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes De Mise À Jour D’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
