---
keywords: Aperçu et référence
description: Utilisez Target avec Adobe Campaign pour optimiser le contenu de vos courriers électroniques.
title: Intégration de à Adobe Campaign
feature: Integrations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 51%

---


# Intégration de Target à Adobe Campaign{#integrate-target-with-adobe-campaign}

Utilisez [!DNL Target] avec [!DNL Adobe Campaign] pour optimiser le contenu du courrier électronique.

Pour optimiser le contenu de votre courrier électronique (par exemple, pour afficher différentes offres pour les destinataires hommes et femmes), vous pouvez créer une offre de redirection dans [!DNL Target], puis utiliser [!DNL Adobe Campaign] pour gérer les offres de courrier électronique.

L’intégration se produit à l’ouverture du courrier électronique. Lorsque le client ouvre le courrier électronique, un appel est lancé à [!DNL Target] et une version dynamique du contenu s’affiche. Le contenu est une image statique compatible avec tous les navigateurs. [!DNL Target] effectue le suivi de la réaction à l’offre au niveau de l’audience ou de la session. Ces données sont disponibles dans les rapports [!DNL Target]

Target peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l’identifiant du visiteur dans Target (sous réserve d’approbation légale)
* Données de Datamart [!DNL Campaign]

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Le suivi n&#39;est pas consolidé dans [!DNL Adobe Campaign].
* Pas d’expérience utilisateur unifiée.

   Vous devez utiliser à la fois [!DNL Target] et [!DNL Campaign] pour configurer différentes parties de l’intégration :

   * La rawbox et l’expérience dans [!DNL Target]
   >[!NOTE]
   >
   >Lors de l’utilisation d’une rawbox et de [!DNL Target], consultez l’avis de sécurité important sous [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à la Cible](/help/administrating-target/hosts.md#allowlist).

   * La diffusion de [!DNL Campaign]



## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Avant d&#39;utiliser [!DNL Adobe Campaign] pour configurer vos offres de messagerie ciblées, configurez les éléments suivants dans [!DNL Target] :

* Deux ou plusieurs offres de redirection [!DNL Target]

   Voir [Création d’une offre de redirection](/help/c-experiences/c-manage-content/offer-redirect.md).
* Une activité Target avec une expérience pour chaque offre et la [mesure de succès](/help/c-activities/r-success-metrics/success-metrics.md) souhaitée.

   Voir [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Début l’activité dans [!DNL Target] avant de configurer la partie [!DNL Campaign] de l’intégration.

## Inclusion d’une offre Target dans un courrier électronique Adobe Campaign  {#section_B201BBE27A704E18AF0D553F35695837}

1. Créez un courrier électronique dans [!DNL Adobe Campaign].
1. Dans les propriétés du courrier électronique, cliquez sur **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique provenant d’Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. Dans [!DNL Campaign], définissez le serveur Edge [!DNL Target] que vous utilisez pour contrôler l&#39;activité et le nom du client.
1. Spécifiez le compte externe utilisé pour le [!DNL Adobe Experience Cloud] afin que vous puissiez accéder aux ressources du [!DNL Experience Cloud].

Pour plus d&#39;informations, consultez la documentation [!DNL Adobe Campaign].
