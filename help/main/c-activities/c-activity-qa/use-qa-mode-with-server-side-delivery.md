---
keywords: assurance qualité;côté serveur;côté serveur;aperçu;liens d’aperçu
description: Découvrez comment utiliser les URL  [!DNL Target] QA avec diffusion côté serveur pour exécuter facilement un contrôle qualité d’activité de bout en bout avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et un compte rendu des performances d’assurance qualité qui reste segmenté à partir des données d’activité en direct.
title: Utiliser Puis-je effectuer un contrôle qualité d’activité avec la diffusion côté serveur ?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 408
ht-degree: 47%

---

# Utilisation de l’AQ d’activité avec diffusion côté serveur

Utilisez les URL d’assurance qualité avec diffusion côté serveur dans [!DNL Adobe Target] pour exécuter facilement une assurance qualité de bout en bout de l’activité, avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et un compte rendu des performances d’assurance qualité qui reste segmenté à partir des données d’activité actives.

L’implémentation standard du QA d’activité prend en charge la transmission de paramètres `qa_mode` via des paramètres `pageUrl`. Cette approche est pratique pour les appels [!DNL Target] standard/ajax. Cependant, pour les appels serveur à serveur, ce n’est pas l’approche idéale dans le cas d’un SDK de Mobile lorsque `pageUrl` n’est pas disponible.

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
| token | Jeton chiffré | Aucun.<br>Il ne peut pas être vide. | Une entité chiffrée qui contient la liste des identifiants d’activité qui peuvent être exécutés dans les règles d’AQ d’activité.<br>Validation : doit être un jeton chiffré appartenant au client spécifié dans la requête de [!DNL Target]. L’ensemble des activités spécifiées dans le jeton doit appartenir au client. |
| bypassEntryAudience | Booléen | False | Indique si les objectifs d’étape d’entrée pour les activités d’AQ doivent être évalués ou s’ils doivent être considérés comme correspondants. |
| listedActivitiesOnly | Booléen | False | Indique si les activités d’AQ doivent être exécutées seules ou si elles doivent être évaluées en tant qu’activités actives pour l’environnement actif. |
| evaluateAsTrueAudienceIds | Liste des ID | Liste vide. | Liste des identifiants d’audience qui doivent toujours être évalués comme vrais dans la portée de la requête [!DNL Target]. |
| evaluateAsFalseAudienceIds | Liste des ID | Liste vide. | Liste des ID d’audience qui doivent toujours être évalués comme faux dans la portée de la requête [!DNL Target]. |
| activityIndex | Entier | Null.<br>Il ne peut pas être vide. | Index des activités dans le jeton chiffré. activityIndex est au-delà des limites de l’activité dans le jeton. Si la valeur est nulle, la requête est ignorée. L’index commence par 1.<br>Règles de validation : doit être au moins un index d’activité et doit référencer une activité spécifiée dans le jeton. |
| experienceIndex | Entier | Valeur nulle. | Lorsque celle-ci en contient, sélectionne une expérience par index dans la définition de l’activité. Lorsque la définition ne contient aucune expérience, L’index commence par 1 règle de validation : peut être nul ou doit référencer une expérience dans l’activité. |
