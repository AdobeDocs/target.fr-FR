---
keywords: cja4t;customer journey analytics;customer journey analytics pour target;source de création de rapports customer journey analytics;customer journey analytics comme source de création de rapports pour target
description: Utilisez  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) pour créer des activités basées sur les mesures de conversio et sur les segments d’audience de  [!DNL Customer Journey Analytics] . Utilisez les rapports de  [!DNL Customer Journey Analytics]  pour examiner les résultats.
title: Qu’est-ce qu’ [!DNL Adobe Customer Journey Analytics]  pour  [!DNL Target]  (CJA4T) ?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: ht
source-wordcount: '919'
ht-degree: 100%

---

# [!DNL Adobe Customer Journey Analytics] comme source de création de rapports pour [!DNL Adobe Target] (CJA4T)

L’intégration [!DNL Customer Journey Analytics for Target] (CJA4T) entre [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html?lang=fr){target=_blank} et [!DNL Target] fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation.

Les principaux avantages offerts par l’utilisation des données de [!DNL Customer Journey Analytics] dans [!DNL Target] sont les suivants :

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de [!DNL Customer Journey Analytics] aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source de données unique élimine l’écart qui survient lorsque les données sont collectées dans deux systèmes distincts.

## Considérations

Tenez compte des informations suivantes avant d’utiliser l’intégration de CJA4T :

