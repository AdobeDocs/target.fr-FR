---
keywords: adresse IP;adresses IP;liste blanche;liste autorisée;pare-feu;recommandations;flux;serveurs;adobe experience cloud;recommendations
description: Vue d’une liste d’adresses IP utilisées dans les  [!DNL Target] serveurs de traitement de flux Recommendations pour vous aider à configurer votre pare-feu afin d’autoriser les adresses IP provenant des serveurs d’Adobe.
title: Quelles adresses IP les serveurs de traitement de flux de Recommendations utilisent-ils ?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 24%

---

# ![PREMIUM](/help/assets/premium.png) Adresses IP utilisées par les serveurs de traitement de flux de Recommendations

Liste des adresses IP utilisées dans les serveurs de traitement des flux [!DNL Adobe Target] [!DNL Recommendations] pour vous aider à configurer votre pare-feu afin d’autoriser les adresses IP provenant de serveurs d’Adobe.

[!DNL Target]  Recommandations Les activités utilisent les hôtes AWS suivants lors de l’accès aux serveurs FTP des clients :

| Emplacement | Hôte |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target] [!UICONTROL Les ] API Recommendations utilisent également les mêmes hôtes AWS.

>[!NOTE]
>
>Ces adresses IP ont été mises à jour pour la dernière fois le 16 mars 2021. Auparavant, les serveurs accédant aux serveurs FTP se trouvaient dans le bloc CIDR d’adresse IP 192.243.242.0/24. Les serveurs hébergeant les API Recommendations se trouvaient dans le bloc CIDR d&#39;adresse IP 192.243.224.0/20.
