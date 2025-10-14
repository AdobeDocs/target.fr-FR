---
keywords: customer parcours analytics;customer parcours analytics for target;source de création de rapports customer parcours analytics;customer parcours analytics comme source de création de rapports pour target;création de rapports target dans cja; création de rapports target dans Customer Journey Analytics
description: Utilisez  [!DNL Target]  rapports dans  [!DNL Adobe Customer Journey Analytics]  pour créer des activités basées sur les mesures  [!DNL Customer Journey Analytics]  conversion et les segments d’audience, et utilisez  [!DNL Customer Journey Analytics]  rapports pour examiner les résultats.
title: En quoi consistent  [!DNL Target]  rapports  [!DNL Adobe Customer Journey Analytics] ?
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 05a4358e0115d7bfd13ec715a0e7eb96f1f2265b
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 41%

---

# [!DNL Target] de rapports dans [!DNL Adobe Customer Journey Analytics]

L’intégration entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target] fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation.

Les principaux avantages de l’utilisation de [!DNL Customer Journey Analytics] comme source de création de rapports pour [!DNL Target] sont les suivants :

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de [!DNL Customer Journey Analytics] aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les marketeurs peuvent tirer parti de [!DNL Customer Journey Analytics] fonctionnalités, telles que le [Panneau d’expérimentation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank} pour analyser plus en détail la personnalisation de leur site web.
* Les marketeurs peuvent avoir une seule source de création de rapports pour [!DNL Adobe Journey Optimizer] et [!DNL Target]. Les deux produits de personnalisation peuvent être connectés à [!DNL Customer Journey Analytics] pour une vue plus holistique de votre personnalisation web.

## Considérations

Tenez compte des informations suivantes avant d’utiliser l’intégration [!DNL Customer Journey Analytics] et [!DNL Target] :

>[!IMPORTANT]
>
>Cette intégration n’est pas identique à [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). L’implémentation et les types d’activité pris en charge sont différents. Assurez-vous d’avoir lu attentivement cet article avant d’utiliser cette intégration pour vos activités [!DNL Target].

