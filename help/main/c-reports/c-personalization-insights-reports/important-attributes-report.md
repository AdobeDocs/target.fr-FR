---
keywords: Ciblage;rapports AP;rapports de personnalisation automatisée;ciblage automatique;ciblage automatique;rapport de ciblage automatique;personnalisation;informations;faq;forum aux questions;attributs importants
description: Découvrez comment utiliser le rapport [!UICONTROL Important Attributes] qui affiche les principaux attributs ayant influencé le modèle de personnalisation et leur importance relative.
title: Qu’est-ce que le rapport Attributs importants ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1773'
ht-degree: 56%

---

# Rapport Attributs importants

Informations sur le rapport [!UICONTROL Important Attributes], l’un des deux rapports spécialisés disponibles pour les utilisateurs des activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT).

>[!NOTE]
>
>Tenez compte des points suivants lors de l’utilisation de rapports [!UICONTROL Personalization Insights] :
>
>* Les activités AP et AT sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas incluses dans [!DNL Target Standard] sans licence [!DNL Target Premium].
>
>* Les rapports [!UICONTROL Personalization Insights] sont disponibles uniquement pour les activités AP et AT qui utilisent un objectif d’optimisation de la conversion. Les activités passées d’un objectif d’optimisation des revenus à un objectif d’optimisation de la conversion, alors qu’elles étaient déjà actives, ne sont pas non plus prises en charge.
>
>* [!UICONTROL Personalization Insights] rapports ne sont disponibles que si le [!UICONTROL Primary Goal] est sélectionné dans la liste déroulante [!UICONTROL Report Metric] .
>
>* [!UICONTROL Personalization Insights] rapports ne sont pris en charge que dans l’environnement [par défaut](/help/main/administrating-target/hosts.md).
>
>* [!UICONTROL Personalization Insights] rapports ne sont générés que pour les activités dont le statut est défini sur [!UICONTROL Live] et qui ont été activées et reçoivent du trafic depuis au moins 15 jours.

Dans les différentes activités, différents attributs sont plus ou moins importants dans la manière dont le modèle décide de personnaliser. Ce rapport indique les attributs principaux qui ont influencé le modèle et leur importance relative.

