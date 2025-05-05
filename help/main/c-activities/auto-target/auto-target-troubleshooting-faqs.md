---
keywords: ciblage automatique;ciblage;affectation de trafic;questions fréquentes;faq;résolution de problèmes;dépannage;trafic
description: Explorez les rubriques de dépannage et les questions fréquentes sur les activités [!UICONTROL Auto-Target].
title: Comment Résoudre Les Problèmes Liés Aux Activités [!UICONTROL Auto-Target] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1850'
ht-degree: 29%

---

# [!UICONTROL Auto-Target] FAQ et dépannage

Dépannage et questions fréquentes sur les activités [!UICONTROL Auto-Target] dans [!DNL Adobe Target].

## [!UICONTROL Auto-Target] Questions fréquentes {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consultez les questions fréquentes et réponses suivantes lorsque vous utilisez des activités [!UICONTROL Auto-Target] :

### Quelles sont les bonnes pratiques pour configurer une activité [!UICONTROL Auto-Target] ?

+++Réponse
* Déterminez si la valeur commerciale d’une mesure de succès [!UICONTROL Revenue per Visit] (RPV) vaut les exigences de trafic supplémentaires. Le RPV nécessite généralement au moins 1 000 conversions par expérience pour qu’une activité soit plus performante qu’une conversion.
* Décidez l’affectation ente l’expérience de contrôle et l’expérience personnalisée avant de débuter l’activité d’après vos objectifs.
* Déterminez si vous disposez d’un trafic suffisant sur la page où s’exécute votre activité [!UICONTROL Auto-Target] pour que les modèles de personnalisation soient créés dans un délai raisonnable.
* Si vous testez l’algorithme de personnalisation, vous ne devez pas modifier les expériences, ni ajouter ou supprimer des attributs de profil tant que l’activité est active.
* Envisagez d’exécuter une activité A/B entre les offres et les lieux que vous prévoyez d’utiliser dans votre activité [!UICONTROL Auto-Target] afin de vous assurer que les emplacements et les offres ont un impact sur l’objectif d’optimisation. Si une activité A/B ne démontre pas de différence significative, [!UICONTROL Auto-Target] ne réussira probablement pas non plus à générer un effet élévateur.

  Si un test A/B ne montre aucune différence statistiquement significative entre des expériences, il est probable que les offres considérées ne sont pas suffisamment différentes les unes des autres, que les emplacements sélectionnés n’influencent pas la mesure de succès, ou que l’objectif d’optimisation soit trop distant dans l’entonnoir de conversion pour être affecté par les offres que vous avez choisies.

* Essayez de ne pas apporter de modifications substantielles aux expériences pendant l’activité.

+++

### [!UICONTROL Adobe] que vous recommandez d&#39;utiliser [!UICONTROL Auto Target] avec un partage 90(Pilotage)/10(Ciblé) jusqu&#39;à ce que les modèles soient créés ?

+++Réponse
La répartition optimale de votre trafic dépend de ce que vous souhaitez accomplir.

Si votre objectif est de personnaliser le plus de trafic possible, vous pouvez conserver une affectation ciblée de 90 % et un contrôle de 10 % sur la durée de vie de l’activité. Si votre objectif est d’exécuter une expérience comparant le fonctionnement des algorithmes personnalisés à celui du contrôle, une répartition 50/50 est préférable pour la durée de vie de l’activité.

Il est recommandé de conserver la répartition de l’affectation du trafic pendant toute la durée de vie de l’activité afin que les visiteurs ne basculent pas entre les expériences ciblées et les expériences de contrôle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Si un visiteur ne **et non** consulte l’activité [!UICONTROL Auto-Target] et effectue une conversion, la conversion est-elle prise en compte dans mon activité ?

+++Réponse
Non, seuls les visiteurs qui remplissent les critères et visualisent l’activité [!UICONTROL Auto-Target] sont comptabilisés dans les rapports.

+++

### Pourquoi mon activité [!UICONTROL Auto-Target] ne semble-t-elle générer aucun effet élévateur ?

+++Réponse
Quatre facteurs sont nécessaires pour qu’une activité [!UICONTROL Auto-Target] génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent se trouver à un endroit qui change l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications.

Si le résultat du test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, le problème provient des offres et des emplacements qui n’ont pas un impact suffisant sur l’objectif d’optimisation à détecter avec une signification statistique.

+++

### Quand dois-je arrêter mon activité [!UICONTROL Auto-Target] ?

+++Réponse
[!UICONTROL Auto-Target] peut être utilisé comme une personnalisation &quot;toujours active&quot; qui optimise constamment. En particulier pour le contenu sans cesse renouvelé, il n’est pas nécessaire d’arrêter votre activité [!UICONTROL Auto-Target].

Si vous souhaitez apporter des modifications substantielles au contenu de votre activité [!UICONTROL Auto-Target], la meilleure pratique consiste à démarrer une nouvelle activité afin que les autres utilisateurs qui visualisent les rapports ne confondent pas ou ne relient pas les résultats passés à un contenu différent.

+++

### Combien de temps dois-je attendre la compilation des modèles ? {#how-long}

+++Réponse
Le temps nécessaire à la compilation des modèles dans votre activité [!UICONTROL Auto-Target] dépend généralement du trafic vers les emplacements d’activité sélectionnés et des taux de conversion associés à la mesure de succès de votre activité.

