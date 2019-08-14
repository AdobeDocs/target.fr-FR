---
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
keywords: service à la clientèle;cname;programme de certification;nom canonique;cookies;certification
seo-description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
seo-title: CNAME et Adobe Target
solution: Target
title: CNAME et Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 72260f1bf82dfeab2582add69111439498ad5eb8

---


# CNAME et Adobe Target{#cname-and-adobe-target}

Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target. Pour mieux gérer les problèmes de blocage des publicités, un CNAME est utilisé pour que les appels soient dirigés vers un domaine détenu par le client plutôt qu'un domaine détenu par Adobe.

Pour demander la prise en charge du CNAME dans Target, procédez comme suit :

1. Faites une  [demande d’assistance clientèle](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) concernant la prise en charge du CNAME pour vos appels Adobe Target.
1. Prenez part au programme [Adobe Managed Certificate (AMC) program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) (en anglais) et suivez les étapes d’implémentation présentes dans le guide des [!DNL Adobe Analytics]*cookies propriétaires*.

   Le programme AMC vous aide à surmonter les efforts et la confusion auxquels doivent faire face les clients lors de l’implémentation de cookies prioritaires. Une fois que vous avez pris part au programme, Adobe procède à l’achat et à la remise du certificat à installer sur des serveurs sécurisés.

   >[!NOTE]
   >
   >Vous devez configurer le CNAME avant de participer au programme AMC.

1. Après avoir exécuté les tâches précédentes, vous devez mettre à jour le `serverDomain` nouveau CNAME dans at. js.

## Vidéo de formation : Cookies propriétaires et utilisation des certificats gérés Adobe

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. La discussion du programme Certificat géré Adobe commence à 10:21.

[Adobe Analytics : Cookies propriétaires et utilisation des certificats gérés Adobe](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)
