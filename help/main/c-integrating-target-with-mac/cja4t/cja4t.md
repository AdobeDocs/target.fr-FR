---
keywords: cja4t;analytics du parcours client;analytics du parcours client pour target;source de création de rapports customer parcours analytics;analytics du parcours client comme source de création de rapports pour target
description: Utiliser  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) pour créer des activités basées sur les mesures de conversion d’ [!DNL Customer Journey Analytics]  et sur les segments d’audience. Utiliser les rapports d’ [!DNL Customer Journey Analytics]  pour examiner les résultats.
title: Présentation [!DNL Adobe Customer Journey Analytics] pour [!DNL Target] (CJA4T) ?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: edaf9cfd03cc3ad5104fc9039a1cdb373bd7a6a3
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 19%

---

# [!DNL Adobe Customer Journey Analytics] comme source de création de rapports pour [!DNL Adobe Target] (CJA4T)

[!DNL Customer Journey Analytics for Target] (CJA4T) est une intégration intersolutions qui vous permet de créer des activités basées sur [Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} mesures de conversion et segments d’audience. L’intégration CJA4T vous permet d’utiliser [!DNL Customer Journey Analytics] rapports pour examiner vos résultats. Si vous utilisez [!DNL Customer Journey Analytics] comme source de création de rapports pour une activité, toutes les créations de rapports et segmentations pour cette activité sont basées sur la collecte de données [!DNL Customer Journey Analytics].

## Aperçu

L’intégration d’[!DNL Customer Journey Analytics for Target] entre [!DNL Customer Journey Analytics] et [!DNL Target] fournit des outils puissants d’analyse et de gain de temps destinés à votre programme d’optimisation.

Les trois principaux avantages offerts par l’utilisation des données d’[!DNL Customer Journey Analytics] dans [!DNL Target] sont les suivants :

* Les marketeurs peuvent appliquer dynamiquement les mesures de succès d’[!DNL Customer Journey Analytics] ou les segments de création de rapports aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Une source unique de données réduit la variance qui survient lors de la collecte de données dans deux systèmes distincts.
* Votre [!DNL Customer Journey Analytics] La mise en oeuvre collecte toutes les données requises. Il n’est pas nécessaire d’implémenter des mbox sur les pages dans le seul but de collecter des données pour les rapports.

Tenez compte des points suivants lorsque vous envisagez d’utiliser CJA4T :

