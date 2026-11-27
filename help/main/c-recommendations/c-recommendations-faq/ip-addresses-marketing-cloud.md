---
keywords: adresse IP;adresses IP;liste blanche;liste autorisée;pare-feu;recommandations;flux;serveurs;adobe experience cloud;recommendations
description: Consultez une liste d’adresses IP utilisées dans les serveurs de traitement de flux de [!DNL Target] Recommendations destinée à vous aider à configurer votre pare-feu afin d’autoriser les adresses IP issues des serveurs Adobe.
title: Quelles adresses IP les serveurs de traitement de flux de Recommandations utilisent-ils ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: 'https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 34%
---
# Adresses IP utilisées par [!DNL Recommendations] serveurs de traitement de flux {#recs-ip-addresses}

>[!BEGINSHADEBOX]

**Sur cette page :** Recherchez les adresses IP utilisées par les serveurs de traitement de flux [!DNL Adobe Target] [!DNL Recommendations] pour configurer un pare-feu qui autorise les adresses IP issues des serveurs [!DNL Adobe].

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>L&#39;équipe [!DNL Target] met actuellement à jour les adresses de passerelle NAT pour télécharger [!DNL Recommendations] flux. Lorsque la liste autorisée d’adresses IP est implémentée, procédez à la liste autorisée des nouveaux hôtes AWS suivants. La mise hors service des hôtes existants est prévue pour le 30 juin 2024. Pour assurer une transition en douceur, placez l’ensemble des neuf adresses sur la liste autorisée. La suppression des adresses existantes n’est pas urgente.

Les activités [!DNL Target] [!UICONTROL Recommendations] utilisent les hôtes AWS suivants lors de l’accès aux serveurs FTP des clients.

**Nouveaux hôtes** :

| Emplacement | Hôte |
| --- | --- |
| Oregon | `52.40.124.129` |
| Oregon | `54.148.219.69` |
| Oregon | `54.189.208.212` |
| Oregon | `44.230.236.35` |
| Oregon | `54.190.78.243` |
| Oregon | `52.41.73.133` |

**Hôtes existants** :

| Emplacement | Hôte |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

Les API [!DNL Target] [!UICONTROL Recommendations] utilisent également les mêmes hôtes AWS.
