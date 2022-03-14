---
keywords: Aperçu et référence
description: Découvrez comment utiliser Adobe [!DNL Target] avec Adobe Campaign pour optimiser le contenu des emails.
title: Comment intégrer [!DNL Target] avec Adobe Campaign ?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# Intégrer [!DNL Target] avec Adobe Campaign

Utilisation [!DNL Target] avec [!DNL Adobe Campaign] pour optimiser le contenu des emails.

Pour optimiser le contenu de vos emails, vous pouvez créer une offre de redirection dans [!DNL Target], puis utilisez [!DNL Adobe Campaign] pour gérer les offres par e-mail. Par exemple, vous pouvez afficher différentes offres pour les destinataires masculins et féminins.

L’intégration se produit à l’ouverture du courrier électronique. Lorsque le client ouvre l’e-mail, un appel est effectué à la fonction [!DNL Target] et une version dynamique du contenu s’affiche. Le contenu est une image statique compatible avec tous les navigateurs. [!DNL Target] effectue le suivi de la réaction à l’offre au niveau de l’audience ou de la session. Ces données sont disponibles dans les rapports [!DNL Target]

[!DNL Target] peut effectuer le suivi des données suivantes :

* Agent utilisateur
* Adresse IP
* Emplacement géographique
* Segment associé à l’identifiant du visiteur dans [!DNL Target] (sous réserve de l&#39;approbation légale)
* Données provenant de [!DNL Campaign] Datamart

Il existe plusieurs limites :

* Puisque seule une image peut être utilisée, le contenu ne peut pas être personnalisé.
* Le suivi n’est pas consolidé dans [!DNL Adobe Campaign].
* Pas d’expérience utilisateur unifiée.

Utilisez les deux [!DNL Target] et [!DNL Campaign] pour configurer différentes parties de l’intégration :

* La zone brute et l’expérience dans [!DNL Target]

>[!NOTE]
>
>Lors de l’utilisation d’une rawbox et de [!DNL Target], consultez l’avis de sécurité important sous [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à Target](/help/main/administrating-target/hosts.md#allowlist).

* La diffusion dans [!DNL Campaign]

## Avant de commencer {#section_FF19BF1BCA064260930BF6C141313B0E}

Avant d’utiliser [!DNL Adobe Campaign] pour configurer vos offres par e-mail ciblées, configurez les éléments suivants dans la section [!DNL Target]:

* Deux ou plus [!DNL Target] offres de redirection

   Voir [Créer une offre de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] une activité avec une expérience pour chaque offre et la [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md).

   Voir [Redirection vers une URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Lancez l’activité dans [!DNL Target] avant de configurer la variable [!DNL Campaign] de l’intégration.

## Inclure une [!DNL Target] d’une offre [!DNL Adobe Campaign] email {#section_B201BBE27A704E18AF0D553F35695837}

1. Création d’un courrier électronique dans [!DNL Adobe Campaign].
1. Dans les propriétés du courrier électronique, cliquez sur **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique provenant d’Adobe Target]**.
1. Sélectionnez l’image par défaut dans les ressources partagées.
1. Spécifiez l’emplacement (rawbox).
1. Ajoutez tout autre paramètre de décision, comme le sexe du destinataire.
1. Prévisualisez le courrier électronique en sélectionnant au moins un destinataire pour chaque offre (dans ce cas, un homme et une femme).
1. Dans [!DNL Campaign], définissez la variable [!DNL Target] Serveur Edge que vous utilisez pour contrôler l’activité et le nom du client.
1. Indiquez le compte externe utilisé pour la variable [!DNL Adobe Experience Cloud] afin que vous puissiez accéder aux ressources dans la variable [!DNL Experience Cloud].

Pour plus d’informations, reportez-vous à la section [!DNL Adobe Campaign] documentation.

## Vidéo : Intégrer [!DNL Target] avec [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
