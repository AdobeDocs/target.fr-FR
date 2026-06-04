---
keywords: paramètres d’activité;objectifs et paramètres du ciblage d’expérience;objectifs et paramètres xt;ciblage d’expérience;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectifs;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur rencontrera cette mesure d’objectif;remarques
description: Découvrez comment utiliser la page [!UICONTROL Objectifs et paramètres] dans  [!DNL Adobe Target]  pour spécifier des informations sur les objectifs d’une activité [!UICONTROL Ciblage d’expérience] (XT).
title: Comment spécifier des [!UICONTROL objectifs et paramètres] dans une activité de [!UICONTROL ciblage d’expérience] ?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
TQID: https://experienceleague.adobe.com/vlpJSJ4Z6mxQI-D8UyUPEXHVWKfR54l89uoxULd2oD0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1285
ht-degree: 42%

---

# Objectifs et paramètres des activités [!UICONTROL Ciblage d’expérience] (XT)

La page [!UICONTROL Objectifs et paramètres] vous permet de saisir des informations sur les objectifs du test :

* [!UICONTROL Paramètres d’activité]
* [!UICONTROL Paramètres de création de rapports]
* [!UICONTROL Autres métadonnées]

Les paramètres disponibles varient selon que vous utilisez [!DNL Target] ou [!DNL Analytics] comme source de création de rapports.

## [!UICONTROL Paramètres d’activité] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Les méthodes suivantes sont disponibles :

### [!UICONTROL Objectif &#x200B;]

Saisissez une intention facultative. L’intention peut être toute information qui vous aide et aide les membres de l’équipe à identifier la campagne.

### [!UICONTROL Priorité]

Selon vos paramètres, l’interface utilisateur [!DNL Target] et les options de [!UICONTROL Priorité] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Faible], [!UICONTROL Medium] ou [!UICONTROL Élevé], ou activer des priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si plusieurs activités sont affectées à l’emplacement, l’activité ayant la priorité la plus élevée est affichée.

Si cette option n’est pas activée dans [!UICONTROL Administration] (valeur par défaut), spécifiez une priorité : [!UICONTROL Faible], [!UICONTROL Medium] ou [!UICONTROL Élevée].

Pour activer les priorités affinées, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Rapports]**, puis activez l’option [!UICONTROL Activer les priorités affinées] sur la position « Activé ».

Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

* 0 = Faible
* 999 = Élevé

Pour les activités créées dans les versions précédentes d’[!DNL Target], la priorité [!UICONTROL Faible] est convertie en 0, la priorité [!UICONTROL Medium] est convertie en 5 et la priorité [!UICONTROL Élevée] est convertie en 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

### [!UICONTROL Durée]

L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut se terminer lorsqu’elle est désactivée ou vous pouvez définir une date et une heure de fin. Le sélecteur d’heure utilise une horloge de 24 heures, 00:00 correspondant à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## [!UICONTROL Paramètres de création de rapports] {#section_13119392051044FBA6387D9B3B1C43CF}

Les méthodes suivantes sont disponibles :

### [!UICONTROL Reporting Source]

Indiquez à partir de quelle solution les données sont collectées :

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Si une solution de création de rapports est spécifiée dans les paramètres de votre [compte](/help/main/administrating-target/reporting.md), la solution spécifiée est utilisée et ce paramètre n’est pas visible.

Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour conserver la cohérence des rapports.

**[!DNL Adobe Analytics]** : voir [[!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour en savoir plus sur les différences entre les solutions de création de rapports et les avantages de chacune d’elles.

Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T), vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir des données d’activité [!DNL Target]. Pour ce faire, choisissez d’abord l’une des [!DNL Analytics] sociétés auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée pour l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Target] peuvent être sélectionnées. Si la suite de rapports attendue ne s’affiche pas, essayez d’abord de vous déconnecter puis de vous reconnecter à la [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports est toujours absente de la liste, contactez l’[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s’affiche dans le champ [!UICONTROL Serveur de suivi]. Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le bon serveur de suivi dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

**[!DNL Adobe Customer Journey Analytics]** : voir [[!DNL Target] Reporting dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].

### [!UICONTROL Mesure d’objectif]

Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure [!UICONTROL Conversion], puis définissez les paramètres qui déterminent le moment où la réussite est atteinte.

Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL Conversion]. [!DNL Analytics] mesures ne peuvent pas être sélectionnées en tant qu’objectif.

Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.

Si cette option est activée, le champ [!UICONTROL Valeur estimée de la conversion] (non disponible pour les mesures [!UICONTROL Score de page]) fournit une valeur pour votre objectif, mais pas pour d’autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de chiffre d’affaires ([!UICONTROL Chiffre d’affaires par visiteur], [!UICONTROL Valeur moyenne de la commande], [!UICONTROL Total des ventes] et [!UICONTROL Commandes]), l’estimation utilise [!UICONTROL Chiffre d’affaires par visiteur]. Les données sont de type devise.

Une fois l’objectif d’activité atteint, le visiteur continue à voir le contenu de l’activité, sauf s’il est qualifié pour une activité prioritaire. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Ce comportement est différent du comportement par défaut dans [!DNL Target Classic], qui comptait les visiteurs comme nouveaux s’ils voyaient à nouveau le test.

### [!UICONTROL Mesures supplémentaires]

Créez des mesures de succès supplémentaires.

Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la suite de rapports [!DNL Analytics] sont appliquées.

### [!UICONTROL Audiences pour le reporting]

Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement les informations sur des audiences spécifiques.

Ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] comme solution de création de rapports. L’audience définie pour la suite de rapports [!DNL Analytics] est appliquée.

## [!UICONTROL Autres données Meta]

Saisissez toute information utile pour vous-même ou pour d’autres membres de l’équipe concernant votre activité. Le volet [!UICONTROL Notes] peut être redimensionné.

## [!UICONTROL Paramètres avancés] {#section_E2FE441AFB324E498793ABB025ED9974}

Les paramètres avancés sont disponibles pour les mesures d’objectif [!UICONTROL Ciblage d’expérience].

![Paramètres avancés](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option [!UICONTROL Paramètres avancés] n’est pas disponible.

Les méthodes suivantes sont disponibles :

### [!UICONTROL Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ?]

Utilisez cette option pour compter les visiteurs comme ayant atteint la mesure de succès uniquement s’ils ont précédemment atteint une autre mesure de succès. Par exemple, une conversion test peut n’être valide que si le visiteur clique sur l’offre ou atteint une page particulière avant la conversion.

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.

Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.

L’option [!UICONTROL Ajouter une dépendance] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après l’ajout de mesures supplémentaires, cliquez sur **[!UICONTROL Paramètres avancés]**.
2. Cliquez sur **[!UICONTROL Ajouter une dépendance]** :

   ![Lien Ajouter une dépendance](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur **[!UICONTROL Atteinte]** pour passer du paramètre [!UICONTROL Atteinte] au paramètre [!UICONTROL Non atteinte].

   ![Boîte de dialogue Ajouter une dépendance de mesures](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

### [!UICONTROL Que se passera-t-il lorsqu’un utilisateur rencontrera cette mesure d’objectif ?]

Trois options sont disponibles :

* Sélectionnez [!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité] pour spécifier comment le décompte est incrémenté.
* Sélectionnez [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et autoriser le retour] pour spécifier quelle expérience affiche l’utilisateur s’il rentre dans l’activité.
* Sélectionnez [!UICONTROL Incrémenter le décompte, Libérer l’utilisateur et la barre de la rentrée] pour spécifier ce que l’utilisateur voit au lieu du contenu de l’activité.

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Vidéo de formation : Paramètres des activités (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