* Pour utiliser [!DNL Customer Journey Analytics] en tant que source de création de rapports pour [!DNL Target], vous et votre société devez avoir accès à [!DNL Customer Journey Analytics] et à [!DNL Target]. Si vous avez besoin d’accéder à l’une des solutions, contactez l’administrateur de votre entreprise ou votre gestionnaire de compte.
* Pour créer [!DNL Target] activités avec [!DNL Customer Journey Analytics] création de rapports, vous devez disposer d’un[!UICONTROL Approbateur]&quot; ou &quot;[!UICONTROL Éditeur]rôle &quot; dans [!DNL Target].
   * Si vous avez une [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) compte, voir [Spécification des rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Utilisateurs*.
   * Si vous avez une [Target Premium](/help/main/c-intro/intro.md#premium) compte, voir [Rôles et autorisations](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) in *Autorisations des utilisateurs d’Enterprise*.

* Selon vos paramètres, la création de rapports peut être modifiée par activité ou au niveau de l’organisation. Voir [Solution Reporting Cloud](/help/main/administrating-target/reporting.md#solution) in *Configuration de la création de rapports dans Target*.
* Utilisez une source de création de rapports ou l’autre. Vous ne pouvez pas collecter des données pour une seule activité auprès de plusieurs sources de création de rapports.
* Lorsque vous définissez [!DNL Customer Journey Analytics] en tant que source de création de rapports, vous êtes invité à spécifier l’environnement de test pour la création de rapports. Pendant la configuration, vous ne voyez que les environnements de test auxquels vous avez accès.
* N’importe quel [!DNL Target] les activités continuent d’utiliser [!DNL Target] collecte de données et ne sont pas affectés par l’activation de CJA4T.
* CJA4T n’est disponible que si vous avez [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. La prise en charge du connecteur de données Analytics est prévue pour l’avenir.
* Pour toute question sur le timing, voir [Considérations relatives à la latence](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#latency){target=_blank} in *Questions fréquentes* dans le *Guide d’Adobe Customer Analytics*.

## Types d’activité pris en charge

Les types d’activité suivants sont pris en charge lors de l’utilisation de la variable [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank}:

| Types d’activité | Compatible avec A4T ? |
|--- |--- |
| [Activité A/B avec fractionnement manuel du trafic](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |
| [Activité A/B avec affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [Activité A/B avec ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Non |
| [Ciblage d’expérience (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Oui |
| [Test multivarié (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Oui |
| [Activité d’Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Non |
| [Activité Recommendations](/help/main/c-recommendations/recommendations.md) | Oui |

## Créer une activité qui utilise Customer Journey Analytics comme source de création de rapports

Création d’un [!DNL Target] activité qui utilise [!DNL Customer Journey Analytics] car la source de création de rapports est similaire à la configuration d’une [!DNL Target] activité.

1. Dans la **[!UICONTROL Activités]** liste, cliquez sur [!UICONTROL Créer une activité], puis sélectionnez le type d’activité (en fonction du graphique d’activités pris en charge ci-dessus) et commencez à configurer l’activité.
1. Lorsque vous accédez au **[!UICONTROL Objectifs et paramètres]** page du workflow de création de l’activité en trois parties, sélectionnez **[!DNL Customer Journey Analytics]** comme source des rapports.

   ![Customer Journey Analytics comme option de source de création de rapports](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >La source de création de rapports ne peut pas être modifiée après un événement [!DNL Target] l’activité est activée.

1. Sélectionner un sandbox.

   Vous ne pouvez afficher que les environnements de test auxquels vous avez accès dans cette liste déroulante. Si un ou plusieurs des environnements de test auxquels vous avez accès ne figurent pas dans la liste, vérifiez que vous avez accès à l’environnement de test. Contact [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si vous continuez à voir des problèmes.

   ![Option Sélectionner un environnement de test](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. Vous pouvez choisir l’une des options suivantes : [!DNL Target] mesures de conversion ou utilisez une [!DNL Customer Journey Analytics] mesure.

   ![Utilisation d’une option de mesure de Customer Journey Analytics sous Mesure d’objectif](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

## Configurez une [!DNL Customer Journey Analytics] connection

Après une [!DNL Target] une activité a été créée, vous devez créer une connexion dans [!DNL Customer Journey Analytics]. Si une connexion est déjà configurée, vous pouvez utiliser votre connexion existante et passer à l’étape 4 ci-dessous. La connexion permet [!DNL Customer Journey Analytics] pour commencer à extraire des données du jeu de données pour la création de rapports.

1. Dans [!DNL Customer Journey Analytics], sur le **[!UICONTROL Connexions]** page, cliquez sur **[!UICONTROL Création d’une connexion]**.

   ![Création d’un lien de connexion dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configurez vos [paramètres de connexion et de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} avec les informations correctes.
1. Ajoutez le jeu de données d’événement que vous avez utilisé lors de la configuration de votre flux de données.
1. Ajoutez la variable **[!UICONTROL Événements de classification Adobe Target]** recherchez un jeu de données, puis cliquez sur **[!UICONTROL Suivant]**.

   ![Boîte de dialogue Ajouter des jeux de données dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configurez votre jeu de données d’événement.

   Pour plus d’informations, voir [Ajout et configuration de jeux de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} in *Création d’une connexion* dans le *Guide Adobe Customer Journey Analytics*.

1. Configurez votre jeu de données de recherche avec le champ Clé comme &quot;clé&quot; et le champ Clé correspondante avec le chemin suivant :

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Boîte de dialogue d’événement Classifications Adobe Target dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Cliquez sur **[!UICONTROL Ajout de jeux de données]**, puis cliquez sur **[!UICONTROL Enregistrer]** sur l’écran suivant pour terminer votre connexion.

## Configuration des vues de données

Configurez une vue de données dans [!DNL Customer Journey Analytics]. Une vue de données garantit que les données de votre connexion peuvent être utilisées correctement.

1. Configurez votre vue de données et assurez-vous qu’elle pointe vers la connexion que vous avez créée ci-dessus.

   Pour plus d’informations, voir [Création ou modification d’une vue de données](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} dans le *Guide Adobe Customer Journey Analytics*.

1. Pour afficher correctement vos [!DNL Target] données dans [!DNL Customer Journey Analytics], vous devez ajouter les champs suivants de votre jeu de données de recherche en tant que dimensions :

   * Nom du contenu
   * Code d’expérience
   * Nom de l’activité
   * Code d’activité

   ![Options Noms et ID dans Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Terminez la configuration d’autres champs, puis cliquez sur **[!UICONTROL Enregistrer et continuer]** une fois terminé.
