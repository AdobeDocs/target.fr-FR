---
keywords: ciblage automatique;ciblage;affectation de trafic;questions fréquentes;faq;résolution de problèmes;dépannage;trafic
description: Consultez les rubriques de dépannage et les questions fréquentes sur les activités de ciblage automatique dans Adobe Target.
title: Comment résoudre les problèmes liés aux activités de ciblage automatique ?
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1919'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Résolution des problèmes de ciblage automatique et questions fréquentes

Résolution des problèmes de [!UICONTROL ciblage automatique] dans [!DNL Adobe Target] et questions fréquentes.

## Questions fréquentes sur le ciblage automatique {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consultez les FAQ et les réponses suivantes lorsque vous effectuez des activités de [!UICONTROL ciblage automatique] :

### Quelles sont les bonnes pratiques pour configurer une activité de [!UICONTROL ciblage automatique] ?

* Décidez si la valeur commerciale d’une mesure de succès fondée sur le revenu par visite (RPV) bénéficie des exigences de trafic supplémentaires. Le RPV nécessite généralement au moins 1 000 conversions par expérience pour qu’une activité soit plus performante qu’une conversion.
* Décidez l’affectation ente l’expérience de contrôle et l’expérience personnalisée avant de débuter l’activité d’après vos objectifs.
* Déterminez si vous disposez d’un trafic suffisant sur la page où votre activité de [!UICONTROL ciblage automatique] doit être exécutée pour que les modèles de personnalisation soient créés dans un laps de temps raisonnable.
   * Si vous testez l’algorithme de personnalisation, vous ne devriez pas modifier les expériences ni ajouter ou supprimer des attributs de profil alors que l’activité est active.

* Envisagez d’exécuter une activité A/B entre les offres et les lieux que vous prévoyez d’utiliser dans votre activité de [!UICONTROL ciblage automatique], afin d’assurer que les lieu(x) et offres ont une incidence sur l’objectif d’optimisation. Si une activité A/B ne met pas en évidence de différence significative, il est probable que le [!UICONTROL ciblage automatique] ne parviendra pas non plus à générer un effet élévateur.

   * Si un test A/B ne montre aucune différence statistiquement significative entre des expériences, il est probable que les offres considérées ne sont pas suffisamment différentes les unes des autres, que les emplacements sélectionnés n’influencent pas la mesure de succès, ou que l’objectif d’optimisation soit trop distant dans l’entonnoir de conversion pour être affecté par les offres que vous avez choisies.

* Essayez de ne pas modifier sensiblement l’expérience durant le déroulement de l’activité.

### Recommandez-vous d’utiliser le [!UICONTROL ciblage automatique] avec une répartition de 90 % en contrôle et de 10 % en ciblé jusqu’à ce que les modèles soient créés ?

La répartition optimale de l’affectation du trafic dépend de vos objectifs.

Si vous souhaitez personnaliser le plus de trafic possible, vous pouvez vous en tenir à 90 % en ciblé et à 10 % en contrôle pendant toute la durée de vie de l’activité. Si votre but est d’exécuter une expérience en comparant les performances des algorithmes personnalisés par rapport au contrôle, une répartition 50/50 est préférable pour la durée de vie de l’activité.

Il est recommandé de conserver la répartition de l’affectation du trafic pendant toute la durée de vie de l’activité afin que les visiteurs ne basculent pas entre les expériences ciblées et les expériences de contrôle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

### Si un visiteur NE voit PAS l’activité de [!UICONTROL ciblage automatique] et effectue une conversion, celle-ci est-elle prise en compte dans mon activité ?

Non, seuls les visiteurs éligibles ayant visualisé l’activité de [!UICONTROL ciblage automatique] sont comptabilisés dans les rapports.

### Mon activité de [!UICONTROL ciblage automatique] ne semble générer aucun effet élévateur. Que se passe-t-il ?

Quatre facteurs sont requis pour qu’une activité de [!UICONTROL ciblage automatique] génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications.

Si le résultat du test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

### Quand dois-je arrêter mon activité de [!UICONTROL ciblage automatique] ?

Le [!UICONTROL ciblage automatique] peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’est pas nécessaire d’arrêter votre activité de [!UICONTROL ciblage automatique].

Si vous souhaitez apporter des modifications substantielles au contenu de votre activité de [!UICONTROL ciblage automatique], la bonne pratique consiste à démarrer une nouvelle activité, afin que les autres utilisateurs qui visualisent les rapports n’en confondent pas les résultats, ou ne les associent pas à d’anciens résultats portant sur des contenus différents.

### Combien de temps dois-je attendre la compilation des modèles ? {#how-long}

Le délai nécessaire aux modèles pour créer votre activité de [!UICONTROL ciblage automatique] dépend généralement du trafic sur les lieux de l’activité sélectionnée et des taux de conversion associés à la mesure de succès de votre activité.

