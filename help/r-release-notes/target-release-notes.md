---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des prochaines versions de la Cible Adobe DNL.
title: Notes de mise à jour préliminaire d’Adobe Cible
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 14%

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 4er mai 2020**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!NOTE]
>
>* **Dépréciation** de mbox.js : Le 30 août 2020, Adobe Cible ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités de Cible sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Voir *Adobe Cible Skill Builder : Chat de développeur, migrez le fichier mbox.js de la Cible Adobe vers at.js* ci-dessous pour plus d’informations.
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et offre l’assistance dont vous avez besoin de la part d’Adobe.


## Adobe Cible Skill Builder : Chat de développeur, migrer le fichier mbox.js de la Cible Adobe vers at.js {#skill-builder}

Avec la prochaine désapprobation de mbox.js, le 30 août 2020, David Son, responsable de produit Adobe Cible, a récemment hébergé une discussion pour les développeurs afin de discuter des avantages de la migration de mbox.js vers at.js. Pendant les 30 prochains jours, vous pouvez [vue l’enregistrement](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)du webinaire.

## Target Standard/Premium 20.4.1 (6 mai 2020)

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème en raison duquel un périphérique et un type de navigateur étaient incorrectement qualifiés pour une audience. (TGT-36266)
* Correction d’un problème en raison duquel les données du rapport ne s’affichaient pas sur des écrans de moins de 963 pixels de large. (TGT-36549)
* Correction d’un problème en raison duquel les rapports Personnalisation automatique ne s’affichaient pas correctement. (TGT-36619)
* Correction d’un problème en raison duquel les mesures incompatibles étaient sélectionnées dans les activités d’affectation automatique et de Cible automatique qui utilisaient Analytics pour la Cible (A4t). (TGT-36646)
* Correction d’un problème en raison duquel certaines options du compositeur d’expérience visuelle ne s’affichaient pas correctement. (TGT-36571)
* Correction d’un problème dans l’interface utilisateur de la Cible en raison duquel d’autres prévisualisations d’offre de recommandations affichaient le contenu modifié lorsqu’un utilisateur remplaçait le contenu dans une seule expérience. (TGT-36053 et TGT-36894)
* Correction d’un problème qui empêchait certains utilisateurs de supprimer des éléments d’un catalogue de recommandations. (TGT-36455)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer des critères de recommandations sur une activité de plusieurs pages. (TGT-36249)
* Correction d’un problème en raison duquel les boutons radio de la source de données comportementales disparaissaient lors de la modification des critères pour une deuxième fois consécutive. (TGT-36796)
* Correction d’un problème d’affichage en raison duquel un algorithme de recommandations affichait des &quot;résultats de récupération&quot; pendant une période prolongée. (TGT-36550 et TGT-36551)
* Mise à jour de nombreuses chaînes d’interface localisées dans différentes langues.

## Modifications de l’API d’état du lot de Profils v2 (12 mai 2020)

Avec la version du 4 mai, l’état du lot de Profils ne retournera que les données d’échec au niveau des lignes (les données de réussite ne seront pas renvoyées). Les ID de profil en échec seront renvoyés par l&#39;API à l&#39;avenir.

Les réponses précédentes et les nouvelles API sont les suivantes :

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**Actuellement, nous voyons la réponse comme suit :**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**Après le 4 mai, la réponse sera :**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
