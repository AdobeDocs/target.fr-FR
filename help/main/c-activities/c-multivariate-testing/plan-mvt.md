---
keywords: test multivarié;mvt;plan mvt;plan de test multivarié
description: Découvrez comment planifier un [!UICONTROL test multivarié] in [!DNL Adobe Target] to afin de créer un test réussi.
title: Comment planifier un [!UICONTROL test multivarié] ?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
TQID: https://experienceleague.adobe.com/Fg9jOrPlkLxpbJdG-AKoWHD3YvIGEJPu7Os-RdfXvQA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 295
ht-degree: 63%

---

# Planification d’un [!UICONTROL test multivarié]

Les activités [!UICONTROL Tests multivariés] (MVT) dans [!DNL Adobe Target] nécessitent une planification avant de pouvoir créer un test réussi.

MVT nécessite suffisamment de trafic pour générer des résultats utiles. Avant de configurer votre test, vous devez connaître le volume de trafic que vous obtenez généralement, y compris le nombre d’impressions et de conversions. Ces informations permettent de réduire les risques de conception d’un test dont les exigences excèdent le trafic sur votre site.

Les éléments doivent être indépendants les uns des autres. Par exemple, ne vérifiez pas la disposition et le contenu dans le même test.

Examinez le code HTML pour les pages que vous souhaitez tester. Assurez-vous que les éléments HTML de votre site ne comportent pas d’ID DOM en double. Les ID en double peuvent avoir pour conséquence la diffusion du même élément de contenu vers plusieurs emplacements.

Prévoyez de tester les éléments de votre page qui sont susceptibles de produire des résultats significatifs. Par exemple, une bannière ou une image principale va probablement générer plus de conversions qu’une modification du pied de page. L’inclusion d’éléments ayant moins d’influence dans votre test ne fait qu’augmenter le volume de trafic et le temps requis pour tester les éléments plus importants de la page.

Enfin, avant de créer votre test, vous devez créer le contenu que vous souhaitez tester. Comprenez les différences de contenu pour chaque offre et créez les offres d’image, de texte et HTML que vous prévoyez d’utiliser dans le test.

## Vidéo de formation : Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target].

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
