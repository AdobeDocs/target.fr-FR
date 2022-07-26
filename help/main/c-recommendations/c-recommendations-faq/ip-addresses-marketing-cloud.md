---
keywords: adresse IP;adresses IP;liste blanche;liste autorisée;pare-feu;recommandations;flux;serveurs;adobe experience cloud;recommendations
description: Consultez une liste d’adresses IP utilisées dans les serveurs de traitement de flux de  [!DNL Target]  Recommendations destinée à vous aider à configurer votre pare-feu afin d’autoriser les adresses IP issues des serveurs Adobe.
title: Quelles adresses IP les serveurs de traitement de flux de Recommendations utilisent-ils ?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Adresses IP utilisées par les serveurs de traitement de flux de Recommendations

Liste d’adresses IP utilisées dans les serveurs de traitement de flux de [!DNL Adobe Target] [!DNL Recommendations] destinée à vous aider à configurer votre pare-feu afin d’autoriser les adresses IP issues des serveurs Adobe.

Les activités [!DNL Target] [!UICONTROL Recommendations] utilisent les hôtes AWS suivants lors de l’accès aux serveurs FTP des clients :

| Emplacement | Hôte |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

Les API [!DNL Target] [!UICONTROL Recommendations] utilisent les mêmes hôtes AWS.

>[!NOTE]
>
>Ces adresses IP ont été mises à jour pour la dernière fois le 16 mars 2021. Auparavant, les serveurs qui accédaient aux serveurs FTP se trouvaient dans le bloc CIDR d’adresses IP 192.243.242.0/24. Les serveurs qui hébergeaient les API Recommendations se trouvaient dans le bloc CIDR d’adresses IP 192.243.224.0/20.
