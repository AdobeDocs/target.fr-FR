---
keywords: assurance qualité;côté serveur;côté serveur;aperçu;liens d’aperçu
description: Découvrez comment utiliser Adobe [!DNL Target] URL d’assurance qualité avec diffusion côté serveur pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives.
title: Utiliser Puis-je exécuter l’AQ d’activité avec la diffusion côté serveur ?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 70%

---

# Utilisation de l’AQ d’activité avec diffusion côté serveur

Utilisation d’URL AQ avec diffusion côté serveur dans [!DNL Adobe Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives.

La mise en oeuvre standard de l’AQ d’activité prend en charge le transfert des `qa_mode` paramètres via `pageUrl` les paramètres Cette approche est pratique pour standard/ajax. [!DNL Target] appels . Cependant, pour les appels serveur à serveur, ce n’est pas l’approche idéale dans le cas d’un SDK de Mobile lorsque `pageUrl` n’est pas disponible.

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
| token | Jeton chiffré | Aucune.<br>Ne peut pas être vide. | Entité chiffrée qui contient la liste des ID d’activité autorisés à être exécutés dans l’AQ d’activité.<br>[!DNL Target]Règles de validation : Doit être un jeton chiffré appartenant au client défini dans la requête L’ensemble des activités spécifiées dans le jeton doit appartenir au client. |
| bypassEntryAudience | Booléen | False | Indique si les objectifs d’étape d’entrée pour les activités d’AQ doivent être évalués ou s’ils doivent être considérés comme correspondants. |
| listedActivitiesOnly | Booléen | False | Indique si les activités d’AQ doivent être exécutées seules ou si elles doivent être évaluées en tant qu’activités actives pour l’environnement actif. |
| evaluateAsTrueAudienceIds | Liste des ID | Liste vide. | Liste des identifiants d’audience qui doivent toujours être évalués comme &quot;true&quot; dans la portée de la variable [!DNL Target] requête. |
| evaluateAsFalseAudienceIds | Liste des ID | Liste vide. | Liste des identifiants d’audience qui doivent toujours être évalués comme faux dans la portée de [!DNL Target] requête. |
| activityIndex | Entier | Valeur nulle.<br>Ne peut pas être vide. | Index des activités dans le jeton chiffré. activityIndex est au-delà des limites de l’activité dans le jeton. Si la valeur est nulle, la requête est ignorée. L’index commence à 1.<br>Règles de validation : L’index doit contenir au minimum une activité et une activité spécifiée dans le jeton. |
| experienceIndex | Entier | Valeur nulle. | Lorsque celle-ci en contient, sélectionne une expérience par index dans la définition de l’activité. Lorsque la définition ne contient aucune expérience, l’index commence à 1. Règles de validation : La valeur peut être nulle, ou une expérience doit être spécifiée dans l’activité. |
