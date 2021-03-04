---
keywords: a4t;analytics;analytics pour target;source de reporting analytics;adobe analytics en tant que source de reporting pour target
description: Utilisez Analytics pour la Cible (A4T) pour créer des activités basées sur les mesures de conversion et les segments d’audience Analytics et utilisez les rapports Analytics pour examiner les résultats.
title: Qu’est-ce qu’Analytics pour la Cible (A4T) ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 42%

---


# Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)

[!DNL Adobe Analytics for Target] (A4T) est une intégration inter-solutions qui vous permet de créer des activités basées sur des mesures de  [!DNL Analytics] conversion et des segments d’audience. L’intégration A4T vous permet d’utiliser des rapports [!DNL Analytics] pour examiner vos résultats. Si vous utilisez [!DNL Analytics] comme source de rapports pour une activité, tous les rapports et segmentations pour cette activité sont basés sur la collecte de données [!DNL Analytics].

## Vue d’ensemble d’A4T {#section_92B66069210C40DBA937790E8CC596CF}

L&#39;intégration [!DNL Analytics for Target] entre [!DNL Analytics] et [!DNL Target] fournit de puissantes outils d&#39;analyse et d&#39;économie de temps pour votre programme d&#39;optimisation.

Les trois avantages Principaux de l&#39;utilisation des données [!DNL Analytics] dans [!DNL Target] sont les suivants :

* Les marketeurs peuvent appliquer dynamiquement des mesures de réussite ou des segments de rapports [!DNL Analytics] aux rapports d’activité [!DNL Target] à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Votre implémentation [!DNL Analytics] existante collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports. L’Adobe vous recommande toujours de mettre en oeuvre une mbox de confirmation de commande pour les activités [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP).

