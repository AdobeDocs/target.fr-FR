---
keywords: a4t;analytics;analytics pour target;source de reporting analytics;adobe analytics en tant que source de reporting pour target
description: Adobe « Analytics for Target » (A4T) est une intégration intersolutions permettant de créer des activités basées sur les mesures de conversion d’Analytics ainsi que sur les segments d’audience. Cette intégration permet d’utiliser les rapports Analytics pour étudier vos résultats. Si vous utilisez Analytics comme source de création de rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur la collecte de données Analytics.
title: Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)
subtopic: Intégration
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Adobe Analytics comme source de création de rapports pour Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

Adobe « Analytics for Target » (A4T) est une intégration intersolutions permettant de créer des activités basées sur les mesures de conversion d’Analytics ainsi que sur les segments d’audience. Cette intégration A4T vous permet d’utiliser les rapports Analytics pour étudier vos résultats. Si vous utilisez Analytics comme source de création de rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur la collecte de données Analytics.

## Présentation d’Analytics pour Target (A4T){#section_92B66069210C40DBA937790E8CC596CF}

L’intégration Analytics for Target entre Analytics et Target fournit des outils puissants d’analyse et de gain de temps destinés à votre programme d’optimisation.

Les trois principaux avantages offerts par l’utilisation des données Analytics dans Target sont les suivants :

* Les marketeurs peuvent appliquer dynamiquement les mesures de succès d’Analytics ou les segments de création de rapports aux rapports d’activités de Target, à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Votre implémentation existante d’Adobe Analytics collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports. Néanmoins, il est toujours recommandé d’implémenter une mbox de confirmation de commande pour les activités Automated Personalization (AP).

