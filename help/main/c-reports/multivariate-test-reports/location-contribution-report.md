---
keywords: mvt, test multivarié, rapport contribution des emplacements
description: Découvrez comment utiliser le rapport Contribution des emplacements pour les activités d’Adobe [!DNL Target] [!UICONTROL Experience Targeting] qui affichent les performances de chaque élément et de chaque offre.
title: Comment utiliser le rapport [!UICONTROL Location Contribution] pour les activités [!UICONTROL Multivariate Test] ?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 39%

---

# [!UICONTROL Location Contribution] rapport (MVT)

Le rapport [!UICONTROL Location Contribution] montre les performances de chaque élément et de chaque offre.

La partie supérieure du rapport présente la mesure, les dates de début et de fin et l’audience utilisées dans le rapport. Vous pouvez modifier n’importe lequel de ces facteurs.

>[!NOTE]
>
>Gardez à l’esprit les informations suivantes lorsque vous utilisez le rapport [!UICONTROL Location Contribution] :
>
>* Les sélecteurs d’audience et de mesure ne sont disponibles que si [!DNL Analytics] est utilisé comme source des rapports (A4T).
>
>* Les données du rapport [!UICONTROL Location Contribution] sont extraites du serveur principal [!DNL Target] même si l’activité est configurée pour utiliser [!UICONTROL Analytics as the reporting source] (A4T).
>
>* Les données du rapport [!UICONTROL Location Contribution] sont récupérées pour l’environnement &quot;Production&quot; même si un autre environnement par défaut est défini au niveau du compte [!DNL Target].

Le rapport [!UICONTROL Location Contribution] comprend deux tableaux.

Le premier tableau présente l’influence relative de chaque élément. Ce tableau indique les éléments pour lesquels vous avez ajouté des offres qui génèrent le plus de conversions.

![Rapport Contribution des emplacements dans Adobe Target](/help/main/c-reports/assets/locationcontributiontop.png)

Le deuxième tableau fournit un rapport au niveau de l’offre. Il présente le taux de conversion, l’effet élévateur et la confiance pour chaque offre dans chaque élément. Ce tableau vous aide à déterminer les offres qui remportent le plus de succès. La deuxième colonne affiche des valeurs pour la mesure sélectionnée (taux de conversion, Recettes par visiteur (RPV), Valeur de commande moyenne (AOV), commandes ou engagement) de l’offre ainsi qu’une normalisation.

![Rapport Contribution des emplacements dans Adobe Target](/help/main/c-reports/assets/locationcontributionbottom.png)

## Vidéo de formation : création d’un test multivarié ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer un test multivarié à l’aide du processus assisté Target à trois étapes. Le rapport Contribution des emplacements est décrit dans la vidéo à partir de 08:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
