---
keywords: Ciblage;rapports AP;rapports de personnalisation automatisée;ciblage automatique;ciblage automatique;rapport de ciblage automatique;personnalisation;informations;faq;forum aux questions;attributs importants
description: Découvrez comment utiliser le rapport [!UICONTROL Important Attributes] qui présente les principaux attributs qui ont influencé le modèle de personnalisation et leur importance relative.
title: Qu’est-ce que le rapport Attributs importants ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1790'
ht-degree: 56%

---

# Rapport Attributs importants

Informations sur le rapport [!UICONTROL Important Attributes], l’un des deux rapports spécialisés disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT).

>[!NOTE]
>
>Tenez compte des points suivants lors de l’utilisation des rapports [!UICONTROL Personalization Insights] :
>
>* Les activités AP et AT sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].
>
>* [!UICONTROL Personalization Insights] Les rapports sont disponibles uniquement pour les activités AP et AT qui utilisent un objectif d’optimisation de conversion. Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.
>
>* Les rapports [!UICONTROL Personalization Insights] ne sont disponibles que si [!UICONTROL Primary Goal] est sélectionné dans la liste déroulante [!UICONTROL Report Metric].
>
>* Les rapports [!UICONTROL Personalization Insights] sont uniquement pris en charge dans l&#39; [environnement par défaut](/help/main/administrating-target/hosts.md).
>
>* Les rapports [!UICONTROL Personalization Insights] sont générés uniquement pour les activités dont l’état est [!UICONTROL Live] et qui ont été activées et qui reçoivent du trafic pendant au moins 15 jours.

Dans les différentes activités, différents attributs sont plus ou moins importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

