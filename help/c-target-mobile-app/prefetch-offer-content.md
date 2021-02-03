---
keywords: offre ; prérécupération ; iOS ; android ; sdk ; mobile ; sdk mobile ; sdk mobile
description: La fonctionnalité de prérécupération d’Adobe Target utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.
title: Prérécupération du contenu des offres
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 60%

---


# Prérécupération du contenu des offres{#prefetch-offer-content}

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. L’ensemble du contenu est récupéré et mis en cache lors de l’appel de prérécupération. Ce contenu sera ensuite récupéré du cache pour tous les appels futurs contenant le contenu mis en cache pour cette mbox spécifique.

Tenez compte des restrictions suivantes lorsque vous utilisez la méthode de prélecture avec les SDK mobiles iOS et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.
* La fonctionnalité de prérécupération n&#39;est pas prise en charge pour les méthodes d&#39;affectation de trafic [!UICONTROL Auto-Allocation] et [!UICONTROL Auto Cible], pour les types d&#39;activité [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations], ou pour les offres de recommandations [dans une activité A/B ou XT](/help/c-recommendations/recommendations-as-an-offer.md).

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **iOS :**  [Prérécupération du contenu des offres dans ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOS dans l’aide *du SDK iOS de* Mobile Services.
* **Android :**  [Prérécupération du contenu des offres dans ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android dans l’aide *du SDK Android* Mobile Services.
