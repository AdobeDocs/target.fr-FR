---
keywords: ciblage automatique;ciblage;affectation de trafic;questions fréquentes;faq;résolution de problèmes;dépannage;trafic
description: Consultez les rubriques de dépannage et les questions fréquentes sur les activités de ciblage automatique dans Adobe Target.
title: Comment résoudre les problèmes liés aux activités de ciblage automatique ?
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: d35ca5955b42772387c08a36e5b9e4ac207718a0
workflow-type: tm+mt
source-wordcount: '1921'
ht-degree: 58%

---

# ![PREMIUM](/help/main/assets/premium.png) FAQ et dépannage du ciblage automatique

Dépannage et questions fréquentes à propos des [!UICONTROL Ciblage automatique] activités dans [!DNL Adobe Target].

## [!UICONTROL Questions fréquentes sur le ciblage automatique] {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consultez les FAQ et les réponses suivantes lorsque vous effectuez des activités de [!UICONTROL ciblage automatique] :

### Quelles sont les bonnes pratiques pour configurer une activité de [!UICONTROL ciblage automatique] ?

+++Réponse
* Déterminer si la valeur commerciale d’une [!UICONTROL Recettes par visite] La mesure de succès (RPV) vaut les exigences de trafic supplémentaires. Le RPV nécessite généralement au moins 1 000 conversions par expérience pour qu’une activité soit plus performante qu’une conversion.
* Décidez l’affectation ente l’expérience de contrôle et l’expérience personnalisée avant de débuter l’activité d’après vos objectifs.
* Déterminez si vous disposez d’un trafic suffisant sur la page où votre activité de [!UICONTROL ciblage automatique] doit être exécutée pour que les modèles de personnalisation soient créés dans un laps de temps raisonnable.
   * Si vous testez l’algorithme de personnalisation, vous ne devez pas modifier les expériences, ni ajouter ou supprimer des attributs de profil tant que l’activité est active.

* Envisagez d’exécuter une activité A/B entre les offres et les lieux que vous prévoyez d’utiliser dans votre [!UICONTROL Ciblage automatique] pour s’assurer que les emplacements et les offres ont un impact sur l’objectif d’optimisation. Si une activité A/B ne met pas en évidence de différence significative, il est probable que le [!UICONTROL ciblage automatique] ne parviendra pas non plus à générer un effet élévateur.

   * Si un test A/B ne montre aucune différence statistiquement significative entre des expériences, il est probable que les offres considérées ne sont pas suffisamment différentes les unes des autres, que les emplacements sélectionnés n’influencent pas la mesure de succès, ou que l’objectif d’optimisation soit trop distant dans l’entonnoir de conversion pour être affecté par les offres que vous avez choisies.

* Essayez de ne pas modifier sensiblement l’expérience durant le déroulement de l’activité.

+++

### Adobe-t-il d’utiliser [!UICONTROL Ciblage automatique] avec un partage 90(Contrôle)/10(Ciblé) jusqu’à ce que les modèles soient créés ?

+++Réponse La répartition optimale du trafic dépend de ce que vous souhaitez accomplir.

Si votre objectif est de personnaliser le plus de trafic possible, vous pouvez conserver une affectation ciblée de 90 % et un contrôle de 10 % sur la durée de vie de l’activité. Si votre but est d’exécuter une expérience en comparant les performances des algorithmes personnalisés par rapport au contrôle, une répartition 50/50 est préférable pour la durée de vie de l’activité.

Il est recommandé de conserver la répartition de l’affectation du trafic pendant toute la durée de vie de l’activité afin que les visiteurs ne basculent pas entre les expériences ciblées et les expériences de contrôle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Si un visiteur le fait **not** voir la [!UICONTROL Ciblage automatique] activité et convertit, la conversion est-elle comptabilisée dans mon activité ?

+++Réponse Non, seuls les visiteurs qui remplissent les critères et qui affichent le [!UICONTROL Ciblage automatique] Les activités sont comptabilisées dans les rapports.

+++

### Pourquoi mon [!UICONTROL Ciblage automatique] l’activité semble générer n’importe quel effet élévateur.

+++Réponse Quatre facteurs sont requis pour une [!UICONTROL Ciblage automatique] activité de génération d’effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications.

Si le résultat du test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

+++

### Quand dois-je arrêter mon activité de [!UICONTROL ciblage automatique] ?

+++Réponse
[!UICONTROL Ciblage automatique] peut être utilisé comme une personnalisation &quot;toujours active&quot; qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’est pas nécessaire d’arrêter votre activité de [!UICONTROL ciblage automatique].

Si vous souhaitez apporter des modifications substantielles au contenu de votre [!UICONTROL Ciblage automatique] , la bonne pratique consiste à démarrer une nouvelle activité de sorte que les autres utilisateurs qui visualisent les rapports ne confondent pas les résultats passés et ne les relient pas à un contenu différent.

+++

### Combien de temps dois-je attendre la compilation des modèles ? {#how-long}

+++Réponse Le temps nécessaire à la compilation des modèles dans votre [!UICONTROL Ciblage automatique] Cette activité dépend généralement du trafic vers les emplacements d’activité sélectionnés et des taux de conversion associés à la mesure de succès de votre activité.

