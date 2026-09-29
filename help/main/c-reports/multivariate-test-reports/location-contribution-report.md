---
keywords: mvt, test multivarié, rapport contribution des emplacements
description: Découvrez comment utiliser le rapport Contribution des emplacements pour les activités Adobe [!DNL Target] [!UICONTROL Ciblage d’expérience] qui présentent les performances de chaque élément et de chaque offre.
title: Comment utiliser le rapport [!UICONTROL Contribution de l’emplacement] pour les activités de [!UICONTROL test multivarié] ?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
TQID: 'https://experienceleague.adobe.com/oS9GtjO8wG2bcAWQWj3IWtwAgtfGHnHMYwPd-8u0zjc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 35%
---
# Rapport [!UICONTROL  Contribution des emplacements ] (MVT)

Le rapport [!UICONTROL  Contribution de l’emplacement ] présente les performances de chaque élément et de chaque offre.

La partie supérieure du rapport présente la mesure, les dates de début et de fin et l’audience utilisées dans le rapport. Vous pouvez modifier n’importe lequel de ces facteurs.

>[!NOTE]
>
>Gardez à l’esprit les informations suivantes lorsque vous utilisez le rapport [!UICONTROL  Contribution de l’emplacement ] :
>
>* Les sélecteurs d’audience et de mesures ne sont disponibles que si [!DNL Analytics] est utilisé comme source de création de rapports (A4T).
>
>* Les données du rapport [!UICONTROL Contribution de l’emplacement] sont récupérées à partir du serveur principal [!DNL Target], même si l’activité est configurée pour utiliser [!UICONTROL Analytics comme source de création de rapports] (A4T).
>
>* Les données du rapport [!UICONTROL  Contribution de l’emplacement ] sont récupérées pour l’environnement de « production », même si un autre environnement par défaut est défini au niveau du compte [!DNL Target].

Le rapport [!UICONTROL  Contribution de l’emplacement ] comprend deux tableaux.

Le premier tableau présente l’influence relative de chaque élément. Ce tableau indique les éléments pour lesquels vous avez ajouté des offres qui génèrent le plus de conversions.

Le deuxième tableau fournit un rapport au niveau de l’offre. Il présente le taux de conversion, l’effet élévateur et la confiance pour chaque offre dans chaque élément. Ce tableau vous aide à déterminer les offres les plus réussies. La deuxième colonne affiche des valeurs pour la mesure sélectionnée (taux de conversion, Recettes par visiteur (RPV), Valeur de commande moyenne (AOV), commandes ou engagement) de l’offre ainsi qu’une normalisation.

## Vidéo de formation : Création d’un test multivarié

Cette vidéo explique comment créer un test multivarié à l’aide du workflow guidé en trois étapes [!DNL Target]. Le rapport Contribution des emplacements est décrit dans la vidéo à partir de 08:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