* Pour utiliser [!DNL Customer Journey Analytics] en tant que source de création de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Customer Journey Analytics] et à [!DNL Target]. Si vous avez besoin d’accéder à l’une des solutions, contactez l’administrateur ou l’administratrice de votre entreprise ou la personne chargée de la gestion de votre compte.
* Pour créer des activités [!DNL Target] avec la création de rapport de [!DNL Customer Journey Analytics], vous devez disposer du rôle « [!UICONTROL Approbateur] » ou « [!UICONTROL Éditeur] » dans [!DNL Target].
   * Si votre organisation dispose d’un compte [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), voir [Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs et utilisatrices*.
   * Si vous avez un compte [Target Premium](/help/main/c-intro/intro.md#premium), voir [Rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) dans *Autorisations des utilisateurs et utilisatrices d’Enterprise*.

* Selon vos paramètres, la création de rapports peut être modifiée par activité ou au niveau de l’organisation. Voir [Solution de création de rapports dans le cloud](/help/main/administrating-target/reporting.md#solution) dans *Configuration de la création de rapports dans Target*.
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données de plusieurs sources pour une même activité.
* Lorsque vous définissez [!DNL Customer Journey Analytics] en tant que source de création de rapports, il vous est demandé de spécifier le sandbox pour la création de rapports. Pendant la configuration, vous ne voyez que les sandbox auxquels vous avez accès.
* Toute activité [!DNL Target] existante continue à utiliser la collecte de données de [!DNL Target] et n’est pas affectée par l’activation de CJA4T.
* CJA4T n’est disponible que si vous avez [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}. La prise en charge du [!DNL Analytics Data Connector] est planifiée pour le futur.
* Pour toute question sur le timing, voir [Considérations relatives à la latence](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=fr#latency){target=_blank} dans *Questions fréquentes* dans le *Guide d’Adobe Customer Analytics*.

## Types d’activité pris en charge {#supported-activities}

Les types d’activité suivants sont pris en charge lors de l’utilisation de la bibliothèque JavaScript du [SDK web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=fr){target=_blank} :

| Types d’activité | Compatible avec CJA4T ? |
|--- |--- |
| [Activité A/B avec fractionnement manuel du trafic](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |
| [Activité A/B avec affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [Activité A/B avec ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Non |
| [Ciblage d’expérience (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Oui |
| [Test multivarié (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Oui |
| [Activité d’Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Non |
| [Activité Recommendations](/help/main/c-recommendations/recommendations.md) | Oui |

## Créer une activité utilisant [!DNL Customer Journey Analytics] en tant que source de création de rapports

La création d’une activité [!DNL Target] qui utilise [!DNL Customer Journey Analytics] en tant que source de création de rapports est similaire à la configuration d’une activité [!DNL Target] standard.

1. Dans la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]**, puis sélectionnez le type d’activité (en fonction du [graphique d’activités prises en charge ci-dessus](#supported-activities)) et commencez à configurer l’activité.
1. Lorsque vous accédez à la page **[!UICONTROL Objectifs et paramètres]** du workflow de création de l’activité en trois parties, sélectionnez **[!DNL Customer Journey Analytics]** comme source de création des rapports.

   ![Customer Journey Analytics comme option de source de création de rapports](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La source de création de rapports ne peut pas être modifiée après l’activation d’une activité [!DNL Target].

1. Sélectionner un sandbox.

   Vous ne pouvez afficher que les sandbox auxquels vous avez accès dans cette liste déroulante. Si un ou plusieurs sandbox auxquels vous avez accès ne figurent pas dans la liste, vérifiez que vous y avez accès. Contactez l’[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si vous continuez à voir des problèmes.

   ![Option Sélectionner un sandbox](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Indiquez l’objectif de l’activité.

   Sélectionnez une mesure de succès à utiliser comme objectif pour chaque activité. Vous pouvez choisir l’une des options suivantes : mesures de conversion [!DNL Target] ou utiliser une mesure [!DNL Customer Journey Analytics].

   ![Utilisation d’une option de mesure de Customer Journey Analytics sous Mesure d’objectif](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

## Configurer une connexion [!DNL Customer Journey Analytics]

Après la création d’une activité [!DNL Target], vous devez créer une connexion dans [!DNL Customer Journey Analytics]. Si une connexion est déjà configurée, vous pouvez utiliser votre connexion existante et passer à l’étape 4 ci-dessous. La connexion permet à [!DNL Customer Journey Analytics] de commencer à extraire des données du jeu de données pour la création de rapports.

1. Dans [!DNL Customer Journey Analytics], sur la page **[!UICONTROL Connexions]**, cliquez sur **[!UICONTROL Créer une connexion]**.

   ![Création d’un lien de connexion dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configurez vos [paramètres de connexion et de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=fr){target=_blank} avec les informations correctes.
1. Ajoutez le jeu de données d’événement que vous avez utilisé lors de la configuration de votre train de données.
1. Ajoutez le jeu de données de recherche **[!UICONTROL Événements de classification Adobe Target]**, puis cliquez sur **[!UICONTROL Suivant]**.

   ![Boîte de dialogue Ajouter des jeux de données dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configurez votre jeu de données d’événement.

   Pour plus d’informations, voir [Ajout et configuration de jeux de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=fr#add-dataset){target=_blank} dans *Création d’une connexion* dans le *Guide Adobe Customer Journey Analytics*.

1. Configurez votre jeu de données de recherche avec le champ [!UICONTROL Clé] en tant que « key » et le champ de clé correspondant avec le chemin suivant :

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Boîte de dialogue d’événement Classifications d’Adobe Target dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Cliquez sur **[!UICONTROL Ajouter des jeux de données]**, puis cliquez sur **[!UICONTROL Enregistrer]** sur l’écran suivant pour terminer votre connexion.

## Configurer des vues de données

Configurez une vue de données dans [!DNL Customer Journey Analytics]. Une vue de données garantit que les données de votre connexion peuvent être utilisées correctement.

1. Configurez votre vue de données et assurez-vous qu’elle pointe vers la connexion que vous avez créée ci-dessus.

   Pour plus d’informations, voir [Création ou modification d’une vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=fr){target=_blank} dans le *Guide Adobe Customer Journey Analytics*.

1. Pour afficher correctement vos données [!DNL Target] dans [!DNL Customer Journey Analytics], vous devez ajouter les champs suivants de votre jeu de données de recherche en tant que dimensions.

   * Nom de l’expérience
   * Code d’expérience
   * Nom de l’activité
   * ID d’activité

   ![Options Noms et ID dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Terminez la configuration d’autres champs, puis cliquez sur **[!UICONTROL Enregistrer et continuer]** une fois terminé.