[!UICONTROL Ciblage automatique] ne tente pas de créer un modèle personnalisé pour une expérience donnée tant qu’il n’y a pas au moins 50 conversions pour cette expérience. En outre, si le modèle créé est de qualité insuffisante (comme déterminé par l’évaluation hors ligne sur les données de &quot;test&quot; d’attente, en utilisant [une mesure appelée AUC](https://fr.wikipedia.org/wiki/Courbe_ROC)), le modèle n’est pas utilisé pour diffuser le trafic d’une manière personnalisée.

Quelques points supplémentaires à garder à l’esprit lors de la création du modèle de [!UICONTROL ciblage automatique] :

* Une fois qu’une activité est active, [!UICONTROL Ciblage automatique] prend en compte jusqu’aux 45 derniers jours de données diffusées de manière aléatoire lors de la tentative de création de modèles (par exemple, le contrôle du trafic, ainsi que certaines données diffusées de manière aléatoire supplémentaires, définies par l’algorithme).
* Lorsque [!UICONTROL Revenu par visite] est votre mesure de succès, ces activités nécessitent généralement plus de données pour créer des modèles en raison de l’écart de données plus élevé existant généralement dans le rapport visite-revenu comparé au taux de conversion.
* Étant donné que les modèles sont construits selon l’expérience, le remplacement d’une expérience par une autre expérience signifie qu’un trafic suffisant (au moins 50 conversions) doit être collecté pour la nouvelle expérience avant que les modèles personnalisés puissent être recréés.

+++

### Un modèle est créé dans mon activité. Les visites de cette expérience sont-elles personnalisées ?

+++Réponse Non, au moins deux modèles doivent être créés dans votre activité pour que la personnalisation puisse commencer.

+++

### Quand puis-je commencer à consulter les résultats de mon [!UICONTROL Ciblage automatique] activité ?

+++Réponse Vous pouvez commencer à consulter les résultats de votre [!UICONTROL Ciblage automatique] testez après avoir créé au moins deux expériences avec des modèles (coche verte) pour l’expérience dont les modèles sont construits.

+++

### Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

+++Réponse Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d’une [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) .

Cette fonctionnalité vous permet d’acheminer l’ensemble du trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’affectation du trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### Puis-je modifier la mesure d’objectif au milieu d’une [!UICONTROL Ciblage automatique] activité ? {#change-metric}

+++L’Adobe de réponse ne vous recommande pas de modifier la mesure d’objectif à mi-chemin d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. Nous ne garantissons pas les résultats obtenus si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’[!UICONTROL affectation automatique], de [!UICONTROL ciblage automatique] et d’[!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

+++

### Puis-je utiliser la variable [!UICONTROL Réinitialisation des données du rapport] lors de l’exécution d’une [!UICONTROL Ciblage automatique] activité ?

+++Réponse à l’aide de la variable [!UICONTROL Réinitialisation des données du rapport] option pour [!UICONTROL Ciblage automatique] Les activités ne sont pas suggérées. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de [!UICONTROL ciblage automatique]. Au lieu d’utiliser l’option [!UICONTROL Réinitialiser les données du rapport] pour les activités de [!UICONTROL ciblage automatique], créez une activité et désactivez l’activité d’origine.

Ce guide s’applique également à [!UICONTROL Affectation automatique] et [!UICONTROL Automated Personalization] activités.

+++

### Que se passe-t-il si je supprime une seule expérience d’une [!UICONTROL Ciblage automatique] activité ?

+++Réponse
[!DNL Target] crée un modèle par expérience, de sorte que la suppression d’une expérience signifie [!DNL Target] crée un modèle de moins et n’affecte pas les modèles pour les autres expériences.

Par exemple, imaginons que vous ayez une activité de [!UICONTROL ciblage automatique] avec huit expériences et que vous ne soyez pas satisfait des performances d’une expérience. Vous pouvez supprimer cette expérience, qui n’affecte pas les modèles des sept expériences restantes.

+++

## Dépannage du [!UICONTROL ciblage automatique] {#section_23995AB813F24525AF294D20A20875C8}

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lors de l’utilisation de [!UICONTROL Ciblage automatique] et quelques suggestions de solutions.

### Mon activité de [!UICONTROL ciblage automatique] prend trop de temps pour générer des modèles.

+++Suggestions de dépannage Plusieurs modifications de configuration de l’activité peuvent réduire le temps escompté de création des modèles, y compris le nombre d’expériences incluses dans votre [!UICONTROL Ciblage automatique] activité, le trafic sur votre site et la mesure de succès sélectionnée.

**Solution :** passez en revue la configuration de votre activité et déterminez si des modifications sont souhaitables pour accélérer la compilation des modèles.

* Si la mesure de succès est définie sur [!UICONTROL RPV], pouvez-vous passer à la conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdrez pas les données d’activité si vous modifiez le critère de mesure de succès en passant du RPV à la conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les exigences de trafic nécessaires à la création des modèles, car un nombre minimum de conversions est requis.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité réduit le temps de création des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus les lieux de votre activité génèrent de trafic et de conversions, plus les modèles se compileront rapidement.

+++

### Mon activité de [!UICONTROL ciblage automatique] ne génère aucun effet élévateur.

+++Suggestions de dépannage Quatre facteurs sont nécessaires pour qu’une activité AT génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent se trouver à un endroit qui change l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** tout d’abord, assurez-vous que votre activité personnalise le trafic. Si aucun modèle n’est compilé pour l’ensemble des expériences, votre activité de [!UICONTROL ciblage automatique] continue de générer au hasard une portion significative des visites pour tenter de créer tous les modèles aussi rapidement que possible. Si les modèles ne sont pas créés, le [!UICONTROL ciblage automatique] ne personnalise pas le trafic.

Ensuite, assurez-vous que les offres et les lieux de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si le résultat d’un test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, le problème provient des offres et des emplacements qui n’ont pas un impact suffisant sur l’objectif d’optimisation à détecter avec une signification statistique.

+++

### Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties.

+++Suggestions de dépannage Ceci est attendu.

Dans une activité de [!UICONTROL ciblage automatique], dès qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, l’utilisateur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 est dépendant de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1, puis A1, A1 n’est toujours pas converti car dès que C1 est converti, le visiteur est libéré.

+++
