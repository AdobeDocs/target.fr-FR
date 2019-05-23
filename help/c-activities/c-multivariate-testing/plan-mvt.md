---
description: Les tests multivariés requièrent une planification pour pouvoir créer un test réussi.
keywords: test multivarié;mvt;plan mvt;plan de test mutlivarié
seo-description: Les tests multivariés requièrent une planification pour pouvoir créer un test réussi.
seo-title: Planification d’un test multivarié
solution: Target
title: Planification d’un test multivarié
uuid: f286d08a-e11d-4a39-8c62-3eba99885299
translation-type: tm+mt
source-git-commit: 5405e95cf516f973b69834ac114a1e351cd3040a

---


# Planification d’un test multivarié{#plan-a-multivariate-test}

Les tests multivariés requièrent une planification pour pouvoir créer un test réussi.

Les tests multivariés requièrent un volume de trafic suffisant pour générer des résultats pertinents. Avant de configurer votre test, vous devez connaître le volume de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions. La connaissance de ces informations réduit la probabilité de concevoir un test avec des exigences qui dépassent le trafic de votre site.

Il est préférable que les éléments soient indépendants les uns des autres. Par exemple, ne vérifiez pas la mise en page et le contenu dans le même test.

Examinez le code HTML des pages que vous voulez tester. Assurez-vous que les éléments HTML de votre site ne comportent pas d’ID DOM en double. Les ID en double peuvent être la conséquence de la diffusion du même élément de contenu à plusieurs emplacements.

Prévoyez de tester les éléments de votre page qui sont susceptibles de produire des résultats significatifs. Par exemple, une bannière ou une image d’un héros va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’éléments ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les éléments plus importants de la page.

Enfin, avant de créer votre test, vous devez créer le contenu que vous souhaitez tester. Comprenez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Vidéo de formation : Création de tests multivariés (9:25)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du flux de travaux Target à trois étapes.

* Définir et créer un test multivarié
* Créer un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)