---
keywords: résolution de problèmes;questions fréquentes;FAQ;FAQ;automated personalization;contrôle;expérience par défaut;bonnes pratiques
description: Explorez une liste de questions fréquentes (FAQ) et de réponses sur les activités d’[!UICONTROL Automated Personalization] (AP) dans [!UICONTROL Adobe Target].
title: Comment puis-je trouver des questions fréquentes sur les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 20%

---

# FAQ sur Automated Personalization

Consultez les FAQ et les réponses suivantes lorsque vous effectuez des activités [!UICONTROL Automated Personalization] dans [!DNL Adobe Target].

## Puis-je spécifier une expérience spécifique à utiliser comme contrôle dans une activité [!UICONTROL Automated Personalization] ?

+++Afficher les détails

Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d’une activité de [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## Comment puis-je comparer [!UICONTROL Automated Personalization] à une expérience par défaut ? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Afficher les détails

Il n’existe pas d’option clé en main permettant de comparer des [!UICONTROL Automated Personalization] à une expérience par défaut. Cependant, pour pallier ce problème, si une offre ou une expérience par défaut existe dans le cadre de l’activité globale, cliquez sur le segment « [!UICONTROL Control] » dans les rapports et localisez cette offre particulière dans le rapport au niveau de l’offre qui en résulte. Le taux de conversion enregistré pour cette offre peut être utilisé à des fins de comparaison avec le taux de conversion de l’ensemble du segment « Forêt aléatoire ». Il est ainsi plus facile de comparer les performances de la machine par rapport à l’offre par défaut.

+++

## Quelles sont les bonnes pratiques pour configurer une activité [!UICONTROL Automated Personalization] ? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Afficher les détails

* Si vous souhaitez personnaliser une page à faible trafic ou apporter des modifications structurelles à l’expérience que vous personnalisez, pensez à utiliser une activité [!UICONTROL Auto-Target] à la place de [!UICONTROL Automated Personalization]. Voir [ Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Envisagez d’effectuer une activité de [!UICONTROL A/B Test] entre les offres et les emplacements que vous prévoyez d’utiliser dans votre activité de [!UICONTROL Automated Personalization] afin de vous assurer que l’emplacement et les offres ont un impact sur l’objectif d’optimisation. Si une activité [!UICONTROL A/B Test] ne parvient pas à démontrer une différence significative, [!UICONTROL Automated Personalization] ne parvient probablement pas non plus à générer d’effet élévateur.

   * Si un test A/B...N ne montre aucune différence statistiquement significative entre les expériences, une ou plusieurs des situations suivantes sont probablement responsables :

      * Les offres ne sont probablement pas suffisamment différentes les unes des autres.
      * Les emplacements que vous avez sélectionnés n’ont aucune incidence sur la mesure de succès.
      * L’objectif d’optimisation se trouve trop loin dans l’entonnoir de conversion pour être affecté par les offres sélectionnées.

* Veillez à utiliser l’[Estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de vous faire une idée du temps nécessaire aux modèles de personnalisation pour intégrer votre activité de [!UICONTROL Automated Personalization].
* Décidez de l’allocation entre le contrôle et le ciblé avant de commencer l’activité, en fonction de vos objectifs.

  Vous devez prendre en compte trois scénarios en fonction de l’objectif de votre activité et du type de contrôle que vous avez sélectionné :

   * **Expériences aléatoires comme objectif de contrôle et d’activité est de tester l’efficacité de l’algorithme de personnalisation** : si votre objectif est d’évaluer l’algorithme de personnalisation, vous souhaitez obtenir une image plus précise de l’effet élévateur. Vous voudrez probablement également comparer le taux de conversion de vos expériences ou offres si vous avez simplement effectué une [!UICONTROL A/B Test] (un contrôle diffusé de manière aléatoire). Dans ce cas, il est recommandé d’utiliser une allocation de 50 % à un contrôle d’expériences diffusées de manière aléatoire.
   * **« Expériences aléatoires » comme contrôle et objectif de votre activité afin d’optimiser le trafic personnalisé** : si vous maîtrisez l’algorithme et souhaitez personnaliser la quantité maximale de trafic, une affectation de 10 % à 30 % au contrôle est recommandée. Le compromis ici est la précision que vous voyez dans vos informations d&#39;ascenseur. Les intervalles de confiance de votre trafic de contrôle sont plus grands, car ils reçoivent moins de trafic.
   * **Expérience spécifique comme contrôle, avec l’un ou l’autre type d’objectif** : Si vous souhaitez comparer une expérience basée sur le spécialiste du marketing aux modèles de personnalisation, une allocation de 10 % à 30 % au contrôle est recommandée. Lorsque vous sélectionnez une seule expérience comme contrôle, ce trafic n’est pas réparti sur toutes les offres ou expériences de l’activité.

* Les règles de ciblage doivent être appliquées avec autant de parcimonie que possible, car elles peuvent interférer avec la capacité d’optimisation du modèle.
* Les groupes de génération de rapports peuvent limiter le succès de votre activité [!UICONTROL Automated Personalization]. Utilisez les groupes de génération de rapports uniquement dans des conditions spécifiques :

   * Utilisez les groupes de génération de rapports uniquement si les conditions suivantes sont remplies :

      * Vous prévoyez de remplacer ou d’ajouter de nouvelles offres pendant l’exécution de l’activité.
      * Les offres du groupe de génération de rapports s’adressent aux mêmes visiteurs.
      * Les offres de ce groupe déclarant ont à peu près le même taux de réponse global.

   * Il n’existe aucune personnalisation entre les offres d’un groupe de génération de rapports. Les offres sont toutes traitées de la même manière par le modèle de personnalisation.
   * Ne placez jamais toutes les offres d’une activité dans un seul groupe de génération de rapports. De cette manière, toutes les offres sont diffusées de manière aléatoire et uniforme à tous les visiteurs de l’activité.

+++

## Quelles sont les limites de [!UICONTROL Automated Personalization] ? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Afficher les détails

[!DNL Target] a une limite stricte de 30 000 expériences, mais elle fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont créées.

Cette même limite est appliquée même lorsque l’activité a activé l’option [!UICONTROL Disalow Duplicates].

Pour plus d’informations sur les limites de caractères et d’autres limites (taille de l’offre, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et autres éléments dans [!DNL Target], voir [Limites](/help/main/r-troubleshooting-target/target-limits.md).

+++

## Comment le ciblage au niveau de l’offre est-il mis en œuvre ? {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Afficher les détails

À l’arrivée de chaque visiteur, l’ensemble des offres possibles que le visiteur peut voir est déterminé par les règles de ciblage au niveau de l’offre. Ensuite, l’algorithme choisit l’offre que le modèle prévoit comme ayant le meilleur chiffre d’affaires ou la meilleure chance de conversion attendus parmi ces offres. Le ciblage des offres affecte l’efficacité des algorithmes de machine learning [!DNL Target] et, par conséquent, doit être utilisé avec la plus grande parcimonie possible.

+++

## Pourquoi mon activité [!UICONTROL Automated Personalization] n’affiche-t-elle pas l’effet élévateur ? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Afficher les détails

Quatre facteurs sont requis pour qu’une activité [!UICONTROL Automated Personalization] génère une effet élévateur :

* Les offres de chaque emplacement doivent être suffisamment différentes pour influencer les visiteurs.
* Les emplacements doivent se trouver à un endroit qui fait la différence dans l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

La meilleure chose à faire est de tout d’abord de s’assurer que le contenu et les emplacements qui constituent les expériences de l’activité font vraiment la différence sur les taux de réponse globaux à l’aide d’une activité de [!UICONTROL A/B Test] simple et non personnalisée. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si les résultats des tests A/B montrent une augmentation statistiquement significative sur une ou plusieurs expériences, il est probable qu’une activité personnalisée réussisse. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres ou les emplacements n’ont pas un impact suffisamment important sur l’objectif d’optimisation pour être détectés avec une signification statistique.

Pour plus d’informations, [Résolution des problèmes d’Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## Comment alloue-t-[!UICONTROL Automated Personalization] le trafic de mon activité ? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Afficher les détails

[!UICONTROL Automated Personalization] dirige les visiteurs vers l’expérience qui a la mesure de succès prévue la plus élevée basée sur les derniers modèles [Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) créés pour chaque modèle. Cette prévision est fondée sur les informations spécifiques à chaque visiteur et sur le contexte de visite.

Supposons, par exemple, qu’une activité [!UICONTROL Automated Personalization] ait deux emplacements avec deux offres chacun. Sur le premier emplacement, l’offre A présente un taux de conversion prévu de 3 % pour un visiteur spécifique, tandis que l’offre B présente un taux de conversion prévu de 1 %. Sur le second emplacement, l’offre C présente un taux de conversion prévu de 2 % pour le même visiteur, tandis que l’offre D présente un taux de conversion prévu de 5 %. Par conséquent, [!UICONTROL Automated Personalization] offre à ce visiteur une expérience avec les offres A et D.

+++

## Quand dois-je arrêter mon activité [!UICONTROL Automated Personalization] ? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Afficher les détails

[!UICONTROL Automated Personalization] peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’est pas nécessaire d’arrêter votre activité [!UICONTROL Automated Personalization]. Si vous souhaitez apporter des modifications substantielles au contenu qui ne sont pas similaires aux offres actuellement dans votre activité de [!UICONTROL Automated Personalization], la bonne pratique consiste à démarrer une nouvelle activité. Le démarrage d’une nouvelle activité permet aux autres utilisateurs qui examinent les rapports de ne pas confondre ou mettre en relation des résultats antérieurs avec du contenu différent.

+++

## Combien de temps dois-je attendre la compilation des modèles ? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Afficher les détails

Le temps nécessaire aux modèles pour créer votre activité dépend généralement du trafic sur les emplacements d’activité sélectionnés et de la mesure de succès de votre activité. Utilisez l’[Estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) pour déterminer le temps estimé nécessaire aux modèles pour créer votre activité.

+++

## Un modèle est créé dans mon activité de [!UICONTROL Automated Personalization]. Les visites de cette expérience sont-elles personnalisées ? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Afficher les détails

Non, il doit exister au moins deux modèles créés au sein de votre activité pour que la personnalisation puisse débuter.

+++

## Quand puis-je consulter les résultats de mon activité [!UICONTROL Automated Personalization] ? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Afficher les détails

Vous pouvez commencer à consulter les résultats de votre activité [!UICONTROL Automated Personalization] après avoir créé au moins deux expériences avec des modèles (coche verte) pour l’expérience sur laquelle les modèles sont créés.

+++

## Comment puis-je réduire le temps nécessaire aux modèles pour créer mon activité [!UICONTROL Automated Personalization] ? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Afficher les détails

Passez en revue la configuration de votre activité et vérifiez si vous êtes prêt à apporter des modifications pour accélérer la création des modèles.

* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles.
* Existe-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité accélère la création de modèles.
* Existe-t-il une page à trafic plus élevé où cette activité serait plus réussie ? Plus il y a de trafic et de conversions dans les emplacements de vos activités, plus les modèles sont créés rapidement.

+++

## Pourquoi les visiteurs voient-ils des expériences pour une activité [!UICONTROL Automated Personalization] qu’ils ne devraient pas voir ? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Afficher les détails

[!UICONTROL Automated Personalization] activités sont évaluées une fois par session. Si des sessions actives se sont qualifiées pour une expérience particulière et que de nouvelles offres y ont été ajoutées, les visiteurs verront le nouveau contenu ainsi que les offres précédemment affichées. Comme ces visiteurs et visiteuses étaient précédemment qualifiés pour ces expériences, ils ou elles pourront toujours les voir au cours de la session. Pour évaluer ce paramètre à chaque visite de page, vous devez passer au type d’activité [!UICONTROL Experience Targeting] (XT) .

+++

## Puis-je modifier la mesure d’objectif au cours d’une activité [!UICONTROL Automated Personalization] ? {#change-metric}

+++Afficher les détails

[!DNL Adobe] ne recommande pas de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. [!DNL Adobe] ne garantissons pas les résultats obtenus si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

+++

## Puis-je utiliser l’option [!UICONTROL Reset Report Data] lors de l’exécution d’une activité [!UICONTROL Automated Personalization] ?

+++Afficher les détails

[!DNL Adobe] déconseille d&#39;utiliser l&#39;option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Automated Personalization]. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de [!UICONTROL Automated Personalization]. Au lieu d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Automated Personalization], créez une activité et désactivez l’activité d’origine. Ces orientations s’appliquent également aux activités de [!UICONTROL Auto-Allocate] et de [!UICONTROL Auto-Target].

+++

## Comment crée-[!UICONTROL Automated Personalization] des modèles en ce qui concerne les environnements ?

+++Afficher les détails

Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic diffusé de manière aléatoire par rapport à l’envoi de tout le trafic vers l’expérience gagnante globale. Ce modèle prend uniquement en compte les accès et les conversions dans l’environnement par défaut.

Le trafic provenant d’un second ensemble de modèles est créé pour chaque groupe de modélisation ([!UICONTROL Automated Personalization]) ou expérience ([!UICONTROL Auto-Target]). Pour chacun de ces modèles, les accès et les conversions dans tous les environnements sont pris en compte.

Les requêtes sont donc diffusées avec le même modèle, quel que soit l’environnement. Cependant, la pluralité du trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement réel.

+++
