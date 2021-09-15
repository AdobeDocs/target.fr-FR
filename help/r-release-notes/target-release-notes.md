---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 41%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 14 septembre 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