Le [!UICONTROL ciblage automatique] ne tente pas de créer un modèle personnalisé pour une expérience donnée tant qu’il n’y a pas au moins 50 conversions pour cette expérience. De plus, si la qualité du modèle créé est insuffisante (comme déterminé par l’évaluation hors ligne sur des données de « test » retenues, à l’aide d’[une mesure appelée AUC](https://fr.wikipedia.org/wiki/Courbe_ROC)), le modèle ne sera pas utilisé pour diffuser le trafic de façon personnalisée.

Quelques points supplémentaires à garder à l’esprit lors de la création du modèle de [!UICONTROL ciblage automatique] :

* Une fois qu’une activité est active, le [!UICONTROL ciblage automatique] tient compte des 45 derniers jours de données diffusées de manière aléatoire lors de la tentative de création de modèles (à savoir le trafic de contrôle, ainsi que quelques données supplémentaires diffusées de manière aléatoire et retenues par l’algorithme).
* Lorsque [!UICONTROL Revenu par visite] est votre mesure de succès, ces activités nécessitent généralement plus de données pour créer des modèles en raison de l’écart de données plus élevé existant généralement dans le rapport visite-revenu comparé au taux de conversion.
* Étant donné que les modèles sont créés sur la base de chaque expérience, le remplacement d’une expérience par une autre signifie que vous devez recueillir suffisamment de trafic (c’est-à-dire au moins 50 conversions) pour la nouvelle expérience avant de pouvoir recréer des modèles personnalisés.

### Un modèle est créé dans mon activité. Les visites de cette expérience sont-elles personnalisées ?

Non, il doit exister au moins deux modèles créés au sein de votre activité pour que la personnalisation puisse débuter.

### Quand puis-je commencer à consulter les résultats de mon activité de [!UICONTROL ciblage automatique] ?

Vous pouvez commencer à consulter les résultats de votre test de [!UICONTROL ciblage automatique] dès qu’au moins deux expériences ont été créées à partir des modèles (indiquées par une coche verte) pour l’expérience sur laquelle les modèles sont créés.

### Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

Vous pouvez sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (Personnalisation automatisée) ou d’une activité de [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

### Puis-je modifier la mesure d’objectif au cours d’une activité de ciblage automatique ?  {#change-metric}

Il est déconseillé de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. Nous ne garantissons pas les résultats obtenus si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’[!UICONTROL affectation automatique], de [!UICONTROL ciblage automatique] et d’[!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

### Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité de ciblage automatique ?

Il n’est pas recommandé d’utiliser l’option [!UICONTROL Réinitialiser les données du rapport] pour les activités de [!UICONTROL ciblage automatique]. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de [!UICONTROL ciblage automatique]. Au lieu d’utiliser l’option [!UICONTROL Réinitialiser les données du rapport] pour les activités de [!UICONTROL ciblage automatique], créez une activité et désactivez l’activité d’origine. (Remarque : ces conseils s’appliquent également aux activités d’[!UICONTROL affectation automatique] et d’[!UICONTROL Automated Personalization].)

### Que se passe-t-il si je supprime une expérience unique d’une activité de ciblage automatique ?

[!DNL Target] crée un modèle par expérience. La suppression d’une expérience signifie donc que [!DNL Target] créera un modèle de moins et que cela n’affectera pas les modèles des autres expériences.

Par exemple, imaginons que vous ayez une activité de [!UICONTROL ciblage automatique] avec huit expériences et que vous ne soyez pas satisfait des performances d’une expérience. Vous pouvez supprimer cette expérience sans que cela n’affecte les modèles des sept expériences restantes.

## Dépannage du [!UICONTROL ciblage automatique] {#section_23995AB813F24525AF294D20A20875C8}

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lorsque vous utilisez le [!UICONTROL ciblage automatique], ainsi que quelques suggestions de solutions.

### Mon activité de [!UICONTROL ciblage automatique] prend trop de temps pour générer des modèles.

Plusieurs modifications de configuration de l’activité peuvent diminuer le temps escompté pour la création des modèles, dont le nombre d’expériences incluses dans votre activité de [!UICONTROL ciblage automatique], le trafic entrant sur votre site et le critère de mesure de succès sélectionné.

**Solution :** passez en revue la configuration de votre activité et déterminez si des modifications sont souhaitables pour accélérer la compilation des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdrez pas les données d’activité si vous modifiez le critère de mesure de succès en passant du RPV à la conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible est de nature à augmenter les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité peut raccourcir le délai nécessaire à la compilation des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus les lieux de votre activité génèrent de trafic et de conversions, plus les modèles se compileront rapidement.

### Mon activité de [!UICONTROL ciblage automatique] ne génère aucun effet élévateur.

Quatre facteurs sont requis pour qu’une activité AP génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** tout d’abord, assurez-vous que votre activité personnalise le trafic. Si aucun modèle n’est compilé pour l’ensemble des expériences, votre activité de [!UICONTROL ciblage automatique] continue de générer au hasard une portion significative des visites pour tenter de créer tous les modèles aussi rapidement que possible. Si les modèles ne sont pas créés, le [!UICONTROL ciblage automatique] ne personnalise pas le trafic.

Ensuite, assurez-vous que les offres et les lieux de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si le résultat d’un test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

### Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties.

Ce comportement est attendu.

Dans une activité de [!UICONTROL ciblage automatique], dès qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, l’utilisateur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 est dépendant de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1, puis A1, A1 n’est toujours pas converti car dès que C1 est converti, le visiteur est libéré.
