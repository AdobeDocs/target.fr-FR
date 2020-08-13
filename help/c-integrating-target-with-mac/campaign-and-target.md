---
keywords: Overview and Reference
description: Utilisez Target avec Adobe Campaign pour optimiser le contenu de vos courriers électroniques.
title: Intégration de Target à Adobe Campaign
feature: campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# Intégration de Target à Adobe Campaign{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

L’intégration se produit à l’ouverture du courrier électronique. When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. Le contenu est une image statique compatible avec tous les navigateurs. [!DNL Target] effectue le suivi de la réaction à l’offre au niveau de l’audience ou de la session. Ces données sont disponibles dans les rapports [!DNL Target]

Target peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l’identifiant du visiteur dans Target (sous réserve d’approbation légale)
* Data from [!DNL Campaign] Datamart

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Tracking is not consolidated in [!DNL Adobe Campaign].
* Pas d’expérience utilisateur unifiée.

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   * La rawbox et l’expérience dans [!DNL Target]
   >[!NOTE]
   >
   >Lors de l’utilisation d’une rawbox et [!DNL Target]d’une autre, consultez l’important avis de sécurité sous [Créer des listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à la Cible](/help/administrating-target/hosts.md#allowlist).

   * The delivery in [!DNL Campaign]



## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* Une activité Target avec une expérience pour chaque offre et la [mesure de succès](/help/c-activities/r-success-metrics/success-metrics.md) souhaitée.

   Voir [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## Inclusion d’une offre Target dans un courrier électronique Adobe Campaign {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. Dans les propriétés du courrier électronique, cliquez sur **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique provenant d’Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.
