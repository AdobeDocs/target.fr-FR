---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 26.7.4 (23 juillet 2026)

**Création de rapports**

+++Afficher les détails

* **Graphique de taux de conversion non disponible pour une audience mobile spécifique.** Correction d’un problème en raison duquel le graphique [!UICONTROL Taux de conversion] n’était pas rendu pour certaines audiences mobiles. (TGT-55611)

* **’objectif de conversion « A affiché une mbox » ne fonctionne pas lorsqu’il est sélectionné dans la liste déroulante.** Correction d’un problème en raison duquel la sélection d’une mbox dans la liste déroulante de [!UICONTROL Objectifs et paramètres] pour un objectif de conversion « Affiché comme mbox » enregistrait incorrectement le nom de la mbox, empêchant l’enregistrement des conversions. (TGT-55588)

+++

**Audiences**

+++Afficher les détails

* **Problème de mise en page sur la page Bibliothèque d’audiences.** Correction d’un problème de mise en page qui se produisait lorsque les filtres étaient activés sur la page [!UICONTROL Bibliothèque d’audiences] lorsque la navigation latérale était réduite. (TGT-55502)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* **La version mobile ne se charge pas correctement.** Correction d’un problème en raison duquel le [!UICONTROL compositeur d’expérience visuelle] ne permettait pas d’actualiser la vue, ce qui empêchait son chargement correct. (TGT-54408)

* **Les actions de modification ne fonctionnent pas lorsqu’elles sont modifiées ou supprimées.** Correction d’un problème en raison duquel la modification ou la suppression d’une modification de la vue [!UICONTROL &#x200B; Modifier l’expérience &#x200B;] ne fonctionnait pas. (TGT-55250)

* **Le mode de navigation ne répond pas après le chargement de l’activité.** Correction d’un problème en raison duquel le mode [!UICONTROL Parcourir] ne réagissait plus pour les expériences contenant une modification, empêchant la navigation et la création ultérieures. (TGT-55306)

* **Impossible de sélectionner des éléments dans Salesforce LWC (Shadow DOM).** Correction d’un problème en raison duquel le [!UICONTROL compositeur d’expérience visuelle] ne pouvait pas sélectionner d’éléments imbriqués dans les composants web Salesforce Lightning à l’aide de Shadow DOM, ce qui entraînait une erreur « sélecteur introuvable ». (TGT-54956)

* **Des offres en double sont apparues dans le [!UICONTROL compositeur d’expérience visuelle].** Correction d’un problème en raison duquel les modifications et les offres étaient par intermittence dupliquées dans l’interface utilisateur de création d’activités. (TGT-55685)

+++

**Administration**

+++Afficher les détails

* **L’assistant de génération de contenu a été renommé [!UICONTROL Generate content].** La fonctionnalité de génération de contenu « Assistant IA » a été renommée [!UICONTROL &#x200B; Générer du contenu &#x200B;] sur [!DNL Target] surfaces de l’interface utilisateur. (TGT-55689)

+++

**Recommandations**

+++Afficher les détails

* **Recommandations basées sur la popularité à l’aide d’attributs de profil.** [!DNL Target] prend désormais en charge les recommandations de popularité de regroupement, les Plus consultés et les Meilleurs vendeurs, de manière dynamique en fonction des attributs de profil du visiteur, tels que le pays, la langue préférée ou le niveau d’adhésion. (TAPER-7614)

* **Incohérence de la collection de recommandations entre [!UICONTROL Collections] et la configuration des activités.** Correction d’un problème où une collection [!UICONTROL Recommendations] renvoyait des entités non qualifiantes supplémentaires lors de l’affichage à partir de la configuration de l’activité par rapport à la vue [!UICONTROL Recommendations] > [!UICONTROL Collections]. (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2 (16 juillet 2026)

**Activités**

+++Afficher les détails

* **Informations d’objectif incorrectes sur la page [!UICONTROL Aperçu de l’activité].** Correction d’un problème en raison duquel la page [!UICONTROL Aperçu de l’activité] pour les activités [!DNL Automated Personalization] affichait des objectifs supplémentaires au lieu de l’objectif d’optimisation. (TGT-55553)

* **Écran ne répondant pas lors de la navigation dans les pages en mode [!UICONTROL Parcourir].** Correction d’un problème en raison duquel l’écran ne répondait plus lors de la navigation entre les pages en mode [!UICONTROL Parcourir]. (TGT-55565)

+++

**Page d’accueil**

+++Afficher les détails

* **Modification de l’interface utilisateur pour [!UICONTROL Meilleures performances] et [!UICONTROL Enregistrements].** Mise à jour de l’interface utilisateur pour les utilisateurs les plus performants et enregistrement de l’expérience. (TGT-54975)

+++

**Audiences**

+++Afficher les détails

* **Chaînes non localisées dans la boîte de dialogue [!UICONTROL Créer un script de profil].** Correction d’un problème où les chaînes de la boîte de dialogue [!UICONTROL Créer un script de profil] n’étaient pas localisées. (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1 (9 juillet 2026)

**Activités**

+++Afficher les détails

* **Affichage de la source incohérent sur les pages [!UICONTROL Activités], [!UICONTROL Audiences] et [!UICONTROL Offres].** Correction d’un problème en raison duquel la source s’affichait de manière incohérente sur les pages [!UICONTROL Activités], [!UICONTROL Audiences] et [!UICONTROL Offres]. (TGT-55247)

* **Modifications de la source d’activité lors de la modification via l’interface utilisateur.** Correction d’un problème en raison duquel la modification d’une activité par le biais de l’interface utilisateur modifiait la source de l’activité originale. (TGT-55248)

+++

**Audiences**

+++Afficher les détails

* **Espace de travail par défaut incorrect lors de la modification d’une audience.** Correction d’un problème en raison duquel l’espace de travail par défaut était incorrect après la modification d’une audience. (TGT-55510)

+++

**Création de rapports**

+++Afficher les détails

* **Échec du téléchargement des fichiers CSV pour les rapports de mai.** Correction d’un problème en raison duquel le téléchargement d’un rapport CSV pour le mois de mai échouait. (TGT-55524)

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
