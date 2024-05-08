---
keywords: recommandations;paramètres;nom;objectif;priorité;durée;paramètres de création de rapports;autres métadonnées
description: Découvrez comment configurer les paramètres utilisés pour décrire et contrôler une activité Recommendations dans Adobe Target.
title: Comment configurer les paramètres d’activité de Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 50%

---

# Paramètres de l’activité de recommandations

Informations sur les paramètres que vous pouvez utiliser pour décrire et contrôler une [!UICONTROL Recommendations] activité dans [!DNL Adobe Target].

![Page Objectifs et paramètres de Recommandations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

Les sections suivantes décrivent les paramètres disponibles pour une [!UICONTROL Recommendations] activité.

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

Si vous spécifiez une [!UICONTROL Recommendations] nom de l’activité qui existe déjà pour une autre activité dans [!UICONTROL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom correspond au nom d’origine complété par un horodatage pour le rendre unique. Le nouveau nom est affiché dans [!DNL Target Standard/Premium] et dans [!UICONTROL Recommendations Classic].

## Intention

(Facultatif) Décrivez l’objectif de l’activité.

## Priorité

Réglez le curseur pour définir le niveau de priorité.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

## Durée

Définissez la durée de l’activité.

L’activité peut démarrer lorsqu’elle est activée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports

* **Source de création de rapports :** Spécifiez les données de solution à partir desquelles collecter :

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  Si une solution de création de rapports est spécifiée dans votre [paramètres du compte](/help/main/administrating-target/reporting.md), la solution spécifiée est utilisée et ce paramètre n’est pas visible.

  Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour préserver la cohérence des rapports.

  **[!DNL Adobe Analytics]**: Voir [[!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune d’elles.

  Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T), vous sélectionnez une [!DNL Analytics] suite de rapports à recevoir [!DNL Target] données d’activité. Pour ce faire, faites d’abord votre choix parmi les options suivantes : [!DNL Analytics] société à laquelle votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Target] sont disponibles pour sélection. Si vous ne voyez pas la suite de rapports attendue, essayez d’abord de vous déconnecter et de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  [!DNL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans la variable [!UICONTROL Tracking Server] champ . Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

  **[!DNL Adobe Customer Journey Analytics]**: Voir [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].

* **Mesure d’objectif :** Sélectionnez la mesure de succès qui détermine si l’activité est réussie.
* **Mesures supplémentaires :** Configurez des mesures de succès supplémentaires à utiliser dans les rapports.
* **Publics pour les rapports :** Définissez des audiences qui peuvent être utilisées lors du filtrage des rapports.

## Autres métadonnées

Entrez des notes relatives à votre activité.

## Vidéo de formation : paramètres d’activité (3:02) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
