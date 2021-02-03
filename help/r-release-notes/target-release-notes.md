---
keywords: notes de mise à jour ; versions ; mises à jour ; versions futures ; améliorations ; nouvelles fonctionnalités ; correctifs ; mises à jour ; pré-version
description: Quelles sont les fonctionnalités incluses dans la prochaine version ?
title: Notes de mise à jour
feature: Release Notes
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 27%

---


# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 14 janvier 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
