---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: d45a38376ebe98d212fba3097159a7b89b792c53

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour pour les API de , les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plateformes sont également incluses, le cas échéant.

>[!NOTE]
>
>* **dépréciation** de mbox.js : Le 30 août 2020, le Adobe  ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles le   l’exécution de . Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Voir *Adobe  Skill Builder : Chat du développeur, migrez le fichier mbox.js de Adobe vers at.js* ci-dessous pour plus d’informations sur l’inscription à une discussion de développeur à venir sur ce sujet.
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons pas fourni de mises à jour de fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et  les  l’assistance que vous attendez d’Adobe.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Adobe  Skill Builder : Conversation avec les développeurs, migrer le Adobe  mbox.js vers at.js {#skill-builder}

Rejoignez David Son, chef de produit d’Adobe, car il présente les avantages de la migration de mbox.js vers at.js. Découvrez les dernières mises à jour d’at.js, ses fonctionnalités améliorées et la manière dont elles s’alignent avec les tendances plus larges du paysage technologique, ainsi que quelques conseils pratiques pour vous assurer d’extraire autant de valeur du lorsque vous mbox.js mbox.js vers at.js. Les développeurs d’ Adobe ne manqueront pas cette fonctionnalité !

Mardi 5 mai, de 8:00 à 9:00 (HAP)

[Inscrivez-vous maintenant ici !](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Target Standard/Premium 20.4.1 (27 avril 2020)

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème en raison duquel un périphérique et un type de navigateur étaient incorrectement qualifiés pour un  . (TGT-36266)
* Correction d’un problème en raison duquel les données du rapport ne s’affichaient pas sur des écrans de moins de 963 pixels de large. (TGT-36549)
* Correction d’un problème en raison duquel les rapports Personnalisation automatique ne s’affichaient pas correctement. (TGT-36619)
* Correction d’un problème en raison duquel certaines options du compositeur d’expérience visuelle ne s’affichaient pas correctement. (TGT-36571)
* Correction d’un problème dans l’interface utilisateur  de l’ qui entraînait l’affichage du contenu modifié par d’autres  de recommandations  leaprès qu’un utilisateur ait remplacé le contenu dans une seule expérience. (TGT-36053 et TGT-36894)
* Correction d’un problème qui empêchait certains utilisateurs de supprimer des éléments d’un catalogue de recommandations. (TGT-36455)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer les critères de recommandations sur un  de plusieurs pages. (TGT-36249)
* Correction d’un problème en raison duquel les boutons radio de la source de données comportementales disparaissaient lors de la modification des critères pour une deuxième fois consécutive. (TGT-36796)
* Correction d’un problème d’affichage en raison duquel un algorithme de recommandations affichait &quot;Récupération des résultats&quot; pendant une période prolongée. (TGT-36550 et TGT-36551)
* Mise à jour de nombreuses chaînes d’interface localisées dans différentes langues.

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour -  API côté serveur côté](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur  Adobe. |
| [Notes de mise à jour -  SDK Node.js du](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js du Adobe. |
| [Notes de mise à jour - SDK Java](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe . |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js du Adobe. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour d’](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
