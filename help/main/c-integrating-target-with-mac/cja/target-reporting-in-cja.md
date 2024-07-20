---
keywords: analytics du parcours client;analytics du parcours client pour target;source de création de rapports customer parcours analytics;analytics du parcours client comme source de création de rapports pour target;création de rapports target dans cja;création de rapports target dans Customer Journey Analytics
description: Utilisez la création de rapports  [!DNL Target] dans  [!DNL Adobe Customer Journey Analytics]  pour créer des activités basées sur les  [!DNL Customer Journey Analytics] mesures de conversion et les segments d’audience et utilisez les  [!DNL Customer Journey Analytics] rapports pour examiner les résultats.
title: Qu’est-ce que la création de rapports  [!DNL Target] dans [!DNL Adobe Customer Journey Analytics] ?
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 5e86d3a95dad291f6c876f126568ba685ff32670
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 58%

---

# [!DNL Target] dans le [!DNL Adobe Customer Journey Analytics]

L’intégration entre [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target] fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation.

Les principaux avantages de l’utilisation de [!DNL Customer Journey Analytics] comme source de création de rapports pour [!DNL Target] sont les suivants :

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de [!DNL Customer Journey Analytics] aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les personnes spécialisées dans le marketing tirent parti des fonctionnalités de [!DNL Customer Journey Analytics], telles que le [panneau Expérimentation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, afin d’analyser plus en détail la personnalisation de votre site web.
* Les spécialistes du marketing disposent d’une source unique de création de rapports pour [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} et [!DNL Target]. Les deux produits de personnalisation peuvent être connectés à [!DNL Customer Journey Analytics] pour une vue plus holistique de votre personnalisation web.

## Considérations

Tenez compte des informations suivantes avant d’utiliser l’intégration [!DNL Customer Journey Analytics] et [!DNL Target] :

>[!IMPORTANT]
>
>Cette intégration n’est pas la même que [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). L’implémentation et les types d’activité pris en charge sont différents. Assurez-vous de lire attentivement cet article avant d’utiliser cette intégration pour vos activités [!DNL Target].

* Pour utiliser [!DNL Customer Journey Analytics] en tant que source de création de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Customer Journey Analytics] et à [!DNL Target]. Si vous avez besoin d’accéder à l’une des solutions, contactez l’administrateur ou l’administratrice de votre entreprise ou la personne chargée de la gestion de votre compte.
* Pour créer des activités [!DNL Target] avec des rapports [!DNL Customer Journey Analytics], vous devez disposer du rôle &quot;[!UICONTROL Approver]&quot; ou &quot;[!UICONTROL Editor]&quot; dans [!DNL Target].
   * Si votre organisation dispose d’un compte [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), voir [Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs et utilisatrices*.
   * Si vous avez un compte [Target Premium](/help/main/c-intro/intro.md#premium), voir [Rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) dans *Autorisations des utilisateurs et utilisatrices d’Enterprise*.

* Vous devez avoir un rôle dans [!DNL Adobe Experience Platform] pour configurer une activité de [!DNL Target] avec [!DNL Customer Journey Analytics] comme source des rapports. Pour plus d’informations, voir [Ajouter un rôle dans [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} dans la section *Configurer des autorisations* du *Tutoriel sur l’architecture et l’ingénierie des données.*
* Selon vos paramètres, la création de rapports peut être modifiée par activité ou au niveau de l’organisation. Voir [Solution de création de rapports dans le cloud](/help/main/administrating-target/reporting.md#solution) dans *Configuration de la création de rapports dans Target*.
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données de plusieurs sources pour une même activité.
* Lorsque vous définissez [!DNL Customer Journey Analytics] en tant que source de création de rapports, il vous est demandé de spécifier le sandbox pour la création de rapports. Pendant la configuration, vous ne voyez que les sandbox auxquels vous avez accès.
* Toutes les activités [!DNL Target] existantes continuent à utiliser la collecte de données [!DNL Target] et ne sont pas affectées par l’activation de cette intégration.
* Pour utiliser cette intégration, la méthode d’implémentation préférée est de faire [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} et [!DNL Target] implémentés par le biais de [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Si [!DNL Adobe Experience Platform Web SDK] n’est actuellement pas implémenté, vous pouvez également créer une [[!DNL Adobe Analytics] connexion source](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) pour importer les données dans [!DNL Adobe Experience Platform]. Si vous prévoyez d’utiliser cette méthode, vous devez sélectionner une suite de rapports [!DNL Analytics] avec l’environnement de test [!DNL Adobe Experience Platform] que vous utilisez avec [!DNL Customer Journey Analytics].

  ![Option Sandbox dans la boîte de dialogue Paramètres de création de rapports](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >Si vous utilisez une connexion source [!DNL Adobe Analytics], vous aurez des rapports dans [!DNL Adobe Analytics] et [!DNL Customer Journey Analytics]. Cependant, en raison de la différence d’algorithmes entre ces deux solutions, les résultats risquent de ne pas correspondre.

* Pour toute question sur le timing, référez-vous aux [Considérations relatives à la latence](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} dans la section *Questions fréquentes* du Guide *[!DNL Adobe Customer Analytics]*.

## Types d’activité pris en charge {#supported-activities}

Les types d’activité suivants sont pris en charge lors de l’utilisation du [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} ou de la bibliothèque JavaScript [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} :

| Types d’activités | Pris en charge ? |
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

>[!TIP]
>
>Vous pouvez également indiquer que [!DNL Target] utilise la création de rapports dans [!DNL Customer Journey Analytics] pour toutes les activités créées dans votre compte (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]** > **[!UICONTROL Reporting Experience Cloud Solution]**). Pour plus d’informations, voir *Solution de cloud de création de rapports* dans [Configuration de la création de rapports dans [!DNL Target]](/help/main/administrating-target/reporting.md#solution).

1. Dans la liste **[!UICONTROL Activities]**, cliquez sur **[!UICONTROL Create Activity]**, puis sélectionnez le type d’activité (en fonction du [ graphique d’activités pris en charge au-dessus de ](#supported-activities)) et commencez à configurer l’activité.
1. Lorsque vous accédez à la page **[!UICONTROL Goals & Settings]** du workflow de création d’activité en trois parties, sélectionnez **[!DNL Customer Journey Analytics]** comme source de création de rapports.

   ![Customer Journey Analytics comme option de source de création de rapports](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La source de création de rapports ne peut pas être modifiée après l’activation d’une activité [!DNL Target].

1. Sélectionner un sandbox.

   Vous ne voyez que les environnements de test auxquels vous avez accès dans cette liste déroulante. Si un ou plusieurs sandbox auxquels vous avez accès ne figurent pas dans la liste, vérifiez que vous y avez accès. Contactez l’[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si vous continuez à voir des problèmes.

   ![Option Sélectionner un sandbox](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. Indiquez l’objectif de l’activité.

   Sélectionnez une mesure de succès à utiliser comme objectif pour chaque activité. Vous pouvez choisir l’une des options suivantes : mesures de conversion [!DNL Target] ou utiliser une mesure [!DNL Customer Journey Analytics].

   ![Utilisation d’une option de mesure de Customer Journey Analytics sous Mesure d’objectif](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. Cliquez sur **[!UICONTROL Save & Close]**.

## Configurer une connexion [!DNL Customer Journey Analytics]

Après la création d’une activité [!DNL Target], vous devez créer une connexion dans [!DNL Customer Journey Analytics]. Si une connexion est déjà configurée, vous pouvez utiliser votre connexion existante et passer à l’étape 4 ci-dessous. La connexion permet à [!DNL Customer Journey Analytics] de commencer à extraire des données du jeu de données pour la création de rapports.

1. Dans [!DNL Customer Journey Analytics], sur la page **[!UICONTROL Connections]**, cliquez sur **[!UICONTROL Create a new connection]**.

   ![Créer un lien de connexion dans [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. Configurez vos [paramètres de connexion et de données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank} avec les informations correctes.
1. Ajoutez le jeu de données d’événement que vous avez utilisé lors de la configuration de votre train de données.
1. Ajoutez le jeu de données de recherche **[!UICONTROL Adobe Target Classification Events]**, puis cliquez sur **[!UICONTROL Next]**.

   ![Boîte de dialogue Ajouter des jeux de données dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. Configurez votre jeu de données d’événement.

   Pour plus d’informations, voir [Ajout et configuration de jeux de données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} dans *Création d’une connexion* dans le *[!DNL Adobe Customer Journey Analytics]Guide*.

1. Configurez votre jeu de données de recherche avec le champ [!UICONTROL Key] comme &quot;clé&quot; et le champ de clé [!UICONTROL Matching] avec le chemin suivant :

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Boîte de dialogue d’événement Classifications d’Adobe Target dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. Cliquez sur **[!UICONTROL Add datasets]**, puis sur **[!UICONTROL Save]** dans l’écran suivant pour terminer votre connexion.

## Configurer des vues de données

Configurez une vue de données dans [!DNL Customer Journey Analytics]. Une vue de données garantit que les données de votre connexion peuvent être utilisées correctement.

1. Configurez votre vue de données et assurez-vous qu’elle pointe vers la connexion que vous avez créée ci-dessus.

   Pour plus d’informations, voir [Création ou modification d’une vue de données](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} dans le *[!DNL Adobe Customer Journey Analytics]Guide*.

1. Pour afficher correctement vos données [!DNL Target] dans [!DNL Customer Journey Analytics], vous devez ajouter les champs suivants de votre jeu de données de recherche en tant que dimensions.

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Options Noms et ID dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Pour utiliser des dimensions [!DNL Target] dans le panneau [!UICONTROL Experimentation], configurez les étiquettes contextuelles suivantes :

   * Pour [!UICONTROL Activity Name], utilisez &quot;Expérience&quot;.
   * [!UICONTROL Experience Name], utilisez &quot;Variante d’expérience&quot;.

   ![Libellés de contexte dans le panneau Expérimentation](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. Terminez la configuration d&#39;autres champs, puis cliquez sur **[!UICONTROL Save and continue]** lorsque vous avez terminé.
