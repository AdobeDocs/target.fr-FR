---
keywords: paramètres d’activité;objectifs et paramètres A/B;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectif;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur aura atteint cette mesure d’objectif;remarques
description: Découvrez comment utiliser la page [!UICONTROL Objectifs et paramètres] pour définir les objectifs des activités A/B.
title: Comment puis-je spécifier des objectifs et des paramètres dans une activité A/B [!DNL Target] ?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
TQID: 'https://experienceleague.adobe.com/X3JDvfXDHM2rAOodEY5N9TVO-tBpz4vNDUvhOpC0XZ4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: abab6b3e464bb9f294e9c3c455dca1f57bb0d458
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 25%
---
# Objectifs et paramètres {#ab-goals-and-settings}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez ce que vous pouvez définir sur la page **[!UICONTROL Objectifs et paramètres]** d’une activité A/B, Ciblage d’expérience (XT) ou Test multivarié (MVT) : les paramètres de l’activité, les paramètres de création de rapports, les paramètres avancés et les notes.

>[!ENDSHADEBOX]

La page **[!UICONTROL Objectifs et paramètres]** de [!DNL Adobe Target] vous permet de spécifier des informations sur les objectifs de l’activité.

Les paramètres disponibles varient selon que vous utilisez Target ou [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Les mêmes paramètres s’appliquent aux activités de [!UICONTROL ciblage d’expérience] (XT) et de [!UICONTROL test multivarié] (MVT), à l’exception de la [méthodologie statistique](#section_statistical-methodology), disponible uniquement pour les activités A/B.

* [Paramètres d’activité](#section_DCBDC354261F420EBD4B43EA34947BAC) : objectif, priorité et durée
* [Paramètres de création de rapports](#section_13119392051044FBA6387D9B3B1C43CF) : source de création de rapports, mesure d’objectif, mesures supplémentaires et audiences
* [Paramètres avancés](#section_E2FE441AFB324E498793ABB025ED9974) : les dépendances et ce qui se passe lorsqu’un visiteur atteint l’objectif
* [Méthodologie statistique](#section_statistical-methodology) : méthode d’analyse des résultats
* [Autres métadonnées](#section_2E8917BEFB954480A4206B9E9E917F80) : notes

## [!UICONTROL Paramètres d’activité] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La section **[!UICONTROL Paramètres d’activité]** de la page **[!UICONTROL Objectifs et paramètres]** vous permet de configurer les options suivantes.

![](../../assets/goals-ab-1.png)

### Intention {#objective}

Saisissez une intention facultative. L’objectif peut être toute information qui vous aide, vous et les membres de votre équipe, à identifier l’activité.

### Priorité {#priority}

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

Selon vos paramètres, l’interface utilisateur [!DNL Target] et les options de **[!UICONTROL Priorité]** varient :

* **Priorités héritées (par défaut) :** Si cette option n’est pas activée dans **[!UICONTROL Administration]** (par défaut), spécifiez une priorité de **[!UICONTROL Faible]**, **[!UICONTROL Medium]** ou **[!UICONTROL Élevée]**.
* **Priorités affinées :** spécifiez une valeur comprise entre 0 et 999, où 0 = **[!UICONTROL Faible]** et 999 = **[!UICONTROL Élevé]**.

  Pour activer [les priorités affinées](/help/main/administrating-target/reporting.md), accédez à **[!UICONTROL Administration]** > **[!UICONTROL Rapports]**, puis activez l’option **[!UICONTROL Activer les priorités affinées]**.

Pour les activités créées dans les versions précédentes de [!DNL Target], la priorité **[!UICONTROL Basse]** est convertie en 0, **[!UICONTROL Medium]** est convertie en 5 et **[!UICONTROL Élevée]** est convertie en 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver les priorités affinées après les avoir utilisées, toutes les priorités doivent être définies sur 0, 5 et 10.

### Durée {#duration}

L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez.

Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## [!UICONTROL Paramètres de création de rapports] {#section_13119392051044FBA6387D9B3B1C43CF}

La section **[!UICONTROL Paramètres de création de rapports]** de la page **[!UICONTROL Objectifs et paramètres]** vous permet de configurer les options suivantes.

![](../../assets/goals-ab-2.png)

### Source de création de rapports {#reporting-source}

Indiquez à partir de quelle solution les données sont collectées :

* [!DNL Adobe Target]

* [!DNL Adobe Analytics]

  +++ En savoir plus sur Analytics comme source de création de rapports

  Voir [Adobe Analytics en tant que source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune. Lors de la sélection de [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir [!DNL Target] données d’activité.

  Pour spécifier une source de création de rapports, choisissez d’abord l’une des [!DNL Analytics] sociétés auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée pour l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] peuvent être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter puis de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports est toujours absente de la liste, contactez l’assistance clientèle.

  [!DNL Analytics for Target] (A4T) nécessite un serveur de suivi pour signaler correctement les résultats. Un serveur de suivi par défaut s&#39;affiche dans le champ **[!UICONTROL Serveur de suivi]**. Si vous utilisez plusieurs serveurs de suivi, veillez à inclure le bon serveur de suivi dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)
  +++

* [!DNL Adobe Customer Journey Analytics]

  +++ En savoir plus sur Customer Journey Analytics comme source de création de rapports

  Consultez la section [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour connaître les types d’activité pris en charge, la sélection de sandbox et de vues de données, les mesures d’objectif et la configuration des rapports dans [!DNL Customer Journey Analytics].
  +++

Si une source de création de rapports est spécifiée dans les [paramètres de votre compte](/help/main/administrating-target/reporting.md), la source spécifiée est utilisée et ce paramètre n&#39;est pas visible.

Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour conserver la cohérence des rapports.

### Mesure de l’objectif {#goal-metric}

>[!NOTE]
>
>Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est **[!UICONTROL Conversion]**. [!DNL Analytics] mesures ne peuvent pas être sélectionnées en tant qu’objectif.

Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure **[!UICONTROL Conversion]**, puis définissez les paramètres qui déterminent à quel moment la conversion est réalisée.

Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).

Pour afficher plus d’options, cliquez sur l’icône **[!UICONTROL Plus]** en regard de la mesure d’objectif, puis cliquez sur **[!UICONTROL Paramètres avancés]**. Voir [Paramètres Avancés](#section_E2FE441AFB324E498793ABB025ED9974).

![](../../assets/goals-ab-3.png)

Si cette option est activée, la **[!UICONTROL Valeur estimée de la conversion]** fournit une valeur pour votre objectif, mais pas pour d’autres mesures. Les points suivants s’appliquent à ce champ :

* La valeur permet à [!DNL Target] de calculer une augmentation estimée du chiffre d’affaires.
* Le champ est facultatif. Toutefois, les revenus incrémentiels pour toute mesure sans revenus ne peuvent pas être calculés sans celui-ci.
* Le champ n’est pas disponible pour les mesures **[!UICONTROL Score de page]**.
* Pour toutes les mesures de chiffre d’affaires (**[!UICONTROL Chiffre d’affaires par visiteur]**, **[!UICONTROL Valeur de commande moyenne]**, **[!UICONTROL Total des ventes]** et **[!UICONTROL Commandes]**), l’estimation utilise **[!UICONTROL Chiffre d’affaires par visiteur]**. Les données sont de type devise.

### Mesures supplémentaires {#additional-metrics}

Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la suite de rapports [!DNL Analytics] sont appliquées.

### Audiences pour les rapports {#audiences-for-reporting}

![](../../assets/goals-ab-4.png)

Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences de rapport pour afficher des informations sur des audiences spécifiques uniquement.

Notez que ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] comme solution de création de rapports. L’audience définie pour la suite de rapports [!DNL Analytics] est appliquée.

## Paramètres avancés {#section_E2FE441AFB324E498793ABB025ED9974}

La section **[!UICONTROL Paramètres avancés]** de la page **[!UICONTROL Objectifs et paramètres]** vous permet de configurer les options avancées.

Pour spécifier des paramètres avancés, cliquez sur l’icône **[!UICONTROL Plus]** ( ![Icône Plus](/help/main/assets/icons/MoreSmallList.svg) ) dans la section **[!UICONTROL Mon objectif de Principal]**, puis cliquez sur **[!UICONTROL Paramètres avancés]**.

![](../../assets/goals-ab-3.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

### Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ? {#dependencies}

Utilisez cette option pour ne comptabiliser une personne comme ayant atteint la mesure de succès que si elle a précédemment atteint une autre mesure de succès. Par exemple, une conversion d’activité peut n’être valide que si le visiteur clique sur l’offre ou atteint une page particulière avant la conversion.

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente. Définissez les deux mesures de succès (ou plusieurs) avant de pouvoir rendre l’une dépendante de l’autre. L’option **[!UICONTROL Ajouter une dépendance]** permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après l’ajout de mesures supplémentaires, cliquez sur **[!UICONTROL Paramètres avancés]**.

1. Cliquez sur l’option **[!UICONTROL Ajouter une dépendance]**.

1. Faites glisser et déposez les mesures souhaitées, puis cliquez sur **[!UICONTROL Atteint]** pour basculer le paramètre entre **[!UICONTROL Atteint]** et **[!UICONTROL Non atteint]**.

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ? {#after-goal}

Une fois l’objectif d’activité atteint, le visiteur continue à voir le contenu de l’activité, sauf s’il est qualifié pour une activité prioritaire. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Ce comportement est différent du comportement par défaut dans [!DNL Target Classic], qui comptait les visiteurs comme nouveaux s’ils voyaient à nouveau l’activité.

Trois options sont disponibles :

* **[!UICONTROL Incrémenter le décompte et laisser l&#39;utilisateur dans l&#39;activité]** pour spécifier comment le décompte est incrémenté.
* **[!UICONTROL Incrémenter le décompte, libérer l’utilisateur et autoriser une reprise]** pour spécifier l’expérience que voit l’utilisateur s’il entre à nouveau dans l’activité.
* **[!UICONTROL Incrémenter le décompte, libérer l’utilisateur et interdire la rentrée]** pour spécifier ce que l’utilisateur voit au lieu du contenu de l’activité.

### Comment sera incrémenté le décompte ? {#count-increment}

Il existe trois options d’incrémentation du décompte :

* **[!UICONTROL Une fois par participant]**
* **[!UICONTROL À chaque impression (à l’exclusion des actualisations de page)]**
* **[!UICONTROL À Chaque Impression]**

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#overview) pour plus d’informations sur les paramètres avancés.

## Méthodologie statistique {#section_statistical-methodology}

La section **[!UICONTROL Méthodologie statistique]** de la page **[!UICONTROL Objectifs et paramètres]** vous permet de choisir la manière dont les résultats de l’expérience sont analysés.

### Options méthodologiques {#methodology-options}

Ce choix détermine le cadre statistique, les mesures de résultats et les critères de décision utilisés pour la mesure d’objectif **[!UICONTROL Conversion]** de cette activité :

* **[!UICONTROL bayésien]:** prise de décision basée sur les probabilités qui met à jour les croyances au fur et à mesure que les données arrivent et prend en charge la surveillance continue et des tailles d’échantillon plus petites. Les résultats sont exprimés comme la probabilité qu’une variante soit meilleure qu’une autre, par exemple « 92 % de probabilité que la variante B surpasse le contrôle ».
  * Convient mieux aux échantillons de petite taille, à la surveillance continue, aux parties prenantes qui préfèrent les probabilités ou lorsque vous avez des connaissances préalables à appliquer à partir de tests antérieurs.
  * Pas idéal lorsque vous avez besoin d’une approbation réglementaire ou de conformité stricte, ou que vous avez besoin de valeurs de p traditionnelles.
  * Les rapports indiquent **[!UICONTROL Chance de battre le contrôle]** et un intervalle crédible au lieu de la colonne fréquentiste **[!UICONTROL Confiance]**.
* **[!UICONTROL Test en t de Welch (Frequentist)] :** Méthodologie traditionnelle existante de test des hypothèses. Utilise des p-values et requiert une taille d’échantillon fixe. Les rapports affichent un pourcentage et un intervalle de confiance de **[!UICONTROL Confiance]**.

Ce paramètre est uniquement disponible pour les activités dont la mesure d’objectif principale est **[!UICONTROL Conversion]**. Les activités avec un objectif principal de **[!UICONTROL chiffre d’affaires]** ou **[!UICONTROL engagement]** utilisent toujours le test en t de **[!UICONTROL Welch]**.

Pour plus d&#39;informations sur la façon dont chaque méthodologie est calculée et rapportée, consultez [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

### Configuration bayésienne {#bayesian-configuration}

Ce paramètre s’affiche uniquement lorsque **[!UICONTROL bayésien]** est sélectionné comme **[!UICONTROL méthodologie statistique]**. Configurez les options suivantes :

* **[!UICONTROL Intervalle crédible]** : définit la plage dans laquelle l&#39;effet réel devrait se produire.
* **[!UICONTROL Seuil de décision]** : définit la probabilité minimale qu’une variante doit atteindre, par rapport à **[!UICONTROL Contrôle]**, avant de pouvoir être déclarée gagnante.
* **[!UICONTROL Utiliser les connaissances préalables des tests précédents ?]** : activez cette option pour fournir des connaissances préalables des performances passées afin d’informer le calcul **[!UICONTROL bayésien]**.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

La section **[!UICONTROL Autres métadonnées]** de la page **[!UICONTROL Objectifs et paramètres]** vous permet de spécifier toute information utile à vous ou aux autres membres de l’équipe concernant votre activité.