>[!IMPORTANT]
>
>Avant de commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Pour ce faire, utilisez [ce formulaire](https://www.adobe.com/go/audiences).
>
>L’intégration qui active Adobe Analytics en tant que source de données pour Adobe Target (A4T) représente la génération suivante du module externe Test&amp;Target vers SiteCatalyst. Ce module externe est devenu obsolète mais est toujours pris en charge pour les clients qui l’utilisent déjà.

Si vous utilisez Analytics comme source des rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur Analytics.

Toutes les mesures Analytics (y compris les mesures calculées) sont disponibles dans Target Standard/Premium et le rapport Activités cibles d’Analytics. De même, tout segment disponible dans Analytics peut être appliqué aux deux solutions. Vous pouvez appliquer la mesure ou l’audience au rapport dans Target Standard/Premium une fois que le test a débuté ou même une fois le test terminé.

Chaque mesure est incluse, y compris toute mesure du client ou calculée intégrée à Analytics.

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics pour Target (A4T) :

* Pour utiliser Adobe Analytics en tant que source de création de rapports pour Adobe Target, vous-même et votre société devez avoir accès à Adobe Analytics et à Adobe Target. [Contactez votre gestionnaire de compte](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. Target continue à collecter les données à utiliser dans la création de rapports et les données Target sont toujours disponibles si vous préférez baser une activité sur les données collectées par Target.
* Vous devez utiliser une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* Lorsque vous utilisez Analytics pour Target, toutes les mesures de succès disponibles pour vos activités sont des mesures Analytics. Cependant, votre mesure d’objectif peut être basée sur un appel de mbox. Par exemple, vous pouvez utiliser les fonctionnalités de suivi des clics prêtes à l’emploi de Target avec A4T au lieu de devoir implémenter le code de suivi des clics d’Analytics.
* Lorsque vous consultez des rapports relatifs à une activité A4T dans l’interface utilisateur de Target, vous consultez des données Analytics. Par exemple, si vous utilisez la mesure Visiteur dans Target, vous utilisez la mesure Visiteurs Analytics, et non la mesure Visiteurs Target, qui est à présent appelée Participants. Cette différence est particulièrement importante pour les mesures de trafic de base (Visiteurs, Visites, Pages vues) et les mesures de conversion.
* Toute activité Target existante continue à utiliser la collecte de données Target et n’est pas affectée par l’activation d’Analytics.
* Lorsqu’Analytics est utilisé comme source des rapports, une seule mesure basée sur mbox est autorisée.
* L’appel serveur à serveur de Target vers Analytics envoie les informations d’activité et d’expérience à Analytics. Cette intégration ne résulte pas en appels au serveur supplémentaires, que ce soit pour Target ou Analytics.

   Dans certains cas, l’appel de classification de Target à Analytics peut échouer et les activités n’affichent pas les données dans Analytics. Si cela se produit, voir [Résolution des problèmes de l’intégration d’Analytics et de Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contacter le service à la clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir de l’aide.

## Types d’activité pris en charge {#section_F487896214BF4803AF78C552EF1669AA}

Le tableau suivant indique les types d’activité qui prennent en charge Analytics comme source de création de rapports (A4T) :

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| Activité A/B avec fractionnement manuel du trafic | Oui |  |
| Activité A/B avec affectation automatique | Non |  |
| Activité A/B avec ciblage automatique | Non |  |
| Ciblage d’expérience (XT) | Oui |  |
| Test multivarié (MVT) | Oui | Requiert la mesure d’objectif basée sur mbox pour obtenir le rapport de contribution des éléments. Le rapport Contribution des éléments ne prend actuellement pas en charge les mesures d’Analytics. |
| Activité d’Automated Personalization | Non |  |
| Activité de recommandations | Oui |  |
| Applications mobiles | Oui | Prise en charge avec le SDK Mobile Services, version 4.13.1 ou ultérieure. Pour plus d’informations, consultez la [documentation sur Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html). |
| Courrier électronique | Non |  |
| API de diffusion côté serveur | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK NodeJS | Oui | Pour plus d’informations, voir [Côté serveur : mise en œuvre de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Intégration du service cloud AEM 6.1 (ou version antérieure) | Non |  |
| Intégration du service cloud AEM 6.2 (ou version ultérieure) | Oui | Pour plus d’informations, reportez-vous à la section [Intégration avec Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) de la documentation d’Adobe Experience Manager 6.2. |
| Activité utilisant une offre de redirection | Oui | Les exigences minimales requises sont plus strictes pour l’utilisation des offres de redirection avec A4T. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Oui |  |

Dans la mesure où tous les types d’activité ne prennent pas encore en charge Analytics pour Target, il est recommandé de conserver ou d’implémenter les mbox de conversion importantes, telles que la mbox « orderConfirmPage ».

## Exemples de rapports A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Pour afficher des rapports A4T dans [!DNL Target], cliquez sur **[!UICONTROL Activités]**, puis sur une activité dans la liste utilisant [!DNL Analytics] comme source de rapports &gt; puis cliquez sur l’onglet **[!UICONTROL Rapports]**.

>[!NOTE]
>
>Vous pouvez utiliser la liste déroulante [!UICONTROL Source de reporting] en haut de la page [!UICONTROL Activités] pour afficher seulement les activités qui utilisent [!DNL Analytics] comme source de reporting.

Vous pouvez basculer entre la vue Tableau et la [!UICONTROL vue Graphique] du rapport en cliquant sur l’icône appropriée en haut à droite du rapport.

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Mesure du rapport] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![](assets/a4t_report_graph2.png)

L’illustration suivante présente la [!UICONTROL vue Tableau] d’un rapport A4T :

![](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL Afficher dans Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Ouvrez le tutoriel [Analytics et Target : bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par Adobe Experience League.

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Analytics for Target (A4T) (4:32)

Dans cette vidéo, on explique de quelle façon utiliser Adobe Analytics comme source de création de rapports dans Adobe Target dans le cadre de l’analyse de votre programme d’optimisation.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384?captions=fre_fr)

### Intégration d’Analytics/de Target (A4T) (40:33)

Cette vidéo est un enregistrement de « [Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures de bureau d’intégration Analytics/Target (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)