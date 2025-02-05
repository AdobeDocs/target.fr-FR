---
keywords: Ciblage;rapports AP;rapports personnalisation automatisée;ciblage automatique;rapport ciblage automatique;personnalisation;informations;segments automatisés;faq;forum aux questions
description: Adobe Découvrez comment différents segments définis par les modèles  [!DNL Target]  personnalisation répondent aux offres/expériences dans l’activité en affichant le rapport Segments automatisés .
title: Qu’est-ce que le rapport Segments automatisés ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 59%

---

# rapport [!UICONTROL Automated Segments]

Informations sur le rapport [!UICONTROL Automated Segments], l’un des deux rapports spécialisés disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT).

>[!NOTE]
>
>Tenez compte des points suivants lors de l’utilisation de rapports [!UICONTROL Personalization Insights] :
>
>* Les activités AP et AT sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].
>
>* Les rapports [!UICONTROL Personalization Insights] sont disponibles uniquement pour les activités AP et AT qui utilisent un objectif d’optimisation de la conversion. Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.
>
>* [!UICONTROL Personalization Insights] rapports ne sont disponibles que si l’[!UICONTROL Primary Goal] est sélectionné dans la liste déroulante [!UICONTROL Report Metric] .
>
>* [!UICONTROL Personalization Insights] rapports ne sont pris en charge que dans l’environnement [par défaut](/help/main/administrating-target/hosts.md).
>
>* [!UICONTROL Personalization Insights] rapports ne sont générés que pour les activités dont le statut est défini sur [!UICONTROL Live] et qui ont été activées et reçoivent du trafic depuis au moins 15 jours.

Différents visiteurs répondent différemment aux offres/expériences de votre activité AP/AT. Ce rapport montre comment différents segments automatisés définis par les modèles de personnalisation de Target ont répondu aux offres/expériences de l’activité.

