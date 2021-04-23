---
keywords: offre ; prérécupération ; iOS ; android ; sdk ; mobile ; sdk mobile ; sdk mobile
description: Utilisez la fonction de prérécupération de l’Adobe [!DNL Target] dans les SDK mobiles iOS et Android pour récupérer le contenu de l’offre le plus souvent possible en mettant en cache les réponses du serveur.
title: Puis-je prérécupérer le contenu des Offres pour les applications mobiles ?
feature: Mise en oeuvre de Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# Prérécupération du contenu des offres

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. L’ensemble du contenu est récupéré et mis en cache lors de l’appel de prérécupération. Ce contenu sera ensuite récupéré du cache pour tous les appels futurs contenant le contenu mis en cache pour cette mbox spécifique.

Tenez compte des restrictions suivantes lorsque vous utilisez la méthode de prélecture avec les SDK mobiles iOS et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.
* La fonctionnalité de prérécupération n&#39;est pas prise en charge pour les méthodes d&#39;affectation de trafic [!UICONTROL Auto-Allocation] et [!UICONTROL Auto Cible], pour les types d&#39;activité [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations], ou pour les offres de recommandations [dans une activité A/B ou XT](/help/c-recommendations/recommendations-as-an-offer.md).

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **iOS :**  [Prérécupération du contenu des offres dans ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOS dans l’aide *du SDK iOS de* Mobile Services.
* **Android :**  [Prérécupération du contenu des offres dans ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android dans l’aide *du SDK Android* Mobile Services.
