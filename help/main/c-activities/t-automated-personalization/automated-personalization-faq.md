---
keywords: dépannage;questions fréquentes;FAQ;FAQ;personnalisation automatisée;contrôle;expérience par défaut;bonnes pratiques
description: Consultez la liste des questions fréquentes et des réponses sur les activités Automated Personalization (AP) dans Adobe Target.
title: Comment puis-je trouver des questions fréquentes sur les activités Automated Personalization ?
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '2004'
ht-degree: 76%

---

# ![PREMIUM](/help/main/assets/premium.png) FAQ sur Automated Personalization

Questions fréquentes au sujet d’Automated Personalization.

## Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

Vous pouvez sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (Personnalisation automatisée) ou d’une activité de [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

## Comment comparer Automated Personalization à une expérience par défaut ? {#section_46C1A620A2384C2C8392D6716DD18495}

Aucune solution clé en main ne permet de comparer Automated Personalization à une expérience par défaut. Toutefois, si une offre ou une expérience par défaut fait partie de l’activité globale, vous pouvez cliquer sur le segment &quot;Contrôle&quot; dans les rapports pour comprendre ses performances de base et localiser cette offre dans le rapport au niveau de l’offre qui en résulte. Le taux de conversion enregistré pour cette offre peut être utilisé pour comparer le taux de conversion de l’ensemble du segment &quot;Forêt aléatoire&quot;. Il est ainsi plus facile de comparer les performances de la machine par rapport à l’offre par défaut.

## Quelles sont les bonnes pratiques pour configurer une activité d’Automated Personalization ? {#section_E155B26282BE49B58EA2683413D11DE6}

* Si vous essayez de personnaliser une page à faible trafic, ou souhaitez apporter des modifications structurelles à l’expérience que vous personnalisez, envisagez d’utiliser le ciblage automatique plutôt qu’Automated Personalization. Voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Envisagez d’exécuter une activité de test A/B entre les offres et les lieux que vous prévoyez d’utiliser dans votre activité Automated Personalization, afin d’assurer que les lieux et les offres ont une incidence sur l’objectif d’optimisation. Si une activité de test A/B échoue ne met pas en évidence de différence significative, il est probable qu’Automated Personalization échouera également à générer l’effet élévateur.

   * Si un test A/B...N ne montre aucune différence statistiquement significative entre des expériences, il est probable que les offres considérées ne sont pas suffisamment différentes les unes des autres, que les emplacements sélectionnés n’influencent pas la mesure de succès, ou que l’objectif d’optimisation soit trop distant dans l’entonnoir de conversion pour être affecté par les offres que vous avez choisies.

* Assurez-vous d’utiliser [l’estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) de manière à estimer le temps nécessaire à la compilation des modèles de personnalisation dans votre activité Automated Personalization.
* Décidez l’affectation ente le contrôle et le ciblage avant de débuter l’activité d’après vos objectifs.

   Il existe trois scénarios à prendre en compte en fonction de l’objectif de votre activité et du type de contrôle que vous avez sélectionné :

   * **Expérience aléatoire comme contrôle et l’objectif de votre activité est de tester l’efficacité de l’algorithme de personnalisation.**: Si votre objectif est d’évaluer l’algorithme de personnalisation, vous souhaitez obtenir une image plus précise de votre effet élévateur. Vous pouvez également comparer le taux de conversion de vos expériences/offres si vous avez simplement effectué un test A/B (contrôle diffusé de manière aléatoire). Dans ce cas, il est recommandé d’utiliser une allocation de 50 % à un contrôle d’expériences diffusées de manière aléatoire.
   * **Expérience aléatoire comme contrôle et l’objectif de votre activité est d’optimiser le trafic personnalisé.**: Si vous vous sentez à l’aise avec l’algorithme et que vous souhaitez personnaliser le trafic maximum, une allocation de 10 à 30 % au contrôle est recommandée. Le compromis ici est la précision que vous pourrez voir dans les informations de l’effet élévateur (car les intervalles de confiance de votre trafic de contrôle seront plus importants parce qu’il y a moins de trafic qui leur arrive).
   * **Expérience spécifique comme contrôle, avec l’un ou l’autre type d’objectif** : Si vous souhaitez comparer une expérience basée sur le spécialiste du marketing aux modèles de personnalisation, une allocation de 10 % à 30 % au contrôle est recommandée. Lorsque vous sélectionnez une seule expérience comme contrôle, ce trafic n’est pas réparti sur toutes les offres/expériences de l’activité.

* Les règles de ciblage doivent être appliquées avec autant de parcimonie que possible, car elles peuvent interférer avec la capacité d’optimisation du modèle.
* Les groupes de génération de rapports peuvent limiter le succès de votre activité Automated Personalization. Ils doivent donc toujours être utilisés dans des conditions spécifiques.

   * Utilisez les groupes de génération de rapports uniquement si les conditions suivantes sont réunies : (1) vous envisagez le remplacement ou l’ajout de nouvelles offres alors que l’activité est en cours d’exécution ; (2) les offres du groupe de génération de rapports considéré font appel aux mêmes visiteurs ; et (3) les offres contenues dans ce groupe présentent sensiblement le même taux de réponse global.
   * Aucune personnalisation n’existe entre des offres dans un groupe de génération de rapports ; les offres sont toutes traitées de manière indifférenciée par le modèle de personnalisation.
   * Ne placez jamais toutes les offres d’une activité dans un seul groupe de génération de rapports. Cette décision ferait que toutes les offres seraient proposées uniformément et aléatoirement à tous les visiteurs inclus dans l’activité.

## Questions fréquentes 

Consultez les questions fréquentes et réponses suivantes lorsque vous utilisez [!UICONTROL Automated Personalization] activités :

### Quelles sont les limites fixées par Automated Personalization ? {#section_08BA09ED51B547299963C94FE6417CFA}

[!DNL Target] se limite à 30 000 expériences, mais fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont créées.

Cette même limite est appliquée même si l’activité a activé la variable [!UICONTROL Diffuser les doublons] .

### Comment le ciblage au niveau de l’offre est-il mis en œuvre ? {#section_9D7A86EA93D74E9B8C81072A681263A4}

À l’arrivée de chaque visiteur, l’ensemble des offres possibles que le visiteur peut voir est déterminé par les règles de ciblage au niveau de l’offre. Puis, l’algorithme sélectionne l’offre dont le modèle prédit qu’elle engendrera le meilleur chiffre d’affaires ou la meilleure chance de conversion parmi les offres existantes. Il est à noter que le ciblage d’offre influe sur l’efficacité des algorithmes d’apprentissage automatique de Target et que, par conséquent, il doit être utilisé avec autant de parcimonie que possible.

### Mon activité n’indique aucun effet élévateur. Que se passe-t-il ? {#section_BFA07C8C258F45318F73A461B8F32737}

Quatre facteurs sont requis pour qu’une activité AP génère un effet élévateur :

* Les offres présentes à chaque emplacement doivent être suffisamment différentes pour influencer les visiteurs.
* Les emplacements doivent être situés de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si le résultat d’un test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

Pour plus d’informations, [Résolution des problèmes liés à Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

### Comment le trafic de mon activité est-il alloué par Automated Personalization ? {#section_4369364F77804E0D9B78BEE551DA5659}

La personnalisation automatisée dirige les visiteurs vers l’expérience dont la mesure de réussite est la plus élevée en fonction des modèles les plus récents de [Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) construits pour chaque modèle. Cette prévision est fondée sur les informations spécifiques à chaque visiteur et sur le contexte de visite.

Supposons par exemple qu’une activité AP comporte deux emplacements comprenant eux-mêmes deux offres chacun. Sur le premier emplacement, l’offre A présente un taux de conversion prévu de 3 % pour un visiteur spécifique, tandis que l’offre B présente un taux de conversion prévu de 1 %. Sur le second emplacement, l’offre C présente un taux de conversion prévu de 2 % pour le même visiteur, tandis que l’offre D présente un taux de conversion prévu de 5 %. Dans ce cas, Automated Personalization délivre à ce visiteur une expérience comportant l’offre A et l’offre D.

### Quand dois-je arrêter mon activité Automated Personalization ? {#section_C51F3DAB8887463BB147373F6FE06B93}

Automated Personalization peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’y a aucune nécessité d’arrêter votre activité Automated Personalization. Si vous souhaitez apporter des modifications substantielles au contenu qui ne sont pas semblables aux offres actuellement présentes dans votre activité Automated Personalization, la meilleure pratique consiste à démarrer une nouvelle activité, afin que les autres utilisateurs qui visualisent les rapports n’en confondent pas les résultats, ou ne les relient pas à d’anciens résultats portant sur des contenus différents.

### Combien de temps dois-je attendre la compilation des modèles ? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

Le délai nécessaire aux modèles pour construire votre activité dépend généralement du trafic présent sur les lieux de l’activité sélectionnée, ainsi que de la mesure de succès de votre activité. Utilisez [l’estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) pour déterminer le temps nécessaire à la compilation des modèles dans votre activité.

### Un modèle est compilé au sein de mon activité. Les visites de cette expérience sont-elles personnalisées ? {#section_51EA953C6D1D4A3185FC9DD290D66621}

Non, il doit exister au moins deux modèles créés au sein de votre activité pour que la personnalisation puisse débuter.

### Quand puis-je consulter les résultats de mon activité Automated Personalization ? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

Vous pouvez commencer à consulter les résultats de votre activité Automated Personalization dès qu’au moins deux expériences ont été compilées à partir des modèles (indiquées par une coche verte) pour l’expérience dont les modèles sont construits.

### Comment puis-je raccourcir le temps nécessaire à la compilation des modèles dans mon activité ? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

Passez en revue la configuration de votre activité et déterminez si des modifications sont souhaitables pour accélérer la compilation des modèles.

* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible est de nature à augmenter les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité peut réduire le temps nécessaire à la compilation des modèles.
* Existe-t-il une page à trafic élevée sur laquelle cette activité serait plus efficace ? Plus les lieux de votre activité génèrent de trafic et de conversions, plus les modèles se compileront rapidement.

### Pourquoi les visiteurs voient-ils des expériences pour une activité AP alors que cela ne devrait pas être le cas ? {#section_41CECEAE0881446A8D9F3B016857914B}

Les activités Automated Personalization sont évaluées une seule fois par session. Si des sessions actives ont été qualifiées pour une expérience particulière et que de nouvelles offres y sont maintenant incorporées, les utilisateurs verront le nouveau contenu en même temps que les offres précédemment affichées. Du fait que leur qualification pour ces expériences est déjà validée, ils continueront de les voir pendant toute la durée de la session. S’il est souhaitable de procéder à cette évaluation pour chaque visite de page unique, vous devez sélectionner le type d’activité XT (ciblage d’expérience).

### Puis-je modifier la mesure d’objectif à mi-chemin d’une activité Automated Personalization ? {#change-metric}

Il est déconseillé de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. Nous ne garantissons pas les résultats obtenus si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’[!UICONTROL affectation automatique], de [!UICONTROL ciblage automatique] et d’[!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

### Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité Automated Personalization ?

En utilisant la variable [!UICONTROL Réinitialisation des données du rapport] option pour [!UICONTROL Automated Personalization] Les activités ne sont pas suggérées. Bien qu’elle supprime les données de création de rapports visibles, cette option ne supprime pas tous les enregistrements d’entraînement de l’événement [!UICONTROL Automated Personalization] modèle. Au lieu d’utiliser la variable [!UICONTROL Réinitialisation des données du rapport] option pour [!UICONTROL Automated Personalization] , créez une activité et désactivez l’activité d’origine. (Remarque : Ce guide s’applique également à [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités.)

### Comment Automated Personalization génère-il des modèles en ce qui concerne les environnements ?

Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic traité de manière aléatoire plutôt que d’envoyer tout le trafic à l’expérience gagnante globale. Ce modèle ne prend en compte que les accès et les conversions dans l’environnement par défaut.

Le trafic provenant d’un deuxième ensemble de modèles est créé pour chaque groupe de modélisation (AP) ou expérience (AT). Pour chacun de ces modèles, les accès et les conversions sont pris en compte dans tous les environnements.

Les requêtes sont donc servies avec le même modèle, quel que soit l’environnement, mais la pluralité du trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement du monde réel.
