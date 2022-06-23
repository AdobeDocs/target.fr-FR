---
keywords: offre;prérécupération;iOS;android;sdk;mobile;sdk mobile
description: Utilisation de l’Adobe [!DNL Target] fonction de prérécupération dans les SDK iOS et Android Mobile pour récupérer le contenu des offres aussi peu de fois que possible en mettant en cache les réponses du serveur.
title: Puis-je prérécupérer le contenu des offres pour les applications mobiles ?
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 54%

---

# Prérécupération du contenu des offres

La fonctionnalité de prérécupération [!DNL Target] utilise les SDK iOS et Android Mobile pour prévisualiser, autant de fois que possible, le contenu des offres, en mettant en cache les réponses du serveur.

Ce processus réduit le délai de chargement, évite la multiplication des appels réseau et permet à [!DNL Target] d’être informé de quelle mbox l’utilisateur de l’application mobile a visité. L’ensemble du contenu est récupéré et mis en cache lors de l’appel de prérécupération. Ce contenu sera ensuite récupéré du cache pour tous les appels futurs contenant le contenu mis en cache pour cette mbox spécifique.

Tenez compte des restrictions suivantes lors de l’utilisation de la méthode de prérécupération avec les SDK mobiles iOS et Android :

* Le contenu de la prérécupération n’est pas conservé d’une exécution à l’autre. Il reste dans le cache tant que l’application est active ou jusqu’à ce que la méthode `clearPrefetchCache()` soit invoquée.

Pour plus d’informations, notamment sur les méthodes de prérécupération, les classes publiques et les échantillons de code, voir :

* **iOS :**  [Prérécupération du contenu des offres dans iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) dans le *Aide du SDK iOS pour Mobile Services*.
* **Android :**  [Prérécupération du contenu des offres dans Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) dans le *Aide du SDK Android pour Mobile Services*.
