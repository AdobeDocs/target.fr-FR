---
keywords: Recommendations;Settings;name;objective;priority;duration;reporting settings;other metadata
description: Plusieurs paramètres peuvent être utilisés pour décrire et contrôler une activité de recommandations dans Adobe Target.
title: Paramètres de l’activité de recommandations dans Adobe Target
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 89%

---


# ![PREMIUM](/help/assets/premium.png) Paramètres de l’activité de recommandations{#recommendations-activity-settings}

Informations sur les paramètres que vous pouvez utiliser pour décrire et contrôler une activité [!UICONTROL Recommendations] dans [!DNL Adobe Target].

![Page Objectifs et paramètres de Recommandations](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

Les sections ci-après décrivent les paramètres disponibles pour une activité de [!UICONTROL recommandations].

## Nom

Fournissez un nom explicite qui aidera votre équipe ainsi que vous-même à identifier l’activité.

Le nom de l’activité ne peut pas contenir les caractères suivants :

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

Si vous spécifiez un nom pour l’activité de [!UICONTROL Recommandations] qui existe déjà pour une autre activité dans [!UICONTROL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Ce nouveau nom s’affiche à la fois dans [!DNL Target Standard/Premium] et [!UICONTROL Recommendations Classic].

## Intention

(Facultatif) Décrivez l’objectif de l’activité.

## Priorité

Réglez le curseur pour définir le niveau de priorité.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

## Durée

Définissez la durée de l’activité.

L’activité peut démarrer lorsqu’elle est activée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports

* **Source du rapports :** sélectionnez la source du rapports :  [!DNL Adobe Target] ou  [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Ne modifiez pas la source de création de rapports une fois l’activité démarrée. La modification de la source des rapports après le démarrage d’une activité entraîne une création incohérente de rapports.
* **Mesure d’objectif :** Sélectionnez la mesure de succès qui détermine si l’activité est réussie.
* **Mesures supplémentaires :** Configurez des mesures de succès supplémentaires à utiliser dans les rapports.
* **Publics pour les rapports :** Définissez des audiences qui peuvent être utilisées lors du filtrage des rapports.

## Autres métadonnées

Entrez des notes relatives à votre activité.

## Vidéo de formation : Paramètres d’Activité (3:02) ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)