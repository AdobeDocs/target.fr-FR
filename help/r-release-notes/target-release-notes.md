---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
title: Notes de mise à jour préalable Adobe Target
feature: Release Notes
translation-type: tm+mt
source-git-commit: ec8aa3c2f6eca3c1f8002526cc2d2f15365f9671
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 19%

---


# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 12 janvier 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites.
>
>* **Adobe Experience Platform Web SDK** : Le  [!UICONTROL Adobe Experience Platform Web ] SDK vous permet d’interagir avec les différents services du  [!DNL Experience Cloud] (y compris  [!DNL Target]) via Adobe Experience Edge Network. Si vous choisissez de migrer vers [!DNL Adobe Experience Platform Web SDK], voir [Qu&#39;est-ce que le SDK Web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), dans le *Guide du SDK Web*. Voir [Présentation de la Cible](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) pour obtenir des informations spécifiques à [!DNL Target].
   >
   >
* **at.js** : La bibliothèque JavaScript at.js offre de nombreux avantages par rapport à mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page. Si vous choisissez de migrer vers at.js, voir [Fonctionnement d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [Adobe Target Skill Builder : Chat de développeur, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Bien que mbox.js soit actuellement pris en charge (jusqu’au 31 mars 2021), nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. En déplaçant tous les clients vers le [!UICONTROL Adobe Experience Platform Web SDK] ou at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre le support que vous attendez de l&#39;Adobe.

## Target Standard/Premium 21.1.1 (19 janvier 2021)

Cette version de maintenance comprend les améliorations, correctifs et modifications suivants.

Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

* Ajouté un avertissement lors de la sélection d’une mesure [!DNL Adobe Analytics] lors de l’utilisation de [!UICONTROL Analytics en tant que source du rapports] (A4T) dans une activité [!UICONTROL Cible automatique]. [!UICONTROL Les modèles de ] ciblage automatique sont optimisés pour fonctionner avec les mesures binaires (basées sur la conversion). La sélection d’une mesure continue, telle que les recettes, peut avoir des résultats sous-optimaux et les rapports [!UICONTROL Custom Insights] peuvent ne pas être précis. (TGT-38926)
* Ajouté une icône d’état dans le rapport [!UICONTROL Synthèse des Cibles automatiques] pour les activités [!UICONTROL Cible automatique] qui utilisent A4T. L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle d’apprentissage automatique personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle. (TGT-38925)
* Les rapports [!UICONTROL Segments automatisés] et [!UICONTROL Attributs importants] pour les activités [!UICONTROL Cible automatique] qui utilisent les mesures de conversion A4T et [!DNL Analytics] sont générés et apparaissent de la même manière que lorsque vous utilisez [!DNL Target] comme source de rapports. (TGT-38931)
* Ajouté une option de filtrage d’environnement à la liste [!UICONTROL Recommendations] [!UICONTROL Collections]. (TGT-38353)
* Correction d’un problème en raison duquel un nombre de produits incorrect s’affichait dans les collections [!UICONTROL Recommendations]. (TGT-39162)
* Ajouté un filtre [!UICONTROL Dernière mise à jour] à [!UICONTROL Recommendations] [!UICONTROL Recherche catalogue]. (TGT-38340)
* Correction d’un problème dans [!UICONTROL Recommendations] en raison duquel la page [!UICONTROL Créer une séquence] se bloquait après modification de la verticale du secteur. (TGT-38160)
* Correction d’un problème qui empêchait l’enregistrement de l’activité si Device Co-op était activé et que l’utilisateur passait de [!DNL Target] en tant que source du rapports à [!DNL Analytics] (A4T). (TGT-38163)
* Correction d’un problème qui empêchait les utilisateurs de supprimer une audience d’une offre dans une activité [!UICONTROL Automated Personalization] (AP). (TGT-39058)
* Correction d’un problème en raison duquel une période incorrecte (dates de début et de fin) s’affichait dans les cartes [!UICONTROL Informations sur l’Audience] pour certains clients. (TGT-39150)
* Correction d’un problème qui empêchait certains clients d’afficher la liste des activités dans l’[!UICONTROL Espace de travail par défaut]. (TGT-38526)
* Augmentation à 1 Mo des limites de taille pour les offres de l&#39;interface utilisateur et de l&#39;API [!DNL Target]. (TGT-38304)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