## Accéder au rapport [!UICONTROL Important Attributes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Cliquez sur **[!UICONTROL Activities]**, puis sur l’activité [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) souhaitée dans la liste.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur **[!UICONTROL Reports]**.

   Le rapport [Résumé d’Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou [Résumé de ciblage automatique](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) s’affiche, ce qui fournit des informations sur les performances de vos activités, représentées par la première icône d’écran. Les deux icônes supplémentaires représentent les deux rapports [!UICONTROL Personalization Insights] : [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes].

   ![Rapport de synthèse pour l’activité Automated Personalization](/help/main/c-reports/assets/summary-report-ap.png)

   Notez que [!UICONTROL Auto-Target] comporte une icône de graphique supplémentaire pour la vue graphique du rapport [!UICONTROL Summary].

   ![Rapport de synthèse pour l’activité de ciblage automatique](/help/main/c-reports/assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >Le rapport [!UICONTROL Important Attributes] ne sera disponible que 15 jours au moins après l’activation de votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ce rapport ou cliquer sur l’icône [!UICONTROL Important Attributes]. Une fois les 15 jours passés, en supposant qu’il existe un trafic personnalisé suffisant dans votre activité, le rapport [!UICONTROL Important Attributes] est disponible.

1. 15 jours après l’activation de l’activité, cliquez sur l’icône **[!UICONTROL Important Attributes]** .

   ![Icône Attributs importants dans un rapport Adobe Target](/help/main/c-reports/assets/model_attribute_ranking.png)

1. Sélectionnez la plage de dates désirée.

   Contrairement au rapport [!UICONTROL Summary] (rapport de performances), [!UICONTROL Personalization Insights], y compris [!UICONTROL Important Attributes], est disponible uniquement pour les plages de dates fixes : 15 jours, 30 jours et 60 jours.

   Ces plages de dates fixes permettent à [!UICONTROL Personalization Insights] d’utiliser une plage de données assez vaste pour réduire la probabilité que vous retiriez des informations d’un modèle de courte durée dans votre activité. Les deux décisions que vous pouvez prendre pour votre plage de dates portent sur la « Date de fin » et la « Durée ». Vous remarquerez que le « Début » est grisé. La date de début change automatiquement en fonction de vos sélections de date de fin et de durée.

   ![Calendrier dans un rapport Adobe Target](/help/main/c-reports/assets/personalization_insights_calendar_1.png)

   Vous pouvez accéder aux plages de dates fixes disponibles dans la liste déroulante [!UICONTROL Choose Duration] .

   ![ Liste déroulante Choisir la durée dans un rapport](/help/main/c-reports/assets/personalization_insights_calendar_2.png)

1. Examinez les données du rapport [!UICONTROL Important Attributes].

   ![Rapport Attributs importants dans Adobe Target](/help/main/c-reports/assets/model_attribute_ranking_report.png)

1. (Facultatif) [Téléchargez le rapport au format CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) en vue d’une analyse dans Excel et d’autres outils.

   >[!NOTE]
   >
   >Le rapport de l’interface utilisateur Informations de personnalisation contient des informations choisies. Le fichier CSV correspondant au rapport Attributs importants contient des détails supplémentaires. Le téléchargement du rapport Attributs importants comprend la liste complète des 100 premiers attributs, tandis que le rapport de l’interface utilisateur inclut les 10 premiers uniquement. Si vous recherchez un attribut spécifique dans le rapport mais qu’il n’y figure pas, cela ne signifie pas que l’attribut n’a pas eu d’incidence sur l’activité, mais il n’a simplement pas atteint la liste des 100 premiers attributs.

## Interprétation du rapport Attributs importants

Le tableau suivant explique comment interpréter le rapport et en décrit les éléments :

| Élément | Détails |
|--- |--- |
| Graphique en barres | Le graphique en barres multicouleur situé en haut de l’écran vous permet de visualiser ces scores d’importance relative et est associé à la couleur du point en regard de chaque attribut respectif dans le tableau. Vous pouvez également survoler une couleur spécifique dans le graphique en barres avec le curseur pour afficher l’attribut qu’elle représente. Les scores d’importance sur les 100 premiers attributs totalisent 100 %. Pour plus d’informations sur l’ajout d’attributs supplémentaires que les modèles de personnalisation de Target peuvent utiliser, voir [Chargement de données pour les algorithmes Personalization de Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Graphique Classement des attributs de modèle | Le Classement des attributs de modèle comprend les 10 premiers attributs les plus importants dans la manière dont le modèle de personnalisation de Target a décidé du contenu à présenter à chaque visiteur. Le score d’importance indique, par rapport aux 100 premiers attributs, le degré d’importance d’un attribut spécifique pour les modèles de personnalisation de Target dans cette activité. |

## FAQ sur Attributs importants {#section_740910A52FA646B4AC9452F98C2F5719}

Consultez les questions fréquentes suivantes pour obtenir des réponses aux questions courantes sur l’utilisation du rapport [!UICONTROL Important Attributes].

### Les rapports Personalization Insights ne sont pas encore disponibles pour mon activité. Pourquoi ?

Plusieurs raisons peuvent expliquer que les rapports [!UICONTROL Personalization Insights] ne soient pas encore disponibles pour votre activité :

* 15 jours ne se sont pas écoulés depuis que vous avez activé l’activité. Les rapports Segments automatisés et Attributs importants ne seront disponibles qu’au moins 15 jours après que vous ayez commencé votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ces rapports ni cliquer sur les icônes Segments automatisés et Attributs importants.
* Votre activité n’a pas présenté assez de trafic au cours de la période spécifiée. Une fois les 15 jours passés, en supposant qu’il existe un [trafic personnalisé suffisant](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) dans votre activité pour construire les modèles de personnalisation, les rapports Segments automatisés et Attributs importants seront disponibles.
* Votre activité a un objectif d’optimisation des revenus. Actuellement, [!UICONTROL Personalization Insights] est disponible uniquement pour les activités d’objectif d’optimisation de conversion. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

### Qu’est-ce qu’un attribut ?

Un attribut consiste en des informations sur un visiteur ou sa visite spécifique utilisées par les algorithmes de personnalisation pour savoir comment personnaliser le trafic. Par exemple, un attribut peut être le type de navigateur, l’emplacement, l’heure de la journée de la visite, etc.

Pour plus d’informations sur les attributs utilisés par [!DNL Target] dans ses modèles de personnalisation, voir [Collecte de données pour les algorithmes de personnalisation de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Pour plus d’informations sur le téléchargement de nouveaux attributs dans Target à utiliser dans les modèles de personnalisation de Target, voir [Méthodes de transfert de données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}.

### Un ou plusieurs attributs que je ne souhaite pas que le modèle utilise pour l’entraînement sont présents. Puis-je supprimer ces attributs du modèle d’entraînement ? {#models-api}

[!UICONTROL Models API], également appelé API de Liste bloquée, permet aux utilisateurs d’afficher et de gérer la liste des attributs (également appelés fonctionnalités) utilisés dans les modèles d’apprentissage automatique pour les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). Si vous souhaitez exclure un ou plusieurs attributs de l’utilisation par les modèles pour les activités AP ou AT, vous pouvez utiliser l’API Modèles pour ajouter ces attributs à la &quot;liste bloquée&quot;.

Pour plus d’informations, reportez-vous à la section [Présentation de l’API de modèles](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} du *Guide du développeur Adobe Target*. Pour utiliser l’API pour bloquer les attributs, voir [API Modèles](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}.

### Les informations contenues dans les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes] sont-elles les mêmes que dans le téléchargement CSV ?

Non, le rapport d’interface utilisateur contient des informations sélectionnées. Le téléchargement CSV contient des détails supplémentaires. Le téléchargement du rapport Informations sur les segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences. Le rapport Attributs importants comprend les 100 premiers attributs de visiteur et leur importance relative, tandis que l’interface utilisateur inclut uniquement les 10 premiers attributs de visiteur.

### Puis-je voir Personalization Insights pour une période personnalisée ?

La création de rapports Personalization Insights (à la fois [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes]) est disponible uniquement pour les plages de dates fixes : 15 jours, 30 jours, 45 jours, 60 jours et 90 jours. Ces plages de dates fixes permettent à [!UICONTROL Personalization Insights] d’utiliser une plage de données assez vaste pour réduire la probabilité que vous retiriez des informations d’un modèle de courte durée dans votre activité. Vous pouvez sélectionner ces durées pour n’importe quelle date de fin (où l’activité comprend assez de données pour satisfaire la durée).

### Comment [!UICONTROL Personalization Insights] est-il créé ?

[!UICONTROL Personalization Insights] est créé à l’aide d’une technique Adobe en attente de brevet appelée MAGIX (Model Agnostic Globally Interpretable Explanations). Vous pouvez en savoir plus sur MAGIX dans l&#39;article publié par l&#39;équipe de recherche d&#39;Adobe sur le [arXiv.org site Web](https://arxiv.org/abs/1706.07160).

### [!UICONTROL Personalization Insights] est-il disponible pour les objectifs/l’objectif principal de modélisation basée sur les recettes ?

Actuellement, [!UICONTROL Personalization Insights] est disponible uniquement pour les activités d’objectif d’optimisation de conversion. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

### Quel est le score d’importance d’attribut dans le rapport Attributs importants ?

Le score d’importance dans la partie « Classement d’importance d’attribut » du rapport fournit des données indiquant quelles variables utilisées par l’algorithme pour apprendre ont été les plus importantes lorsqu’il a déterminé comment diviser tous les visiteurs dans les segments qu’il a identifiés. Il a attribué un score en pourcentage aux 100 premiers attributs utilisés par le modèle.

### Pourquoi certaines offres/expériences présentant un taux de conversion plus faible reçoivent un trafic plus important par rapport à d’autres offres/expériences pour un certain segment automatisé ?

Plusieurs raisons peuvent expliquer le fait que vous puissiez constater plus de visites sur une offre/expérience présentant un taux de conversion plus bas, y compris les raisons suivantes :

* Un petit nombre de vues pour certaines des offres/expériences ou toutes pour un certain segment automatisé.
* Activités de volume inférieur dans lesquelles certaines offres ou expériences n’ont pas de modèles créés.
* Activités de volume inférieur dans lesquelles les modèles ont été créés plus tôt pour certaines offres/expériences que d’autres. Supposons, par exemple, qu’un modèle supplémentaire ait été créé le jour 22 et que vous consultiez les données des jours 10-24.
* Des règles de ciblage sur une offre spécifique qui limitent quels visiteurs peuvent voir quelles offres/expériences.
* Les rapports d’informations ne comportent aucun intervalle de confiance. Cependant, si les taux de conversion sont suffisamment proches, le modèle peut diffuser le trafic afin qu’il soit plus élevé dans le nombre de points, mais il ne s’agit pas de nombres &quot;statistiquement différents&quot;.

Il peut s’avérer utile de savoir comment fonctionne le modèle qui diffuse le trafic. Chaque personne est servie en fonction de son profil total. Toutefois, les rapports d’informations généralisent ce comportement pour le rendre plus facile à interpréter par un humain. Par conséquent, les segments ne sont pas mutuellement exclusifs. Cela peut conduire à des segments individuels affichant ce type de comportement, car la même personne peut apparaître dans plusieurs segments.

### Quelles sont les différentes manières dont je peux exploiter les informations dans Personalization Insights ?

* Découvrez de nouvelles audiences à cibler : si un segment automatisé particulier est particulièrement efficace, vous pouvez envisager de créer une audience afin de pouvoir réutiliser ce segment dans d’autres rapports.
* Testez vos hypothèses sur le fait de savoir quels types de visiteur répondront auxquelles de vos expériences.
* Générez des informations indiquant quel contenu a fonctionné pour quel type de visiteur : quelles offres ont eu un effet élévateur chez quels visiteurs.
* Identifiez le contenu peu efficace.
* Identifiez les attributs les plus essentiels dans la manière dont le modèle a appris.
* Identifiez quels attributs sont utilisés dans les modèles de personnalisation et leur importance.
* Identifiez les opportunités de points de données supplémentaires que vous pouvez transmettre à Target pour informer davantage votre personnalisation.

## Problèmes connus

Le problème suivant est actuellement examiné par l’équipe d’ingénierie [!DNL Target].

* [!DNL Adobe Experience Platform] noms de segment ne s’affichent pas dans le rapport [!UICONTROL Important Attributes] pour les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). (TOP-3813)
