---
keywords: paramètres d’activité;objectifs et paramètres;multivarié;mvt
description: Découvrez comment utiliser la page Objectifs et paramètres dans Adobe [!DNL Target] pour spécifier des informations sur les objectifs d’une activité de test multivarié (MVT).
title: Comment spécifier les objectifs et les paramètres dans une activité de test multivarié (MVT) ?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 91%

---

# Objectifs et paramètres (tests multivariés)

La page Objectifs et paramètres d’Adobe Target vous permet de saisir des informations sur les objectifs de votre [!UICONTROL Multivariate] Tests (MVT).

* Paramètres d’activité
* Paramètres de création de rapports
* Autres métadonnées

Les paramètres disponibles dépendent si vous utilisez Target ou Analytics en tant que source de données.

![](assets/mvt_settings.png)

## Paramètres d’activité  {#section_DCBDC354261F420EBD4B43EA34947BAC}

Les méthodes suivantes sont disponibles :

### Intention

Saisissez une intention facultative. L’intention peut être toute information qui vous aide et aide les membres de l’équipe à identifier la campagne.

### Priorité

En fonction de vos paramètres, l’interface utilisateur et les options pour Priorité peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

Si cette option n’est pas activée dans S[!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : Faible, Moyen ou Élevé.

Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez l’option Activer les priorités affinées .

Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :

* 0 = Faible
* 999 = Élevé

Pour les activités créées dans les anciennes versions de Target Standard/Premium, la priorité Faible correspond à 0, Moyen à 5 et Élevé à 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10.

### Durée

L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le.

## Paramètres de création de rapports {#section_13119392051044FBA6387D9B3B1C43CF}

Les méthodes suivantes sont disponibles :

### Solution de création de rapports

Indiquez si les données sont collectées depuis Adobe Target ou Adobe Analytics. Voir [Adobe Analytics en tant que source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune.

Lors de la sélection d’Analytics en tant que source de création de rapports pour Target, vous sélectionnez une suite de rapports Analytics pour recevoir les données d’activité Target. Pour ce faire, faites d’abord votre choix parmi les sociétés Analytics auxquelles votre compte est lié, puis sélectionnez la suite de rapports adaptée à l’activité. Seules les suites de rapports configurées pour se connecter à Adobe Target pourront être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous connecter à nouveau à Adobe Experience Cloud. Si la suite de rapports n’apparaît toujours pas dans la liste, veuillez contacter l’assistance clientèle.

Analytics for Target requiert un serveur de suivi pour consigner les résultats de manière appropriée. Un serveur de suivi par défaut apparaîtra dans le champ Serveur de suivi. Si vous utilisez plus d’un serveur de suivi, vous devriez vérifier afin de vous assurer d’avoir ajouté le serveur de suivi approprié dans ce champ. Pour plus d’informations, voir [Utiliser un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)

Si une solution de création de rapports est spécifiée dans les paramètres de votre compte, la solution spécifiée est utilisée et ce paramètre n’est pas visible.

>[!NOTE]
>
>Afin de préserver la cohérence des rapports, la source de reporting ne peut plus être modifiée une fois l’activité mise en ligne.

### Objectif

Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, sélectionnez la mesure Conversion, puis définissez les paramètres qui déterminent le moment où le succès est obtenu.

>[!NOTE]
>
>Si la solution de compte rendu des performances est définie sur Analytics, la seule mesure d’objectif disponible est Conversion. Les mesures d’Analytics ne peuvent pas être sélectionnées en tant qu’objectif.

Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.

S’il est activé, le champ Valeur estimée de la conversion (indisponible pour les mesures Note de page) fournit une valeur pour votre objectif (mais pas pour les autres mesures). Cette valeur permet à Target de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes (Recettes par visiteur, Valeur de commande moyenne, Total ventes et Commandes), l’estimation utilise la mesure Recettes par visiteur. Les données sont de type devise.

Après avoir atteint l’objectif de l’activité, un visiteur continue à voir le contenu de l’activité sauf si le visiteur est admissible pour une activité de priorité plus élevée. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Notez que c’est différent du comportement par défaut dans Target Classic qui comptabilise les visiteurs en tant que nouveaux si ces derniers visualisent à nouveau le test.

### Mesures supplémentaires

Créez des mesures de succès supplémentaires.

Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur Analytics. Dans ce cas, les mesures définies pour la suite de rapports Analytics s’appliquent.

Audiences pour les rapports

### Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement les informations sur des audiences spécifiques.

## Paramètres avancés  {#section_E2FE441AFB324E498793ABB025ED9974}

Les paramètres avancés sont disponibles pour les mesures d’objectif Test multivarié.

![Menu Paramètres avancés](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Si vous utilisez Adobe Analytics en tant que source de compte rendu des performances, les paramètres sont gérés par le serveur Analytics. L’option Paramètres avancés n’est pas disponible.

### Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ?

Utilisez cette option pour comptabiliser uniquement une personne comme atteignant la mesure de succès si elle a déjà atteint une autre mesure de succès. Par exemple, une conversion de test peut être valide uniquement si le visiteur clique sur l’offre ou atteint une page spécifique avant la conversion.

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.

Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.

L’option Ajouter une dépendance permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après l’ajout de mesures supplémentaires, cliquez sur **[!UICONTROL Paramètres avancés]**.
2. Cliquez sur l’option Ajouter une dépendance :

   ![Ajouter une dépendance](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur **[!UICONTROL Atteinte]** pour passer du paramètre Atteinte au paramètre Non atteinte .

   ![Dépendance atteinte](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

### Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?

Trois options sont disponibles :

* Sélectionnez Incrémenter le décompte et laisser l’utilisateur dans l’activité pour spécifier comment le décompte est incrémenté.
* Sélectionnez Incrémenter le décompte, libérer l’utilisateur et autoriser le retour pour spécifier quelle expérience affiche l’utilisateur s’il rentre dans l’activité.
* Sélectionnez Incrémenter le décompte, libérer l’utilisateur et bloquer le retour pour spécifier ce qu’affiche l’utilisateur à la place du contenu de l’activité.

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

Les paramètres suivants sont disponibles :

### Remarques

Entrez des informations sur l’activité qui soient utiles pour vous et d’autres membres de l’équipe. Le volet Notes peut être redimensionné.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Paramètres d’activité (3:02) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Création de tests multivariés (9:25) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer un test multivarié à l’aide du processus assisté Target à trois étapes. Les objectifs et les paramètres sont abordés à partir de 7:00.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395)
