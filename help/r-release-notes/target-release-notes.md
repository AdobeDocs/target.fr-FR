---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: afa370a38921ab76babf5e49edc1e4b23ee807b0
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 24 août 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.8.1 (10 août 2021)

Cette version de maintenance offre de nombreuses améliorations du serveur principal, notamment la modification suivante destinée aux clients :

* Correction d’un problème en raison duquel les rapports d’activités de [!UICONTROL Personnalisation automatique] créées dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] référençaient des offres supprimées dans les rapports. Ce problème entraînait l’affichage du message d’erreur suivant : « Problème lors de la récupération des données de ce rapport. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-41028)

## API de diffusion Target (3 août 2021)

Les améliorations suivantes ont été apportées à cette version :

* La limite des paramètres de mbox a été augmentée à 100 paramètres. Auparavant, les paramètres étaient limités à 50. (TNT-41717)
* La limite pour `categoryId` a augmenté, passant à 256 caractères. Auparavant, la limite était de 128 caractères.
* Les détails [!DNL Adobe Audience Manager] (AAM) suivants ont été ajoutés à l’API de diffusion :

   * UUID AAM : ID AAM interne utilisé pour identifier un utilisateur de manière unique.
   * dataPartnerId : ID d’un partenaire de données.
   * dataPartnerUserId : ID utilisateur fourni par un partenaire de données.

   Auparavant, l’API de diffusion incluait uniquement `dcsLocationHint` et `blob`. (TNT-41644)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
