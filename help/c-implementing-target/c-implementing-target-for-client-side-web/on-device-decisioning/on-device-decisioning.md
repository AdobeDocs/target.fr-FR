---
keywords: implémentation ; bibliothèque javascript ; js ; atjs ; prise de décision sur périphérique ; prise de décision sur périphérique ; at.js ; on-device ; on-device ; on device
description: Découvrez comment prendre des décisions sur périphérique avec la bibliothèque at.js
title: Comment la prise de décision sur le périphérique fonctionne-t-elle avec la bibliothèque JavaScript at.js ?
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
translation-type: tm+mt
source-git-commit: 7b9870fc79a41e387f557dd36edf5a7af4b443c7
workflow-type: tm+mt
source-wordcount: '3747'
ht-degree: 6%

---

# Prise de décision sur périphérique pour at.js

>[!NOTE]
>
>La prise de décision sur périphérique sera disponible avec la prochaine version [at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). Date à annoncer prochainement.

À compter de la version 2.5.0, at.js offre la prise de décision sur le périphérique. La prise de décision sur périphérique permet de mettre en cache vos activités [Test A/B](/help/c-activities/t-test-ab/test-ab.md) et [Ciblage d’expérience](/help/c-activities/t-experience-target/experience-target.md) (XT) sur le navigateur pour effectuer la prise de décision en mémoire sans qu’une demande réseau de blocage ne soit envoyée au réseau Edge [!DNL Adobe Target].

[!DNL Target] offre également la flexibilité de fournir l&#39;expérience la plus pertinente et la plus à jour de votre expérimentation et de vos activités de personnalisation d&#39;apprentissage automatique (pilotées par ML) via un appel serveur en direct. En d’autres termes, lorsque les performances sont les plus importantes, vous pouvez choisir d’utiliser la prise de décision sur le périphérique. Cependant, lorsque l’expérience la plus pertinente, à jour et pilotée par ML est nécessaire, un appel serveur peut être effectué à la place.

## Quels sont les avantages de la prise de décision sur périphérique ?

Les avantages de la prise de décision sur périphérique sont les suivants :

* **Proposez des décisions et des expériences rapides et éblouissantes.** Le regroupement et la prise de décision sont effectués en mémoire et sur le navigateur pour éviter de bloquer les requêtes réseau.
* **Améliorer les performances de l&#39;application.** Exécutez des expériences et proposez une personnalisation à vos clients et utilisateurs sans compromettre les expériences des utilisateurs finaux.
* **Améliorer le score de qualité du site Google.** Avec la prise de décision en mémoire, améliorez le score de qualité du site Google de votre entreprise en ligne pour la rendre plus visible par les consommateurs.
* **Découvrez les analyses en temps réel.** Obtenez des informations sur les performances de vos activités en temps réel via le rapports  [Analytics for Cible](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T). A4T vous permet de faire pivoter votre stratégie à des moments critiques.

## Fonctionnalités prises en charge

Le Adobe Target JS SDK offre aux clients la possibilité de choisir entre les performances et la fraîcheur des données pour les décisions. En d’autres termes, si la diffusion du contenu personnalisé le plus pertinent et attrayant par le biais de l’apprentissage automatique est la plus importante pour vous, un appel au serveur en direct doit être effectué. Mais lorsque les performances sont plus critiques, une décision sur périphérique et en mémoire doit être prise. Pour que la décision sur périphérique fonctionne, reportez-vous à la liste des fonctionnalités prises en charge :

* Types d’activités
* Ciblage des Audiences
* Méthode d’allocation

