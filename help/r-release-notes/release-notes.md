---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js afin dʼéviter tout problème potentiel avec vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## [!DNL Target Standard/Premium] 21.9.1 (14 septembre 2021)

Cette version de maintenance comprend les améliorations, modifications et correctifs suivants.

* Correction de problèmes qui empêchaient les clients de se connecter au [!UICONTROL compositeur d’expérience visuelle] (VEC) en raison de nouvelles stratégies de sécurité pour les cookies tiers dans certains navigateurs Web. Ce problème a été abordé dans &quot;Pages ne se chargeant pas dans le compositeur d’expérience visuelle (VEC) ou le compositeur d’expérience avancé (EEC) lors de l’utilisation de Google Chrome version 80+&quot; dans [Dépannage des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Correction d’un problème en raison duquel les noms d’offre dans le VEC affichaient le chemin de l’offre au lieu du nom convivial de l’offre. (TGT-41300)
* Les noms d’expérience sont désormais pris en compte dans [!DNL Analysis Workspace] pour les activités A4T (TGT-38674).
* Correction d’un problème dans [!DNL Recommendations] en raison duquel les modifications d’ID d’entité étaient appliquées par erreur dans une promotion d’une activité dupliquée à l’activité d’origine. (TGT-41482)
* Correction d’un problème qui empêchait l’affichage correct du bouton &quot;Modifier les critères&quot; sur la page [!UICONTROL Expériences] pour les activités [!DNL Recommendations] dans le compositeur d’expérience visuelle. (TGT-39512)
* Correction d’un problème qui empêchait la synchronisation des activités lorsqu’elles étaient dupliquées et copiées dans un espace de travail de test. (TGT-40686)
* Correction d’un problème qui empêchait les modifications apportées à un sélecteur avec [fragments d’expérience](/help/c-experiences/c-manage-content/aem-experience-fragments.md) lors de l’utilisation de &quot;[!UICONTROL Insérer après]&quot; dans le VEC. (TGT-41802)
* Correction d’un problème qui empêchait l’envoi du contenu JSON vide dans une offre au serveur principal. [!DNL Target] envoie maintenant l’objet JSON même s’il est vide. (TGT-41555)
* Correction d’un problème en raison duquel les rapports [!DNL Analytics] hérités s’ouvraient au lieu de [!DNL Analysis Workspace] lorsque les clients cliquaient sur &quot;[!UICONTROL Afficher dans Analytics]&quot; lors de l’affichage d’un rapport. (TGT-41867)
* Ajout d’une clarification supplémentaire au message de l’interface utilisateur affiché lorsqu’un client tente de sélectionner [!DNL Analytics] comme source des rapports (A4T) pour une activité [!UICONTROL Automated Personalization]. Le message indique que &quot;[!DNL Target] est la seule source prise en charge pour les activités [!UICONTROL Automated Personalization]&quot;. (TGT-41954)
* Ajout d’une clarification supplémentaire au message d’erreur lorsque les clients tentent de séparer les hôtes avec &quot;nouvelle ligne&quot; au lieu de virgules. (TGT-40671)
* Correction d’un problème en raison duquel les dates &quot;[!UICONTROL Dernière mise à jour]&quot; de certaines activités différaient de celles de l’interface utilisateur en anglais pour les clients espagnols et japonais (lors de l’affichage de l’interface utilisateur en espagnol et en japonais). (TGT-38980)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
