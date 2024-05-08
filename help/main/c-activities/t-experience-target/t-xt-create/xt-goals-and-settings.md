---
keywords: paramètres d’activité;objectifs et paramètres du ciblage d’expérience;objectifs et paramètres xt;ciblage d’expérience;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectifs;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur rencontrera cette mesure d’objectif;remarques
description: Découvrez comment utiliser le [!UICONTROL Goals & Settings] page [!DNL Adobe Target] pour spécifier des informations sur les objectifs d’une [!UICONTROL Experience Targeting] (XT).
title: Comment spécifier [!UICONTROL Goals & Settings] dans un [!UICONTROL Experience Targeting] Activité ?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 40%

---

# Objectifs et paramètres dans [!UICONTROL Experience Targeting] Activités (XT)

La variable [!UICONTROL Goals & Settings] où vous saisissez des informations sur les objectifs du test :

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Les paramètres disponibles dépendent si vous utilisez [!DNL Target] ou [!DNL Analytics] comme source des rapports.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Les méthodes suivantes sont disponibles :

### [!UICONTROL Objective]

Saisissez une intention facultative. L’intention peut être toute information qui vous aide et aide les membres de l’équipe à identifier la campagne.

### [!UICONTROL Priority]

Selon vos paramètres, la variable [!DNL Target] Interface utilisateur et options pour [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium], ou [!UICONTROL High]ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si plusieurs activités sont affectées à l’emplacement, l’activité avec la priorité la plus élevée s’affiche.

Si cette option n’est pas activée dans [!UICONTROL Administration] (valeur par défaut), spécifiez une priorité : [!UICONTROL Low], [!UICONTROL Medium], ou [!UICONTROL High].

Pour activer les priorités affinées, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Reporting]**, puis faites basculer le [!UICONTROL Enable Fine-Grained Priorities] à la position &quot;Activé&quot;.

Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

* 0 = Faible
* 999 = Élevé

Pour les activités créées dans les versions précédentes de [!DNL Target], [!UICONTROL Low] La priorité est convertie en 0, [!UICONTROL Medium] est converti en 5 et [!UICONTROL High] est converti en 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

### [!UICONTROL Duration]

L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut se terminer lorsqu’elle est désactivée ou vous pouvez définir une date et une heure de fin pour l’activité. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

Les méthodes suivantes sont disponibles :

### [!UICONTROL Reporting Source]

Spécifiez les données de solution à partir desquelles collecter :

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si une solution de création de rapports est spécifiée dans votre [paramètres du compte](/help/main/administrating-target/reporting.md), la solution spécifiée est utilisée et ce paramètre n’est pas visible.

Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour préserver la cohérence des rapports.

**[!DNL Adobe Analytics]**: Voir [[!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune d’elles.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T), vous sélectionnez une [!DNL Analytics] suite de rapports à recevoir [!DNL Target] données d’activité. Pour ce faire, faites d’abord votre choix parmi les options suivantes : [!DNL Analytics] société à laquelle votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Target] sont disponibles pour sélection. Si vous ne voyez pas la suite de rapports attendue, essayez d’abord de vous déconnecter et de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans la variable [!UICONTROL Tracking Server] champ . Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

**[!DNL Adobe Customer Journey Analytics]**: Voir [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].

### [!UICONTROL Goal Metric]

Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez un [!UICONTROL Conversion] , puis définissez les paramètres qui déterminent le moment où la réussite est atteinte.

Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL Conversion]. [!DNL Analytics] ne peuvent pas être sélectionnées en tant qu’objectif.

Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.

Si cette option est activée, la variable [!UICONTROL Estimated Value of the Conversion] (non disponible pour [!UICONTROL Page Score] (mesures) fournit une valeur pour votre objectif, mais pas pour les autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise.

Après avoir atteint l’objectif de l’activité, un visiteur continue à voir le contenu de l’activité, sauf si le visiteur est admissible pour une activité de priorité plus élevée. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Ce comportement diffère du comportement par défaut dans [!DNL Target Classic], qui comptabilise les visiteurs comme nouveaux s’ils affichent à nouveau le test.

### [!UICONTROL Additional Metrics]

Créez des mesures de succès supplémentaires.

Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la variable [!DNL Analytics] suite de rapports sont appliquées.

### [!UICONTROL Audiences for Reporting]

Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement les informations sur des audiences spécifiques.

Ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] en tant que solution de création de rapports. L’audience définie pour la variable [!DNL Analytics] suite de rapports est appliquée.

## [!UICONTROL Other Meta Data]

Saisissez des informations sur votre activité qui vous seront utiles, ainsi qu’aux autres membres de l’équipe. La variable [!UICONTROL Notes] est redimensionnable.

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

Les paramètres avancés sont disponibles pour [!UICONTROL Experience Targeting] mesures d’objectif.

![Paramètres avancés](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. La variable [!UICONTROL Advanced Settings] n’est pas disponible.

Les méthodes suivantes sont disponibles :

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

Utilisez cette option pour comptabiliser uniquement les visiteurs comme atteignant la mesure de succès s’ils ont déjà atteint une autre mesure de succès. Par exemple, une conversion de test peut uniquement être valide si le visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.

Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.

La variable [!UICONTROL Add Dependency] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Advanced Settings]**.
2. Cliquez sur **[!UICONTROL Add Dependency]**:

   ![Lien Ajouter une dépendance](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur **[!UICONTROL Reached]** pour basculer entre les paramètres [!UICONTROL Reached] et [!UICONTROL Not Reached].

   ![Boîte de dialogue Ajouter une dépendance de mesures](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

### [!UICONTROL What will happen after a user encounters this goal metric?]

Trois options sont disponibles :

* Sélectionner [!UICONTROL Increment Count & Keep User in Activity] pour spécifier le mode d’incrémentation du nombre.
* Sélectionner [!UICONTROL Increment Count, Release User & Allow Reentry] pour spécifier l’expérience que l’utilisateur voit s’il entre à nouveau dans l’activité.
* Sélectionner [!UICONTROL Increment Count, Release User & Bar from Reentry] pour spécifier ce que l’utilisateur voit à la place du contenu de l’activité.

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Vidéo de formation : Paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
