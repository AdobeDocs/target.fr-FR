---
keywords: recommandations;paramètres;nom;objectif;priorité;durée;paramètres de création de rapports;autres métadonnées
description: Découvrez comment configurer les paramètres utilisés pour décrire et contrôler une activité Recommendations dans Adobe Target.
title: Comment configurer les paramètres d’activité de Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 84%

---

# Paramètres de l’activité de recommandations

Informations sur les paramètres que vous pouvez utiliser pour décrire et contrôler une [!UICONTROL Recommendations] activité dans [!DNL Adobe Target].

![Page Objectifs et paramètres de Recommandations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

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

Si vous spécifiez un nom pour l’activité de [!UICONTROL Recommandations] qui existe déjà pour une autre activité dans [!UICONTROL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Ce nouveau nom s’affiche dans les deux [!DNL Target Standard/Premium] et [!UICONTROL Recommendations Classic].

## Intention

(Facultatif) Décrivez l’objectif de l’activité.

## Priorité

Réglez le curseur pour définir le niveau de priorité.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

## Durée

Définissez la durée de l’activité.

L’activité peut démarrer lorsqu’elle est activée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports

* **Source de création de rapports :** Sélectionnez la source de création de rapports : [!DNL Adobe Target] ou [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md). Ne modifiez pas la source de création de rapports une fois l’activité démarrée. La modification de la source des rapports après le démarrage d’une activité entraîne une création incohérente de rapports.
* **Mesure d’objectif :** Sélectionnez la mesure de succès qui détermine si l’activité est réussie.
* **Mesures supplémentaires :** Configurez des mesures de succès supplémentaires à utiliser dans les rapports.
* **Publics pour les rapports :** Définissez des audiences qui peuvent être utilisées lors du filtrage des rapports.

## Autres métadonnées

Entrez des notes relatives à votre activité.

## Vidéo de formation : Paramètres d’activité (3:02) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
