---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
title: Notes de version préliminaire d’Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 93ffd24946ad23780b8c141bec79e4492f0e8cda

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 18 février 2020**

>[!NOTE]
>
>* Cet article contient des informations sur la version préliminaire. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
   >
   >
* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].
   >
   >
* À compter du 1er mars 2020, Target désactivera la prise en charge du chiffrement TLS 1.1 et TLS 1.0. Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. Ce changement est nécessaire pour répondre à la norme de conformité de sécurité généralement acceptée de TLS 1.2 ou version ultérieure. Vérifiez la version TLS que vous utilisez actuellement. Si votre version est inférieure à 1.2, implémentez les modifications requises avant le 1er mars 2020 afin de continuer à utiliser Target comme prévu.
   >
   >   
   Pour plus d’informations sur l’impact possible et sur les étapes à suivre pour mettre à jour votre implémentation, voir Modifications [du chiffrement](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).


## Target Standard/Premium 20.2.1 (19 février 2020)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème qui empêchait les clients de sélectionner une collection lors de l’exécution d’une recherche de catalogue. (TGT-36230)
* Correction d’un problème suite auquel un critère créé via l’API, mais non référencé par une activité créée dans l’interface utilisateur de Target, pouvait être supprimé par erreur de l’interface utilisateur. (TGT-35917)
* Amélioration de la sécurité mise en oeuvre dans la stratégie de sécurité du contenu (CSP). (TGT-36190)
* Correction d’un problème en raison duquel &quot;NaN%&quot; s’affichait lors du glissement de la barre de pourcentage Pondération d’attribut vers l’extrême gauche. (TGT-36211)
* Correction d’un problème qui empêchait les clients de modifier l’algorithme dans une activité de personnalisation automatisée (AP) de Forêt aléatoire à Variance résiduelle. (TGT-36321)
* Correction de problèmes de localisation afin que le texte de l’interface utilisateur s’affiche correctement dans différentes langues.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
