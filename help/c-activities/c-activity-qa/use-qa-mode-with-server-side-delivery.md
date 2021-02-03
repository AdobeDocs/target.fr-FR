---
keywords: assurance qualité;côté serveur;côté serveur;aperçu;liens d’aperçu
description: Utilisez les URL d’assurance qualité Adobe Target avec diffusion côté serveur pour effectuer un contrôle qualité de l’activité de bout en bout simple avec des liens de prévisualisation qui ne changent jamais, un ciblage facultatif des audiences et un rapports d’assurance qualité qui reste segmenté à partir des données d’activité en direct.
title: ' Utilisation de l’AQ d’activité avec diffusion côté serveur.'
feature: Activities
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 72%

---


# Utilisation de l’AQ d’activité avec diffusion côté serveur

Utilisez les URL de contrôle qualité avec diffusion côté serveur dans [!DNL Adobe Target] pour effectuer un contrôle qualité de l&#39;activité de bout en bout simple avec des liens de prévisualisation qui ne changent jamais, le ciblage facultatif des audiences et le rapports de contrôle qualité qui restent segmentés à partir des données d&#39;activité en direct.

La mise en oeuvre standard de l’AQ d’activité prend en charge le transfert des `qa_mode` paramètres via `pageUrl` les paramètres Cette approche est pratique pour les appels standard/ajax [!DNL Target]. Cependant, pour les appels serveur à serveur, ce n’est pas l’approche idéale dans le cas d’un SDK de Mobile lorsque `pageUrl` n’est pas disponible.

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
| evaluateAsTrueAudienceIds | Liste des ID | Liste vide. | Liste des ID d’audience qui doivent toujours être évalués comme vraie dans la portée de la requête [!DNL Target]. |
| evaluateAsFalseAudienceIds | Liste des ID | Liste vide. | Liste des ID d’audience qui doivent toujours être évalués comme faux dans la portée de la requête [!DNL Target]. |
| activityIndex | Entier | Valeur nulle.<br>Ne peut pas être vide. | Index des activités dans le jeton chiffré. activityIndex est au-delà des limites de l’activité dans le jeton. Si la valeur est nulle, la requête est ignorée. L’index commence à 1.<br>Règles de validation : L’index doit contenir au minimum une activité et une activité spécifiée dans le jeton. |
| experienceIndex | Entier | Valeur nulle. | Lorsque celle-ci en contient, sélectionne une expérience par index dans la définition de l’activité. Lorsque la définition ne contient aucune expérience, l’index commence à 1. Règles de validation : La valeur peut être nulle, ou une expérience doit être spécifiée dans l’activité. |