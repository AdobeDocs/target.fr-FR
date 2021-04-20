---
keywords: implémenter ; implémentation ; liste autorisée ; liste autorisée ; liste autorisée ; liste autorisée ; arête ; arêtes
description: Vue d’une liste d’hôtes pour vous aider à placer sur la liste autorisée les arêtes Adobe Target (des noeuds de service répartis géographiquement qui garantissent un temps de réponse optimal aux utilisateurs finaux).
title: Comment Placer sur la liste autorisée les noeuds Edge de Cible ?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: 806c52e69cce636a56eb067759612f80829418f9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---


# Liste autorisée des noeuds de bord de Cible

Cette section contient des informations et une liste actualisée d’hôtes pour vous aider à placer sur la liste autorisée [!DNL Adobe Target] arêtes.

Une arête est une architecture de diffusion géographiquement distribuée qui garantit un temps de réponse optimal aux utilisateurs finaux qui demandent du contenu, où qu’ils se trouvent. Chaque noeud Edge contient toutes les informations nécessaires pour répondre à la demande de contenu de l’utilisateur et pour effectuer le suivi des données d’analyse sur cette demande. Les requêtes des utilisateurs sont acheminées vers le noeud de bord le plus proche. Pour plus d&#39;informations, voir [The edge network](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) dans *How Adobe [!DNL Target] working*.

Si vous le souhaitez, vous pouvez placer sur la liste autorisée des noeuds de bord [!DNL Target].

## Traduction d&#39;adresses réseau (NAT) Adresses IP des arêtes de la Cible

Liste des adresses IP d&#39;échappement des arêtes [!DNL Target]. Placez sur la liste autorisée ces adresses IP si vous prévoyez d’avoir Cible à contacter vos services.

| Emplacement Edge | Envoyer les adresses IP |
| --- | --- |
| Edge31 (Mumbai) | 13.126.131.246<br>13.234.229.8 |
| Edge32 (Tokyo) | 3.115.154.28<br>3.115.227.146 |
| Edge34 (côte Est des États-Unis) | 34.232.149.249<br>52.21.139.93 |
| Edge35 (côte ouest des États-Unis) | 52.10.11.139<br>44.231.171.161 |
| Edge36 (Sydney) | 13.237.227.20<br>13.210.93.142 |
| Edge37 (Irlande) | 54.72.21.68<br>52.208.139.19 |
| Edge38 (Singapour) | 18.141.132.96<br>54.179.187.167 |

## Adresses IP du bord de la cible

Liste des adresses IP des arêtes [!DNL Target]. Placez sur la liste autorisée ces adresses IP si vous souhaitez effectuer des appels d&#39;API aux bords des Cibles.

| Emplacement Edge | Domaine | Adresses IP |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(où CLIENTCODE est votre ID  [!DNL Target] client) |  |
| Edge31 (Mumbai) | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32 (Tokyo) | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34 (côte Est des États-Unis) | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.22.9 3<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35 (côte ouest des États-Unis) | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36 (Sydney) | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37 (Irlande) | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>5 2.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38 (Singapour) | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |





