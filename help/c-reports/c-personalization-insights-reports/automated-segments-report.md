---
keywords: Ciblage;rapports AP;rapports personnalisation automatisée;ciblage automatique;rapport ciblage automatique;personnalisation;informations;segments automatisés;faq;forum aux questions
description: Informations sur le rapport Segments automatisés, l’un des deux rapports spécialisés disponibles pour les utilisateurs des activités Automated Personalization (AP) et de ciblage automatique (AT).
title: Rapport Segments automatisés
uuid: 3f736d7d-b305-438b-8320-2a54e4a9234f
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Rapport Segments automatisés{#automated-segments-report}

Informations sur le rapport Segments automatisés, l’un des deux rapports spécialisés disponibles pour les utilisateurs des activités Automated Personalization (AP) et de ciblage automatique (AT).

>[!NOTE]
>Les activités AP et AT sont disponibles dans le cadre de la solution Target Premium. Ils ne sont pas inclus dans Target Standard sans licence Target Premium.
>
>Les rapports Informations sur la personnalisation sont disponibles uniquement pour les activités AP et AT ayant un objectif d’optimisation de la conversion. Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.|

Différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

## Accès au rapport Segments automatisés {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Cliquez sur **[!UICONTROL Activités]**, puis sélectionnez l’activité [AP](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [AT](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3) souhaitée dans la liste.

   Si vous avez beaucoup d’activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL État], [!UICONTROL Source de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesure] et [!UICONTROL Source d’activité].

