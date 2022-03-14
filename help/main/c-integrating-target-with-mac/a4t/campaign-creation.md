---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Découvrez comment configurer une activité dans Adobe [!DNL Target] qui utilise Adobe Analytics comme source des rapports (A4T).
title: Comment créer une activité qui utilise A4T ?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 36%

---

# Création d’une activité utilisant Analytics en tant que source de rapports

Vous pouvez configurer une activité dans [!DNL Adobe Target] pour utiliser [!DNL Adobe Analytics] comme source des rapports (A4T).

Avant de configurer une activité qui utilise [!DNL Analytics] comme source des rapports, définissez l’objectif de l’activité, par exemple améliorer les recettes par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner d’autres mesures à tout moment dans [!DNL Analytics], vous devez toujours spécifier une mesure spécifique que ce test doit affecter.

## Créez l’activité

Création d’un [!DNL Target] activité utilisant [!DNL Analytics] car la source de création de rapports est similaire à la configuration d’une [!DNL Target] avec quelques différences importantes. Par exemple, vous ne pouvez pas sélectionner un segment pour la création de rapports lors de la création de l’activité, car tous les segments disponibles dans [!DNL Analytics] peut être appliqué lors de l’affichage d’un rapport.

1. Cliquez sur **[!UICONTROL Créer l’activité]**.

   >[!NOTE]
   >
   >Un nom d’activité ne peut pas inclure le caractère &quot;%&quot; si [!DNL Analytics] est utilisée comme source de création de rapports.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.

   Si vous souhaitez créer une [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique] activité, voir [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) pour plus d’informations.

1. Lorsque vous êtes dans la section **[!UICONTROL Paramètres]** du flux de création de l’activité, choisissez **[!UICONTROL Adobe Analytics]** et entrez le nom de votre entreprise.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir toute suite de rapports disponible dans [!DNL Analytics]. La suite de rapports définit l’emplacement où les données collectées sont disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste des suites de rapports.

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.

      Vérifiez vos [!DNL Analytics] société. Si votre [!DNL Adobe Experience Cloud] compte est lié à plusieurs [!DNL Analytics] société, déconnectez-vous de [!DNL Target]et connectez-vous à [!DNL Analytics] sous la bonne société. Ensuite, revenez à [!DNL Target]et les suites de rapports se chargent.

   * Vous ne voyez pas les suites de rapports attendues.

      Seules les suites de rapports configurées pour se connecter à [!DNL Target] sont disponibles pour sélection. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer.
   Si une ou plusieurs suites de rapports sont toujours manquantes dans la liste, veuillez [Contacter l’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque activité. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez choisir n’importe lequel [!DNL Analytics] mesure disponible dans la variable [!DNL Analytics] sélecteur de mesures.

   >[!NOTE]
   >
   >Vous pouvez envoyer une mesure personnalisée basée sur Target à [!DNL Analytics] plutôt que de ne compter que sur [!DNL Analytics] data. Vous pouvez, par exemple, surveiller les clics sur une page, qui n’est généralement pas suivie par [!DNL Analytics]. Cette mesure personnalisée est envoyée à [!DNL Analytics] automatiquement à partir du [!DNL Target] et s’affiche sous la forme du[!DNL Target] Mesure &quot;Conversion&quot; dans le sélecteur de mesures dans [!DNL Analytics]. Le [!DNL Target] La mesure de conversion est vide si vous choisissez d’utiliser [!DNL Analytics] mesures.

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >Lors de la configuration d’une activité après la configuration [!DNL Analytics] en tant que source de création de rapports, il n’existe pas d’option pour configurer des audiences pour la création de rapports. [!DNL Analytics] sont disponibles dans la variable [!DNL Target] Rapport Activités .

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## A4T et activités d’affectation automatique et de ciblage automatique

Pour plus d’informations, consultez [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