>[!IMPORTANT]
>
>Avant de pouvoir commencer à utiliser A4T, vous devez demander l’attribution de privilèges d’accès à l’intégration pour votre compte. Pour ce faire, utilisez [ce formulaire](https://www.adobe.com/go/audiences).
>
>L’intégration qui active [!DNL Analytics] en tant que source de données pour [!DNL Target] (A4T) représente la prochaine génération du module externe Test&amp;Cible to SiteCatalyst. Ce module externe est devenu obsolète mais est toujours pris en charge pour les clients qui l’utilisent déjà.

Si vous utilisez [!DNL Analytics] comme source de rapports pour une activité, tous les rapports et segmentations pour cette activité sont basés sur [!DNL Analytics].

Toutes les mesures [!DNL Analytics], y compris les mesures calculées, sont disponibles dans [!DNL Target] et le rapport [!UICONTROL Activités de Cible] dans [!DNL Analytics]. De même, tout segment disponible dans [!DNL Analytics] peut être appliqué aux deux solutions. Vous pouvez appliquer la mesure ou l&#39;audience au rapport dans [!DNL Target] après le démarrage de l&#39;activité, ou même après la fin de l&#39;activité.

Chaque mesure est incluse, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics pour Target (A4T) :

* Pour utiliser [!DNL Analytics] comme source de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Analytics] et à [!DNL Target]. [Contactez votre gestionnaire de compte](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. [!DNL Target][!DNL Target] continue à collecter les données à utiliser dans la création de rapports et les données sont toujours disponibles si vous préférez baser une activité sur les données collectées par [!DNL Target].
* Utilisez une source de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* Lors de l’utilisation d’A4T, toutes les mesures de réussite disponibles pour vos activités sont des mesures [!DNL Analytics]. Cependant, votre mesure d’objectif peut être basée sur un appel de mbox. Par exemple, vous pouvez utiliser les fonctionnalités de suivi des clics prêtes à l’emploi de la Cible avec A4T au lieu d’avoir à implémenter [!DNL Analytics] code de suivi des clics.
* Lors de l’affichage du rapports d’une activité A4T dans l’interface utilisateur [!DNL Target], vous consultez les données [!DNL Analytics]. Par exemple, si vous utilisez la mesure [!UICONTROL Visiteur] dans [!DNL Target], vous utilisez la mesure [!DNL Analytics] [!UICONTROL Visiteur], et non la mesure [!DNL Target] [!UICONTROL Visiteurs], qui est maintenant appelée [!UICONTROL Participants]. Cette différence est particulièrement importante pour les mesures de trafic de base ([!UICONTROL Visiteurs], [!UICONTROL Visites], [!UICONTROL Vues de page]) et les mesures de conversion.
* Toutes les activités [!DNL Target] existantes continuent d’utiliser la collecte de données [!DNL Target] et ne sont pas affectées par l’activation d’A4T.
* Une seule mesure basée sur une mbox est autorisée lors de l’utilisation de [!DNL Analytics] en tant que source de rapports.
* Un appel serveur à serveur de [!DNL Target] à [!DNL Analytics] envoie les informations d&#39;activité et d&#39;expérience à [!DNL Analytics]. Cette intégration n’entraîne pas davantage d’appels serveur pour [!DNL Target] ou [!DNL Analytics].

   Dans certains cas, les classifications de [!DNL Target] à [!DNL Analytics] échouent et les activités n&#39;affichent pas les données dans [!DNL Analytics]. Voir [Résolution des problèmes d’intégration d’Analytics et de Cible (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contacter le service à la clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir de l’aide.

## Types d’activité pris en charge {#section_F487896214BF4803AF78C552EF1669AA}

Le tableau suivant présente les types d’activité qui prennent en charge [!DNL Analytics] en tant que source de rapports dans [!DNL Target] (A4T) :

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| Activité A/B avec fractionnement manuel du trafic | Oui |  |
| Activité A/B avec affectation automatique | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| Activité A/B avec ciblage automatique | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| Ciblage d’expérience (XT) | Oui |  |
| Test multivarié (MVT) | Oui | Requiert l’objectif de la mesure d’objectif mbox pour obtenir le rapport [!UICONTROL Contribution des éléments]. Le rapport [!UICONTROL Contribution des éléments] ne prend actuellement pas en charge les mesures [!DNL Analytics]. |
| Activité d’Automated Personalization | Non |  |
| Activité de recommandations | Oui |  |
| Applications mobiles | Oui | Prise en charge avec le SDK Mobile Services, version 4.13.1 ou ultérieure. Pour plus d’informations, consultez la [documentation sur Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| Courrier électronique | Non |  |
| API Diffusion côté serveur | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK NodeJS | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Intégration du service cloud AEM 6.1 (ou version antérieure) | Non |  |
| Intégration du service cloud AEM 6.2 (ou version ultérieure) | Oui | Pour plus d’informations, voir [Intégration à Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) dans la documentation [!DNL Adobe Experience Manager] 6.2. |
| Toute activité utilisant une offre de redirection | Oui | Les exigences minimales requises sont plus strictes pour l’utilisation des offres de redirection avec A4T. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Oui | Pour plus d’informations, voir [Node.js SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk) dans le guide *Adobe Target SDKs*. |
| SDK Java | Oui | Pour plus d’informations, voir [Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk) dans le guide *Adobe Target* SDKs. |

Comme tous les types d’activités ne prennent pas encore en charge A4T, il est recommandé de conserver ou d’implémenter des mbox de conversion importantes, telles que la mbox `orderConfirmPage`.

## Exemples de rapports A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Pour vue des rapports A4T dans [!DNL Target], cliquez sur **[!UICONTROL Activités]**, cliquez sur l’activité de votre choix dans la liste qui utilise [!DNL Analytics] comme source de rapports, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.

>[!NOTE]
>
>Vous pouvez utiliser la liste déroulante [!UICONTROL Source de reporting] en haut de la page [!UICONTROL Activités] pour afficher seulement les activités qui utilisent [!DNL Analytics] comme source de reporting.

Vous pouvez permuter entre la [!UICONTROL Vue de tableau] et la [!UICONTROL Vue graphique] du rapport en cliquant sur l’icône appropriée dans l’angle supérieur droit du rapport.

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Mesure du rapport] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![](assets/a4t_report_graph2.png)

L’illustration suivante présente la [!UICONTROL vue Tableau] d’un rapport A4T :

![](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL Afficher dans Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Ouvrez [Analytics &amp; Cible : Didacticiel sur les meilleures pratiques en matière d’Analyse ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par [!DNL Adobe Experience League].

## Vidéos de formation :

Les vidéos suivantes contiennent plus d&#39;informations sur les concepts abordés dans cette rubrique.

### Analytics for Cible (A4T) (4:32) ![badge Aperçu](/help/assets/overview.png)

Cette vidéo explique comment utiliser [!DNL Analytics] comme source de rapports dans [!DNL Target] pour générer l&#39;analyse de votre programme d&#39;optimisation.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Cible Integration (A4T) (40:33) ![Badge du didacticiel](/help/assets/tutorial.png)

Cette vidéo est un enregistrement de « [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures de bureau d’intégration Analytics/Cible (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)
