---
keywords: assurance qualité;côté serveur;côté serveur;aperçu;liens d’aperçu
description: Découvrez comment utiliser les URL d’Adobe [!DNL Target] AQ avec diffusion côté serveur pour effectuer une AQ d’activité de bout en bout avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives.
title: Utiliser Puis-je effectuer l’AQ d’activité avec la diffusion côté serveur ?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 59%

---

# Utilisation de l’AQ d’activité avec diffusion côté serveur

Utilisez les URL AQ avec diffusion côté serveur dans [!DNL Adobe Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et des rapports d’AQ qui restent segmentés à partir des données d’activité actives.

L’implémentation standard de l’AQ d’activité prend en charge le transfert de `qa_mode` paramètres via `pageUrl` paramètres. Cette approche est pratique pour les appels standard/ajax [!DNL Target]. Cependant, pour les appels serveur à serveur, ce n’est pas l’approche idéale dans le cas d’un SDK de Mobile lorsque `pageUrl` n’est pas disponible.

L’échantillon de code suivant montre l’AQ d’activité dans un appel côté serveur :

```json
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

Le tableau suivant décrit les détails d’une requête côté serveur :

| Paramètre | Type | Valeur par défaut | Description |
|--- |--- |--- |--- |
| token | Jeton chiffré | Aucune.<br>Ne peut pas être vide. | Entité chiffrée qui contient la liste des ID d’activité autorisés à être exécutés dans l’AQ d’activité.<br>Règles de validation : Doit être un jeton chiffré appartenant au client spécifié dans la requête [!DNL Target]. L’ensemble des activités spécifiées dans le jeton doit appartenir au client. |
| bypassEntryAudience | Booléen | False | Indique si les objectifs d’étape d’entrée pour les activités d’AQ doivent être évalués ou s’ils doivent être considérés comme correspondants. |
| listedActivitiesOnly | Booléen | False | Indique si les activités d’AQ doivent être exécutées seules ou si elles doivent être évaluées en tant qu’activités actives pour l’environnement actif. |
| evaluateAsTrueAudienceIds | Liste des ID | Liste vide. | Liste des identifiants d’audience qui doivent toujours être évalués comme &quot;true&quot; dans la portée de la requête [!DNL Target]. |
| evaluateAsFalseAudienceIds | Liste des ID | Liste vide. | Liste des identifiants d’audience qui doivent toujours être évalués sur false dans la portée de la requête [!DNL Target]. |
| activityIndex | Entier | Valeur nulle.<br>Ne peut pas être vide. | Index des activités dans le jeton chiffré. activityIndex est au-delà des limites de l’activité dans le jeton. Si la valeur est nulle, la requête est ignorée. L’index commence à 1.<br>Règles de validation : L’index doit contenir au minimum une activité et une activité spécifiée dans le jeton. |
| experienceIndex | Entier | Valeur nulle. | Lorsque celle-ci en contient, sélectionne une expérience par index dans la définition de l’activité. Lorsque la définition ne contient aucune expérience, L’index commence par 1 règle de validation : peut être nul ou doit référencer une expérience dans l’activité. |
