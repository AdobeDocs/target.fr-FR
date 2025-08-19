---
keywords: mvt, test multivarié, rapport contribution des emplacements
description: Découvrez comment utiliser le rapport Contribution de l’emplacement pour les activités Adobe [!DNL Target] [!UICONTROL Experience Targeting] qui présentent les performances de chaque élément et de chaque offre.
title: Comment utiliser le rapport [!UICONTROL Location Contribution] pour les activités [!UICONTROL Multivariate Test] ?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 35%

---

# Rapport [!UICONTROL Location Contribution] (MVT)

Le rapport [!UICONTROL Location Contribution] affiche les performances de chaque élément et de chaque offre.

La partie supérieure du rapport présente la mesure, les dates de début et de fin et l’audience utilisées dans le rapport. Vous pouvez modifier n’importe lequel de ces facteurs.

>[!NOTE]
>
>Gardez à l’esprit les informations suivantes lorsque vous utilisez le rapport [!UICONTROL Location Contribution] :
>
>* Les sélecteurs d’audience et de mesures ne sont disponibles que si [!DNL Analytics] est utilisé comme source de création de rapports (A4T).
>
>* Les données du rapport [!UICONTROL Location Contribution] sont récupérées à partir du serveur principal [!DNL Target], même si l’activité est configurée pour utiliser [!UICONTROL Analytics as the reporting source] (A4T).
>
>* Les données du rapport [!UICONTROL Location Contribution] sont récupérées pour l’environnement de « production », même si un autre environnement par défaut est défini au niveau du compte [!DNL Target].

Le rapport [!UICONTROL Location Contribution] comprend deux tableaux.

Le premier tableau présente l’influence relative de chaque élément. Ce tableau indique les éléments pour lesquels vous avez ajouté des offres qui génèrent le plus de conversions.

Le deuxième tableau fournit un rapport au niveau de l’offre. Il présente le taux de conversion, l’effet élévateur et la confiance pour chaque offre dans chaque élément. Ce tableau vous aide à déterminer les offres les plus réussies. La deuxième colonne affiche des valeurs pour la mesure sélectionnée (taux de conversion, Recettes par visiteur (RPV), Valeur de commande moyenne (AOV), commandes ou engagement) de l’offre ainsi qu’une normalisation.

## Vidéo de formation : Création d’un test multivarié

Cette vidéo explique comment créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target]. Le rapport Contribution de l’emplacement est décrit à partir de la :45 8.

>[!VIDEO](https://video.tv.adobe.com/v/30144?captions=fre_fr)
