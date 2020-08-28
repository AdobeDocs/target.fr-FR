---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 81b9735ea1fa6c42aa9c73565efd68a4d474622c
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 31%

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

## at.js 2.3.2 (24 juillet 2020)

Cette version d’at.js est une version de maintenance et comprend les correctifs suivants :

* Correction d’un bogue en raison duquel un script ou un code ajoutait la propriété par défaut à la fenêtre ou au document.

## Target Standard/Premium 20.7.1 (27 juillet 2020)

Les modifications suivantes ont été apportées à cette version :

### [!UICONTROL Actualisation de l’interface utilisateur de la section Administration]

Nous réécrivons progressivement l’ensemble de l’ [!DNL Target] interface utilisateur à l’aide d’une nouvelle pile technologique afin de pouvoir offre des performances améliorées, réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et améliorer l’expérience utilisateur sur l’ensemble du produit. La première section actualisée est la section [!UICONTROL Configuration] , qui a été renommée [!UICONTROL Administration].

Dans le cadre de cette actualisation, vous pourrez exécuter facilement de nombreuses actions à l’aide des pages de la section [!UICONTROL Administration] , telles que :

* Téléchargez le dernier fichier at.js depuis l’onglet [!UICONTROL Implémentation] (**[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**).
* Personnalisez vos paramètres at.js et vérifiez facilement vos modifications (**[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**).
* Modifiez les paramètres de rapports améliorés, tels que la devise et le fuseau horaire par défaut, les adresses IP à exclure du rapports, etc. (**[!UICONTROL Administration]** > **[!UICONTROL Rapports]**)
* Obscurcir les adresses IP du visiteur pour des raisons de confidentialité (**[!UICONTROL Administration]** > **[!UICONTROL Mise en oeuvre]**)
* Vue de la liste existante des utilisateurs par espace de travail et de leurs rôles, avant de les gérer dans Adobe Admin Console (**[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**).
* Recherchez et filtrez tous les tableaux de la section [!UICONTROL Administration] .

Pour plus d’informations, voir Présentation [de la](/help/administrating-target/administrating-target.md)gestion des Cibles.

### Améliorations, correctifs et modifications

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait la conservation des préférences du site après l’actualisation. (TGT-37239)
* Correction d’un problème en raison duquel [!UICONTROL Insérer après] > [!UICONTROL Image] ne fonctionnait pas correctement avec les images SVG (Scalable Vector Graphics). (TGT-37242)
* Correction d’un problème qui empêchait la suppression de brouillons d’activités pour les utilisateurs dotés du rôle [!UICONTROL Editeur] . (TGT-37358)
* Correction d’un problème qui empêchait les utilisateurs de modifier une activité lorsque [!UICONTROL Tous mes espaces de travail] étaient sélectionnés. (TGT-37276)

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
