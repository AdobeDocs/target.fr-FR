---
description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
keywords: offre;prérécupération;iOS;android;sdk;mobile;sdk mobile
seo-description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
seo-title: Prérécupération du contenu des offres
solution: Target
title: Prérécupération du contenu des offres
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# Prérécupération du contenu des offres{#prefetch-offer-content}

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. Tout le contenu est récupéré et mis en cache pendant l’appel de prérécupération. Ce contenu est récupéré du cache pour tous les appels futurs qui contiennent du contenu mis en cache pour le nom de mbox spécifié.

Tenez compte des points suivants lorsque vous utilisez la méthode de prérécupération avec les SDK mobiles iOS et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.
* La fonctionnalité de prérécupération dans les SDK mobiles iOS et Android n’est pas prise en charge pour les types d’activité Ciblage automatique, Affectation automatique et Personnalisation automatisée.

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **** iOS :  [Prérécupérer le contenu de l’offre dans iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) dans l’aide *du SDK iOS* Mobile Services.
* **** Android :  [Prérécupérer le contenu de l’offre dans Android](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) dans l’aide *du SDK Android* Mobile Services.
