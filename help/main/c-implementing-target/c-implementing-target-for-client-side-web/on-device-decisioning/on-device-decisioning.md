---
keywords: mise en oeuvre;bibliothèque javascript;js;atjs;prise de décision sur l’appareil;prise de décision sur l’appareil;at.js;sur l’appareil;sur l’appareil
description: Découvrez comment prendre des décisions sur l’appareil avec la bibliothèque at.js
title: Comment la prise de décision sur l’appareil fonctionne-t-elle avec la bibliothèque JavaScript at.js ?
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '3546'
ht-degree: 18%

---

# Prise de décision sur appareil pour at.js

À compter de la version 2.5.0, at.js propose la prise de décision sur l’appareil. La prise de décision sur appareil vous permet de mettre en cache votre [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) et [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activités sur le navigateur pour effectuer une prise de décision en mémoire sans bloquer la demande réseau au [!DNL Adobe Target] Edge Network.

[!DNL Target] offre également la flexibilité de fournir l’expérience la plus pertinente et la plus à jour de vos activités de personnalisation d’expérimentation et d’apprentissage automatique (basées sur le ML) via un appel serveur en direct. En d’autres termes, lorsque les performances sont plus importantes, vous pouvez choisir d’utiliser la prise de décision sur l’appareil. Cependant, lorsque l’expérience la plus pertinente, à jour et pilotée par ML est nécessaire, un appel au serveur peut être effectué à la place.

## Quels sont les avantages de la prise de décision sur appareil ?

Les avantages de la prise de décision sur appareil incluent :

* **Proposez des décisions et des expériences rapides et éclatantes.** Le regroupement et la prise de décision sont effectués en mémoire et sur le navigateur afin d’éviter de bloquer les requêtes réseau.
* **Amélioration des performances de l’application.** Exécutez des expériences et personnalisez vos clients et utilisateurs sans compromettre les expériences de l’utilisateur final.
* **Amélioration du score de qualité du site Google.** Une fois la prise de décision en mémoire, améliorez le score de qualité du site Google de votre entreprise en ligne pour le rendre plus facilement détectable par les consommateurs.
* **Découvrez les analyses en temps réel.** Obtenez des informations sur les performances de votre activité en temps réel via [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) création de rapports. A4T vous permet de faire pivoter votre stratégie à des moments critiques.

## Fonctionnalités prises en charge

Le SDK Adobe Target JS offre aux clients la possibilité de choisir entre les performances et l’actualisation des données pour les décisions. En d’autres termes, si la diffusion de contenu personnalisé le plus pertinent et attrayant par le biais de l’apprentissage automatique est la plus importante pour vous, un appel au serveur en direct doit être effectué. Mais lorsque les performances sont plus critiques, une décision doit être prise sur l’appareil et en mémoire. Pour que la prise de décision sur l’appareil fonctionne, reportez-vous à la liste des fonctionnalités prises en charge :

* Types d’activités
* Ciblage de l’audience
* Méthode d’affectation

Pour plus d’informations, voir [Fonctionnalités prises en charge pour la prise de décision sur les appareils](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

## Comment fonctionne la prise de décision sur appareil ?

Lorsque vous déployez et initialisez at.js avec la prise de décision sur l’appareil activée, une [artefact de règle](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/) qui inclut votre prise de décision sur l’appareil pour les activités A/B et XT, les audiences et les ressources, est téléchargé du réseau de diffusion de contenu Akamai le plus proche à votre visiteur et mis en cache localement sur le navigateur de votre visiteur. Lorsqu’une demande est envoyée à partir d’at.js pour récupérer une expérience, la décision concernant l’expérience à renvoyer est prise en mémoire, en fonction des métadonnées codées dans l’artefact de règle mis en cache.

## Méthode de prise de décision

Avec la prise de décision sur l’appareil, [!DNL Target] introduit un nouveau paramètre appelé [!UICONTROL Méthode de prise de décision]. Le [!UICONTROL Méthode de prise de décision] détermine la manière dont at.js fournit vos expériences. [!UICONTROL Méthode de prise de décision] a trois valeurs :

* [!UICONTROL Côté serveur uniquement]
* [!UICONTROL Sur appareil uniquement]
* [!UICONTROL Hybride]

### Côté serveur uniquement

[!UICONTROL Côté serveur uniquement] est la méthode de prise de décision par défaut préconfigurée lors de l’implémentation et du déploiement d’at.js 2.5.0+ sur vos propriétés web.

L’utilisation de [!UICONTROL Côté serveur uniquement] comme configuration par défaut signifie que toutes les décisions sont prises sur le réseau Edge de [!DNL Target], ce qui implique un appel au serveur bloquant. Cette approche peut entraîner une latence incrémentielle, mais elle offre également des avantages significatifs, comme la possibilité d’appliquer les fonctionnalités de machine learning de Target qui incluent les activités [Recommendations](/help/main/c-recommendations/recommendations.md), [Personnalisation automatisée](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) et [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

En outre, l’amélioration de vos expériences personnalisées à l’aide du profil utilisateur de Target, qui est persistant entre les sessions et les canaux, peut fournir des résultats performants pour votre entreprise.

Enfin, la valeur [!UICONTROL côté serveur uniquement] vous permet d’utiliser Adobe Experience Cloud et d’affiner les audiences qui peuvent être ciblées par le biais des segments d’Audience Manager et d’Adobe Analytics.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et le réseau Adobe Target Edge. Ce diagramme de flux capture les nouveaux visiteurs et les visiteurs récurrents.

![Diagramme de flux côté serveur uniquement](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

La liste suivante correspond aux nombres du diagramme :

| Étape | Description |
| --- | --- |
| 1 | Le [!DNL Experience Cloud Visitor ID] est récupéré à partir de la fonction [Service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>   La bibliothèque at.js peut également être chargée de manière asynchrone avec un fragment de code de prémasquage facultatif implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une requête de chargement de page est envoyée, qui inclut tous les paramètres configurés, tels que (ECID, ID de client, paramètres personnalisés, profil utilisateur, etc.). |
| 5 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils.<br>La banque de profils demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, les audiences partagées depuis [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 6 | La banque de profils est utilisée pour la qualification et le regroupement des audiences afin de filtrer les activités. |
| 7 | Le contenu résultant est sélectionné une fois que l’expérience est déterminée à partir de l’expérience en direct. [!DNL Target] activités. |
| 8 | La bibliothèque at.js masque les éléments correspondants sur la page associés à l’expérience qui doit être rendue. |
| 9 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour que le visiteur puisse l’afficher. |
| 10 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir du réseau Target Edge. |
| 11 | L’expérience est générée pour le visiteur. |
| 12 | La page web entière se charge. |
| 13 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. |
| 14 | Les données ciblées sont associées à [!DNL Analytics] Les données par l’intermédiaire du SDID sont traitées dans la variable [!DNL Analytics] stockage des rapports. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

### Sur appareil uniquement

[!UICONTROL Sur l’appareil uniquement] est la méthode de prise de décision qui doit être définie dans at.js 2.5.0+ lorsque la prise de décision sur l’appareil doit uniquement être utilisée sur l’ensemble de vos pages web.

La prise de décision sur l’appareil permet une diffusion incroyablement rapide de vos expériences et de vos activités de personnalisation. Les décisions sont en effet prises à partir d’un artefact de règles mis en cache qui contient toutes vos activités remplissant les critères de la prise de décision sur l’appareil.

Pour en savoir plus sur les activités qui remplissent les critères de la prise de décision sur les appareils, voir [Fonctionnalités prises en charge dans la prise de décision sur les appareils](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/).

Cette méthode de prise de décision ne doit être utilisée que si les performances sont très critiques sur toutes les pages qui requièrent des décisions de [!DNL Target]. En outre, gardez en tête que lorsque cette méthode de prise de décision est sélectionnée, vos activités [!DNL Target] ne remplissant pas les critères de la prise de décision sur l’appareil ne seront ni diffusées ni exécutées. La bibliothèque at.js version 2.5.0+ est configurée pour rechercher uniquement l’artefact de règles mis en cache afin de prendre des décisions.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et le réseau de diffusion de contenu Akamai. Le réseau de diffusion de contenu Akamai met en cache l’artefact de règles pour la première visite du visiteur. Pour la première visite de page d’un nouveau visiteur, l’artefact de règles JSON doit être téléchargé à partir du réseau de diffusion de contenu Akamai pour être mis en cache localement sur le navigateur du visiteur. Une fois l’artefact de règles JSON téléchargé, la décision est prise immédiatement sans appel réseau de blocage. Le diagramme de flux suivant capture les nouveaux visiteurs.

![Diagramme de flux sur périphérique uniquement](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

La liste suivante correspond aux nombres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités admissibles pour la prise de décision sur l’appareil, génèrent l’artefact de règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour puissent générer un nouvel artefact de règles JSON à propager sur le réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | Le [!DNL Experience Cloud Visitor ID] est récupéré à partir de la fonction [Service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un fragment de code de prémasquage facultatif implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | La bibliothèque at.js émet une requête pour récupérer l’artefact de règle JSON du réseau de diffusion de contenu Akamai le plus proche au visiteur. |
| 5 | Le réseau de diffusion de contenu Akamai répond avec l’artefact de règle JSON. |
| 6 | L’artefact de règle JSON est mis en cache localement sur le navigateur du visiteur. |
| 7 | La bibliothèque at.js interprète l’artefact de règle JSON et exécute la décision de récupérer l’expérience et masque les éléments testés. |
| 8 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour que le visiteur puisse l’afficher. |
| 9 | La bibliothèque at.js manipule le modèle DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 10 | L’expérience est générée pour le visiteur. |
| 11 | La page web entière se charge. |
| 12 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] Les données par l’intermédiaire du SDID sont traitées dans la variable [!DNL Analytics] stockage des rapports. [!DNL Analytics][!DNL Analytics]Il est alors possible de consulter les données dans et dans par l’intermédiaire des rapports Analytics for Target (A4T).[!DNL Target] |

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et l’artefact de règle JSON mis en cache pour l’accès à la page ou la visite récurrente du visiteur. Comme l’artefact de règles JSON est déjà mis en cache et disponible sur le navigateur, la décision est prise immédiatement sans appel réseau bloquant. Ce diagramme de flux capture la navigation de page ou les visiteurs récurrents qui s’ensuivent.

![Diagramme de flux sur l’appareil uniquement pour la navigation suivante sur la page et les visites répétées](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

La liste suivante correspond aux nombres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités admissibles pour la prise de décision sur l’appareil, génèrent l’artefact de règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour puissent générer un nouvel artefact de règles JSON à propager sur le réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | Le [!DNL Experience Cloud Visitor ID] est récupéré à partir de la fonction [Service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un fragment de code de prémasquage facultatif implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | La bibliothèque at.js interprète l’artefact de règle JSON et exécute en mémoire la décision de récupérer l’expérience. |
| 5 | Les éléments testés sont masqués. |
| 6 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour que le visiteur puisse l’afficher. |
| 7 | La bibliothèque at.js manipule le modèle DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 8 | L’expérience est générée pour le visiteur. |
| 9 | La page web entière se charge. |
| 10 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] Les données par l’intermédiaire du SDID sont traitées dans la variable [!DNL Analytics] stockage des rapports. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

### Hybride

[!UICONTROL Hybride] représente la méthode de prise de décision qui doit être définie dans at.js 2.5.0+ lorsque la prise de décision sur l’appareil et les activités nécessitant un appel au réseau Edge d’Adobe Target doivent être exécutées.

Lorsque vous gérez des activités de prise de décision sur l’appareil et des activités côté serveur, il peut s’avérer un peu compliqué et fastidieux de réfléchir à la manière de déployer et de configurer [!DNL Target] sur vos pages. Avec la méthode de prise de décision hybride, [!DNL Target] sait quand il doit effectuer un appel au serveur vers le réseau Edge d’Adobe Target pour les activités qui nécessitent une exécution côté serveur. Il sait également quand exécuter uniquement les décisions sur l’appareil.

L’artefact de règles JSON comprend des métadonnées qui indiquent à at.js si une mbox comporte une activité côté serveur en cours d’exécution ou une activité de prise de décision sur l’appareil. Cette méthode de prise de décision garantit que les activités que vous prévoyez de diffuser rapidement sont conduites par le biais de la prise de décision sur l’appareil. Les activités qui nécessitent une personnalisation plus puissante pilotée par ML sont conduites via le réseau Edge d’Adobe Target.

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+, le réseau de diffusion de contenu Akamai et le réseau Edge Adobe Target pour un nouveau visiteur qui consulte votre page pour la première fois. Ce diagramme montre que l’artefact de règles JSON est téléchargé de manière asynchrone pendant que les décisions sont prises via le réseau Adobe Target Edge.

Cette approche garantit que la taille de l’artefact, qui peut inclure de nombreuses activités, n’influence pas négativement la latence de la décision. Le téléchargement synchrone de l’artefact de règles JSON et la prise de la décision par la suite peuvent également avoir des effets négatifs sur la latence et peuvent être incohérents. Par conséquent, la méthode de prise de décision hybride est une recommandation recommandée pour toujours effectuer un appel côté serveur pour la décision d’un nouveau visiteur, car l’artefact de règles JSON est mis en cache en parallèle. Pour toutes les visites de page suivantes et les visites récurrentes, les décisions sont prises à partir du cache et en mémoire par le biais de l’artefact de règles JSON.

![Diagramme de flux hybride pour un nouveau visiteur](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

La liste suivante correspond aux nombres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités admissibles pour la prise de décision sur l’appareil, génèrent l’artefact de règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour puissent générer un nouvel artefact de règles JSON à propager sur le réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | Le [!DNL Experience Cloud Visitor ID] est récupéré à partir de la fonction [Service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un fragment de code de prémasquage facultatif implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une demande de chargement de page est envoyée à Adobe Target Edge Network, y compris tous les paramètres configurés tels que (ECID, ID de client, paramètres personnalisés, profil utilisateur, etc.). |
| 5 | En parallèle, at.js émet une requête pour récupérer l’artefact de règle JSON du réseau de diffusion de contenu Akamai le plus proche au visiteur. |
| 6 | (Adobe Target Edge Network) Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. La banque de profils demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, les audiences partagées depuis [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], etc.). |
| 7 | Le réseau de diffusion de contenu Akamai répond avec l’artefact de règle JSON. |
| 8 | La banque de profils est utilisée pour la qualification et le regroupement des audiences afin de filtrer les activités. |
| 9 | Le contenu résultant est sélectionné une fois que l’expérience est déterminée à partir de l’expérience en direct. [!DNL Target] activités. |
| 10 | La bibliothèque at.js masque les éléments correspondants sur la page associés à l’expérience qui doit être rendue. |
| 11 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour que le visiteur puisse l’afficher. |
| 12 | La bibliothèque at.js manipule le DOM pour effectuer le rendu de l’expérience à partir du réseau Target Edge. |
| 13 | L’expérience est générée pour le visiteur. |
| 14 | La page web entière se charge. |
| 15 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] Les données par l’intermédiaire du SDID sont traitées dans la variable [!DNL Analytics] stockage des rapports. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

Le diagramme suivant illustre l’interaction entre votre visiteur, le navigateur, at.js 2.5.0+ et l’artefact de règles JSON mis en cache pour une navigation de page ou une visite de retour ultérieure. Dans ce diagramme, concentrez-vous uniquement sur le cas d’utilisation où une décision sur l’appareil est prise pour la navigation ou la visite récurrente de la page suivante. Gardez à l’esprit que, selon les activités actives pour certaines pages, un appel côté serveur peut être effectué pour exécuter des décisions côté serveur.

![Diagramme de flux hybride pour la navigation suivante sur une page et les visites répétées](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

La liste suivante correspond aux nombres du diagramme :

>[!NOTE]
>
>[!DNL Adobe Target] Les serveurs d’administration qualifient toutes vos activités admissibles pour la prise de décision sur l’appareil, génèrent l’artefact de règles JSON et le propagent au réseau de diffusion de contenu Akamai. Vos activités sont surveillées en permanence pour que les mises à jour puissent générer un nouvel artefact de règles JSON à propager sur le réseau de diffusion de contenu Akamai.

| Étape | Description |
| --- | --- |
| 1 | Le [!DNL Experience Cloud Visitor ID] est récupéré à partir de la fonction [Service Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>La bibliothèque at.js peut également être chargée de manière asynchrone avec un fragment de code de prémasquage facultatif implémenté sur la page. |
| 3 | La bibliothèque at.js masque le corps pour éviter le scintillement. |
| 4 | Une demande est envoyée pour récupérer une expérience. |
| 5 | La bibliothèque at.js confirme que l’artefact de règle JSON a déjà été mis en cache et exécute en mémoire la décision de récupérer l’expérience. |
| 6 | Les éléments testés sont masqués. |
| 7 | La bibliothèque at.js affiche le corps afin que le reste de la page puisse être chargé pour que le visiteur puisse l’afficher. |
| 8 | La bibliothèque at.js manipule le modèle DOM pour effectuer le rendu de l’expérience à partir de l’artefact de règle JSON mis en cache. |
| 9 | L’expérience est générée pour le visiteur. |
| 10 | La page web entière se charge. |
| 11 | Les données [!DNL Analytics] sont envoyées aux serveurs de collecte de données. Les données ciblées sont associées à [!DNL Analytics] Les données par l’intermédiaire du SDID sont traitées dans la variable [!DNL Analytics] stockage des rapports. Il est alors possible de consulter les données [!DNL Analytics] dans [!DNL Analytics] et dans [!DNL Target] par l’intermédiaire des rapports [!UICONTROL Analytics for Target] (A4T). |

## Comment activer la prise de décision sur l’appareil ?

La prise de décision sur appareil est disponible pour tous les [!DNL Target] clients qui utilisent at.js 2.5.0+.

Pour activer la prise de décision sur l’appareil :

>[!NOTE]
>
>Vous devez avoir la variable [!UICONTROL Administration] ou [!UICONTROL Approbateur] [rôle utilisateur](/help/main/administrating-target/c-user-management/user-management.md) pour activer ou désactiver le bouton activer/désactiver de la prise de décision sur le périphérique.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Détails du compte]**.
1. Sous **[!UICONTROL Détails du compte]**, faites glisser le curseur **[!UICONTROL Prise de décision sur appareil]** basculez sur la position &quot;activé&quot;.

   ![Bascule de la prise de décision sur l’appareil](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   Le &quot;[!UICONTROL Incluez toutes les activités qualifiées de prise de décision sur l’appareil existantes dans l’artefact.]&quot; s’affiche si vous activez la prise de décision sur l’appareil.
1. (Conditionnel) Faites glisser le bouton d’activation vers la position &quot;Activé&quot; si vous souhaitez que toutes vos activités Target actives qui remplissent les critères pour la prise de décision sur l’appareil soient automatiquement incluses dans l’artefact.

   Si vous laissez ce bouton désactivé, vous devez recréer et activer toutes les activités de prise de décision sur l’appareil pour qu’elles soient incluses dans l’artefact de règles généré. En d’autres termes, toute activité à l’état actif avant d’activer la fonction [!UICONTROL Prise de décision sur appareil] Les bascules ne sont pas incluses dans l’artefact de règles.

Après avoir activé la variable [!UICONTROL Prise de décision sur appareil] basculer, [!DNL Target] commence à générer et à propager ; [artefacts de règle](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/rule-artifact/) pour votre client.

>[!IMPORTANT]
>
>Veillez à activer le bouton bascule avant d’initialiser le SDK Adobe Target pour utiliser la prise de décision sur l’appareil. Les artefacts de règle doivent d’abord être générés et propagés aux réseaux de diffusion de contenu Akamai pour que la prise de décision sur l’appareil fonctionne. La propagation peut prendre entre cinq et dix minutes pour que le premier artefact de règle soit généré et propagé vers le réseau de diffusion de contenu Akamai.

## Comment configurer at.js 2.5.0+ pour utiliser la prise de décision sur l’appareil ?

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!UICONTROL Détails du compte]**.
1. Sous **[!UICONTROL Méthodes de mise en oeuvre]** > **[!UICONTROL Méthode de mise en oeuvre principale]**, cliquez sur **[!UICONTROL Modifier]** en regard de votre version d’at.js (doit être at.js 2.5.0 ou version ultérieure).

   ![Modification des paramètres de la méthode d’implémentation principale](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Avant de modifier ces paramètres par défaut, contactez le service à la clientèle afin de ne pas affecter votre mise en oeuvre actuelle.

1. Sélectionnez la méthode de prise de décision souhaitée :

   * [!UICONTROL Côté serveur uniquement]
   * [!UICONTROL Sur appareil uniquement]
   * [!UICONTROL Hybride]

   ![Modification du panneau des paramètres at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Paramètres globaux

Vous pouvez configurer une valeur par défaut. [!UICONTROL Méthode de prise de décision] pour tous les [!DNL Target] décisions. Les différentes méthodes de prise de décision sont les suivantes : [!UICONTROL Côté serveur uniquement], [!UICONTROL Sur appareil uniquement], et [!UICONTROL Hybride]. La méthode de prise de décision sélectionnée dans l’interface utilisateur de Target est configurée dans `window.targetGlobalSettings` sous le `decisioningMethod` champ . En savoir plus sur les `decisioningMethod` in [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

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

Si vous définissez la variable `decisioningMethod` in `window.targetGlobalSettings`, mais souhaitez remplacer la variable `decisioningMethod` pour chaque décision Adobe Target en fonction de votre cas d’utilisation, vous pouvez effectuer cette procédure en spécifiant `decisioningMethod` dans at.js2.5.0+ [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) appelez .

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
>Pour utiliser &quot;sur l’appareil&quot; ou &quot;hybride&quot; comme méthode de prise de décision dans l’appel getOffers() , assurez-vous que le paramètre global comporte `decisioningMethod` comme &quot;sur l’appareil&quot; ou &quot;hybride&quot;. La bibliothèque at.js version 2.5.0+ doit savoir si l’artefact des règles JSON doit être téléchargé et mis en cache immédiatement après le chargement sur la page. Si la méthode de prise de décision pour le paramètre global est définie sur &quot;côté serveur&quot; et que la méthode de prise de décision &quot;on-device&quot; ou &quot;hybride&quot; est transmise à l’appel getOffers(), at.js 2.5.0+ n’aurait pas l’artefact de règle JSON mis en cache pour exécuter vos décisions sur l’appareil.

### TTL du cache des artefacts

[!DNL Target] représente vos activités qui remplissent les critères de la prise de décision sur l’appareil comme un artefact constitué de métadonnées, de règles et de conditions. Cet artefact est mis en cache sur le réseau de diffusion de contenu Akamai. Lors de la première visite de votre utilisateur, le navigateur de l’utilisateur télécharge et met en cache l’artefact qui représente vos activités de prise de décision sur l’appareil.

Lors des visites suivantes sur votre site, le navigateur vérifie automatiquement s’il doit télécharger une version plus récente de l’artefact. Cette vérification ajoute une latence. La durée de vie (TTL) du cache des artefacts définit le nombre de minutes pendant lesquelles le navigateur ne doit pas rechercher un artefact mis à jour depuis le dernier téléchargement réussi. Plus la période est longue, meilleures sont les performances. Plus la période est courte, plus l’actualisation des données est importante, mais au prix d’une latence supplémentaire.

## Comment savoir si une activité est éligible à la prise de décision sur appareil ?

Une fois que vous avez créé une activité éligible à la prise de décision sur l’appareil, un libellé qui indique [!UICONTROL Prise de décision sur appareil éligible], est visible dans la variable [!UICONTROL Présentation] page.

![Prise de décision sur l’appareil Libellé éligible sur la page Aperçu de l’activité.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Cette étiquette ne signifie pas que l’activité sera toujours diffusée par le biais de la prise de décision sur l’appareil. Cette activité ne sera exécutée sur l’appareil que lorsque at.js 2.5.0+ est configuré pour utiliser la prise de décision sur l’appareil. Si at.js 2.5.0+ n’est pas configuré pour utiliser sur l’appareil, cette activité sera toujours diffusée via un appel au serveur effectué à partir d’at.js.

Vous pouvez filtrer toutes les activités qui sont éligibles à la prise de décision sur les appareils sur le [!UICONTROL Activités] via la page [!UICONTROL Prise de décision sur appareil éligible] filtre.

![Prise de décision sur l’appareil Filtre éligible sur la page Activités.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>Après avoir créé et activé une activité éligible à la prise de décision sur l’appareil, il peut s’écouler entre cinq et dix minutes avant qu’elle ne soit incluse dans l’artefact de règles généré et propagé vers le point de présence du réseau de diffusion de contenu Akamai.

## Résumé des étapes pour garantir que mes activités de prise de décision sur l’appareil sont diffusées via at.js 2.5.0+?

1. Accédez à l’interface utilisateur d’Adobe Target et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** > **[!DNL Account Details]** pour activer la variable **[!UICONTROL Prise de décision sur appareil]** bascule.
1. Activez la variable **&quot;[!UICONTROL Incluez toutes les activités qualifiées de prise de décision sur l’appareil existantes dans l’artefact.]&quot;** bascule.

   La première génération d’artefact de règles JSON peut prendre jusqu’à 10 minutes.

1. Créez et activez un [type d’activité pris en charge par la prise de décision sur l’appareil](https://developer.adobe.com/target/implement/client-side/atjs/on-device-decisioning/supported-features/), et vérifiez qu’il est éligible à la prise de décision sur l’appareil.
1. Définissez la variable **[!UICONTROL Méthode de prise de décision]** à **[!UICONTROL &quot;Hybride&quot;]** ou **[!UICONTROL &quot;Sur appareil uniquement&quot;]** via l’interface utilisateur des paramètres at.js.
1. Téléchargez et déployez at.js 2.5.0+ sur vos pages.