## Accès au rapport Segments automatisés {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Cliquez sur **[!UICONTROL Activities]**, puis sur l’activité [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) de votre choix dans la liste.

   Si vous avez de nombreuses activités, cliquez sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur **[!UICONTROL Reports]**.

   Le rapport [Résumé Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou [Résumé du ciblage automatique](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) s’affiche, et fournit des informations sur les performances de vos activités, représentées par l’icône du premier écran. Les deux icônes supplémentaires représentent les deux rapports [!UICONTROL Personalization Insights] : **[!UICONTROL Automated Segments]** ( ![rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) et **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ). Le ciblage automatique comporte une icône de graphique supplémentaire pour la vue graphique du rapport [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >Le rapport [!UICONTROL Automated Segments] ne sera disponible que 15 jours au moins après l’activation de votre activité. Au cours de cette période initiale, vous ne pourrez pas accéder à ce rapport ni cliquer sur l’icône [!UICONTROL Automated Segments]. Une fois que 15 jours se sont écoulés, en supposant qu’il y ait suffisamment de trafic personnalisé dans votre activité, le rapport [!UICONTROL Automated Segments] sera disponible.

1. 15 jours après l’activation de l’activité, vous pouvez cliquer sur l’icône **[!UICONTROL Automated Segments]**.

1. Sélectionnez la plage de dates désirée.

   Contrairement au rapport [!UICONTROL Summary] (rapport de performances), [!UICONTROL Personalization Insights], y compris [!UICONTROL Automated Segments], n’est disponible que pour des périodes fixes : 15 jours, 30 jours et 60 jours. Ces périodes fixes [!UICONTROL Personalization Insights] permettent d’utiliser une plage de données suffisamment étendue pour réduire la probabilité d’obtenir des informations à partir d’un modèle de courte durée dans votre activité. Les deux décisions que vous pouvez prendre pour votre plage de dates portent sur la « Date de fin » et la « Durée ». Vous remarquerez que le bouton « Démarrer » est grisé. La date de début change automatiquement en fonction de vos sélections de date de fin et de durée.

   Vous pouvez accéder aux périodes fixes disponibles à partir de la liste déroulante [!UICONTROL Preset Date Range] .

1. Examinez les données du rapport [!UICONTROL Automated Segments].

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Download]** ( ![icône Télécharger](/help/main/assets/icons/Download.svg) ) pour [télécharger le rapport au format CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) afin de l’analyser dans Excel et d’autres outils.

   >[!NOTE]
   >
   >Le rapport de l’interface utilisateur Informations de personnalisation contient des informations choisies. Le fichier CSV correspondant au rapport Segments automatisés contient des détails supplémentaires. Le téléchargement du rapport Segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences.

## Interprétation du rapport Segments automatisés

Le tableau suivant explique comment interpréter le rapport et en décrit les éléments :

| Élément | Détails |
|--- |--- |
| Panneau de la partie gauche | Le panneau de gauche répertorie les 20 segments automatisés les plus grands identifiés par les modèles de personnalisation de Target pour cette activité. Un « segment automatisé » est semblable à une audience, mais est défini par les modèles de personnalisation de Target et non pas par le spécialiste du marketing. Chaque segment automatisé est constitué de valeurs spécifiques (ou plages de valeurs) d’attributs spécifiques.<br>Les segments automatisés peuvent se chevaucher. Les segments automatisés peuvent être définis par un, deux, trois ou quatre attributs. Consultez les exemples ci-dessous pour plus de détails.<br>Pour en savoir plus sur les modèles de personnalisation de Target, voir [Algorithme Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). Pour en savoir plus sur les attributs que les modèles de personnalisation de Target utilisent afin de créer les segments automatisés, voir [Collecte de données pour les algorithmes de personnalisation de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). |
| Graphiques du milieu | Les graphiques centraux affichent les performances du contenu de votre activité pour le segment automatisé mis en surbrillance. Lorsque vous cliquez sur différents segments dans le panneau de gauche, les graphiques du milieu sont mis à jour. |
| Graphiques circulaires | Les graphiques circulaires situés en haut du panneau central indiquent la taille du segment automatisé, ainsi que le nombre total de visites personnalisées dans l’activité (par exemple, le trafic vers cette activité qui a été traité par le modèle de personnalisation). Ceci n’inclut pas le trafic de contrôle ou le trafic traité par le modèle gagnant global. La taille du segment est basée uniquement sur des visites personnalisées.<br>![Graphique en secteurs](/help/main/c-reports/assets/pie.png) |
| Graphique à barres à axe double | Le graphique à barres à axe double inclut des informations de visite et de conversion selon l’offre ou l’expérience pour ce segment automatisé spécifique. |
| Barre rose | La barre rose représente le taux de conversion et utilise l’axe inférieur du graphique. Vous pouvez survoler la barre avec le curseur pour obtenir plus d’informations |
| Barre bleue | La barre bleue représente le nombre de visites et utilise l’axe supérieur du graphique. Vous pouvez survoler la barre avec le curseur pour obtenir plus d’informations. |
| Ligne pointillée grise | La ligne pointillée grise représente le taux de conversion de toutes les visites personnalisées dans l’activité, à travers toutes les offres/expériences et les segments automatisés. |

**Exemple de segment automatisé 1**

Ce segment automatisé est défini en fonction d’un seul attribut uniquement. Les visiteurs inclus dans ce segment automatisé ont vu cette activité AP un jour de la semaine en dehors des heures de travail standard ou lors d’un week-end.

![Exemple de rapport Segments automatisés 1](/help/main/c-reports/assets/automated_segment_example_1.png)

**Exemple de segment automatisé 2**

Ce segment automatisé est défini en fonction de deux attributs. Les visiteurs inclus dans ce segment automatisé qui ont vu cette activité AP ont eu moins de trois pages vues dans leur visite actuelle et se trouvaient géographiquement basés à la latitude 42.57 et 47.29 (approximativement entre le New Hampshire/l’Oregon et Washington/le Maine pour une société basée aux États-Unis).

![Exemple de rapport Segments automatisés 2](/help/main/c-reports/assets/automated_segment_example_2.png)

## FAQ sur Segments automatisés {#section_740910A52FA646B4AC9452F98C2F5719}

**Les rapports Informations sur la personnalisation ne sont pas encore disponibles pour mon activité. Pourquoi ?**

Plusieurs raisons expliquent pourquoi les rapports [!UICONTROL Personalization Insights] ne sont pas encore disponibles pour votre activité :

* 15 jours ne se sont pas écoulés depuis l’activation de l’activité. Les rapports Segments automatisés et Attributs importants ne seront disponibles qu’au moins 15 jours après que vous ayez commencé votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ces rapports ni cliquer sur les icônes Segments automatisés et Attributs importants.
* Votre activité n’a pas présenté assez de trafic au cours de la période spécifiée. Une fois les 15 jours passés, en supposant qu’il existe un trafic personnalisé suffisant dans votre activité pour construire les modèles de personnalisation, les rapports Segments automatisés et Attributs importants seront disponibles.
* Votre activité a un objectif d’optimisation des revenus. Actuellement, [!UICONTROL Personalization Insights] n’est disponible que pour les activités d’objectif d’optimisation de conversion. L’Adobe ajoutera la prise en charge des activités d’objectif d’optimisation du chiffre d’affaires dans une version ultérieure.

**Qu’est-ce qu’un attribut ?**

Un attribut consiste en des informations sur un visiteur ou sa visite spécifique utilisées par les algorithmes de personnalisation pour savoir comment personnaliser le trafic. Par exemple, un attribut peut être le type de navigateur, l’emplacement, l’heure de la journée de la visite, etc.

Pour plus d’informations sur les attributs utilisés par [!DNL Target] dans ses modèles de personnalisation, voir [Collecte de données pour les algorithmes de personnalisation de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Pour plus d’informations sur le téléchargement de nouveaux attributs dans Target afin de les utiliser dans les modèles de personnalisation de Target, consultez la section [Méthodes pour importer des données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}.

**Qu’est-ce qu’un segment automatisé ?**

Un « segment automatisé » est semblable à une audience, mais est défini par les modèles de personnalisation de Target et non pas par le spécialiste du marketing.

Un segment automatisé est constitué de valeurs spécifiques (ou plages de valeurs) d’attributs spécifiques. Voir l’étape 5 ci-dessus pour obtenir des exemples de segment automatisé. Les segments peuvent se chevaucher.

Pour en savoir plus sur l’algorithme de personnalisation de forêt aléatoire, qui constitue la base des modèles de personnalisation de Target, voir [ Algorithme de forêt aléatoire ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**Qu’est-ce qui décide de l’ordre des segments automatisés ?**

Un score est calculé pour chaque segment, en fonction de sa taille et de la différence de son comportement par rapport au contenu de votre activité. La combinaison de ces entrées détermine l’ordre des segments automatisés, de sorte que les segments plus grands présentant des différences plus importantes dans leur réponse face au différent contenu apparaissent plus en haut de la liste des segments.

**Pourquoi seules certaines de mes offres/expériences apparaissent dans le rapport Segments automatisés ?**

Les activités AP et AT génèrent un modèle par offre (dans le cas de AP) et un modèle par expérience (dans le cas de AT). Ces activités commencent à diffuser du trafic personnalisé et à créer votre [!UICONTROL Personalization Insights] avec seulement deux modèles créés. Si vous ne voyez pas toutes vos offres/expériences dans [!UICONTROL Personalization Insights], il est probable que vous ne disposiez pas de modèles créés pour ces offres/expériences spécifiques. Vous pouvez vérifier le rapport [!UICONTROL Summary] de votre activité et voir s’il existe une icône d’horloge en regard de cette offre/expérience. Cette icône indique que les modèles ne sont pas encore créés pour cette offre/expérience.

**Pourquoi certaines offres/expériences présentant un taux de conversion plus faible reçoivent un trafic plus important par rapport à d’autres offres/expériences pour un certain segment automatisé ?**

Plusieurs raisons peuvent expliquer le fait que vous puissiez constater plus de visites sur une offre ou une expérience présentant un taux de conversion plus bas, y compris les raisons suivantes :

* Un petit nombre de vues pour certaines des offres/expériences ou toutes pour un certain segment automatisé.
* Des activités à volume plus faible dans lesquelles certaines offres/expériences n’ont pas de modèles construits, ou dans lesquelles des modèles ont été construits plus rapidement pour certaines offres/expériences que d’autres.
* Des règles de ciblage sur une offre spécifique qui limite quels visiteurs peuvent voir quelles offres/expériences.

**Les informations contenues dans les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes] sont-elles identiques à celles du téléchargement CSV ?**

Non, le rapport d’interface utilisateur contient des informations sélectionnées. Le téléchargement CSV contient des détails supplémentaires. Le téléchargement du rapport Informations sur les segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences. Le rapport Attributs importants comprend les 100 premiers attributs de visiteur et leur importance relative, tandis que l’interface utilisateur inclut uniquement les 10 premiers attributs de visiteur.

**Puis-je voir [!UICONTROL Personalization Insights] pour une période personnalisée ?**

La création de rapports Personalization Insights ([!UICONTROL Automated Segments] et [!UICONTROL Important Attributes]) est disponible uniquement pour les périodes fixes : 15 jours, 30 jours et 60 jours. Ces périodes fixes [!UICONTROL Personalization Insights] permettent d’utiliser une plage de données suffisamment étendue pour réduire la probabilité d’obtenir des informations à partir d’un modèle de courte durée dans votre activité. Vous pouvez sélectionner ces durées pour n’importe quelle date de fin (où l’activité comprend assez de données pour satisfaire la durée).

**Comment les [!UICONTROL Personalization Insights] sont-elles créées ?**

[!UICONTROL Personalization Insights] est réalisé à l&#39;aide d&#39;une technique Adobe en instance de brevet appelée MAGIX (Model Agnostic Globally Interpretable Explanations). Pour en savoir plus sur MAGIX, consultez l&#39;article publié par l&#39;équipe de recherche sur l&#39;Adobe sur le site Web [arXiv.org](https://arxiv.org/abs/1706.07160).

**Pourquoi les données de trafic total des visiteurs dans le rapport [!UICONTROL Automated Segments] ne correspondent-elles pas à mon rapport de synthèse/performances AP ou AT ?**

Les rapports [!UICONTROL Personalization Insights] incluent uniquement les visiteurs et visiteuses qui ont vu un élément de contenu sélectionné par les modèles de personnalisation de Target (c’est-à-dire qu’ils ne prennent pas en compte le trafic de contrôle ou le trafic fourni par le modèle gagnant global). Ce type de trafic est appelé trafic « personnalisé ». Le rapport de performances récapitulatif dans AP/AT inclut le trafic de contrôle par rapport au trafic « ciblé ». Le trafic ciblé inclut le trafic personnalisé, ainsi que le trafic qui a été traité à l’aide du modèle gagnant global et un certain trafic traité de manière aléatoire utilisé pour continuer à apprendre.

**Les segments automatisés sont-ils mutuellement exclusifs ?**

Non, il existe un chevauchement entre les segments automatisés.

**Est-[!UICONTROL Personalization Insights] disponible pour les objectifs de modélisation basés sur le chiffre d’affaires/objectif principal ?**

Actuellement, [!UICONTROL Personalization Insights] n’est disponible que pour les activités d’objectif d’optimisation de la conversion. L’Adobe ajoutera la prise en charge des activités d’objectif d’optimisation du chiffre d’affaires dans une version ultérieure.

**Quelles sont les différentes méthodes pour exploiter les informations du rapport Informations sur la personnalisation ?**

* Découvrez de nouvelles audiences à cibler : si un segment automatisé particulier s’avère performant, vous pouvez envisager de créer une audience afin de pouvoir réutiliser ce segment dans d’autres rapports.
* Testez vos hypothèses sur le type de visiteurs qui répond à l’une de vos expériences.
* Générez des informations indiquant quel contenu a fonctionné pour quel type de visiteur : quelles offres ont eu un effet élévateur chez quels visiteurs.
* Identifiez le contenu peu efficace.
* Identifiez les attributs les plus essentiels dans la manière dont le modèle a appris.
* Identifiez quels attributs sont utilisés dans les modèles de personnalisation et leur importance.
* Identifiez les opportunités de points de données supplémentaires que vous pouvez transmettre à Target pour informer davantage votre personnalisation.

**Existe-t-il une logique dans l’ordre dans lequel les attributs apparaissent dans une carte de segment ?**

Non, l’ordre des cartes est basé uniquement sur un classement décrit ci-dessus. L’ordre des attributs dans une carte n’est basé sur aucune logique.
