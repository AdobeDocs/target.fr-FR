---
keywords: service à la clientèle;cname;certificate program;canononname;cookies;certificate;amc;adobe managed certificate;canonic name;cookies;certificate;certificate;certificate;amc;adobe managed certificate
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
title: CNAME et Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CNAME et Adobe Target {#cname-and-adobe-target}

Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans [!DNL Target]. Pour gérer au mieux les problèmes de blocage des publicités ou les stratégies de cookies liées au protocole ITP, un CNAME est utilisé de sorte que les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par Adobe.

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Créez des enregistrements CNAME (voir les instructions ci-dessous).

   Une fois le billet reçu, un spécialiste FPSSL doit vous fournir une paire de dossiers CNAME. Ces enregistrements doivent être configurés sur le serveur DNS de votre entreprise pour qu’Adobe puisse acheter le certificat en votre nom.

   Le CNAMES sera similaire à l’exemple suivant :

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. Lorsque ces CNAMES seront en place, Adobe collaborera avec DigiCert pour acheter et installer un certificat sur les serveurs de production d’Adobe.

1. Après avoir effectué les tâches précédentes, vous devez mettre à jour `serverDomain` vers le nouveau CNAME dans at.js.
