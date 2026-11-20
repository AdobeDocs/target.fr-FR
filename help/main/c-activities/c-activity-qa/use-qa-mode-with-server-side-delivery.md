---
keywords: assurance qualité;côté serveur;côté serveur;aperçu;liens d’aperçu
description: Découvrez comment utiliser les URL d’assurance qualité [!DNL Target] d’Adobe avec diffusion côté serveur pour exécuter facilement une assurance qualité de bout en bout de l’activité, avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et un compte rendu des performances d’assurance qualité qui reste segmenté à partir des données d’activité en direct.
title: Utiliser Puis-je effectuer un contrôle qualité d’activité avec la diffusion côté serveur ?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# Utilisation de l’AQ d’activité avec diffusion côté serveur {#qa-server-side}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment transmettre des paramètres d’AQ d’activité dans un appel [!DNL Adobe Target] côté serveur, afin que vous puissiez tester des activités lorsque `pageUrl` n’est pas disponible.

>[!ENDSHADEBOX]

L’implémentation standard du QA d’activité prend en charge la transmission de `qa_mode` paramètres via `pageUrl` paramètres. Cette approche est pratique pour les appels [!DNL Target] standard/ajax. Cependant, il n’est pas adapté aux appels serveur à serveur, comme une implémentation de Mobile SDK, où `pageUrl` n’est pas disponible. Dans ces cas, transmettez les paramètres d’assurance qualité dans la requête elle-même, qui conserve les mêmes liens de prévisualisation, le ciblage facultatif des audiences et le compte rendu des performances d’assurance qualité segmenté à partir des données d’activité actives.

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

Le tableau suivant décrit les paramètres d’une requête côté serveur :

| Paramètre | Type | Valeur par défaut | Description |
|--- |--- |--- |--- |
| jeton | Jeton chiffré | Aucune. Ne peut pas être vide. | Entité chiffrée contenant la liste des identifiants d’activité pouvant être exécutés dans AQ d’activité.<br>Règles de validation : le jeton doit être un jeton chiffré appartenant au client spécifié dans la requête [!DNL Target]. Toutes les activités spécifiées dans le jeton doivent appartenir au client. |
| bypassEntryAudience | Booléen | False | Indique si les cibles d&#39;étape d&#39;entrée pour les activités d&#39;assurance qualité sont évaluées ou considérées comme correspondantes. |
| listedActivitiesOnly | Booléen | False | Indique si les activités d’assurance qualité sont exécutées de manière isolée ou si elles sont évaluées en tant qu’activités actives pour l’environnement actuel. |
| evaluateAsTrueAudienceIds | Liste des ID | Liste vide | Liste des identifiants d&#39;audience qui sont toujours évalués comme vrais dans la portée de la requête [!DNL Target]. |
| evaluateAsFalseAudienceIds | Liste des ID | Liste vide | Liste des ID d’audience toujours évalués comme faux dans la portée de la requête [!DNL Target]. |
| activityIndex | Entier | Null. Ne peut pas être vide. | Index des activités dans le jeton chiffré. Si `activityIndex` est nul ou hors des limites des activités dans le jeton, il est ignoré. L&#39;index commence par 1.<br>Règles de validation : au moins un index d&#39;activité est requis et il doit référencer une activité spécifiée dans le jeton. |
| experienceIndex | Entier | Null | Lorsque celle-ci en contient, sélectionne une expérience par index dans la définition de l’activité. Si elle n’est pas spécifiée ou dépasse les limites, elle revient à la stratégie du sélecteur d’expérience de l’activité. L’index commence par 1.<br>Règles de validation : la valeur peut être nulle ou elle doit référencer une expérience dans l’activité. |