## Accès au rapport [!UICONTROL Important Attributes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Cliquez sur **[!UICONTROL Activities]**, puis sur l’activité [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) de votre choix dans la liste.

   Si vous avez de nombreuses activités, cliquez sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur **[!UICONTROL Reports]**.

   Le rapport [Résumé Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou [Résumé du ciblage automatique](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) s’affiche, et fournit des informations sur les performances de vos activités, représentées par l’icône du premier écran. Les deux icônes supplémentaires représentent les deux rapports [!UICONTROL Personalization Insights] : **[!UICONTROL Automated Segments]** ( ![rapport Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) et **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).


   Notez que [!UICONTROL Auto-Target] comporte une icône de graphique supplémentaire pour la vue graphique du rapport [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >Le rapport [!UICONTROL Important Attributes] ne sera disponible que 15 jours au moins après l’activation de votre activité. Au cours de cette période initiale, vous ne pourrez pas accéder à ce rapport ni cliquer sur l’icône [!UICONTROL Important Attributes]. Une fois que 15 jours se sont écoulés, en supposant qu’il y ait suffisamment de trafic personnalisé dans votre activité, le rapport [!UICONTROL Important Attributes] est disponible.

1. 15 jours après l’activation de l’activité, cliquez sur l’icône **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ).

1. Sélectionnez la plage de dates désirée.

   Contrairement au rapport [!UICONTROL Summary] (rapport de performances), [!UICONTROL Personalization Insights], y compris [!UICONTROL Important Attributes], n’est disponible que pour des périodes fixes : 15 jours, 30 jours et 60 jours.

   Ces périodes fixes [!UICONTROL Personalization Insights] permettent d’utiliser une plage de données suffisamment étendue pour réduire la probabilité d’obtenir des informations à partir d’un modèle de courte durée dans votre activité. Les deux décisions que vous pouvez prendre pour votre plage de dates portent sur la « Date de fin » et la « Durée ». Vous remarquerez que le « Début » est grisé. La date de début change automatiquement en fonction de vos sélections de date de fin et de durée.

   Vous pouvez accéder aux périodes fixes disponibles à partir de la liste déroulante [!UICONTROL Preset Date Range] .

1. Examinez les données du rapport [!UICONTROL Important Attributes].

1. (Facultatif) Cliquez sur l’icône Télécharger ( ![icône Télécharger](/help/main/assets/icons/Download.svg) ) pour [télécharger le rapport au format CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) afin de l’analyser dans Excel et d’autres outils.

   >[!NOTE]
   >
   >Le rapport de l’interface utilisateur Informations de personnalisation contient des informations choisies. Le fichier CSV correspondant au rapport Attributs importants contient des détails supplémentaires. Le téléchargement du rapport Attributs importants comprend la liste complète des 100 premiers attributs, tandis que le rapport de l’interface utilisateur inclut les 10 premiers uniquement. Si vous recherchez un attribut spécifique dans le rapport mais qu’il n’y figure pas, cela ne signifie pas que l’attribut n’a pas eu d’incidence sur l’activité, mais il n’a simplement pas atteint la liste des 100 premiers attributs.

## Interprétation du rapport Attributs importants

Le tableau suivant explique comment interpréter le rapport et en décrit les éléments :

| Élément | Détails |
|--- |--- |
| Graphique en barres | Le graphique en barres multicouleur situé en haut de l’écran vous permet de visualiser ces scores d’importance relative et est associé à la couleur du point en regard de chaque attribut respectif dans le tableau. Vous pouvez également survoler une couleur spécifique dans le graphique en barres avec le curseur pour afficher l’attribut qu’elle représente. Les scores d’importance sur les 100 premiers attributs totalisent 100 %. Pour plus d’informations sur l’ajout d’attributs supplémentaires utilisables par les modèles de personnalisation de Target, voir [Chargement de données pour les algorithmes Personalization de Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Graphique Classement des attributs de modèle | Le Classement des attributs de modèle comprend les 10 premiers attributs les plus importants dans la manière dont le modèle de personnalisation de Target a décidé du contenu à présenter à chaque visiteur. Le score d’importance indique, par rapport aux 100 premiers attributs, le degré d’importance d’un attribut spécifique pour les modèles de personnalisation de Target dans cette activité. |

## FAQ sur Attributs importants {#section_740910A52FA646B4AC9452F98C2F5719}

Consultez les FAQ suivantes pour obtenir des réponses aux questions les plus fréquemment posées sur l’utilisation du rapport [!UICONTROL Important Attributes].

### Les rapports Personalization Insights ne sont pas encore disponibles pour mon activité. Pourquoi ?

Plusieurs raisons peuvent expliquer pourquoi les rapports [!UICONTROL Personalization Insights] ne sont pas encore disponibles pour votre activité :

* 15 jours ne se sont pas écoulés depuis que vous avez activé l’activité. Les rapports Segments automatisés et Attributs importants ne seront disponibles qu’au moins 15 jours après que vous ayez commencé votre activité. Pendant cette période initiale, vous ne pourrez pas accéder à ces rapports ni cliquer sur les icônes Segments automatisés et Attributs importants.
* Votre activité n’a pas présenté assez de trafic au cours de la période spécifiée. Une fois les 15 jours passés, en supposant qu’il existe un [trafic personnalisé suffisant](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) dans votre activité pour construire les modèles de personnalisation, les rapports Segments automatisés et Attributs importants seront disponibles.
* Votre activité a un objectif d’optimisation des revenus. Actuellement, [!UICONTROL Personalization Insights] n’est disponible que pour les activités d’objectif d’optimisation de la conversion. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

### Qu’est-ce qu’un attribut ?

Un attribut consiste en des informations sur un visiteur ou sa visite spécifique utilisées par les algorithmes de personnalisation pour savoir comment personnaliser le trafic. Par exemple, un attribut peut être le type de navigateur, l’emplacement, l’heure de la journée de la visite, etc.

Pour plus d’informations sur les attributs utilisés par [!DNL Target] dans ses modèles de personnalisation, voir [Collecte de données pour les algorithmes de personnalisation de Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Pour plus d’informations sur le téléchargement de nouveaux attributs dans Target afin de les utiliser dans les modèles de personnalisation de Target, consultez la section [Méthodes pour importer des données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}.

### Un ou plusieurs attributs que je ne souhaite pas que le modèle utilise pour l’entraînement sont présents. Puis-je supprimer ces attributs du modèle d’entraînement ? {#models-api}

L’[!UICONTROL Models API], également appelée API de Place sur la liste bloquée, permet aux utilisateurs d’afficher et de gérer la liste des attributs (également appelés fonctionnalités) utilisés dans les modèles de machine learning pour les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). Si vous souhaitez exclure un ou plusieurs attributs de l’utilisation des modèles pour les activités AP ou AT, vous pouvez utiliser l’API Modèles pour ajouter ces attributs au « place sur la liste bloquée ».

Pour plus d’informations, consultez [Présentation de l’API Modèles](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} dans le *Guide du développeur d’Adobe Target*. Pour utiliser l’API pour bloquer des attributs, voir [API Modèles](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}.

### Les informations contenues dans les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes] sont-elles identiques à celles du téléchargement CSV ?

Non, le rapport d’interface utilisateur contient des informations sélectionnées. Le téléchargement CSV contient des détails supplémentaires. Le téléchargement du rapport Informations sur les segments automatisés inclut des segments automatisés supplémentaires au-delà des segments supérieurs inclus dans l’interface utilisateur, ainsi que la manière dont ces segments se sont comportés par rapport à vos offres ou expériences. Le rapport Attributs importants comprend les 100 premiers attributs de visiteur et leur importance relative, tandis que l’interface utilisateur inclut uniquement les 10 premiers attributs de visiteur.

### Puis-je afficher des informations sur Personalization pour une période personnalisée ?

La création de rapports Personalization Insights ([!UICONTROL Automated Segments] et [!UICONTROL Important Attributes]) est disponible uniquement pour les périodes fixes : 15 jours, 30 jours, 45 jours, 60 jours et 90 jours. Ces périodes fixes [!UICONTROL Personalization Insights] permettent d’utiliser une plage de données suffisamment étendue pour réduire la probabilité d’obtenir des informations à partir d’un modèle de courte durée dans votre activité. Vous pouvez sélectionner ces durées pour n’importe quelle date de fin (où l’activité comprend assez de données pour satisfaire la durée).

### Comment est-[!UICONTROL Personalization Insights] créé ?

[!UICONTROL Personalization Insights] est réalisé à l&#39;aide d&#39;une technique Adobe en instance de brevet appelée MAGIX (Model Agnostic Globally Interpretable Explanations). Pour en savoir plus sur MAGIX, consultez l&#39;article publié par l&#39;équipe de recherche sur l&#39;Adobe sur le site Web [arXiv.org](https://arxiv.org/abs/1706.07160).

### Les [!UICONTROL Personalization Insights] sont-elles disponibles pour les objectifs de modélisation basés sur le chiffre d’affaires/objectif principal ?

Actuellement, [!UICONTROL Personalization Insights] n’est disponible que pour les activités d’objectif d’optimisation de la conversion. Nous ajouterons une prise en charge des activités d’objectif des revenus dans une prochaine version.

### Quel est le score d’importance de l’attribut dans le rapport Attributs importants ?

Le score d’importance dans la partie « Classement d’importance d’attribut » du rapport fournit des données indiquant quelles variables utilisées par l’algorithme pour apprendre ont été les plus importantes lorsqu’il a déterminé comment diviser tous les visiteurs dans les segments qu’il a identifiés. Il a attribué un score en pourcentage aux 100 premiers attributs utilisés par le modèle.

### Pourquoi certaines offres/expériences avec un taux de conversion inférieur reçoivent-elles une quantité de trafic plus importante par rapport à d’autres offres/expériences pour un certain segment automatisé ?

Plusieurs raisons peuvent expliquer le fait que vous puissiez constater plus de visites sur une offre/expérience présentant un taux de conversion plus bas, y compris les raisons suivantes :

* Un petit nombre de vues pour certaines des offres/expériences ou toutes pour un certain segment automatisé.
* Activités de volume inférieur dans lesquelles certaines offres ou expériences n’ont pas de modèles créés.
* Activités de volume inférieur dans lesquelles les modèles ont été créés plus tôt pour certaines offres/expériences que d’autres. Supposons, par exemple, qu’un modèle supplémentaire ait été créé le jour 22 et que vous consultiez les données des jours 10-24.
* Des règles de ciblage sur une offre spécifique qui limitent quels visiteurs peuvent voir quelles offres/expériences.
* Les rapports d’informations ne comportent aucun intervalle de confiance. Cependant, si les taux de conversion sont suffisamment proches, le modèle peut diffuser le trafic de sorte qu’il soit plus élevé en termes de nombre de points, mais il ne s’agit pas de nombres « statistiquement différents ».

Il peut s’avérer utile de savoir comment fonctionne le modèle qui diffuse le trafic. Chaque personne est servie en fonction de son profil total. Toutefois, les rapports d’informations généralisent ce comportement pour le rendre plus facile à interpréter par un humain. Par conséquent, les segments ne sont pas mutuellement exclusifs. Cela peut conduire à des segments individuels affichant ce type de comportement, car la même personne peut apparaître dans plusieurs segments.

### Quelles sont les différentes manières d’exploiter les informations dans Personalization Insights ?

* Découvrez de nouvelles audiences à cibler : si un segment automatisé particulier est particulièrement efficace, vous pouvez envisager de créer une audience afin de pouvoir réutiliser ce segment dans d’autres rapports.
* Testez vos hypothèses sur le fait de savoir quels types de visiteur répondront auxquelles de vos expériences.
* Générez des informations indiquant quel contenu a fonctionné pour quel type de visiteur : quelles offres ont eu un effet élévateur chez quels visiteurs.
* Identifiez le contenu peu efficace.
* Identifiez les attributs les plus essentiels dans la manière dont le modèle a appris.
* Identifiez quels attributs sont utilisés dans les modèles de personnalisation et leur importance.
* Identifiez les opportunités de points de données supplémentaires que vous pouvez transmettre à Target pour informer davantage votre personnalisation.

## Problèmes connus

L’équipe d’ingénierie [!DNL Target] étudie actuellement le problème suivant.

* [!DNL Adobe Experience Platform] noms de segment ne s’affichent pas dans le rapport [!UICONTROL Important Attributes] pour les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT). (TOP-3813)
