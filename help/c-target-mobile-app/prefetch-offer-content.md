---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
title: Prérécupération du contenu des offres
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 4f877bf6a0bd73e2d29c2d41ab64dc2a39c61a31

---


# Prérécupération du contenu des offres{#prefetch-offer-content}

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. L’ensemble du contenu est récupéré et mis en cache lors de l’appel de prérécupération. Ce contenu sera ensuite récupéré du cache pour tous les appels futurs contenant le contenu mis en cache pour cette mbox spécifique.

Tenez compte des restrictions suivantes lorsque vous utilisez la méthode de prérécupération avec les SDK mobiles iOS et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.
* La fonctionnalité de prérécupération n’est pas prise en charge pour les méthodes d’affectation  automatique et de ciblage  automatique du trafic, pour les types d’activité Personnalisation [!UICONTROL automatisée ou] [!UICONTROL Recommandations ou pour les offres de recommandations au sein d’une activité A/B ou XT.][](/help/c-recommendations/recommendations-as-an-offer.md)

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **** iOS :  [Prérécupérer le contenu de l’offre dans iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) dans l’aide *du SDK iOS* Mobile Services.
* **** Android :  [Prérécupérer le contenu de l’offre dans Android](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) dans l’aide *du SDK Android* Mobile Services.
