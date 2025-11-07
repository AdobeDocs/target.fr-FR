---
keywords: a4t;analytics;analytics for target;source de création analytics;adobe analytics comme source de création des rapports pour target;atjs;at.js;sdk web adobe experience platform;sdk web platform;sdk platform
description: Utiliser  [!DNL Analytics]  for  [!DNL Target]  (A4T) pour créer des activités basées sur les mesures de conversion d’ [!DNL Analytics]  et sur les segments d’audience. Utiliser les rapports d’ [!DNL Analytics]  pour examiner les résultats.
title: Qu’est-ce qu’ [!DNL Analytics]  for  [!DNL Target]  (A4T) ?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 80%

---

# [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) est une intégration intersolutions permettant de créer des activités basées sur les mesures de conversion d’[!DNL Analytics] ainsi que sur les segments d’audience. L’intégration A4T vous permet d’utiliser les rapports d’[!DNL Analytics] pour étudier vos résultats. Si vous utilisez [!DNL Analytics] comme source de création de rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur la collecte de données [!DNL Analytics].

## Aperçu {#section_92B66069210C40DBA937790E8CC596CF}

L’intégration d’[!DNL Analytics for Target] entre [!DNL Analytics] et [!DNL Target] fournit des outils puissants d’analyse et de gain de temps destinés à votre programme d’optimisation.

Les trois principaux avantages offerts par l’utilisation des données d’[!DNL Analytics] dans [!DNL Target] sont les suivants :

* Les marketeurs peuvent appliquer dynamiquement les mesures de succès d’[!DNL Analytics] ou les segments de création de rapports aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine la variance qui survient lorsque les données sont collectées dans deux systèmes distincts.
* Votre implémentation existante d’[!DNL Analytics] collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports.

Si vous utilisez [!DNL Analytics] comme source des rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur [!DNL Analytics].

Toutes les mesures [!DNL Analytics], y compris les mesures calculées, sont disponibles dans [!DNL Target] et le rapport [!UICONTROL Target Activities] dans [!DNL Analytics], à une exception près. Les mesures calculées pour [!UICONTROL Lift & Confidence] ne sont pas prises en charge. De même, tout segment disponible dans [!DNL Analytics] peut être appliqué aux deux solutions. Vous pouvez appliquer la mesure ou l’audience au rapport dans [!DNL Target] une fois que l’activité a débuté ou même une fois que celle-ci est terminée.

Chaque mesure est incluse, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

Après la période de classification, les données apparaissent dans ces rapports environ une heure après avoir été collectées à partir du site Web. Toutes les mesures et valeurs et tous les segments des rapports proviennent de la suite de rapports que vous avez sélectionnée lorsque vous avez configuré l’activité.

Gardez ce qui suit à l’esprit lorsque vous envisagez d’utiliser Analytics for Target (A4T) :

