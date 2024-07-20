---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment configurer une activité dans Adobe [!DNL Target] qui utilise Adobe Analytics comme source des rapports (A4T).
title: Comment créer une activité qui utilise A4T ?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 28%

---

# Création d’une activité utilisant Analytics en tant que source de rapports

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source de création de rapports, définissez l’objectif de l’activité, comme l’amélioration des recettes par visiteur (RPV) ou l’augmentation des clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner d’autres mesures à tout moment dans [!DNL Analytics], vous devez tout de même spécifier une mesure particulière que vous prévoyez d’affecter à ce test.

## Création de l’activité

La création d’une activité [!DNL Target] qui utilise [!DNL Analytics] comme source de création de rapports est similaire à la configuration d’une activité [!DNL Target] régulière, avec quelques différences importantes. Par exemple, vous ne pouvez pas sélectionner un segment pour la création de rapports lors de la création de l’activité, car tous les segments disponibles dans [!DNL Analytics] peuvent être appliqués lors de l’affichage d’un rapport.

1. Cliquez sur **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Un nom d’activité ne peut pas inclure le caractère &quot;%&quot; si [!DNL Analytics] est utilisé comme source des rapports.
   >
   >N’utilisez pas le même nom d’activité pour deux activités des [espaces de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) distincts qui utilisent les rapports A4T.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.

   Si vous souhaitez créer une activité [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) pour plus d’informations.

1. Lorsque vous atteignez la partie **[!UICONTROL Settings]** du flux de création de l’activité, sélectionnez **[!UICONTROL Adobe Analytics]** et indiquez votre société.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir n’importe quelle suite de rapports disponible dans [!DNL Analytics]. La suite de rapports définit l’emplacement où les données collectées sont disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste des suites de rapports.

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.

     Vérifiez votre société [!DNL Analytics]. Si votre compte [!DNL Adobe Experience Cloud] est lié à plusieurs [!DNL Analytics] sociétés, déconnectez-vous de [!DNL Target] et connectez-vous à [!DNL Analytics] sous la bonne société. Revenez ensuite à [!DNL Target] et les suites de rapports se chargent.

   * Vous ne voyez pas les suites de rapports attendues.

     Seules les suites de rapports configurées pour se connecter à [!DNL Target] peuvent être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer.

   Si une ou plusieurs suites de rapports sont toujours manquantes dans la liste, [contactez l’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe quelle mesure [!DNL Analytics] disponible dans le sélecteur de mesures [!DNL Analytics].

   >[!NOTE]
   >
   >Vous pouvez envoyer une mesure personnalisée basée sur Target à [!DNL Analytics] plutôt que de vous fier uniquement aux données [!DNL Analytics]. Par exemple, vous pouvez surveiller les clics sur une page, qui n’est généralement pas suivie par [!DNL Analytics]. Cette mesure personnalisée est envoyée automatiquement à [!DNL Analytics] à partir du serveur [!DNL Target] et apparaît comme la mesure &quot;[!DNL Target] Conversion&quot; dans le sélecteur de mesures dans [!DNL Analytics]. La mesure de conversion [!DNL Target] est vide si vous choisissez d’utiliser des mesures [!DNL Analytics].

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >Lors de la configuration d’une activité après avoir configuré [!DNL Analytics] comme source de création de rapports, il n’existe pas d’option pour configurer des audiences pour la création de rapports. [!DNL Analytics] segments sont disponibles dans le rapport [!DNL Target] Activités .

1. Cliquez sur **[!UICONTROL Save]**.

## A4T, affectation automatique et ciblage automatique

Pour plus d’informations, voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
