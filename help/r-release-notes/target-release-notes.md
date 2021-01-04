---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
title: Notes de mise à jour préalable Adobe Target
feature: null
translation-type: tm+mt
source-git-commit: 10d8f47dcca1d09654405c8382c70adc0b828e50
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 10%

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 27 octobre 2020**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe a de nouveau nommé un leader dans le Quadrant Magique Gartner pour les moteurs** de personnalisation : L&#39;Adobe a de nouveau été nommé Leader dans le troisième rapport annuel Gartner Magic Quadrant for Personalization Moteurs, 2020. Le Quadrant magique Gartner pour les moteurs de personnalisation a évalué les fournisseurs selon 15 critères qui se répartissent en deux catégories : l&#39;exhaustivité de la vision et la capacité d&#39;exécuter. [Lisez-le sur le blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/) The Adobe.
   >
   >
* **Fin de vie** de mbox.js : Le 31 mars 2021, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages dont les activités de Cible s’exécutent en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir [Fonctionnement d’At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [Adobe Target Skill Builder : Chat de développeur, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d&#39;informations, voir [Annonces de Cible](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.10.1 (27 octobre 2020)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| [Prise de décision sur périphérique](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | La prise de décision sur périphérique permet à la fois aux marketeurs et aux développeurs de produits de proposer des expériences et une personnalisation pilotée par l’apprentissage automatique depuis l’appareil d’un utilisateur, d’un canal à l’autre, à une latence proche de zéro.<br>La vitesse et les performances sont importantes, en ce qui concerne les connaissances des clients et la satisfaction des utilisateurs.<br>La prise de décision sur périphérique vous permet de compiler les instructions de personnalisation et d’expérimentation clés dans les activités A/B Test and Experience Targeting (XT) en &quot;artefacts d’optimisation :&quot; objets JSON chargés sur les périphériques client via le CDN. Et comme la prise de décision sur le périphérique se connecte nativement aux produits [!DNL Adobe Experience Cloud], les utilisateurs [!DNL Target] obtiennent une analyse rapide et des itérations d’expérience plus rapides.<br>Pour plus d’informations, voir Prise de décision[ sur le ](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md)périphérique. |

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait [!UICONTROL Intervalle de fiabilité de l’effet élévateur moyen] et [!UICONTROL Confiance] de s’afficher dans le rapports [!DNL Auto-Target] pour la ligne [!UICONTROL Total]. Les mesures s’affichaient correctement pour toutes les expériences individuelles. (TGT-37301)
* Correction d’un problème qui affectait [!DNL Adobe Target Premium] le rapports [!UICONTROL Cible automatique] des utilisateurs à partir du 15 septembre à 14 h 30. (HAP) au 6 octobre, de 9 h 25 (PDT). Lors de l’affichage de rapports pour les mesures de conversion affectées (configurées à l’aide de l’option &quot;[!UICONTROL Affichage d’une page]&quot; ou &quot;[!UICONTROL En cliquant sur mbox]&quot;), les taux de conversion sont incorrectement signalés. Il n&#39;y a pas de problème de diffusion connu pour le moment. Pour plus d’informations sur la resynchronisation et la correction de votre rapports, voir [rapports de Cible automatique](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) sous *Problèmes résolus* dans *Problèmes connus et problèmes résolus*.
* Ajouté une colonne [!UICONTROL Dernière mise à jour à] sélectionnable dans la table [!UICONTROL Recherche catalogue] et un filtre [!UICONTROL Dernière mise à jour à]. Cette amélioration vous permet de gagner du temps et d’obtenir des efforts car vous n’avez pas à ouvrir chaque élément pour savoir quand il a été mis à jour pour la dernière fois et vous pouvez filtrer par date la dernière mise à jour des éléments.

   ![Illustration Dernière mise à jour à la colonne et au filtre](/help/r-release-notes/assets/column-and-filter.png)

* Des mises à jour ont été apportées pour aider à rendre l&#39;interface utilisateur de la Cible conforme aux [Lignes directrices sur l&#39;accessibilité du contenu Web](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 Niveau A et aux critères de réussite AA (WCAG 2.0 AA). (TGT-34384 et TGT-24679)
* Amélioration de la stratégie de sécurité de contenu (CSP). (TGT-37035)
* Ajout d’un moyen de spécifier le code client en tant que paramètre pour les clients utilisant CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] la documentation se déplace vers  [!DNL Experience League]. En octobre, toutes les notes de mise à jour, articles, vidéos et didacticiels passeront de leur emplacement actuel à `docs.adobe.com` à [!DNL Experience League]. Ce déplacement permet de s’assurer que tous les contenus d’apprentissage, d’auto-assistance, d’activation et de communauté sont diffusés à partir d’un seul emplacement. Lorsque ce changement se produit, il n&#39;y a rien à faire, car tous les liens seront redirigés vers [!DNL Experience League]. Nous mettrons à jour les notes de mise à jour au début du découpage.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
