---
keywords: multivariate test;mvt;mvt plan;multivariate test plan
description: Les tests multivariés dans Adobe Target requièrent une planification pour pouvoir créer un test réussi.
title: Planification d’un test multivarié dans Adobe Target
feature: mvt
uuid: f286d08a-e11d-4a39-8c62-3eba99885299
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 97%

---


# Planification d’un test multivarié{#plan-a-multivariate-test}

[!UICONTROL Les tests multivariés] (MVT) dans [!DNL Adobe Target] requièrent une planification pour pouvoir créer un test réussi.

MVT requièrent un volume de trafic suffisant pour générer des résultats pertinents. Avant de configurer votre test, vous devez connaître le volume de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions. La connaissance de ces informations réduit la probabilité de concevoir un test avec des exigences qui dépassent le trafic de votre site.

Il est préférable que les éléments soient indépendants les uns des autres. Par exemple, ne vérifiez pas la mise en page et le contenu dans le même test.

Examinez le code HTML des pages que vous voulez tester. Assurez-vous que les éléments HTML de votre site ne comportent pas d’ID DOM en double. Les ID en double peuvent avoir pour conséquence la diffusion du même élément de contenu vers plusieurs emplacements.

Prévoyez de tester les éléments de votre page qui sont susceptibles de produire des résultats significatifs. Par exemple, une bannière ou une image principale va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’éléments ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les éléments plus importants de la page.

Enfin, avant de créer votre test, vous devez créer le contenu que vous souhaitez tester. Comprenez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Vidéo de formation : Création de tests multivariés (9:25) ![Balise de didacticiel](/help/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du flux de travaux Target à trois étapes.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)