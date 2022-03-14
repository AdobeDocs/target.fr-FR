---
keywords: a4t;analytics;analytics pour target;source de création de rapports analytics;adobe analytics en tant que source de création de rapports pour target;atjs;at.js;sdk web adobe experience platform;sdk web platform;sdk platform
description: Utilisation [!DNL Analytics] pour [!DNL Target] (A4T) pour créer des activités basées sur [!DNL Analytics] mesures de conversion et segments d’audience et utilisation [!DNL Analytics] rapports pour examiner les résultats.
title: Présentation [!DNL Analytics] pour [!DNL Target] (A4T) ?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 32%

---

# [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) est une intégration intersolutions qui vous permet de créer des activités basées sur des [!DNL Analytics] mesures de conversion et segments d’audience. L’intégration A4T vous permet d’utiliser [!DNL Analytics] rapports pour examiner vos résultats. Si vous utilisez [!DNL Analytics] en tant que source de création de rapports pour une activité, toutes les créations de rapports et segmentation pour cette activité sont basées sur [!DNL Analytics] collecte de données.

## Aperçu {#section_92B66069210C40DBA937790E8CC596CF}

Le [!DNL Analytics for Target] intégration entre [!DNL Analytics] et [!DNL Target] fournit de puissants outils d’analyse et d’économie de temps pour votre programme d’optimisation.

Les trois Principaux avantages de l’utilisation de [!DNL Analytics] données dans [!DNL Target] sont :

* Les marketeurs peuvent appliquer dynamiquement [!DNL Analytics] mesures de succès ou segments de création de rapports vers [!DNL Target] rapports d’activité à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Votre [!DNL Analytics] La mise en oeuvre collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports.

Si vous utilisez [!DNL Analytics] en tant que source de création de rapports pour une activité, toutes les créations de rapports et segmentation pour cette activité sont basées sur [!DNL Analytics].

Tous [!DNL Analytics] Les mesures, y compris les mesures calculées, sont disponibles dans [!DNL Target] et le [!UICONTROL Activités Target] rapport dans [!DNL Analytics], à une exception près. Les mesures calculées pour [!UICONTROL Effet élévateur et degré de confiance] ne sont pas prises en charge. De même, tout segment disponible dans [!DNL Analytics] peuvent être appliquées aux deux solutions. Vous pouvez appliquer la mesure ou l’audience au rapport dans [!DNL Target] une fois que l’activité a commencé, ou même une fois qu’elle est terminée.

Chaque mesure est incluse, y compris toute mesure personnalisée ou calculée intégrée [!DNL Analytics].

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics pour Target (A4T) :

