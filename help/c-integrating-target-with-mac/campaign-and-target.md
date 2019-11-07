---
keywords: Aperçu et référence
description: Utilisez Target avec Adobe Campaign pour optimiser le contenu de vos courriers électroniques.
title: Intégration de Target à Adobe Campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Intégration de Target à Adobe Campaign{#integrate-target-with-adobe-campaign}

Utilisez Target avec Adobe Campaign pour optimiser le contenu de vos courriers électroniques.

Pour optimiser le contenu de vos courriers électroniques (par exemple, pour afficher des offres différentes selon le sexe du destinataire), vous pouvez créer une offre de redirection dans Target, puis utiliser Adobe Campaign pour gérer les offres par courrier électronique.

L’intégration se produit à l’ouverture du courrier électronique. Quand le client ouvre le courrier électronique, un appel est fait à Target et une version dynamique du contenu apparaît. Le contenu est une image statique compatible avec tous les navigateurs. Target effectue le suivi de la réaction à l’offre au niveau de l’audience ou de la session. Ces données sont disponibles dans les rapports Target.

Target peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l’identifiant du visiteur dans Target (sous réserve d’approbation légale)
* Données provenant du Datamart de Campaign

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Le suivi n’est pas consolidé dans Adobe Campaign.
* Pas d’expérience utilisateur unifiée.

   Vous devez utiliser à la fois Target et Campaign pour configurer certaines parties de l’intégration :

   * La rawbox et l’expérience dans Target
   * La diffusion dans Campaign

## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Avant d’utiliser Adobe Campaign pour configurer vos offres par courrier électronique ciblées, configurez les éléments suivants dans Target :

* Deux offres de redirection Target ou plus

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* Une activité Target avec une expérience pour chaque offre et la [mesure de succès](/help/c-activities/r-success-metrics/success-metrics.md) souhaitée.

   Voir [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Commencez l’activité dans Target avant de configurer la partie Campaign de l’intégration.

## Inclusion d’une offre Target dans un courrier électronique Adobe Campaign {#section_B201BBE27A704E18AF0D553F35695837}

1. Créez un courrier électronique dans Adobe Campaign.
1. Dans les propriétés du courrier électronique, cliquez sur **[!UICONTROL Inclure]** &gt; **[!UICONTROL Image dynamique provenant d’Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. Dans Campaign, définissez le serveur Target Edge utilisé pour contrôler l’activité et le nom du client.
1. Spécifiez le compte externe utilisé pour Experience Cloud afin d’accéder aux ressources dans Experience Cloud.

Pour plus d’informations, consultez la documentation Adobe Campaign.
