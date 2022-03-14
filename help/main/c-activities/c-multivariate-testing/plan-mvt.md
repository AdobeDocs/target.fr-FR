---
keywords: test multivarié;mvt;plan mvt;plan de test multivarié
description: Découvrez comment planifier des tests multivariés dans Adobe [!DNL Target] vous pouvez ainsi créer un test réussi.
title: Comment planifier un test multivarié ?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 89%

---

# Planification d’un test multivarié

[!UICONTROL Les tests multivariés] (MVT) dans [!DNL Adobe Target] requièrent une planification pour pouvoir créer un test réussi.

MVT requièrent un volume de trafic suffisant pour générer des résultats pertinents. Avant de configurer votre test, vous devez connaître le volume de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions. La connaissance de ces informations réduit la probabilité de concevoir un test avec des exigences qui dépassent le trafic de votre site.

Il est préférable que les éléments soient indépendants les uns des autres. Par exemple, ne vérifiez pas la mise en page et le contenu dans le même test.

Examinez le code HTML des pages que vous voulez tester. Assurez-vous que les éléments HTML de votre site ne comportent pas d’ID DOM en double. Les ID en double peuvent avoir pour conséquence la diffusion du même élément de contenu vers plusieurs emplacements.

Prévoyez de tester les éléments de votre page qui sont susceptibles de produire des résultats significatifs. Par exemple, une bannière ou une image principale va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’éléments ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les éléments plus importants de la page.

Enfin, avant de créer votre test, vous devez créer le contenu que vous souhaitez tester. Comprenez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Vidéo de formation : Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du flux de travaux Target à trois étapes.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
