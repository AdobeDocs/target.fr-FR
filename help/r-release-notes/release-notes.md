---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 2aca4490a70c0f6a1f38fab2e62cdab55b5b7a4f
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 34%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!NOTE]
>
>* **Dépréciation** de mbox.js : Le 30 août 2020, Adobe Cible ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités de Cible sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Voir *Adobe Cible Skill Builder : Chat de développeur, migrez le fichier mbox.js de la Cible Adobe vers at.js* ci-dessous pour plus d’informations.
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et le personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et offre l’assistance qu’Adobe vous a proposée.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

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

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur de Cible](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur d’Adobe Cible. |
| [Notes de mise à jour - SDK Node.js Cible](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js de la Cible Adobe. |
| [Notes de mise à jour - Cible Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe Cible. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js d’Adobe Cible. |
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