* Pour utiliser [!DNL Analytics] en tant que source de création de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Analytics] et à [!DNL Target]. [Contactez votre gestionnaire de compte](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) si vous avez besoin de l’une des solutions.
* La source de création de rapports est définie pour chaque activité. [!DNL Target] continue à collecter les données à utiliser dans la création de rapports et les [!DNL Target] données sont toujours disponibles si vous préférez baser une activité sur les données collectées par [!DNL Target].
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données des deux sources pour une même activité.
* Lorsque vous utilisez A4T, toutes les mesures de succès disponibles pour vos activités sont des mesures [!DNL Analytics]. Cependant, votre mesure d’objectif peut être basée sur un appel de mbox si vous utilisez at.js. Par exemple, vous pouvez utiliser les fonctionnalités de suivi des clics prêtes à l’emploi de Target avec A4T au lieu de devoir implémenter le code de suivi des clics d’[!DNL Analytics].
* Lorsque vous consultez des rapports relatifs à une activité A4T dans l’interface utilisateur de [!DNL Target], vous consultez des données [!DNL Analytics]. Par exemple, si vous utilisez la mesure [!UICONTROL Visitor] dans [!DNL Target], vous utilisez la mesure [!DNL Analytics] [!UICONTROL Visitor], et non la mesure [!DNL Target] [!UICONTROL Visitors], qui est désormais appelée [!UICONTROL Entrants]. Cette différence est particulièrement importante pour les mesures de trafic de base ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) et pour les mesures de conversion.
* Toute activité [!DNL Target] existante continue à utiliser la collecte de données [!DNL Target] et n’est pas affectée par l’activation d’A4T.
* Une seule mesure basée sur mbox est autorisée lors de l’utilisation d’A4T.
* L’appel serveur à serveur de [!DNL Target] vers [!DNL Analytics] envoie les informations d’activité et d’expérience à [!DNL Analytics]. Cette intégration ne résulte pas en appels au serveur supplémentaires, que ce soit pour [!DNL Target] ou [!DNL Analytics].

  Dans certains cas, les classifications de [!DNL Target] à [!DNL Analytics] échouent et n’affichent pas de données dans [!DNL Analytics]. Consultez la page [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Vous pouvez également [contacter le service clientèle](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) pour obtenir une assistance supplémentaire.

## Implémenter A4T

Pour plus d’informations sur l’implémentation d’A4T avec at.js et [!DNL Adobe Experience Platform Web SDK], consultez la page [Implémentation d’Analytics for  [!DNL Target] &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Types d’activité pris en charge {#section_F487896214BF4803AF78C552EF1669AA}

Les sections suivantes contiennent des informations sur les types d’activité pris en charge lors de l’utilisation d’[!DNL Adobe Experience Platform Web SDK] ou d’at.js :

| Types d’activité | Compatible avec A4T ? | Remarques, le cas échéant |
|--- |--- |--- |
| [Activité A/B avec fractionnement manuel du trafic](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |  |
| [Activité A/B avec affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Oui | Consultez la page [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Activité A/B avec ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Oui | La prise en charge d’A4T pour les activités de ciblage automatique est désormais prise en charge pour [!DNL Platform Web SDK] et at.js. |
| [Ciblage d’expérience (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Oui |  |
| [Test multivarié (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Oui | Requiert la mesure d’objectif basée sur mbox pour obtenir le rapport [!UICONTROL Element Contribution]. Le rapport [!UICONTROL Element Contribution] ne prend actuellement pas en charge les mesures [!DNL Analytics]. |
| [Activité d’Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Non |  |
| [Activité Recommendations](/help/main/c-recommendations/recommendations.md) | Oui |  |
| [Activité utilisant une offre de redirection](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Oui |  |

Dans la mesure où tous les types d’activité ne prennent pas encore en charge A4T, il est recommandé de conserver ou d’implémenter les mbox de conversion importantes, telles que la mbox `orderConfirmPage`.

## Exemples de rapports A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Pour afficher les rapports A4T dans [!DNL Target], cliquez sur **[!UICONTROL Activities]**, cliquez sur l’activité souhaitée dans la liste qui utilise [!DNL Analytics] comme source de rapports, puis cliquez sur l’onglet **[!UICONTROL Reports]** .

>[!NOTE]
>
>Vous pouvez utiliser la liste déroulante [!UICONTROL Reporting Source] en haut de la page [!UICONTROL Activities] pour afficher uniquement les activités qui utilisent A4T.

Vous pouvez basculer entre les [!UICONTROL Table View] et les [!UICONTROL Graph View] du rapport en cliquant sur l’icône appropriée en haut à droite du rapport.

L’illustration suivante présente la [!UICONTROL Graph View] d’un rapport A4T avec la liste déroulante [!UICONTROL Report Metric] répertoriant les mesures d’objectifs [!DNL Analytics] disponibles :

![image a4t_report_graph1](assets/a4t_report_graph1.png)

L’illustration suivante présente la [!UICONTROL Graph View] d’un rapport A4T avec la liste déroulante [!UICONTROL Audience] répertoriant les audiences [!DNL Analytics] disponibles :

![image a4t_report_graph2](assets/a4t_report_graph2.png)

L’illustration suivante présente les [!UICONTROL Table View] d’un rapport A4T :

![image a4t_report_table](assets/a4t_report_table.png)

Pour afficher le rapport dans [!DNL Analytics] plutôt que dans [!DNL Target], cliquez sur **[!UICONTROL View in Analytics]** en haut du rapport.

## Tutoriel Analytics et Target : bonnes pratiques relatives à l’analyse {#section_3438E6E77A464424B717A4FD333B84B2}

Ouvrez le tutoriel [Analytics et Target : bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par [!DNL Adobe Experience League].

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cette rubrique.

### Analytics for Adobe Target (A4T) (4:32) ![Badge de présentation](/help/main/assets/overview.png)

Cette vidéo explique de quelle façon utiliser [!DNL Analytics] comme source de création de rapports dans [!DNL Target] dans le cadre de l’analyse de votre programme d’optimisation.

* Présentation d’A4T et des raisons pour lesquelles l’utiliser
* Explication du fonctionnement d’A4T
* Compréhension des conditions préalables requises pour pouvoir utiliser A4T

>[!VIDEO](https://video.tv.adobe.com/v/3421725?captions=fre_fr)

### Intégration d’Analytics/d’Adobe Target (A4T) (40:33) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo est un enregistrement de « [Office Hours](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Comment configurer et confirmer que l’intégration fonctionne
* Fonctionnement de l’intégration
* Découvrez les rapports idéaux à utiliser dans Analytics
* Réponses aux questions courantes sur A4T

[Heures d’ouverture de l’intégration d’Analytics/de Target (A4T)](https://helpx.adobe.com/fr/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* Implémentation d’[Analytics for  [!DNL Target] &#x200B;](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md) : contient des informations d’implémentation pour at.js et le SDK Web Platform.
>* [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [Qu’est-ce que SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) : contient des informations générales sur le SDK Web Platform.
>* [Présentation de Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html?lang=fr) : contient des informations spécifiques à [!DNL Target] et au [!DNL Platform Web SDK].
