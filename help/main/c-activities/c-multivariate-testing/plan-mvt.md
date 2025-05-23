---
keywords: test multivarié;mvt;plan mvt;plan de test multivarié
description: Découvrez comment planifier un [!UICONTROL Multivariate Test] dans  [!DNL Adobe Target] afin de pouvoir créer un test réussi.
title: Comment planifier un [!UICONTROL Multivariate Test] ?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 64%

---

# Planification d’un [!UICONTROL Multivariate Test]

Les activités [!UICONTROL Multivariate Tests] (MVT) dans [!DNL Adobe Target] nécessitent une planification avant de pouvoir créer un test réussi.

Le test multivarié nécessite un trafic suffisant pour générer des résultats utiles. Avant de configurer votre test, vous devez connaître le volume de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions. Le fait d’avoir ces informations permet de réduire la probabilité de concevoir un test avec des exigences qui dépassent le trafic de votre site.

Les éléments doivent être indépendants les uns des autres. Par exemple, ne vérifiez pas la disposition et le contenu dans le même test.

Examinez le code d’HTML des pages que vous souhaitez tester. Assurez-vous que les éléments HTML de votre site ne comportent pas d’ID DOM en double. Les ID en double peuvent avoir pour conséquence la diffusion du même élément de contenu vers plusieurs emplacements.

Prévoyez de tester les éléments de votre page qui sont susceptibles de produire des résultats significatifs. Par exemple, une bannière ou une image principale va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’éléments ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les éléments plus importants de la page.

Enfin, avant de créer votre test, vous devez créer le contenu que vous souhaitez tester. Comprenez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Vidéo de formation : création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du processus assisté en trois étapes [!DNL Target].

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/30144?captions=fre_fr)
