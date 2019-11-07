---
keywords: a4t, A4T, Analytics en tant que source de reporting pour Target
description: Vous pouvez configurer une activité dans Target Standard/Premium afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).
title: Création de l’activité
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Création de l’activité{#activity-creation}

Vous pouvez configurer une activité dans Target Standard/Premium afin d’utiliser Adobe Analytics en tant que source des rapports (A4T).

Avant de configurer une activité qui utilise Analytics en tant que source de création de rapports, définissez l’objectif de l’activité, par exemple améliorer le chiffre d’affaires par visiteur (RPV) ou augmenter les clics sur votre panier. Sélectionnez une mesure de succès finale de l’activité. Bien que vous puissiez sélectionner des mesures supplémentaires à tout moment dans Analytics, vous devez tout de même indiquer une mesure spécifique qui devrait être affectée par ce test.

La création d’une activité Target Standard qui utilise Analytics en tant que source de création de rapports est similaire à la configuration d’une activité Target Standard classique, avec peu de différences importantes. Par exemple, vous ne pouvez pas sélectionner un segment pour création de rapports tout en créant l’activité car tous les segments disponibles dans Analytics peuvent être appliqués lors de l’affichage d’un rapport.

1. Cliquez sur **[!UICONTROL Créer l’activité]**.

   >[!NOTE]
   >
   >Un nom d’activité ne peut pas inclure le caractère « % » si Analytics est utilisé en tant que source de reporting.

1. Sélectionnez le type d’activité et commencez à configurer l’activité.
1. Lorsque vous êtes dans la section **[!UICONTROL Paramètres]** du flux de création de l’activité, choisissez **[!UICONTROL Adobe Analytics]** et entrez le nom de votre entreprise.
1. Sélectionnez une suite de rapports.

   Vous pouvez choisir toute suite de rapports disponible dans Adobe Analytics. La suite de rapports définit l’emplacement où les données collectées seront disponibles. Les suites de rapports virtuelles ne sont pas incluses dans la liste des suites de rapports..

   Lors de la sélection de la suite de rapports, vous êtes susceptible de rencontrer deux erreurs possibles :

   * Vous obtenez une erreur indiquant qu’aucune suite de rapports n’est disponible mais que votre compte est correctement configuré.
   Vous devez alors vérifier votre société Analytics. Si votre compte Experience Cloud est lié à plusieurs sociétés Analytics, déconnectez-vous de Target et connectez-vous à Analytics sous la société appropriée. Puis, retournez à Target et les suites de rapports se chargent.

   * Vous ne voyez pas les suites de rapports attendues.
   Seules les suites de rapports configurées pour se connecter à Adobe Target pourront être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous connecter à nouveau à Adobe Experience Cloud.

   Si la suite de rapports n’apparaît toujours pas dans la liste, veuillez contacter [l’assistance clientèle](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
1. Spécifiez votre serveur de suivi.

   Consultez [Utilisation d’un serveur de suivi Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Définissez l’expérience.
1. Indiquez l’objectif de l’activité.

   Vous devez sélectionner une mesure de succès à utiliser comme objectif pour chaque test. L’objectif de l’activité est l’activité de conversion qui signale une activité réussie. La bonne pratique consiste à ne jamais exécuter un test sans avoir un objectif d’amélioration d’une manière spécifique. Vous pouvez sélectionner toute mesure Analytics disponible dans le sélecteur de mesure Analytics.

   >[!NOTE]
   >
   >Vous pouvez envoyer une mesure personnalisée basée sur Target à Analytics plutôt que de vous fier uniquement aux données Analytics. Par exemple, vous pouvez surveiller les clics sur une page, surveillance qui n’est habituellement pas effectuée par Analytics. Cette mesure personnalisée est envoyée automatiquement à Analytics depuis le serveur Target et s’affiche en tant que mesure « Conversion cible » dans le sélecteur de mesures d’Analytics. La mesure Conversion cible est vide si vous choisissez d’utiliser des mesures Analytics.

   La définition d’un objectif ne signifie pas que vous ne pouvez pas utiliser une autre mesure lors de l’évaluation des résultats d’un test. L’objectif est, néanmoins, un rappel de l’une des choses que l’activité permet d’améliorer.

   Le visiteur reste dans l’activité après avoir atteint l’objectif. Le visiteur continue à voir le contenu de l’activité mais n’est pas comptabilisé comme une nouvelle entrée d’activité.

   >[!NOTE]
   >
   >Lorsque vous configurez une activité après avoir configuré Analytics en tant que source de reporting, il n’existe pas d’option pour configurer des audiences pour la création de rapports. Les segments Analytics sont disponibles dans le rapport Activités cibles.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

