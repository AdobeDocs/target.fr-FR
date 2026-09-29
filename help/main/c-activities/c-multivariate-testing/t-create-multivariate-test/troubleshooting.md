---
keywords: Tests multivariés;dépannage;dépannage;mvt
description: Explorez les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation des activités [!UICONTROL &#x200B; Test multivarié &#x200B;] (MVT) dans [!DNL Adobe Target], ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés à un [!UICONTROL &#x200B; test multivarié &#x200B;] ?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
TQID: 'https://experienceleague.adobe.com/O9lmC1PmICPCOxcMDYVcSdpRoM-bqwKR-79deFIG2mg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 21%
---
# Résolution des problèmes liés aux activités [!UICONTROL test multivarié]

Cet article contient des suggestions pour résoudre certains problèmes qui peuvent se produire lors de la conception d’un [!UICONTROL test multivarié] (MVT) dans [!DNL Adobe Target].

* Lors de la modification d’une activité, si vous avez utilisé des mesures basées sur [!DNL Analytics] et que la suite de rapports ne se charge pas (affichage à double flèche), basculez les mesures vers des mesures [!DNL Target], puis revenez à la mesure basée sur [!DNL Analytics]. La suite de rapports devrait maintenant se charger.
* Si vous apportez des modifications à un test en cours d’exécution, vous pouvez réinitialiser le test et ses données.

  [!DNL Target] permet de modifier une activité active. La modification d’une activité en cours peut réinitialiser le test et les rapports peuvent ne pas reconnaître certaines des modifications.

  Il est prudent d’apporter de petites modifications, telles que la modification d’offres de texte ou HTML existantes.

  Les actions spécifiques qui réinitialisent les noms d’expérience et les rapports incluent :

  * Ajout d’un nouvel emplacement
  * Suppression d’un emplacement
  * Ajout de nouvelles offres ou suppression d’offres d’un emplacement existant
