---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment configurer une activité dans Adobe Target qui utilise Adobe Analytics comme source de rapports (A4T).
title: Comment créer une Activité qui utilise A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 33%

---


# Création d’une activité qui utilise Analytics en tant que source du rapports

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source de rapports (A4T).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source de rapports, définissez l’objectif de l’activité, par exemple améliorer les recettes par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner d&#39;autres mesures à tout moment dans [!DNL Analytics], vous devez tout de même spécifier une mesure particulière que vous prévoyez que ce test affectera.

## Créez l’activité

La création d&#39;une activité [!DNL Target] qui utilise [!DNL Analytics] comme source de rapports est similaire à la configuration d&#39;une activité [!DNL Target] régulière, avec quelques différences importantes. Par exemple, vous ne pouvez pas sélectionner un segment pour le rapports lors de la création de l&#39;activité, car tous les segments disponibles dans [!DNL Analytics] peuvent être appliqués lors de l&#39;affichage d&#39;un rapport.

1. Cliquez sur **[!UICONTROL Créer l’activité]**.

   >[!NOTE]
   >
   >Un nom d&#39;activité ne peut pas inclure le caractère &quot;%&quot; si [!DNL Analytics] est utilisé comme source de rapports.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.

   Si vous souhaitez créer une activité [!UICONTROL Affectation automatique] ou [!UICONTROL Cible automatique], voir [Prise en charge d’A4T pour l’affectation automatique et les activités de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) pour plus d’informations.

1. Lorsque vous êtes dans la section **[!UICONTROL Paramètres]** du flux de création de l’activité, choisissez **[!UICONTROL Adobe Analytics]** et entrez le nom de votre entreprise.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir toute suite de rapports disponible dans [!DNL Analytics]. La suite de rapports définit l’emplacement où les données collectées sont disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste de suites de rapports.

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.

      Vérifiez votre société [!DNL Analytics]. Si votre compte [!DNL Adobe Experience Cloud] est lié à plusieurs sociétés [!DNL Analytics], déconnectez-vous de [!DNL Target] et connectez-vous à [!DNL Analytics] sous la société appropriée. Revenez ensuite à [!DNL Target] et les suites de rapports se chargent.

   * Vous ne voyez pas les suites de rapports attendues.

      Seules les suites de rapports configurées pour se connecter à [!DNL Target] peuvent être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d&#39;abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer.
   Si une ou plusieurs suites de rapports sont toujours manquantes dans la liste, [contactez le service à la clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de réussite à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe quelle mesure [!DNL Analytics] disponible dans le sélecteur de mesures [!DNL Analytics].

   >[!NOTE]
   >
   >Vous pouvez envoyer une mesure personnalisée basée sur une Cible à [!DNL Analytics] au lieu de vous reposer uniquement sur les données [!DNL Analytics]. Par exemple, vous pouvez surveiller le fait de cliquer sur une page, qui n&#39;est généralement pas suivie par [!DNL Analytics]. Cette mesure personnalisée est envoyée automatiquement à [!DNL Analytics] à partir du serveur [!DNL Target] et s’affiche sous la forme de la mesure &quot;[!DNL Target] Conversion&quot; dans le sélecteur de mesures de [!DNL Analytics]. La mesure de conversion [!DNL Target] est vide si vous choisissez d’utiliser des mesures [!DNL Analytics].

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >Lors de la configuration d&#39;une activité après avoir configuré [!DNL Analytics] comme source de rapports, il n&#39;existe aucune option pour configurer des audiences pour le rapports. [!DNL Analytics] sont disponibles dans le rapport  [!DNL Target] Activités.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## A4T et activités d’affectation automatique et de Cible automatique

Pour plus d’informations, voir [Prise en charge d’A4T pour l’affectation automatique et les activités d’Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).