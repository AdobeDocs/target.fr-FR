---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: 44d9cd4de7ff2064e6005a4d7ece7f37194fbf2f
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 41%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes liées à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points saillants importants concernant votre mise en œuvre :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.3.2 (10 mars 2026)

**Activités**

+++Afficher les détails

* **Les modifications directes des offres dans l’expérience ne sont pas enregistrées.** Ce correctif résout un problème où les modifications apportées aux offres directes dans une expérience d’activité n’étaient pas enregistrées. Auparavant, lorsque les utilisateurs ouvraient une offre directe, apportaient des modifications et les enregistraient, les modifications semblaient reflétées initialement, mais étaient perdues lors de la réouverture de l’offre. Le correctif garantit que les modifications apportées aux offres directes sont correctement enregistrées et conservées lorsque l’offre est rouverte. (TGT-54653)

+++

**Implémentation**

+++Afficher les détails

* **Activez/désactivez la gestion du scintillement sur l&#39;écran Implémentation.** Un nouveau bouton (bascule) a été ajouté à l’écran [!UICONTROL Implementation] pour contrôler l’activation du paramètre de gestion du scintillement. Ce bouton permet aux administrateurs de configurer la gestion du scintillement directement à partir de l’écran Implémentation . (TGT-52247)

+++

**Aperçu**

+++Afficher les détails

* **Afficher le nom complet de l’audience et de l’expérience dans la page Aperçu .** Cette amélioration met à jour la page [!UICONTROL Overview] pour afficher le nom complet des audiences et des expériences. Auparavant, les noms longs étaient tronqués et pas entièrement visibles, ce qui obligeait les utilisateurs à triple-cliquer pour sélectionner tout le texte pour afficher le nom complet. La mise à jour garantit que les noms complets de l’audience et de l’expérience sont visibles, ce qui facilite l’identification et la révision des configurations d’activité. (TGT-53323)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Afficher les détails

* **Les modifications du compositeur d’expérience visuelle ne sont pas répercutées sur les sites utilisant Shadow DOM (composants web Salesforce Lightning).** Ce correctif résout un problème en raison duquel les modifications apportées dans Adobe Target (telles que les changements de couleur CTA) n’étaient pas enregistrées ou répercutées sur le site actif pour les sites basés sur Salesforce utilisant les composants web Lightning (LWC). Le CMS n’acceptait pas les mises à jour des activités Target, et ce problème est survenu de manière cohérente entre les tests A/B et d’autres types d’activités. (TGT-54059)

+++

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
| [Notes De Mise À Jour De Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