1. Cliquez sur **[!UICONTROL Rapports]**.

   Le rapport de [!UICONTROL synthèse] s’affiche fournissant des informations sur les performances de vos activités, représentées par la première icône d’écran. Les deux icônes supplémentaires représentent les deux rapports Informations sur la personnalisation : Segments automatisés et Attributs importants. Notez que Ciblage automatique comporte une icône graphique supplémentaire pour la vue graphique du rapport de [!UICONTROL synthèse].

   ![](assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >Le rapport [!UICONTROL Segments automatisés] sera disponible au plus tôt 15 jours après la date d’activation de votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ce rapport ni cliquer sur l’icône [!UICONTROL Segments automatisés]. Une fois les 15 jours passés, en supposant qu’il existe un trafic personnalisé suffisant dans votre activité, le rapport [!UICONTROL Segments automatisés] sera disponible.

1. 15 jours après l’activation de l’activité, vous pouvez cliquer sur l’icône **[!UICONTROL Segments automatisés].**

   ![](assets/model_attribute_ranking.png)

1. Sélectionnez la plage de dates désirée.

   Contrairement au rapport de [!UICONTROL synthèse] (rapport de performances), [!UICONTROL Informations sur la personnalisation], y compris [!UICONTROL Segments automatisés], est uniquement disponible pour les plages de dates fixes : 15 jours, 30 jours, 45 jours, 60 jours et 90 jours. Ces plages de dates fixes permettent à [!UICONTROL Informations sur la personnalisation] d’utiliser une plage de données assez vaste pour limiter les probabilités que vous retiriez des informations d’un modèle à courte durée de vie dans votre activité. Les deux décisions que vous pouvez prendre pour votre plage de dates portent sur la « Date de fin » et la « Durée ». Vous remarquerez que le « Début » est grisé. La date de début change automatiquement en fonction de vos sélections de date de fin et de durée.

   ![](assets/personalization_insights_calendar_1.png)

   Vous pouvez accéder aux plages de dates fixes disponibles dans la liste déroulante [!UICONTROL Choisir la durée].

   ![](assets/personalization_insights_calendar_2.png)

1. Examinez les données du rapport [!UICONTROL Segments automatisés].

   ![](assets/automated_segments_report.png)


1. (Facultatif) [Téléchargez le rapport au format CSV](../../c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) en vue d’une analyse dans Excel et d’autres outils.

   >[!NOTE]
   >
   >Le rapport de l’interface utilisateur Informations de personnalisation contient des informations choisies. Le fichier CSV correspondant au rapport Segments automatisés contient des détails supplémentaires. Le téléchargement du rapport Segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences.

## Interprétation du rapport Segments automatisés

Le tableau suivant explique comment interpréter le rapport et en décrit les éléments :

| Élément | Détails |
|--- |--- |
| Panneau de la partie gauche | Le panneau de gauche répertorie les 20 segments automatisés les plus grands identifiés par les modèles de personnalisation de Target pour cette activité. Un « segment automatisé » est semblable à une audience, mais est défini par les modèles de personnalisation de Target et non pas par le spécialiste du marketing. Chaque segment automatisé est constitué de valeurs spécifiques (ou plages de valeurs) d’attributs spécifiques.<br>Notez que les segments automatisés peuvent se chevaucher. Les segments automatisés peuvent être définis par un, deux, trois ou quatre attributs. Consultez les exemples ci-dessous pour plus de détails.<br>Pour en savoir plus sur les modèles de personnalisation de Target, voir [Algorithme Forêt aléatoire](/help/c-activities/t-automated-personalization/algo-random-forest.md). Pour en savoir plus sur les attributs que les modèles de personnalisation de Target utilisent afin de créer les segments automatisés, voir [Collecte de données pour les algorithmes de personnalisation de Target](/help/c-activities/t-automated-personalization/ap-data.md). |
| Graphiques du milieu | Les graphiques du milieu indiquent comment le contenu de votre activité est exécuté pour le segment automatisé mis en surbrillance. Lorsque vous cliquez sur différents segments dans le panneau de gauche, les graphiques du milieu sont mis à jour. |
| Graphiques circulaires | Les graphiques circulaires situés en haut du panneau central indiquent la taille du segment automatisé, ainsi que le nombre total de visites personnalisées dans l’activité (par exemple, le trafic vers cette activité qui a été traité par le modèle de personnalisation). Ceci n’inclut pas le trafic de contrôle ou le trafic traité par le modèle gagnant global. Notez que la taille du segment est uniquement basée sur les visites personnalisées.<br>![Graphique circulaire](/help/c-reports/c-personalization-insights-reports/assets/pie.png) |
| Graphique à barres à axe double | Le graphique à barres à axe double inclut des informations de visite et de conversion selon l’offre ou l’expérience pour ce segment automatisé spécifique. |
| Barre rose | La barre rose représente le taux de conversion et utilise l’axe inférieur du graphique. Vous pouvez survoler la barre avec le curseur pour obtenir plus d’informations |
| Barre bleue | La barre bleue représente le nombre de visites et utilise l’axe supérieur du graphique. Vous pouvez survoler la barre avec le curseur pour obtenir plus d’informations. |
| Ligne pointillée grise | La ligne pointillée grise représente le taux de conversion de toutes les visites personnalisées dans l’activité, à travers toutes les offres/expériences et les segments automatisés. |

**Exemple de segment automatisé 1**

Ce segment automatisé est défini en fonction d’un seul attribut uniquement. Les visiteurs inclus dans ce segment automatisé ont vu cette activité AP un jour de la semaine en dehors des heures de travail standard ou lors d’un week-end.

![](assets/automated_segment_example_1.png)

**Exemple de segment automatisé 2**

Ce segment automatisé est défini en fonction de deux attributs. Les visiteurs inclus dans ce segment automatisé qui ont vu cette activité AP ont eu moins de trois pages vues dans leur visite actuelle et se trouvaient géographiquement basés à la latitude 42.57 et 47.29 (approximativement entre le New Hampshire/l’Oregon et Washington/le Maine pour une société basée aux États-Unis).

![](assets/automated_segment_example_2.png)

## FAQ sur Segments automatisés {#section_740910A52FA646B4AC9452F98C2F5719}

**Les rapports Informations sur la personnalisation ne sont pas encore disponibles pour mon activité. Pourquoi ?**

Il existe plusieurs raisons pour lesquelles les rapports [!UICONTROL Informations sur la personnalisation] ne sont pas encore disponibles pour votre activité :

* 15 jours ne se sont pas écoulés depuis que vous avez activé l’activité. Les rapports Segments automatisés et Attributs importants ne seront disponibles qu’au moins 15 jours après que vous ayez commencé votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ces rapports ni cliquer sur les icônes Segments automatisés et Attributs importants.
* Votre activité n’a pas présenté assez de trafic au cours de la période spécifiée. Une fois les 15 jours passés, en supposant qu’il existe un trafic personnalisé suffisant dans votre activité pour construire les modèles de personnalisation, les rapports Segments automatisés et Attributs importants seront disponibles.
* Votre activité a un objectif d’optimisation des revenus. Pour l’instant, [!UICONTROL Informations sur la personnalisation] est uniquement disponible pour les activités d’objectif d’optimisation des conversions. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

**Qu’est-ce qu’un attribut ?**

Un attribut consiste en des informations sur un visiteur ou sa visite spécifique utilisées par les algorithmes de personnalisation pour savoir comment personnaliser le trafic. Par exemple, un attribut peut être le type de navigateur, l’emplacement, l’heure de la journée de la visite, etc.

Pour plus d’informations sur les attributs utilisés par [!DNL Target] dans ses modèles de personnalisation, voir [Collecte de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058). Pour plus d’informations sur la manière de télécharger de nouveaux attributs dans Target pour les utiliser dans les modèles de personnalisation de Target, voir [Méthodes de transfert de données dans Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17).

**Qu’est-ce qu’un segment automatisé ?**

Un « segment automatisé » est semblable à une audience, mais est défini par les modèles de personnalisation de Target et non pas par le spécialiste du marketing.

Un segment automatisé est constitué de valeurs spécifiques (ou plages de valeurs) d’attributs spécifiques. Voir l’étape 5 ci-dessus pour obtenir des exemples de segment automatisé. Notez que les segments peuvent se chevaucher.

Pour en savoir plus sur l’algorithme de personnalisation de la forêt aléatoire, qui est la base des modèles de personnalisation de Target, voir [Algorithme Forêt aléatoire](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

**Quel élément détermine l’ordre des segments automatisés ? **

Un score est calculé pour chaque segment, en fonction de sa taille et de la différence de son comportement par rapport au contenu de votre activité. La combinaison de ces entrées détermine l’ordre des segments automatisés, de sorte que les segments plus grands présentant des différences plus importantes dans leur réponse face au différent contenu apparaissent plus en haut de la liste des segments.

**Pourquoi seules certaines de mes offres/expériences apparaissent dans le rapport Segments automatisés ?**

Les activités AP et AT génèrent un modèle par offre (dans le cas de AP) et un modèle par expérience (dans le cas de AT). Ces activités commencent à traiter du trafic personnalisé et à créer vos [!UICONTROL Informations sur la personnalisation] avec pas plus de deux modèles construits. Si toutes vos offres/expériences n’apparaissent pas dans les rapports [!UICONTROL Informations sur la personnalisation], il est probable que vous ne disposez pas de modèles conçus pour ces offres/expériences spécifiques. Vous pouvez vérifier le rapport de [!UICONTROL synthèse] de votre activité et voir si une icône d’horloge se trouve à côté de cette offre/expérience. Cette icône indique que des modèles ne sont pas encore construits pour cette offre/expérience.

**Pourquoi certaines offres/expériences présentant un taux de conversion plus faible reçoivent un trafic plus important par rapport à d’autres offres/expériences pour un certain segment automatisé ?**

Plusieurs raisons peuvent expliquer le fait que vous puissiez constater plus de visites sur une offre ou une expérience présentant un taux de conversion plus bas, y compris les raisons suivantes :

* Un petit nombre de vues pour certaines des offres/expériences ou toutes pour un certain segment automatisé.
* Des activités à volume plus faible dans lesquelles certaines offres/expériences n’ont pas de modèles construits, ou dans lesquelles des modèles ont été construits plus rapidement pour certaines offres/expériences que d’autres.
* Des règles de ciblage sur une offre spécifique qui limite quels visiteurs peuvent voir quelles offres/expériences.

**Les informations présentes dans les rapports[!UICONTROL Segments automatisés]et[!UICONTROL Attributs importants]sont-elles les même que celles contenues dans le fichier CSV téléchargé ?**

Non, le rapport d’interface utilisateur contient des informations sélectionnées. Le téléchargement CSV contient des détails supplémentaires. Le téléchargement du rapport Informations sur les segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences. Le rapport Attributs importants comprend les 100 premiers attributs de visiteur et leur importance relative, tandis que l’interface utilisateur inclut uniquement les 10 premiers attributs de visiteur.

**Puis-je voir[!UICONTROL Informations sur la personnalisation]pour une plage de dates personnalisée ?**

Les rapports Informations sur la personnalisation ([!UICONTROL Segments automatisés] et [!UICONTROL Attributs importants]) sont uniquement disponibles pour des plages de dates fixes : 15 jours, 30 jours, 45 jours, 60 jours et 90 jours. Ces plages de dates fixes permettent à [!UICONTROL Informations sur la personnalisation] d’utiliser une plage de données assez vaste pour limiter les probabilités que vous retiriez des informations d’un modèle à courte durée de vie dans votre activité. Vous pouvez sélectionner ces durées pour n’importe quelle date de fin (où l’activité comprend assez de données pour satisfaire la durée).

**Comment est créé[!UICONTROL Informations sur la personnalisation ]?**

[!UICONTROL Informations sur la personnalisation] est créé à l’aide d’une technique Adobe en attente de brevet appelée MAGIX (Model Agnostic Globally Interpretable Explanations). Pour en savoir plus sur MAGIX, consultez l’article publié par l’équipe de recherche Adobe sur le [site web arXiv.org](https://arxiv.org/abs/1706.07160).

**Pourquoi les données du trafic de visiteur totales dans le rapport[!UICONTROL Segments automatisés]ne correspondent-elles pas à mon rapport de synthèse/de performances AP ou AT ?**

Les rapports [!UICONTROL Informations sur la personnalisation] incluent uniquement les visiteurs qui ont vu une partie de contenu sélectionnée par les modèles de personnalisation de Target (c’est-à-dire qu’il ne considère pas le trafic de contrôle ou le trafic traité par le modèle gagnant global). Ce type de trafic est appelé trafic « personnalisé ». Le rapport des performances de synthèse dans AP/AT inclut le trafic de contrôle et le trafic « ciblé ». Le trafic ciblé inclut le trafic personnalisé, ainsi que le trafic qui a été traité à l’aide du modèle gagnant global et un certain trafic traité de manière aléatoire utilisé pour continuer à apprendre.

**Les segments automatisés sont-ils mutuellement exclusifs ?**

Non, il existe un chevauchement entre les segments automatisés.

**Le rapport[!UICONTROL Informations sur la personnalisation]est-il disponible pour les objectifs/l’objectif principal de modélisation basée sur les revenus ?**

Pour l’instant, [!UICONTROL Informations sur la personnalisation] est uniquement disponible pour les activités d’objectif d’optimisation des conversions. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

**Quelles sont les différentes méthodes pour exploiter les informations du rapport Informations sur la personnalisation ?**

* Découvrez de nouvelles audiences à cibler : si un segment automatisé particulier est particulièrement efficace, vous pouvez envisager de créer une audience afin de pouvoir réutiliser ce segment dans d’autres rapports.
* Testez vos hypothèses sur le fait de savoir quels types de visiteur répondront auxquelles de vos expériences.
* Générez des informations indiquant quel contenu a fonctionné pour quel type de visiteur : quelles offres ont eu un effet élévateur chez quels visiteurs.
* Identifiez le contenu peu efficace.
* Identifiez les attributs les plus essentiels dans la manière dont le modèle a appris.
* Identifiez quels attributs sont utilisés dans les modèles de personnalisation et leur importance.
* Identifiez les opportunités de points de données supplémentaires que vous pouvez transmettre à Target pour informer davantage votre personnalisation.

**Existe-t-il une logique dans l’ordre dans lequel les attributs apparaissent dans une carte de segment ?**

Non, l’ordre des cartes est basé uniquement sur un classement décrit ci-dessus. L’ordre des attributs d’une carte n’est pas basé sur une logique.