---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
title: Notes de mise à jour préalable Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 036b7e07efb0d814a9ec7e398f87371033c77eb8
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 15%

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 7 octobre 2020**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe a de nouveau nommé un leader dans le Quadrant Magique Gartner pour les moteurs** de personnalisation : L&#39;Adobe a de nouveau été nommé Leader dans le troisième rapport annuel Gartner Magic Quadrant for Personalization Moteurs, 2020. Le Quadrant magique Gartner pour les moteurs de personnalisation a évalué les fournisseurs selon 15 critères qui se répartissent en deux catégories : l&#39;exhaustivité de la vision et la capacité d&#39;exécuter. [Lisez-le sur le blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)The Adobe.
   >
   >
* **Fin de vie** de mbox.js : Le 18 janvier 2021, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 18 janvier 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages dont les activités de Cible s’exécutent en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir [Fonctionnement d’At.js et](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) [Adobe Target Skill Builder : Messagerie instantanée des développeurs, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d’informations, voir Annonces [de](/help/r-release-notes/target-announcements.md)Cible.


## Target Standard/Premium 20.10.1 (27 octobre 2020)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| Décisions sur périphérique | Grâce aux décisions sur périphérique, les marketeurs et les développeurs de produits peuvent expérimenter et personnaliser l’apprentissage automatique depuis l’appareil d’un utilisateur, sur plusieurs canaux, à une latence proche de zéro.<br>La vitesse et les performances sont importantes, en ce qui concerne les connaissances des clients et la satisfaction des utilisateurs. Les décisions sur périphérique permettent aux spécialistes du marketing, et désormais aux développeurs de produits, de tester et d’optimiser des expériences directement depuis un périphérique utilisateur, en réduisant les temps de décision et de chargement à presque zéro pour les expériences contextuelles en temps réel.<br>Les décisions sur périphérique vous permettent de compiler toutes les instructions de personnalisation et d’expérimentation sur des &quot;artefacts d’optimisation&quot;, qui sont chargés sur les périphériques client. Ces artefacts de latence zéro permettent aux spécialistes du marketing de personnaliser individuellement, de recibler leurs comportements et de formuler des recommandations sur les produits et le contenu en temps réel, tout en donnant aux développeurs et aux propriétaires de produits un accès direct au code pour tester les expériences des utilisateurs et les lancements de cible et de phase des produits, en les affinant en temps réel. Et comme les décisions sur périphérique se connectent nativement à [!DNL Adobe Experience Cloud] des produits, [!DNL Target] les utilisateurs obtiennent une analyse rapide et des itérations d’expérience plus rapides. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
