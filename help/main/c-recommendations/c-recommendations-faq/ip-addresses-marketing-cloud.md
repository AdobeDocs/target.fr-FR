---
keywords: adresse IP;adresses IP;liste blanche;liste autorisée;pare-feu;recommandations;flux;serveurs;adobe experience cloud;recommendations
description: Consultez une liste d’adresses IP utilisées dans les serveurs de traitement de flux de  [!DNL Target]  Recommendations destinée à vous aider à configurer votre pare-feu afin d’autoriser les adresses IP issues des serveurs Adobe.
title: Quelles adresses IP les serveurs de traitement de flux de Recommendations utilisent-ils ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 558de92e672c276474bc76fad19e5461ae7d4c88
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 49%

---

# Adresses IP utilisées par [!DNL Recommendations] serveurs de traitement de flux

Liste des adresses IP utilisées dans [!DNL Adobe Target] [!DNL Recommendations] serveurs de traitement de flux pour vous aider à configurer votre pare-feu pour autoriser les adresses IP issues de [!DNL Adobe] serveurs.

>[!IMPORTANT]
>
>23 février 2023 : Le [!DNL Target] L’équipe met actuellement à jour les adresses de passerelle NAT pour le téléchargement. [!DNL Recommendations] flux. Si vous implémentez l’liste autorisée IP, veillez à placer sur la liste autorisée les nouveaux hôtes AWS suivants. Les hôtes existants doivent être mis hors service à l’avenir. Les neuf hôtes sont maintenant opérationnels.

Les activités [!DNL Target] [!UICONTROL Recommendations] utilisent les hôtes AWS suivants lors de l’accès aux serveurs FTP des clients :

**Nouveaux hôtes**:

| Emplacement | Hôte |
| --- | --- |
| Oregon | `52.40.124.129` |
| Oregon | `54.148.219.69` |
| Oregon | `54.189.208.212` |
| Oregon | `44.230.236.35` |
| Oregon | `54.190.78.243` |
| Oregon | `52.41.73.133` |

**Hôtes existants**:

| Emplacement | Hôte |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

Les API [!DNL Target] [!UICONTROL Recommendations] utilisent les mêmes hôtes AWS.