* Pour utiliser [!DNL Customer Journey Analytics] en tant que source de création de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Customer Journey Analytics] et à [!DNL Target]. Si vous avez besoin d’accéder à l’une des solutions, contactez l’administrateur ou l’administratrice de votre entreprise ou la personne chargée de la gestion de votre compte.
* Pour créer des activités [!DNL Target] avec des rapports [!DNL Customer Journey Analytics], vous devez disposer du rôle « [!UICONTROL Approver] » ou « [!UICONTROL Editor] » dans [!DNL Target].
   * Si votre organisation dispose d’un compte [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), voir [Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs et utilisatrices*.
   * Si vous avez un compte [Target Premium](/help/main/c-intro/intro.md#premium), voir [Rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) dans *Autorisations des utilisateurs et utilisatrices d’Enterprise*.

* Faire partie d’un rôle dans la [!DNL Adobe Experience Platform] de configurer une activité de [!DNL Target] avec [!DNL Customer Journey Analytics] comme source de création de rapports. Pour plus d’informations, voir [Ajouter un rôle dans [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/fr/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} dans *Configurer les autorisations* dans le tutoriel *Architecte et ingénieur de données.*
* Selon vos paramètres, la création de rapports peut être modifiée par activité ou au niveau de l’organisation. Voir [Solution de création de rapports dans le cloud](/help/main/administrating-target/reporting.md#solution) dans *Configuration de la création de rapports dans Target*.
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter de données de plusieurs sources pour une même activité.
* Lorsque vous définissez [!DNL Customer Journey Analytics] en tant que source de création de rapports, il vous est demandé de spécifier le sandbox pour la création de rapports. Pendant la configuration, vous ne voyez que les sandbox auxquels vous avez accès.
* Toutes les activités [!DNL Target] existantes continuent à utiliser la collecte de données [!DNL Target] et ne sont pas affectées par l’activation de cette intégration.
* Pour utiliser cette intégration, la méthode de mise en œuvre préférée consiste à [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/fr/docs/experience-platform){target=_blank} et [!DNL Target] mises en œuvre par le biais de l’[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} .

  Si le [!DNL Adobe Experience Platform Web SDK] n’est pas actuellement implémenté, vous pouvez également créer une [[!DNL Adobe Analytics] connexion source](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) pour importer les données dans [!DNL Adobe Experience Platform]. Si vous envisagez d’utiliser cette méthode, vous devez sélectionner une suite de rapports [!DNL Analytics] avec le sandbox [!DNL Adobe Experience Platform] que vous utilisez avec [!DNL Customer Journey Analytics].

  ![Option Sandbox dans la boîte de dialogue Paramètres des rapports](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >Si vous utilisez une connexion source [!DNL Adobe Analytics], vous disposez de rapports dans [!DNL Adobe Analytics] et [!DNL Customer Journey Analytics]. Cependant, en raison d’algorithmes différents entre ces deux solutions, il est peu probable que les résultats correspondent.

* Pour toute question sur le minutage, consultez [Considérations relatives à la latence](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} dans *Questions fréquentes* dans le guide de *[!DNL Adobe Customer Analytics]-réseau*.

## Types d’activité pris en charge {#supported-activities}

Les types d&#39;activités suivants sont pris en charge lors de l&#39;utilisation de la bibliothèque JavaScript [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} ou [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} :

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
>Vous pouvez également indiquer que [!DNL Target] utilise les rapports dans [!DNL Customer Journey Analytics] pour toutes les activités créées dans votre compte (**[!UICONTROL Administration]** > **[!UICONTROL Reporting]** > **[!UICONTROL Reporting Experience Cloud Solution]**). Pour plus d’informations, voir *Solution cloud de création de rapports* dans [Configuration des rapports dans [!DNL Target]](/help/main/administrating-target/reporting.md#solution).

1. Dans la liste **[!UICONTROL Activities]**, cliquez sur **[!UICONTROL Create Activity]**, puis sélectionnez le type d’activité (selon le [graphique d’activité pris en charge ci-dessus](#supported-activities)) et commencez à configurer l’activité.
1. Lorsque vous accédez à la page **[!UICONTROL Goals & Settings]** du workflow de création d’activités en trois parties, sélectionnez **[!DNL Customer Journey Analytics]** comme source de création de rapports.

   ![Customer Journey Analytics comme option de source de création de rapports](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La source de création de rapports ne peut pas être modifiée après l’activation d’une activité [!DNL Target].

1. Sélectionner un sandbox.

   Seules les sandbox auxquelles vous avez accès apparaissent dans cette liste déroulante. Si un ou plusieurs sandbox auxquels vous avez accès ne figurent pas dans la liste, vérifiez que vous y avez accès. Contactez l’[Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si vous continuez à voir des problèmes.

   ![Option Sélectionner un sandbox](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. Indiquez l’objectif de l’activité.

   Sélectionnez une mesure de succès à utiliser comme objectif pour chaque activité. Vous pouvez choisir l’une des options suivantes : mesures de conversion [!DNL Target] ou utiliser une mesure [!DNL Customer Journey Analytics].

   ![Utilisation d’une option de mesure de Customer Journey Analytics sous Mesure d’objectif](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. Cliquez sur **[!UICONTROL Save & Close]**.

## Configurer une connexion [!DNL Customer Journey Analytics]

Après la création d’une activité [!DNL Target], vous devez créer une connexion dans [!DNL Customer Journey Analytics]. Si une connexion est déjà configurée, vous pouvez utiliser votre connexion existante et passer à l’étape 4 ci-dessous. La connexion permet à [!DNL Customer Journey Analytics] de commencer à extraire des données du jeu de données pour la création de rapports.

1. Dans [!DNL Customer Journey Analytics], sur la page **[!UICONTROL Connections]**, cliquez sur **[!UICONTROL Create a new connection]**.

   ![Créer un lien de connexion dans [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. Configurez vos [paramètres de connexion et de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/overview){target=_blank} avec les informations appropriées.
1. Ajoutez le jeu de données d’événement que vous avez utilisé lors de la configuration de votre train de données.
1. Ajoutez le jeu de données de recherche **[!UICONTROL Adobe Target Classification Events]**, puis cliquez sur **[!UICONTROL Next]**.

   ![Boîte de dialogue Ajouter des jeux de données dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. Configurez votre jeu de données d’événement.

   Pour plus d’informations, voir [Ajouter et configurer des jeux de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} dans *Créer une connexion* dans le guide de *[!DNL Adobe Customer Journey Analytics].*

1. Configurez votre jeu de données de recherche avec le champ [!UICONTROL Key] comme « clé » et le champ clé [!UICONTROL Matching] comme suit :

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Boîte de dialogue d’événement Classifications d’Adobe Target dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. Cliquez sur **[!UICONTROL Add datasets]**, puis sur **[!UICONTROL Save]** dans l’écran suivant pour terminer la connexion.

## Configurer des vues de données

Configurez une vue de données dans [!DNL Customer Journey Analytics]. Une vue de données garantit que les données de votre connexion peuvent être utilisées correctement.

1. Configurez votre vue de données et assurez-vous qu’elle pointe vers la connexion que vous avez créée ci-dessus.

   Pour plus d’informations, voir [Création ou modification d’une vue de données](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} dans le guide de *[!DNL Adobe Customer Journey Analytics].*

1. Pour afficher correctement vos données [!DNL Target] dans [!DNL Customer Journey Analytics], vous devez ajouter les champs suivants de votre jeu de données de recherche en tant que dimensions.

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Options Noms et ID dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Pour utiliser [!DNL Target] dimensions dans le panneau [!UICONTROL Experimentation], configurez les libellés de contexte suivants :

   * Par [!UICONTROL Activity Name], utilisez « Expérience d’expérimentation ».
   * [!UICONTROL Experience Name], utilisez « Variante d’expérience ».

   ![Libellés de contexte dans le panneau Expérimentation](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. Terminez de configurer d’autres champs, puis cliquez sur **[!UICONTROL Save and continue]** lorsque vous avez terminé.

## Créer et afficher des rapports d’activité dans [!DNL Customer Journey Analytics]

Une fois la configuration terminée, [!DNL Customer Journey Analytics] via le [!DNL Adobe Experience Cloud] ou l&#39;onglet [!UICONTROL Reports] de l&#39;activité dans [!DNL Target].

L’onglet Rapports comporte un lien **[!UICONTROL View in Customer Journey Analytics]**. Actuellement, ce lien vous redirige vers la page de destination d’accueil [!DNL Customer Journey Analytics].

![Lien de création de rapports CJA](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>Cette intégration n’est pas identique à [!UICONTROL Adobe Analytics for Target] (A4T).
>
>* L’intégration [!DNL Target]/[!DNL Customer Journey Analytics] n’inclut pas de rapport préconfiguré tel qu’A4T. Les rapports d’activité doivent être créés dans [!DNL Customer Journey Analytics].
>
>* Si [!UICONTROL Use a CJA Metric] que la mesure d’objectif de l’activité est sélectionnée, cette option permet de déterminer le moment où des mesures de succès spécifiques doivent être définies. La mesure de succès est sélectionnée lors de la configuration du panneau [!UICONTROL Experimentation]. L’effet élévateur et le degré de confiance sont calculés à partir de la mesure CJA sélectionnée.

1. Dans [!DNL Customer Journey Analytics], créez un panneau Expérimentation , puis sélectionnez l’activité dans le menu déroulant **[!UICONTROL Experiment]**.

   Pour plus d’informations, voir [Panneau Expérimentation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank} sous *Panneau Expérimentation* dans le guide d’*[!DNL Customer Journey Analytics]*.

   ![Panneau Expérimentation dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >Si l’activité n’apparaît pas dans la liste déroulante [!UICONTROL Experiment], vérifiez que la vue de données appropriée est sélectionnée et que les dimensions [!DNL Target] incluent les libellés de contexte requis (voir l’étape 3 de la section [Configurer des vues de données](https://experienceleague.adobe.com/fr/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}).

1. Cliquez sur **[!UICONTROL Build]**.

   Le panneau [!UICONTROL Experimentation] renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les performances de vos expériences. Pour plus d’informations, voir [[!UICONTROL Panel output]](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank} sous *Panneau Expérimentation* dans le guide d’*[!DNL Customer Journey Analytics]*.

   ![&#x200B; Expérimentation &#x200B;](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)