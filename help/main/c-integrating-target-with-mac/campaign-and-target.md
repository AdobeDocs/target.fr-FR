---
keywords: Aperçu et référence
description: Découvrez comment utiliser Adobe [!DNL Target] avec Adobe Campaign pour optimiser le contenu des emails.
title: Comment intégrer  [!DNL Target]  à Adobe Campaign ?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 32%

---

# Intégration de [!DNL Target] avec Adobe Campaign

Utilisez [!DNL Target] avec [!DNL Adobe Campaign] pour optimiser le contenu des emails.

Pour optimiser le contenu de vos emails, vous pouvez créer une offre de redirection dans [!DNL Target], puis utiliser [!DNL Adobe Campaign] pour gérer les offres par email. Par exemple, vous pouvez afficher différentes offres pour les destinataires masculins et féminins.

L’intégration se produit à l’ouverture du courrier électronique. Lorsque le client ouvre l’e-mail, un appel est effectué à [!DNL Target] et une version dynamique du contenu s’affiche. Le contenu est une image statique compatible avec tous les navigateurs. [!DNL Target] suit la réaction à l’offre au niveau de l’audience ou de la session et ces données sont disponibles dans les rapports [!DNL Target].

[!DNL Target] peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l’identifiant du visiteur dans [!DNL Target] (soumis à l’approbation légale)
* Données de [!DNL Campaign] Datamart

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Le suivi n’est pas consolidé dans [!DNL Adobe Campaign].
* Pas d’expérience utilisateur unifiée.

Utilisez [!DNL Target] et [!DNL Campaign] pour configurer différentes parties de l’intégration :

* La boîte brute et l’expérience dans [!DNL Target]

>[!NOTE]
>
>Lors de l’utilisation d’une rawbox et de [!DNL Target], consultez l’avis de sécurité important sous [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à Target](/help/main/administrating-target/hosts.md#allowlist).

* La diffusion dans [!DNL Campaign]

## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Avant d’utiliser [!DNL Adobe Campaign] pour configurer vos offres par e-mail ciblées, configurez les éléments suivants dans [!DNL Target] :

* Deux offres de redirection ou plus [!DNL Target]

  Voir [Créer une offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* Une activité [!DNL Target] avec une expérience pour chaque offre et la [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) souhaitée.

  Voir [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Démarrez l’activité dans [!DNL Target] avant de configurer la partie [!DNL Campaign] de l’intégration.

## Inclure une offre [!DNL Target] dans un email [!DNL Adobe Campaign] {#section_B201BBE27A704E18AF0D553F35695837}

1. Créez un email dans [!DNL Adobe Campaign].
1. Dans les propriétés de l&#39;email, cliquez sur **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. Dans [!DNL Campaign], définissez le serveur Edge [!DNL Target] que vous utilisez pour contrôler l’activité et le nom du client.
1. Indiquez le compte externe utilisé pour le [!DNL Adobe Experience Cloud] afin que vous puissiez accéder aux ressources dans le [!DNL Experience Cloud].

Pour plus d&#39;informations, consultez la documentation [!DNL Adobe Campaign].

## Vidéo : Intégrez [!DNL Target] à [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
