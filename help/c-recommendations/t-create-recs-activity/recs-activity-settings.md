---
description: Plusieurs paramètres peuvent être utilisés pour décrire et contrôler une activité de recommandations.
keywords: recommandations;paramètres;nom;objectif;priorité;durée;paramètres de création de rapports;autres métadonnées
seo-description: Plusieurs paramètres peuvent être utilisés pour décrire et contrôler une activité de recommandations dans Adobe Target.
seo-title: Paramètres d'activité de recommandations dans Adobe Target
solution: Target
subtopic: Recommandations
title: Paramètres de l’activité de recommandations
title-outputclass: premium
topic: Premium
uuid: 7c66d0e8-cecf-4d0d-8c62-5347a7d80a53
badge: Premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) Paramètres de l’activité de recommandations{#recommendations-activity-settings}

Informations sur les paramètres que vous pouvez utiliser pour décrire et contrôler une activité de [!UICONTROL recommandations].

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

Si vous spécifiez un nom pour l’activité de [!UICONTROL Recommandations] qui existe déjà pour une autre activité dans [!UICONTROL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Le nouveau nom est affiché dans Target Standard/Premium et dans [!UICONTROL Recommendations Classic].

## Intention

(Facultatif) Décrivez l’objectif de l’activité.

## Priorité

Réglez le curseur pour définir le niveau de priorité.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

## Durée

Définissez la durée de l’activité.

L&#39;activité peut démarrer lorsqu&#39;elle est activée ou vous pouvez définir une date et une heure spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports

* **Source de création de rapports :** Sélectionnez la source de création de rapports : Adobe Target ou [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Ne modifiez pas la source de création de rapports une fois l&#39;activité activée. La modification de la source des rapports après l&#39;activation d&#39;une activité entraîne une création de rapports incohérente.
* **Mesure d&#39;objectif :** Sélectionnez la mesure de réussite qui détermine si l&#39;activité est réussie.
* **Mesures supplémentaires :** configurez des mesures de succès supplémentaires à utiliser dans les rapports.
* **Publics pour les rapports :** définissez des audiences qui peuvent être utilisées lors du filtrage des rapports.

## Autres métadonnées

Entrez des notes relatives à votre activité.

## Vidéo de formation : Paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381?captions=fre_fr)