[!UICONTROL Auto-Target] ne tente pas de créer un modèle personnalisé pour une expérience donnée tant qu’il n’y a pas au moins 50 conversions pour cette expérience. De plus, si le modèle généré est de qualité insuffisante (comme déterminé par l’évaluation hors ligne sur les données de &quot;test&quot; d’attente, à l’aide de [une mesure appelée AUC](https://fr.wikipedia.org/wiki/Courbe_ROC)), le modèle n’est pas utilisé pour traiter le trafic d’une manière personnalisée.

Quelques points supplémentaires à garder à l’esprit concernant la création de modèles de [!UICONTROL Auto-Target] :

* Une fois qu’une activité est active, [!UICONTROL Auto-Target] prend en compte jusqu’aux 45 derniers jours de données diffusées de manière aléatoire lors de la tentative de création de modèles. Par exemple, contrôlez le trafic, plus certaines données supplémentaires diffusées de manière aléatoire, conservées par l’algorithme.
* Lorsque [!UICONTROL Revenue per Visit] est votre mesure de succès, ces activités nécessitent généralement plus de données pour créer des modèles en raison de la variance de données plus élevée qui existe généralement dans les recettes de visite par rapport au taux de conversion.
* Étant donné que les modèles sont construits selon l’expérience, le remplacement d’une expérience par une autre expérience signifie qu’un trafic suffisant (au moins 50 conversions) doit être collecté pour la nouvelle expérience avant que les modèles personnalisés puissent être reconstruits.

+++

### Un modèle est créé dans mon activité. Les visites de cette expérience sont-elles personnalisées ?

+++Réponse
Non, au moins deux modèles doivent être créés dans votre activité pour que la personnalisation puisse commencer.

+++

### Quand puis-je commencer à consulter les résultats de mon activité [!UICONTROL Auto-Target] ?

+++Réponse
Vous pouvez commencer à consulter les résultats de votre test [!UICONTROL Auto-Target] après avoir créé au moins deux expériences avec des modèles (coche verte) pour l’expérience dont les modèles sont construits.

+++

### Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

+++Réponse
Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d’une activité [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer l’ensemble du trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’affectation du trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### Puis-je modifier la mesure d’objectif à mi-chemin d’une activité [!UICONTROL Auto-Target] ? {#change-metric}

+++Réponse
Adobe ne vous recommande pas de modifier la mesure d’objectif à mi-chemin d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. Adobe ne garantit pas ce qui se passe si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source des rapports.

+++

### Puis-je utiliser l’option [!UICONTROL Reset Report Data] lors de l’exécution d’une activité [!UICONTROL Auto-Target] ?

+++Réponse
L’utilisation de l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Auto-Target] n’est pas suggérée. Bien qu’elle supprime les données de rapport visibles, cette option ne supprime pas tous les enregistrements d’entraînement du modèle [!UICONTROL Auto-Target]. Au lieu d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Auto-Target], créez une activité et désactivez l’activité d’origine.

Cette recommandation s’applique également aux activités [!UICONTROL Auto-Allocate] et [!UICONTROL Automated Personalization].

+++

### Que se passe-t-il si je supprime une seule expérience d’une activité [!UICONTROL Auto-Target] ?

+++Réponse
[!DNL Target] crée un modèle par expérience, de sorte que la suppression d’une expérience signifie que [!DNL Target] crée un modèle de moins et n’affecte pas les modèles pour les autres expériences.

Par exemple, supposons que vous ayez une activité [!UICONTROL Auto-Target] avec huit expériences et que vous n’aimez pas les performances d’une seule expérience. Vous pouvez supprimer cette expérience, qui n’affecte pas les modèles des sept expériences restantes.

+++

## Résolution des problèmes [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lors de l’utilisation de [!UICONTROL Auto-Target] et quelques suggestions de solutions.

### Mon activité [!UICONTROL Auto-Target] prend trop de temps pour créer des modèles.

+++Suggestions de dépannage
Plusieurs modifications de configuration de l’activité peuvent diminuer le temps escompté pour la création des modèles, notamment le nombre d’expériences incluses dans votre activité [!UICONTROL Auto-Target], le trafic entrant sur votre site et la mesure de succès sélectionnée.

**Solution :** Vérifiez la configuration de votre activité et vérifiez si vous êtes prêt à apporter des modifications afin d’améliorer la vitesse de compilation des modèles.

* Si votre mesure de succès est définie sur [!UICONTROL RPV], pouvez-vous la convertir ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdrez pas les données d’activité si vous modifiez le critère de mesure de succès en passant du RPV à la conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les exigences de trafic nécessaires à la création des modèles, car un nombre minimum de conversions est requis.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité réduit le temps de création des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus le trafic et les conversions sont importants dans les emplacements de vos activités, plus les modèles sont rapides à générer.

+++

### Mon activité [!UICONTROL Auto-Target] ne génère aucun effet élévateur.

+++Suggestions de dépannage
Quatre facteurs sont nécessaires pour qu’une activité [!UICONTROL Auto-Target] génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent se trouver à un endroit qui change l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** tout d’abord, assurez-vous que votre activité personnalise le trafic. Si les modèles ne sont pas créés pour l’ensemble des expériences, votre activité [!UICONTROL Auto-Target] continue de générer de manière aléatoire une portion significative des visites pour tenter de créer tous les modèles aussi rapidement que possible. Si les modèles ne sont pas créés, [!UICONTROL Auto-Target] ne personnalise pas le trafic.

Ensuite, assurez-vous que les offres et les emplacements d’activité font réellement une différence dans les taux de réponse globaux à l’aide d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si les résultats d’un test A/B présentent un effet élévateur statistiquement significatif sur une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionne. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient des offres et des emplacements qui n’ont pas un impact suffisant sur l’objectif d’optimisation à détecter avec une signification statistique.

+++

### Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties.

+++Suggestions de dépannage
C’est ce qui est attendu.

Dans une activité [!UICONTROL Auto-Target], une fois qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, l’utilisateur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 dépend de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1 puis A1, A1 n’est toujours pas converti, car lorsque C1 est converti, le visiteur est libéré.

+++
