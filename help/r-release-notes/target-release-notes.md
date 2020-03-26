---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les dernières versions ou les versions à venir de  Adobe DNL.
title: 'Notes de mise à jour préliminaire d’Adobe '
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 25 mars 2020**

>[!NOTE]
>
>* Cet article contient des informations sur la version préliminaire. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
   >
   >
* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].
   >
   >
* **Modifications** de la prise en charge TLS : À compter du 1er mars 2020, les  désactiveront la prise en charge du chiffrement TLS 1.1 et TLS 1.0. Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. Ce changement est nécessaire pour répondre à la norme de conformité de sécurité généralement acceptée de TLS 1.2 ou version ultérieure. Vérifiez la version TLS que vous utilisez actuellement. Si votre version est antérieure à la version 1.2, implémentez les modifications requises avant le 1er mars 2020 afin de continuer à utiliser les  comme prévu.
   >
   >   
   Pour plus d’informations sur l’impact possible et sur les étapes à suivre pour mettre à jour votre implémentation, voir Modifications [du chiffrement](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **dépréciation** de mbox.js : Le 30 août 2020, le Adobe  ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles le   l’exécution de . Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons pas fourni de mises à jour de fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et  les  l’assistance que vous attendez d’Adobe.


##  d’at.js (25 mars 2020)

Les nouvelles versions suivantes des bibliothèques JavaScript at.js du sont disponibles :

* at.js version 2.3.0
* at.js version 1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 mars 2020)

>[!IMPORTANT]
>
>Consultez les informations ci-dessus à propos de la désapprobation de mbox.js.

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait les clients de sélectionner une collection lors de l’exécution d’une recherche de catalogue. (TGT-36230)
* Correction d’un problème suite auquel un critère créé via l’API, mais non référencé par un  créé dans l’interface utilisateur de l’, pouvait être supprimé par erreur de l’interface utilisateur. (TGT-35917)
* Amélioration de la sécurité mise en oeuvre dans la stratégie de sécurité du contenu (CSP). (TGT-36190)
* Correction d’un problème en raison duquel &quot;NaN%&quot; s’affichait lors du glissement de la barre de pourcentage Pondération d’attribut vers l’extrême gauche. (TGT-36211)
* Correction de problèmes  d’interface utilisateur afin que le texte de l’interface dans différentes langues s’affiche correctement.
* Nous avons normalisé le  des mesures disponibles d’Adobe Analytics pour les  de (A4T) en abandonnant les mesures d’Adobe Analytics qui ne sont pas prises en charge dans la version actuelle des API d’Adobe Analytics. Cela nous permettra d’étendre la prise en charge d’A4T dans les prochaines versions des  d’Adobe.

   Les modifications suivantes ont été apportées :

   * &quot;Durée moyenne de consultation de la page&quot; a été remplacé par &quot;Durée moyenne de consultation du site&quot;. Tout   utilisant cette mesure comme mesure de la mesure Objectif principal aura &quot;Durée moyenne de la visite du site&quot; (remarque : mesurée en minutes plutôt qu’en secondes) sélectionnée comme mesure principale de l’objectif lors de la prochaine modification de l’ de .
   * &quot;&quot; a été remplacé par &quot;uniques&quot;. Tout   utilisant cette mesure comme mesure d’objectif principal aura &quot;uniques&quot; sélectionné comme mesure d’objectif principal lors de la prochaine modification du  principal.

* Les mesures suivantes ont été abandonnées et ne peuvent plus être sélectionnées comme mesure d’objectif principal lors de la création d’un nouvel   A4T.

   | Mesure(s) obsolète(s) | Mesure(s) de remplacement suggérée(s) |
   |--- |--- |
   | quotidiens, horaires, mensuels, trimestriels, hebdomadaires, annuels | Visiteurs uniques |
   | Profondeur de visite moyenne | n/d. Non suggéré comme mesure d’objectif principal |
   | Robots | n/d. Non suggéré comme mesure d’objectif principal |
   | Taux de plantage mobile, Durée de session antérieure moyenne mobile, Classement moyen de la boutique d’applications mobiles, Taux de plantage des performances des applications mobiles, Note moyenne de la boutique d’applications mobiles | n/d. Non suggéré comme mesure d’objectif principal |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
