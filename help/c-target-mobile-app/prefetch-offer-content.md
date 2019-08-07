---
description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
keywords: offre;prérécupération;iOS;android; sdk ; mobile ; sdk mobile
seo-description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
seo-title: Prérécupération du contenu des offres
solution: Target
title: Prérécupération du contenu des offres
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 95bf4b2070cc2de235ac09ac164f0f9ec48dd6cd

---


# Prérécupération du contenu des offres{#prefetch-offer-content}

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. Tout le contenu est récupéré et mis en cache pendant l'appel de prérécupération. Ce contenu est récupéré du cache pour tous les appels futurs contenant du contenu mis en cache pour le nom de mbox spécifié.

Tenez compte des éléments suivants lorsqu'ils sont utilisés dans la méthode de prérécupération avec les SDK mobiles ios et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.
* La fonctionnalité de prérécupération des kits SDK mobiles ios et Android n'est pas prise en charge pour les types d'activité Ciblage automatique, Affectation automatique et Personnalisation automatisée.

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **iOS :**[Prérécupération du contenu des offres sous iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html) dans le guide du *kit iOS SDK 4.x pour les solutions Experience Cloud*.
* **Android :**[Prérécupération du contenu des offres sous Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html) dans le guide du *kit Android SDK 4.x pour les solutions Experience Cloud*.
