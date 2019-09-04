---
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
keywords: service à la clientèle;cname;programme de certification;nom canonique;cookies;certification; amc ; certificat géré Adobe
seo-description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
seo-title: CNAME et Adobe Target
solution: Target
title: CNAME et Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME et Adobe Target {#cname-and-adobe-target}

Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans [!DNL Target]. Pour mieux gérer les problèmes de blocage des publicités ou les stratégies de cookie liées à ITP, un CNAME est utilisé pour que les appels soient dirigés vers un domaine détenu par le client plutôt qu'un domaine détenu par Adobe.

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Créez des enregistrements CNAME (voir les instructions ci-dessous).

   Lors de la réception du ticket, un spécialiste FPSSL doit vous fournir une paire d'enregistrements CNAME. Ces enregistrements doivent être configurés sur le serveur DNS de votre entreprise pour qu'Adobe puisse acheter le certificat en votre nom.

   Les CNAMES sont similaires à l'exemple suivant :

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. Lorsque ces CNAME sont en place, Adobe travaille avec digicert pour acheter et installer un certificat sur les serveurs de production d'Adobe.

1. Après avoir exécuté les tâches précédentes, vous devez mettre à jour le `serverDomain` nouveau CNAME dans at. js.
