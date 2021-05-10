---
keywords: Aperçu et référence
description: Découvrez comment utiliser Adobe [!DNL Target] avec Adobe Campaign pour optimiser le contenu des courriels.
title: Comment puis-je intégrer  [!DNL Target] à Adobe Campaign ?
feature: Intégrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
translation-type: tm+mt
source-git-commit: f3a9ee9827d635d335cb9707d3d92d0de1bd0304
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 36%

---

# Intégrer [!DNL Target] à Adobe Campaign

Utilisez [!DNL Target] avec [!DNL Adobe Campaign] pour optimiser le contenu du courrier électronique.

Pour optimiser le contenu de votre courrier électronique, vous pouvez créer une offre de redirection dans [!DNL Target], puis utiliser [!DNL Adobe Campaign] pour gérer les offres de courrier électronique. Par exemple, vous pouvez afficher différentes offres pour les destinataires hommes et femmes.

L’intégration se produit à l’ouverture du courrier électronique. Lorsque le client ouvre le courrier électronique, un appel est lancé à [!DNL Target] et une version dynamique du contenu s’affiche. Le contenu est une image statique compatible avec tous les navigateurs. [!DNL Target] effectue le suivi de la réaction à l’offre au niveau de l’audience ou de la session. Ces données sont disponibles dans les rapports [!DNL Target]

[!DNL Target] peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l&#39;ID de visiteur dans [!DNL Target] (sous réserve de l&#39;approbation légale)
* Données de Datamart [!DNL Campaign]

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Le suivi n&#39;est pas consolidé dans [!DNL Adobe Campaign].
* Pas d’expérience utilisateur unifiée.

Utilisez [!DNL Target] et [!DNL Campaign] pour configurer différentes parties de l’intégration :

    * La zone brute et l&#39;expérience dans [!DNL Target]
    
    >[!NOTE]
    >
    >Lors de l&#39;utilisation d&#39;une rawbox et [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to Target] (/help/administrating-target/hosts.md#liste autorisée).
    
    * La diffusion dans [!DNL Campaign]

## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Avant d&#39;utiliser [!DNL Adobe Campaign] pour configurer vos offres de messagerie ciblées, configurez les éléments suivants dans [!DNL Target] :

* Deux ou plusieurs offres de redirection [!DNL Target]

   Voir [Création d’une offre de redirection](/help/c-experiences/c-manage-content/offer-redirect.md).

* Activité [!DNL Target] avec une expérience pour chaque offre et la [mesure de réussite ](/help/c-activities/r-success-metrics/success-metrics.md) souhaitée.

   Voir [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Début l’activité dans [!DNL Target] avant de configurer la partie [!DNL Campaign] de l’intégration.

## Inclure une offre [!DNL Target] dans un [!DNL Adobe Campaign] courriel {#section_B201BBE27A704E18AF0D553F35695837}

1. Créez un courrier électronique dans [!DNL Adobe Campaign].
1. Dans les propriétés du courrier électronique, cliquez sur **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique provenant d’Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. Dans [!DNL Campaign], définissez le serveur Edge [!DNL Target] que vous utilisez pour contrôler l&#39;activité et le nom du client.
1. Spécifiez le compte externe utilisé pour le [!DNL Adobe Experience Cloud] afin que vous puissiez accéder aux ressources du [!DNL Experience Cloud].

Pour plus d&#39;informations, consultez la documentation [!DNL Adobe Campaign].

## Vidéo : Intégrer [!DNL Target] à [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
