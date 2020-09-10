---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 00749d54d0416c57364ff648bd0911e636c84bc7
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 26%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>* **adobe a de nouveau nommé un leader dans le Quadrant Magique Gartner pour les moteurs** de personnalisation : L&#39;Adobe a de nouveau été nommé Leader dans le troisième rapport annuel Gartner Magic Quadrant for Personalization Moteurs, 2020. Le Quadrant magique Gartner pour les moteurs de personnalisation a évalué les fournisseurs selon 15 critères qui se répartissent en deux catégories : l&#39;exhaustivité de la vision et la capacité d&#39;exécuter. [Lisez-le sur le blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)The Adobe.
   >
   >
* **Dépréciation** de mbox.js : Le 18 janvier 2021, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 18 janvier 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages dont les activités de Cible s’exécutent en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir [Fonctionnement d’At.js et](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) [Adobe Target Skill Builder : Messagerie instantanée des développeurs, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d’informations, voir Annonces [de](/help/r-release-notes/target-announcements.md)Cible.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Target Standard/Premium 20.8.2 (10 septembre 2020)

| Fonctionnalité | Détails |
| --- | --- |
| ![Emplacements de recommandations de contrôle de badge](/help/assets/premium.png) Premium dans les séquences de critères | Les séquences de critères vous permettent désormais de contrôler le nombre d’emplacements pris en charge par chaque critère de recommandation, ce qui vous permet de mélanger et de faire correspondre différents types d’éléments ou une logique d’algorithme différente.<br>Voir [Création de séquences](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) de critères pour en savoir plus. |

## Target Standard/Premium 20.8.1 (2 septembre 2020)

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème en raison duquel des erreurs s’affichaient lors du chargement des nouvelles pages [!UICONTROL Administration] après le changement d’organisation. (TGT-37730)
* Correction d’un problème d’affichage en raison duquel un code client incorrect s’affichait sur la page [!UICONTROL Administration > Implémentation] . (TGT-37849)
* Correction d’un problème qui empêchait parfois les utilisateurs d’utiliser les fonctions de modification dans le compositeur d’expérience [!UICONTROL visuelle après le chargement du compositeur d’expérience] visuelle. (TGT-37162)
* Correction d’un problème qui empêchait le chargement des pages dans le compositeur d’expérience visuelle et dans le compositeur d’expérience amélioré (CEE) même si l’extension d’assistance du compositeur d’expérience visuelle était installée. Ceci est dû à des modifications dans Google Chrome 80+. Téléchargez la [mise à jour de l’extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)d’assistance du compositeur d’expérience visuelle. (TGT-37893)
* Correction d’un problème qui empêchait parfois les utilisateurs de télécharger at.js à partir de la page [!UICONTROL Administration > Implémentation] après avoir changé d’organisation. (TGT-37668)
* Le bouton de téléchargement d’at.js est maintenant désactivé lors du chargement afin d’empêcher [!DNL Target] l’envoi de plusieurs requêtes si les utilisateurs cliquent plusieurs fois sur le bouton de téléchargement. (TGT-37633)
* Correction d’un problème dans les activités de ciblage [!UICONTROL d’] expérience en raison duquel les expériences affichaient des &quot;résultats d’extraction&quot; pendant une longue période. (TGT-37684)
* Amélioration de la navigation et des fonctionnalités pour les utilisateurs utilisant uniquement le clavier. (TGT-34479 et TGT-34473)
* Des étiquettes Ajoutées dans l’interface utilisateur aident les utilisateurs à utiliser les technologies d’assistance. (TGT-34480)
* Amélioration du message d’erreur lors de la suppression d’une fenêtre d’affichage mobile actuellement utilisée dans une activité. Le message d&#39;erreur indique maintenant : &quot;Cette fenêtre d’affichage est actuellement associée à une ou plusieurs activités. Vous devez supprimer la fenêtre d’affichage de ces activités avant de pouvoir la supprimer.&quot; (TGT-37030)
* Prise en charge Ajoutée dans le compositeur d’expérience visuelle pour autoriser le suivi des clics sur un sélecteur CSS qui correspond à plusieurs éléments de la page. (TGT-37323)
* Correction d’un problème qui empêchait certains utilisateurs d’afficher la liste [!UICONTROL d’Activité] . Le message d’erreur suivant s’affichait : &quot;Impossible de récupérer les suggestions d&#39;URL.&quot; L&#39;erreur s&#39;est produite pour les utilisateurs qui utilisaient les retours chariot dans leur Prénom (Prénom/r/n) dans le système principal d&#39;Adobe. (TGT-37330)
* Correction d’un problème qui empêchait les utilisateurs d’afficher la page d’ [!UICONTROL Activité] si le nom de l’espace de travail (spécifié dans [!UICONTROL Adobe Admin Console for Enterprise]) contenait une apostrophe. (TGT-37709)
* Correction d’un problème dans les activités d’affectation  automatique lors de la sélection des mesures d’optimisation et de conversion en raison duquel un message d’erreur informait incorrectement les utilisateurs de sélectionner une suite de rapports, même si une suite de rapports était déjà spécifiée. (TGT-37689)
* Correction d’un problème en raison duquel les mesures de la page [!UICONTROL Objectifs et paramètres] étaient parfois vides après avoir accédé à la page [!UICONTROL Ciblage] , puis revenaient. (TGT-37691)
* Correction d’un problème en raison duquel une valeur de dernière modification incorrecte était générée pour [!DNL Recommendations] les critères. (TGT-37666)
* Correction d’un problème en raison duquel les ID de mbox s’affichaient dans la liste déroulante Mbox au lieu de noms de mbox. (TGT-37739)

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur Adobe Target. |
| [Notes de mise à jour - SDK Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js Adobe Target. |
| [Notes de mise à jour - Cible Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java Adobe Target. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript Adobe Target at.js. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour des](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