* Pour utiliser [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous et votre entreprise devez avoir accès à [!DNL Analytics] et à [!DNL Target]. [Contactez votre gestionnaire de compte](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. [!DNL Target][!DNL Target] continue à collecter les données à utiliser dans la création de rapports et les données sont toujours disponibles si vous préférez baser une activité sur les données collectées par [!DNL Target].
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* Lors de l’utilisation d’A4T, toutes les mesures de succès disponibles pour vos activités sont [!DNL Analytics] mesures. Toutefois, la mesure d’objectif peut être basée sur un appel de mbox si vous utilisez at.js. Par exemple, vous pouvez utiliser les fonctionnalités de suivi des clics prêtes à l’emploi de Target avec A4T au lieu d’avoir à implémenter . [!DNL Analytics] code de suivi des clics.
* Lors de l’affichage des rapports d’une activité A4T dans le [!DNL Target] IU, que vous affichez [!DNL Analytics] data. Par exemple, si vous utilisez la variable [!UICONTROL Visiteur] dans [!DNL Target], vous utilisez le [!DNL Analytics] [!UICONTROL Visiteur] , pas la mesure [!DNL Target] [!UICONTROL Visiteurs] mesure qui s’appelle désormais [!UICONTROL Participants]. Cette différence est particulièrement importante pour les mesures de trafic de base ([!UICONTROL Visiteurs], [!UICONTROL Visites], [!UICONTROL Pages vues]) et les mesures de conversion.
* Tout [!DNL Target] les activités continuent à utiliser [!DNL Target] collecte de données et ne sont pas affectés par l’activation d’A4T.
* Une seule mesure mbox est autorisée lors de l’utilisation d’A4T.
* Un appel serveur à serveur de [!DNL Target] to [!DNL Analytics] envoie des informations sur l’activité et l’expérience à [!DNL Analytics]. Cette intégration n’entraîne pas d’appels au serveur supplémentaires pour [!DNL Target] ou [!DNL Analytics].

   Dans certains cas, les classifications de [!DNL Target] to [!DNL Analytics] les activités échouent et n’affichent pas de données dans [!DNL Analytics]. Voir [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contactez le service à la clientèle](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir une assistance supplémentaire.

## Mise en oeuvre d’A4T

Pour plus d’informations sur l’implémentation d’A4T avec at.js et le [!DNL Adobe Experience Platform Web SDK], voir [Analytics pour [!DNL Target] implémentation](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Types d’activité pris en charge {#section_F487896214BF4803AF78C552EF1669AA}

Les sections suivantes contiennent des informations sur les types d’activité pris en charge lors de l’utilisation de la variable [!DNL Adobe Experience Platform Web SDK] ou at.js :

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| [Activité A/B avec fractionnement manuel du trafic](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |  |
| [Activité A/B avec affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [Activité A/B avec ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Oui | Voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Ciblage d’expérience (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Oui |  |
| [Test multivarié (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Oui | Requiert la mesure d’objectif basée sur mbox pour obtenir le [!UICONTROL Contribution des éléments] rapport. Le [!UICONTROL Contribution des éléments] ne prend actuellement pas en charge le rapport [!DNL Analytics] mesures. |
| [Activité d’Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Non |  |
| [Activité Recommendations](/help/main/c-recommendations/recommendations.md) | Oui |  |
| [Toute activité utilisant une offre de redirection](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Oui |

Comme tous les types d’activité ne prennent pas encore en charge A4T, il est recommandé de conserver ou d’implémenter des mbox de conversion importantes, telles que la variable `orderConfirmPage` mbox.

## Exemples de rapports A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Pour afficher des rapports A4T dans [!DNL Target], cliquez sur **[!UICONTROL Activités]**, cliquez sur l’activité souhaitée dans la liste qui utilise [!DNL Analytics] comme source de création de rapports, puis cliquez sur le **[!UICONTROL Rapports]** .

>[!NOTE]
>
>Vous pouvez utiliser la variable [!UICONTROL Source de création de rapports] Liste déroulante en haut de la page [!UICONTROL Activités] pour afficher uniquement les activités qui utilisent A4T.

Vous pouvez basculer entre les [!UICONTROL Vue Tableau] et [!UICONTROL Vue graphique] du rapport en cliquant sur l’icône appropriée dans le coin supérieur droit du rapport.

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Mesure du rapport] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL vue Graphique] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![](assets/a4t_report_graph2.png)

L’illustration suivante présente la [!UICONTROL vue Tableau] d’un rapport A4T :

![](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL Afficher dans Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Ouvrez le [Analytics et Target : Bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutoriel fourni par [!DNL Adobe Experience League].

## Vidéos de formation :

Les vidéos suivantes contiennent plus d’informations sur les concepts abordés dans cette rubrique.

### Analytics pour Adobe Target (A4T) (4:32) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique comment utiliser [!DNL Analytics] comme source de création de rapports dans [!DNL Target] pour piloter l’analyse de votre programme d’optimisation.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Intégration d’Analytics/d’Adobe Target (A4T) (40:33) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo est un enregistrement de « [Office Hours](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures d’ouverture de l’intégration Analytics/Target (A4T)](https://helpx.adobe.com/fr/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics pour [!DNL Target] implémentation](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md): Contient des informations d’implémentation pour at.js et le SDK Web Platform.
>* [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [Présentation du SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html): Contient des informations d’aperçu sur le SDK Web de Platform.
>* [Présentation de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html): Contient des informations spécifiques à [!DNL Target] et le [!DNL Platform Web SDK].

