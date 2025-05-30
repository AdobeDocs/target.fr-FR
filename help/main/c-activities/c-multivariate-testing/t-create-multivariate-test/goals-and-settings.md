---
keywords: paramètres d’activité;objectifs et paramètres;multivarié;mvt
description: Découvrez comment utiliser la page [!UICONTROL Goals & Settings] dans  [!DNL Adobe Target]  pour spécifier des informations sur les objectifs d’une activité [!UICONTROL Multivariate Test] (MVT).
title: Comment spécifier les objectifs et les paramètres dans une activité [!UICONTROL Multivariate Test] (MVT) ?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 41%

---

# Objectifs et paramètres ([!UICONTROL Multivariate Test])

La page [!UICONTROL Goals & Settings] de [!DNL Adobe Target] est l’endroit où vous saisissez des informations sur les objectifs de vos activités [!UICONTROL Multivariate Test] (MVT).

Les sections suivantes sont disponibles :

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Les paramètres disponibles dans chaque section dépendent si vous utilisez [!DNL Target] ou [!DNL Analytics] comme source des rapports.

## Paramètres d’activité {#section_DCBDC354261F420EBD4B43EA34947BAC}

Les méthodes suivantes sont disponibles :

### Intention

Saisissez une intention facultative. L’intention peut être toute information qui vous aide et aide les membres de l’équipe à identifier la campagne.

### Priorité

Selon vos paramètres, l’interface utilisateur de [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

Si cette option n&#39;est pas activée dans [!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].

Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez l’option [!UICONTROL Enable Fine-Grained Priorities].

Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

* 0 = Faible
* 999 = Élevé

Pour les activités créées dans les versions précédentes de [!DNL Target], la priorité [!UICONTROL Low] est convertie en 0, la priorité [!UICONTROL Medium] est convertie en 5 et la priorité [!UICONTROL High] en 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

### Durée

L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports {#section_13119392051044FBA6387D9B3B1C43CF}

Les méthodes suivantes sont disponibles :

### Source de création de rapports

Spécifiez les données de solution à partir desquelles collecter :

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si une solution de création de rapports est spécifiée dans les [paramètres du compte](/help/main/administrating-target/reporting.md), la solution spécifiée est utilisée et ce paramètre n’est pas visible.

Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour préserver la cohérence des rapports.

**[!DNL Adobe Analytics]** : voir [[!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune d’elles.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T), vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir les données d’activité [!DNL Target]. Pour ce faire, faites d’abord votre choix parmi les sociétés [!DNL Analytics] auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Target] peuvent être sélectionnées. Si vous ne voyez pas la suite de rapports attendue, essayez d’abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez l’ [assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans le champ [!UICONTROL Tracking Server] . Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

**[!DNL Adobe Customer Journey Analytics]** : Voir [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].

### Mesure de l’objectif

Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure [!UICONTROL Conversion], puis définissez les paramètres qui déterminent le moment où la réussite est atteinte.

>[!NOTE]
>
>Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL Conversion]. Les mesures [!DNL Analytics] ne peuvent pas être sélectionnées en tant qu’objectif.

Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.

S’il est activé, le champ [!UICONTROL Estimated Value of the Conversion] (indisponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif, mais pas pour les autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise.

Après avoir atteint l’objectif de l’activité, un visiteur continue à voir le contenu de l’activité, sauf si le visiteur est admissible pour une activité de priorité plus élevée. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Ce comportement est différent du comportement par défaut dans [!DNL Target Classic], qui comptabilise les visiteurs comme nouveaux s’ils voient à nouveau le test.

### Mesures supplémentaires

Créez des mesures de succès supplémentaires.

Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la suite de rapports [!DNL Analytics] sont appliquées.

### Audiences pour les rapports

Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement les informations sur des audiences spécifiques.

### Paramètres avancés  {#section_E2FE441AFB324E498793ABB025ED9974}

Les paramètres avancés sont disponibles pour les mesures d’objectif [!UICONTROL Multivariate Test].

![Menu Paramètres avancés](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

#### Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ?

Utilisez cette option pour comptabiliser une personne comme atteignant la mesure de succès uniquement si elle a déjà atteint une autre mesure de succès. Par exemple, une conversion de test peut être valide uniquement si le visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.

Définissez les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.

L’option [!UICONTROL Add Dependency] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Advanced Settings]**.
2. Cliquez sur l’option **[!UICONTROL Add Dependency]** :

   ![Ajouter une dépendance](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur **[!UICONTROL Reached]** pour passer du paramètre Atteinte au paramètre Non atteinte .

   ![Dépendance atteinte](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?

Trois options sont disponibles :

* [!UICONTROL Select Increment Count & Keep User in Activity] pour spécifier comment le nombre est incrémenté.
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] pour spécifier l’expérience que l’utilisateur voit s’il entre à nouveau dans l’activité.
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] pour spécifier ce que l’utilisateur voit à la place du contenu de l’activité.

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

Les paramètres suivants sont disponibles :

### Remarques

Saisissez des informations sur votre activité qui vous seront utiles, ainsi qu’aux autres membres de l’équipe. Le volet [!UICONTROL Notes] peut être redimensionné.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Création de tests multivariés (9:25)

Cette vidéo explique comment créer un test multivarié à l’aide du processus assisté en trois étapes [!DNL Target]. Les objectifs et les paramètres sont abordés à partir de 7:00.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/30144?captions=fre_fr)