Pour plus d’informations, voir [Fonctionnalités prises en charge pour la prise de décision sur le périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

## Comment fonctionne la prise de décision sur périphérique ?

Lorsque vous déployez et initialisez at.js avec la prise de décision sur périphérique activée, un artefact [de règle](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) qui comprend votre prise de décision sur périphérique pour les activités, audiences et ressources A/B et XT est téléchargé depuis le CDN Akamai le plus proche de votre visiteur et mis en cache localement sur votre navigateur visiteur. Lorsqu’une requête est envoyée à partir d’at.js pour récupérer une expérience, la décision concernant l’expérience à renvoyer est prise en mémoire, en fonction des métadonnées codées dans l’artefact de règle mis en cache.

## Méthode de prise de décision

Avec la prise de décision sur périphérique, [!DNL Target] introduit un nouveau paramètre appelé [!UICONTROL Méthode de prise de décision]. Le paramètre [!UICONTROL Méthode de prise de décision] détermine comment at.js fournit vos expériences. [!UICONTROL La ] méthode de prise de décision comporte trois valeurs :

* [!UICONTROL Serveur uniquement]
* [!UICONTROL Sur périphérique uniquement]
* [!UICONTROL Hybride]

### Serveur uniquement

[!UICONTROL La méthode de prise de décision par défaut, côté serveur ] uniquement, est définie hors champ lorsque at.js 2.5.0+ est implémenté et déployé sur vos propriétés Web.

L&#39;utilisation de [!UICONTROL serveur uniquement] comme configuration par défaut signifie que toutes les décisions sont prises sur le réseau de périphérie [!DNL Target], ce qui implique un appel serveur de blocage. Cette approche peut introduire une latence incrémentielle, mais elle offre également des avantages significatifs, comme la possibilité d’appliquer les capacités d’apprentissage automatique de la Cible qui incluent des activités [Recommendations](/help/c-recommendations/recommendations.md), [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) et [Cible automatique](/help/c-activities/auto-target/auto-target-to-optimize.md).

En outre, l’amélioration de vos expériences personnalisées à l’aide du profil d’utilisateur de Cible, qui est persisté d’une session à l’autre et dans les canaux, peut fournir des résultats importants à votre entreprise.

Enfin, [!UICONTROL côté serveur uniquement] vous permet d’utiliser le Adobe Experience Cloud et d’affiner les audiences qui peuvent être ciblées par le biais de segments d’Audience Manager et de Adobe Analytics.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et le réseau Adobe Target Edge. Ce diagramme de flux capture les nouveaux visiteurs et les visiteurs de retour.

![Diagramme de flux côté serveur uniquement](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

La liste suivante correspond aux chiffres du diagramme :

| Étape | Description |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID] est récupéré à partir du [Service d&#39;identité de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>   La bibliothèque at.js peut également être chargée de manière asynchrone avec un extrait de code de prémasquage en option implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une demande de chargement de page comprend tous les paramètres configurés, tels que (ECID, ID de client, Paramètres personnalisés, Profil d’utilisateur, etc.). |
| 5 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils.<br>Le magasin de Profils demande des audiences qualifiées à la bibliothèque d’Audiences (par exemple, des audiences partagées à partir de  [!DNL Adobe Analytics],  [!DNL Adobe Audience Manager]etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 6 | Le magasin de Profils est utilisé pour la qualification des audiences et la mise en cache pour filtrer les activités. |
| 7 | Le contenu résultant est sélectionné une fois l’expérience déterminée à partir d’activités [!DNL Target] en direct. |
| 8 | La bibliothèque at.js masque les éléments correspondants sur la page qui sont associés à l’expérience qui doit être rendue. |
| 9 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour votre visiteur à la vue. |
| 10 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir du réseau Edge de Cible. |
| 11 | L’expérience est générée pour le visiteur. |
| 12 | La page Web entière se charge. |
| 13 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. |
| 14 | Les données ciblées sont associées à [!DNL Analytics] données par l’intermédiaire du SDID et sont traitées dans l’enregistrement de rapports [!DNL Analytics]. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

### Sur périphérique uniquement

[!UICONTROL La méthode de prise de décision ] uniquement sur le périphérique doit être définie dans at.js 2.5.0+ lorsque la prise de décision sur le périphérique ne doit être utilisée que sur l’ensemble de vos pages Web.

La prise de décision sur le périphérique peut fournir vos expériences et vos activités de personnalisation à une vitesse fulgurante, car les décisions sont prises à partir d’un artefact de règles mis en cache qui contient toutes vos activités admissibles à la prise de décision sur le périphérique.

Pour en savoir plus sur les activités admissibles pour la prise de décision sur le périphérique, voir [Fonctions prises en charge dans la prise de décision sur le périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

Cette méthode de prise de décision ne doit être utilisée que si les performances sont extrêmement critiques sur toutes les pages qui nécessitent des décisions de [!DNL Target]. En outre, gardez à l’esprit que lorsque cette méthode de prise de décision est sélectionnée, vos [!DNL Target] activités qui ne remplissent pas les critères pour la prise de décision sur le périphérique ne seront pas livrées ou exécutées. La bibliothèque at.js 2.5.0+ est configurée pour rechercher uniquement l’artefact des règles mises en cache pour prendre des décisions.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et le réseau de diffusion de contenu Akamai. Le réseau de diffusion de contenu Akamai met en cache l’artefact de règles pour la première visite de l’visiteur. Pour la première visite de page d’un nouveau visiteur, l’artefact de règles JSON doit être téléchargé à partir du CDN Akamai pour être mis en cache localement dans le navigateur du visiteur. Une fois l’artefact des règles JSON téléchargé, la décision est prise immédiatement sans appel réseau de blocage. Le diagramme de flux suivant capture de nouveaux visiteurs.

![Diagramme de flux sur périphérique uniquement](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

La liste suivante correspond aux chiffres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités qui peuvent prendre des décisions sur le périphérique, génèrent l’artefact des règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour génèrent un nouvel artefact de règles JSON à propager au réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 3 | [!DNL Experience Cloud Visitor ID] est récupéré à partir du [Service d&#39;identité de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un extrait de code de prémasquage en option implémenté sur la page. |
| 1 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | La bibliothèque at.js émet une requête pour récupérer l’artefact de règle JSON depuis le CDN Akamai le plus proche vers le visiteur. |
| 5 | Le réseau de diffusion de contenu Akamai répond par l’artefact de règle JSON. |
| 6 | L’artefact de règle JSON est mis en cache localement dans le navigateur du visiteur. |
| 7 | La bibliothèque at.js interprète l’artefact de règle JSON et exécute la décision de récupérer l’expérience et masque les éléments testés. |
| 8 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour votre visiteur à la vue. |
| 9 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 10 | L’expérience est générée pour le visiteur. |
| 11 | La page Web entière se charge. |
| 12 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] données par l’intermédiaire du SDID et sont traitées dans l’enregistrement de rapports [!DNL Analytics]. [!DNL Analytics][!DNL Analytics]Il est alors possible de consulter les données dans et dans par l’intermédiaire des rapports Analytics for Target (A4T).[!DNL Target] |

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et l’artefact de règle JSON mis en cache pour l’accès à la page suivant ou la visite de retour du visiteur. L’artefact des règles JSON étant déjà mis en cache et disponible sur le navigateur, la décision est prise immédiatement sans appel réseau de blocage. Ce diagramme de flux capture les visiteurs de navigation de page suivants ou de retour.

![Diagramme de flux sur périphérique uniquement pour la navigation de page suivante et les visites répétées](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

La liste suivante correspond aux chiffres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités qui peuvent prendre des décisions sur le périphérique, génèrent l’artefact des règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour génèrent un nouvel artefact de règles JSON à propager au réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID] est récupéré à partir du [Service d&#39;identité de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un extrait de code de prémasquage en option implémenté sur la page. |
| 1 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | La bibliothèque at.js interprète l’artefact de règle JSON et exécute la décision en mémoire de récupérer l’expérience. |
| 5 | Les éléments testés sont masqués. |
| 6 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour votre visiteur à la vue. |
| 7 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 8 | L’expérience est générée pour le visiteur. |
| 9 | La page Web entière se charge. |
| 10 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] données par l’intermédiaire du SDID et sont traitées dans l’enregistrement de rapports [!DNL Analytics]. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

### Hybride

 Hybridis est la méthode de prise de décision qui doit être définie dans at.js 2.5.0+ lorsque la prise de décision sur le périphérique et les activités qui nécessitent un appel réseau au réseau Adobe Target Edge doivent être exécutées.

Lorsque vous gérez à la fois des activités de prise de décision sur périphérique et des activités côté serveur, il peut s&#39;avérer un peu compliqué et fastidieux de réfléchir à la manière de déployer et de configurer [!DNL Target] vos pages. Avec la méthode de prise de décision hybride, [!DNL Target] sait quand il doit effectuer un appel serveur au réseau Adobe Target Edge pour les activités qui nécessitent une exécution côté serveur et quand exécuter uniquement les décisions sur le périphérique.

L’artefact de règles JSON comprend des métadonnées pour indiquer à at.js si une mbox comporte une activité côté serveur en cours d’exécution ou une activité de prise de décision sur le périphérique. Cette méthode de prise de décision garantit que les activités que vous prévoyez de livrer rapidement sont effectuées par le biais de la prise de décision sur le périphérique et, pour les activités qui nécessitent une personnalisation plus puissante pilotée par ML, ces activités sont effectuées via le réseau Adobe Target Edge.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+, le réseau de diffusion de contenu Akamai et le réseau Edge Adobe Target pour un nouveau visiteur visitant votre page pour la première fois. La leçon à tirer de ce diagramme est que l’artefact des règles JSON est téléchargé de manière asynchrone pendant que les décisions sont prises via le réseau Adobe Target Edge.

Cette approche permet de s’assurer que la taille de l’artefact, qui peut inclure de nombreuses activités, n’influence pas négativement la latence de la décision. Le téléchargement des règles JSON de manière synchrone et la prise de décision par la suite peuvent également avoir des effets négatifs sur la latence et peuvent être incohérents. Par conséquent, la méthode de prise de décision hybride est une recommandation recommandée pour toujours effectuer un appel côté serveur pour la décision d’un nouveau visiteur, et comme l’artefact des règles JSON est mis en cache en parallèle. Pour les visites de page et les visites de retour ultérieures, les décisions sont prises à partir du cache et en mémoire par le biais de l’artefact des règles JSON.

![Diagramme de flux hybride pour un nouveau visiteur](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

La liste suivante correspond aux chiffres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités qui peuvent prendre des décisions sur le périphérique, génèrent l’artefact des règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour génèrent un nouvel artefact de règles JSON à propager au réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 3 | [!DNL Experience Cloud Visitor ID] est récupéré à partir du [Service d&#39;identité de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un extrait de code de prémasquage en option implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une demande de chargement de page est envoyée à Adobe Target Edge Network, y compris tous les paramètres configurés tels que (ECID, ID de client, paramètres personnalisés, Profil d’utilisateur, etc.). |
| 5 | En parallèle, at.js effectue une demande pour récupérer l’artefact de règle JSON depuis le CDN Akamai le plus proche vers le visiteur. |
| 6 | (Adobe Target Edge Network) Les scripts de Profil s’exécutent, puis sont introduits dans le Profil Store. Le magasin de Profils demande des audiences qualifiées à la bibliothèque d’Audiences (par exemple, des audiences partagées à partir de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], etc.). |
| 7 | Le réseau de diffusion de contenu Akamai répond par l’artefact de règle JSON. |
| 8 | Le magasin de Profils est utilisé pour la qualification des audiences et la mise en cache pour filtrer les activités. |
| 9 | Le contenu résultant est sélectionné une fois l’expérience déterminée à partir d’activités [!DNL Target] en direct. |
| 10 | La bibliothèque at.js masque les éléments correspondants sur la page qui sont associés à l’expérience qui doit être rendue. |
| 11 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour votre visiteur à la vue. |
| 12 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir du réseau Edge de Cible. |
| 13 | L’expérience est générée pour le visiteur. |
| 14 | La page Web entière se charge. |
| 15 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] données par l’intermédiaire du SDID et sont traitées dans l’enregistrement de rapports [!DNL Analytics]. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et l’artefact des règles JSON mis en cache pour une navigation de page ou une visite de retour ultérieure. Dans ce diagramme, vous vous intéressez uniquement au cas d’utilisation où une décision sur le périphérique est prise pour la navigation de page ou la visite de retour ultérieure. Gardez à l’esprit que, selon les activités actives pour certaines pages, un appel côté serveur peut être effectué pour exécuter les décisions côté serveur.

![Diagramme de flux hybride pour la navigation suivante sur les pages et les visites répétées](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

La liste suivante correspond aux chiffres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités qui peuvent prendre des décisions sur le périphérique, génèrent l’artefact des règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour génèrent un nouvel artefact de règles JSON à propager au réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | [!DNL Experience Cloud Visitor ID] est récupéré à partir du [Service d&#39;identité de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un extrait de code de prémasquage en option implémenté sur la page. |
| 1 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une demande est envoyée pour récupérer une expérience. |
| 5 | La bibliothèque at.js confirme que l’artefact de règle JSON a déjà été mis en cache et exécute la décision en mémoire de récupérer l’expérience. |
| 6 | Les éléments testés sont masqués. |
| 7 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour votre visiteur à la vue. |
| 8 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 9 | L’expérience est générée pour le visiteur. |
| 10 | La page Web entière se charge. |
| 11 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] données par l’intermédiaire du SDID et sont traitées dans l’enregistrement de rapports [!DNL Analytics]. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

## Comment activer la prise de décision sur le périphérique ?

La prise de décision sur périphérique est disponible pour tous les clients [!DNL Target] qui utilisent At.js 2.5.0+.

Pour activer la prise de décision sur le périphérique :

>[!NOTE]
>
>Vous devez disposer du [!UICONTROL rôle d’administrateur] ou [!UICONTROL approbateur] [rôle d’utilisateur](/help/administrating-target/c-user-management/user-management.md) pour activer ou désactiver l’option de prise de décision sur le périphérique.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Détails du compte]**.
1. Sous **[!UICONTROL Détails du compte]**, faites glisser l&#39;option **[!UICONTROL Décision sur le périphérique]** à la position &quot;on&quot;.

   ![Basculement de la prise de décision sur le périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   L&#39;option &quot;[!UICONTROL Inclure toutes les activités qualifiées de prise de décision sur périphérique existantes dans l&#39;artefact]&quot; s&#39;affiche si vous activez la prise de décision sur périphérique.
1. (Conditionnel) Faites glisser la bascule vers la position &quot;Activé&quot; si vous souhaitez que toutes les activités de Cible en direct admissibles à la prise de décision sur l’appareil soient automatiquement incluses dans l’artefact.

   Si vous laissez cette option désactivée, vous devez recréer et activer toutes les activités de prise de décision sur le périphérique pour qu’elles soient incluses dans l’artefact des règles généré. En d’autres termes, toute activité à l’état actif avant d’activer la bascule [!UICONTROL Décision sur le périphérique] n’est pas incluse dans l’artefact de règles.

Après avoir activé la bascule [!UICONTROL Décision sur le périphérique], [!DNL Target] commence à générer et à propager [les artefacts de règle](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) pour votre client.

>[!IMPORTANT]
>
>Veillez à activer la bascule avant d’initialiser le SDK Adobe Target pour utiliser la prise de décision sur le périphérique. Les artefacts de règle doivent d’abord générer et propager les réseaux de diffusion de contenu Akamai pour que la prise de décision sur le périphérique fonctionne. La propagation peut prendre de cinq à dix minutes pour que le premier artefact de règle soit généré et propagé sur le réseau de diffusion de contenu Akamai.

## Comment configurer at.js 2.5.0+ pour utiliser la prise de décision sur périphérique ?

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Détails du compte]**.
1. Sous **[!UICONTROL Méthodes d’implémentation]** > **[!UICONTROL Méthode d’implémentation principale]**, cliquez sur **[!UICONTROL Modifier]** en regard de votre version at.js (doit être at.js 2.5.0 ou version ultérieure).

   ![Modifier les paramètres de la méthode d’implémentation principale](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Avant de modifier ces paramètres par défaut, contactez le service à la clientèle afin de ne pas affecter votre mise en oeuvre actuelle.

1. Sélectionnez la méthode de prise de décision de votre choix :

   * [!UICONTROL Serveur uniquement]
   * [!UICONTROL Sur périphérique uniquement]
   * [!UICONTROL Hybride]

   ![Modification du panneau des paramètres d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Paramètres globaux

Vous pouvez configurer une [!UICONTROL méthode de prise de décision] par défaut pour toutes les décisions [!DNL Target]. Les différentes méthodes de prise de décision sont [!UICONTROL côté serveur uniquement], [!UICONTROL On-device only] et [!UICONTROL Hybrid]. La méthode de prise de décision sélectionnée dans l’interface utilisateur de la Cible est configurée dans `window.targetGlobalSettings` sous le champ `decisioningMethod`. En savoir plus sur `decisioningMethod` dans [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### Paramètre personnalisé

Si vous définissez `decisioningMethod` dans `window.targetGlobalSettings`, mais souhaitez remplacer `decisioningMethod` pour chaque décision Adobe Target en fonction de votre cas d’utilisation, vous pouvez effectuer cette procédure en spécifiant `decisioningMethod` dans l’appel [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) d’At.js2.5.0+.

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>Pour utiliser &quot;sur périphérique&quot; ou &quot;hybride&quot; comme méthode de prise de décision dans l’appel getOffers(), assurez-vous que le paramètre global a `decisioningMethod` comme &quot;sur périphérique&quot; ou &quot;hybride&quot;. La bibliothèque at.js 2.5.0+ doit savoir si l’artefact des règles JSON doit être téléchargé et mis en cache immédiatement après son chargement sur la page. Si la méthode de prise de décision pour le paramètre global est définie sur &quot;côté serveur&quot; et que la méthode de prise de décision &quot;sur périphérique&quot; ou &quot;hybride&quot; est transmise à l’appel getOffers(), at.js 2.5.0+ ne verra pas l’artefact de règle JSON mis en cache pour exécuter vos décisions sur périphérique.

### TTL de cache d&#39;artefact

[!DNL Target] représente vos activités qui remplissent les conditions requises pour la prise de décision sur périphérique en tant qu’artefact constitué de métadonnées, de règles et de conditions. Cet artefact est mis en cache sur le réseau de diffusion de contenu Akamai. Lors de la première visite de votre utilisateur, le navigateur de l’utilisateur télécharge et met en cache l’artefact qui représente vos activités de prise de décision sur le périphérique.

Lors des visites suivantes sur votre site, le navigateur vérifie automatiquement s’il doit télécharger une version plus récente de l’artefact. Cette vérification ajoute de la latence. Le TTL du cache d’artefacts définit le nombre de minutes pendant lesquelles le navigateur ne souhaite pas rechercher un artefact mis à jour depuis le dernier téléchargement réussi. Plus la période est longue, meilleures sont les performances. Plus la période est courte, plus la fraîcheur des données est bonne, mais au prix d&#39;une latence supplémentaire.

## Comment puis-je savoir qu’une activité est admissible à la prise de décision sur périphérique ?

Une fois que vous avez créé une activité éligible pour la prise de décision sur le périphérique, une étiquette indiquant [!UICONTROL La prise de décision sur le périphérique éligible] est visible dans la page de l’activité [!UICONTROL Aperçu].

![Décision sur le périphérique Étiquette éligible sur la page Aperçu de l’activité.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Cette étiquette ne signifie pas que l’activité sera toujours fournie par le biais de la prise de décision sur le périphérique. Ce n’est que lorsque at.js 2.5.0+ est configuré pour utiliser la prise de décision sur le périphérique que cette activité sera exécutée sur le périphérique. Si at.js 2.5.0+ n’est pas configuré pour l’utilisation sur le périphérique, cette activité sera toujours diffusée via un appel au serveur effectué à partir d’at.js.

Vous pouvez filtrer toutes les activités qui prennent une décision sur le périphérique et qui sont éligibles sur la page [!UICONTROL Activités] via le filtre [!UICONTROL Autorisation de prise de décision sur le périphérique].

![Décision sur le périphérique Filtre éligible sur la page Activités.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>Après avoir créé et activé une activité éligible pour la prise de décision sur périphérique, il peut s’écouler de cinq à dix minutes avant qu’elle ne soit incluse dans l’artefact de règles qui est généré et propagé au point de présence CDN d’Akamai.

## Récapitulatif des étapes permettant de s’assurer que mes activités de prise de décision sur périphérique sont fournies via At.js 2.5.0+ ?

1. Accédez à l’interface utilisateur Adobe Target et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!DNL Account Details]** pour activer la bascule **[!UICONTROL Prise de décision sur le périphérique]**.
1. Activez l’option **&quot;[!UICONTROL Inclure toutes les activités qualifiées de prise de décision sur périphérique existantes dans l’option artefact]&quot;**.

   La première génération d’artefact de règles JSON peut prendre jusqu’à 10 minutes.

1. Créez et activez un type d&#39;activité [pris en charge par la prise de décision sur le périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md) et vérifiez qu&#39;il est éligible à la prise de décision sur le périphérique.
1. Définissez la **[!UICONTROL méthode de prise de décision]** sur **[!UICONTROL &quot;Hybrid&quot;]** ou **[!UICONTROL &quot;On-device only&quot;]** via l’interface utilisateur des paramètres at.js.
1. Téléchargez et déployez At.js 2.5.0+ sur vos pages.

## Résolution des problèmes

Suivez les étapes ci-après pour résoudre les problèmes de prise de décision sur le périphérique :

1. Activation du journal de la console pour at.js
1. Vérifiez le téléchargement de l’artefact de règle dans l’onglet Réseau de votre navigateur.
1. Vérification du téléchargement d’artefact de règle à l’aide de événements personnalisés at.js

Les sections suivantes décrivent chaque étape de manière plus détaillée :

### Étape 1 : Activation du journal de la console pour at.js

L’ajout du paramètre d’URL `mboxDebug=1` permet à at.js d’imprimer des messages dans la console de votre navigateur.

Tous les messages contiennent un préfixe &quot;AT:&quot; pour un aperçu pratique. Pour vous assurer qu’un artefact a bien été chargé, votre journal de console doit contenir des messages similaires à ceux-ci :

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

L’illustration suivante présente ces messages dans le journal de la console :

![Journal de la console avec des messages d&#39;artefact](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

### Étape 2 : Vérifiez le téléchargement de l’artefact de règle dans l’onglet Réseau de votre navigateur.

Ouvrez l’onglet Réseau de votre navigateur.

Par exemple, pour ouvrir DevTools dans Google Chrome :

1. Appuyez sur Ctrl+Maj+J (Windows) ou Commande+Option+J (Mac).
1. Accédez à l&#39;onglet Réseau.
1. Vous pouvez filtrer vos appels par mot-clé &quot;règles.json&quot; pour vous assurer que seul le fichier de règles d’artefact s’affiche.

   En outre, vous pouvez filtrer par &quot;/diffusion|rules.json/&quot; pour afficher tous les appels [!DNL Target] et artefact rule.json.

   ![Onglet Réseau dans Google Chrome](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

### Vérification du téléchargement d’artefact de règle à l’aide de événements personnalisés at.js

La bibliothèque at.js distribue deux nouveaux événements personnalisés pour prendre en charge la prise de décision sur le périphérique.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Vous pouvez vous abonner pour écouter ces événements personnalisés dans votre application afin de passer à l’action en cas de succès ou d’échec du téléchargement du fichier de règles d’artefact.

L’exemple suivant montre un exemple de code qui écoute les événements de succès et d’échec du téléchargement d’artefact :

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
