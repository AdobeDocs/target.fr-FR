---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les dernières versions ou les versions à venir de  Adobe DNL.
title: 'Notes de mise à jour préliminaire d’Adobe '
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e9a6545ab65cf1214977f8fa472904527c18a04d

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations sur la version préliminaire. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 24 avril 2020**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!NOTE]
>
>* **dépréciation** de mbox.js : Le 30 août 2020, le Adobe  ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles le   l’exécution de . Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Voir *Adobe  Skill Builder : Chat du développeur, migrez le fichier mbox.js de Adobe vers at.js* ci-dessous pour plus d’informations sur l’inscription à une discussion de développeur à venir sur ce sujet.
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons pas fourni de mises à jour de fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et  les  l’assistance que vous attendez d’Adobe.


## Adobe  Skill Builder : Conversation avec les développeurs, migrer le Adobe  mbox.js vers at.js {#skill-builder}

Rejoignez David Son, chef de produit d’Adobe, car il présente les avantages de la migration de mbox.js vers at.js. Découvrez les dernières mises à jour d’at.js, ses fonctionnalités améliorées et la manière dont elles s’alignent avec les tendances plus larges du paysage technologique, ainsi que quelques conseils pratiques pour vous assurer d’extraire autant de valeur du lorsque vous mbox.js mbox.js vers at.js. Les développeurs d’ Adobe ne manqueront pas cette fonctionnalité !

Mardi 5 mai, de 8:00 à 9:00 (HAP)

[Inscrivez-vous maintenant ici !](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1 (27 avril 2020)

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème en raison duquel un périphérique et un type de navigateur étaient incorrectement qualifiés pour un  . (TGT-36266)
* Correction d’un problème en raison duquel les données du rapport ne s’affichaient pas sur des écrans de moins de 963 pixels de large. (TGT-36549)
* Correction d’un problème en raison duquel les rapports Personnalisation automatique ne s’affichaient pas correctement. (TGT-36619)
* Correction d’un problème en raison duquel les mesures incompatibles étaient sélectionnées dans l’ d’affectation automatique et de automatique  qui utilisaient Analytics pour le(A4t). (TGT-36646)
* Correction d’un problème en raison duquel certaines options du compositeur d’expérience visuelle ne s’affichaient pas correctement. (TGT-36571)
* Correction d’un problème dans l’interface utilisateur  de l’ qui entraînait l’affichage du contenu modifié par d’autres  de recommandations  leaprès qu’un utilisateur ait remplacé le contenu dans une seule expérience. (TGT-36053 et TGT-36894)
* Correction d’un problème qui empêchait certains utilisateurs de supprimer des éléments d’un catalogue de recommandations. (TGT-36455)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer les critères de recommandations sur un  de plusieurs pages. (TGT-36249)
* Correction d’un problème en raison duquel les boutons radio de la source de données comportementales disparaissaient lors de la modification des critères pour une deuxième fois consécutive. (TGT-36796)
* Correction d’un problème d’affichage en raison duquel un algorithme de recommandations affichait &quot;Récupération des résultats&quot; pendant une période prolongée. (TGT-36550 et TGT-36551)
* Mise à jour de nombreuses chaînes d’interface localisées dans différentes langues.

## Modifications de l’API v2 de l’état du lot  du (4 mai 2020)

Avec la version du 4 mai, l’état du lot de  ne renverra que les données d’échec au niveau de la ligne (les données de réussite ne seront pas renvoyées). Les ID de  d’échec seront renvoyés par l’API.

Les réponses précédentes et nouvelles de l’API sont les suivantes :

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
