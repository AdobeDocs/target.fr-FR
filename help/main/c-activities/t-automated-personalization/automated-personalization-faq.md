---
keywords: dépannage;questions fréquentes;FAQ;FAQ;personnalisation automatisée;contrôle;expérience par défaut;bonnes pratiques
description: Consultez la liste des questions fréquentes et des réponses sur les activités [!UICONTROL Automated Personalization] (AP) dans [!UICONTROL Adobe Target].
title: Comment puis-je trouver des questions fréquentes sur les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 22%

---

# Questions fréquentes sur Automated Personalization

Consultez les questions fréquentes et réponses suivantes lorsque vous utilisez des activités [!UICONTROL Automated Personalization] dans [!DNL Adobe Target].

## Puis-je spécifier une expérience spécifique à utiliser comme contrôle dans une activité [!UICONTROL Automated Personalization] ?

+++Voir les détails

Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d’une activité [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## Comment comparer [!UICONTROL Automated Personalization] à une expérience par défaut ? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Voir les détails

Il n’existe pas d’option clé en main pour comparer [!UICONTROL Automated Personalization] à une expérience par défaut. Cependant, si une offre ou une expérience par défaut fait partie de l’activité globale, pour comprendre ses performances de base, cliquez sur le segment &quot;[!UICONTROL Control]&quot; dans les rapports et recherchez cette offre dans le rapport au niveau de l’offre qui en résulte. Le taux de conversion enregistré pour cette offre peut être utilisé pour comparer le taux de conversion de l’ensemble du segment &quot;Forêt aléatoire&quot;. Il est ainsi plus facile de comparer les performances de la machine par rapport à l’offre par défaut.

+++

## Quelles sont les bonnes pratiques pour configurer une activité [!UICONTROL Automated Personalization] ? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Voir les détails

* Si vous souhaitez personnaliser une page à faible trafic ou apporter des modifications structurelles à l’expérience que vous personnalisez, envisagez d’utiliser une activité [!UICONTROL Auto-Target] à la place de [!UICONTROL Automated Personalization]. Voir [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Envisagez d’exécuter une activité [!UICONTROL A/B Test] entre les offres et les emplacements que vous prévoyez d’utiliser dans votre activité [!UICONTROL Automated Personalization] afin de vous assurer que l’emplacement et les offres ont un impact sur l’objectif d’optimisation. Si une activité [!UICONTROL A/B Test] ne montre pas de différence significative, [!UICONTROL Automated Personalization] ne réussira probablement pas non plus à générer un effet élévateur.

   * Si un test A/B...N ne montre aucune différence statistiquement significative entre les expériences, une ou plusieurs des situations suivantes sont probablement responsables :

      * Les offres ne sont probablement pas suffisamment différentes les unes des autres.
      * Les emplacements que vous avez sélectionnés n’ont aucune incidence sur la mesure de succès.
      * L’objectif d’optimisation est trop loin dans l’entonnoir de conversion pour être affecté par les offres que vous avez sélectionnées.

* Veillez à utiliser l’ [estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin que vous puissiez avoir une idée du temps nécessaire à la compilation des modèles de personnalisation dans votre activité [!UICONTROL Automated Personalization].
* Déterminez l’affectation entre le contrôle et le ciblage avant de commencer l’activité, en fonction de vos objectifs.

  Il existe trois scénarios à prendre en compte en fonction de l’objectif de votre activité et du type de contrôle que vous avez sélectionné :

   * **Expériences aléatoires comme contrôle et l’objectif de votre activité est de tester l’efficacité de l’algorithme de personnalisation** : si votre objectif est d’évaluer l’algorithme de personnalisation, vous souhaitez obtenir une image plus précise de l’effet élévateur. Il est également probable que vous souhaitiez comparer le taux de conversion de vos expériences ou offres si vous avez simplement effectué une [!UICONTROL A/B Test] (contrôle diffusé de manière aléatoire). Dans ce cas, il est recommandé d’utiliser une allocation de 50 % à un contrôle d’expériences diffusées de manière aléatoire.
   * **&quot;Expériences aléatoires&quot; en tant que contrôle et l’objectif de votre activité est d’optimiser le trafic personnalisé** : si vous êtes à l’aise avec l’algorithme et que vous souhaitez personnaliser le volume maximal de trafic, une allocation de 10 à 30 % au contrôle est recommandée. Le compromis ici est la précision que vous voyez dans les informations de l’effet élévateur. Les intervalles de confiance de votre trafic de contrôle sont plus importants, car le trafic qui leur est affecté est moins important.
   * **Expérience spécifique comme contrôle, avec l’un ou l’autre type d’objectif** : Si vous souhaitez comparer une expérience basée sur le spécialiste du marketing aux modèles de personnalisation, une allocation de 10 % à 30 % au contrôle est recommandée. Lorsque vous sélectionnez une seule expérience comme contrôle, ce trafic n’est pas réparti sur toutes les offres ou expériences de l’activité.

* Les règles de ciblage doivent être appliquées avec autant de parcimonie que possible, car elles peuvent interférer avec la capacité d’optimisation du modèle.
* Les groupes de génération de rapports peuvent limiter le succès de votre activité [!UICONTROL Automated Personalization]. Utilisez des groupes de génération de rapports uniquement dans des conditions spécifiques :

   * Utilisez les groupes de génération de rapports uniquement si les conditions suivantes sont remplies :

      * Vous prévoyez de remplacer ou d’ajouter de nouvelles offres pendant l’exécution de l’activité.
      * Les offres du groupe de génération de rapports s’adressent aux mêmes visiteurs.
      * Les offres de ce groupe de génération de rapports ont à peu près le même taux de réponse global.

   * Il n’existe aucune personnalisation entre les offres d’un groupe de génération de rapports. Les offres sont toutes traitées comme identiques par le modèle de personnalisation.
   * Ne placez jamais toutes les offres d’une activité dans un seul groupe de génération de rapports. Cela entraîne la diffusion aléatoire uniforme de toutes les offres à tous les visiteurs de l’activité.

+++

## Quelles sont certaines limites dans [!UICONTROL Automated Personalization] ? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Voir les détails

[!DNL Target] a une limite de 30 000 expériences, mais fonctionne au mieux lorsque moins de 10 000 expériences sont créées.

Cette même limite est appliquée même lorsque l’activité a activé l’option [!UICONTROL Disalow Duplicates].

Pour plus d’informations sur les limites de caractères et autres limites (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et autres éléments dans [!DNL Target], voir [Limites](/help/main/r-troubleshooting-target/target-limits.md).

+++

## Comment le ciblage au niveau de l’offre est-il mis en œuvre ? {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Voir les détails

À l’arrivée de chaque visiteur, l’ensemble des offres possibles que le visiteur peut voir est déterminé par les règles de ciblage au niveau de l’offre. Ensuite, l’algorithme sélectionne l’offre prédite par le modèle qui présente les meilleures recettes attendues ou les meilleures chances de conversion parmi ces offres. Le ciblage des offres a un impact sur l’efficacité des algorithmes d’apprentissage automatique [!DNL Target] et, par conséquent, doit être utilisé avec le moins de parcimonie possible.

+++

## Pourquoi mon activité [!UICONTROL Automated Personalization] n’affiche-t-elle pas l’effet élévateur ? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Voir les détails

Quatre facteurs sont nécessaires pour qu’une activité [!UICONTROL Automated Personalization] génère un effet élévateur :

* Les offres de chaque emplacement doivent être suffisamment différentes pour influencer les visiteurs.
* Les emplacements doivent être situés quelque part qui font une différence dans l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

Le meilleur plan d’action consiste d’abord à s’assurer que le contenu et les emplacements qui composent les expériences de l’activité font réellement une différence par rapport aux taux de réponse globaux à l’aide d’une activité simple non personnalisée [!UICONTROL A/B Test]. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si les résultats du test A/B présentent un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée soit réussie. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres ou les emplacements n’ont pas un impact suffisant sur l’objectif d’optimisation à détecter avec une signification statistique.

Pour plus d’informations, voir [Dépannage d’Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## Comment [!UICONTROL Automated Personalization] alloue-t-il le trafic de mon activité ? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Voir les détails

[!UICONTROL Automated Personalization] dirige les visiteurs vers l’expérience dont la mesure de succès est la plus élevée en fonction des modèles [Forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) les plus récents créés pour chaque modèle. Cette prévision est fondée sur les informations spécifiques à chaque visiteur et sur le contexte de visite.

Supposons, par exemple, qu’une activité [!UICONTROL Automated Personalization] ait deux emplacements comportant deux offres chacun. Sur le premier emplacement, l’offre A présente un taux de conversion prévu de 3 % pour un visiteur spécifique, tandis que l’offre B présente un taux de conversion prévu de 1 %. Sur le second emplacement, l’offre C présente un taux de conversion prévu de 2 % pour le même visiteur, tandis que l’offre D présente un taux de conversion prévu de 5 %. Par conséquent, [!UICONTROL Automated Personalization] offre à ce visiteur une expérience avec l’offre A et l’offre D.

+++

## Quand dois-je arrêter mon activité [!UICONTROL Automated Personalization] ? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Voir les détails

[!UICONTROL Automated Personalization] peut être utilisé comme une personnalisation &quot;toujours active&quot; qui optimise constamment. En particulier pour le contenu sans cesse renouvelé, il n’est pas nécessaire d’arrêter votre activité [!UICONTROL Automated Personalization]. Si vous souhaitez apporter des modifications substantielles au contenu qui ne sont pas similaires aux offres actuellement dans votre activité [!UICONTROL Automated Personalization], la bonne pratique consiste à démarrer une nouvelle activité. Le démarrage d’une nouvelle activité permet à d’autres utilisateurs qui visualisent des rapports de ne pas confondre ou associer des résultats antérieurs à un contenu différent.

+++

## Combien de temps dois-je attendre la compilation des modèles ? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Voir les détails

Le temps nécessaire à la compilation des modèles dans votre activité dépend généralement du trafic vers les emplacements d’activité sélectionnés et de la mesure de succès de votre activité. Utilisez l’ [ estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) pour déterminer le temps nécessaire à la compilation des modèles dans votre activité.

+++

## Un modèle est créé dans mon activité [!UICONTROL Automated Personalization]. Les visites de cette expérience sont-elles personnalisées ? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Voir les détails

Non, il doit exister au moins deux modèles créés au sein de votre activité pour que la personnalisation puisse débuter.

+++

## Quand puis-je consulter les résultats de mon activité [!UICONTROL Automated Personalization] ? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Voir les détails

Vous pouvez commencer à consulter les résultats de votre activité [!UICONTROL Automated Personalization] après avoir créé au moins deux expériences avec des modèles (coche verte) pour l’expérience dont les modèles sont construits.

+++

## Comment puis-je réduire le temps nécessaire à la compilation des modèles dans mon activité [!UICONTROL Automated Personalization] ? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Voir les détails

Vérifiez la configuration de votre activité et vérifiez si vous êtes prêt à apporter des modifications pour améliorer la vitesse de compilation des modèles.

* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles.
* Existe-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité accélère le temps de création des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus le trafic et les conversions sont importants dans les emplacements de vos activités, plus les modèles sont rapides à générer.

+++

## Pourquoi les visiteurs voient-ils des expériences pour une activité [!UICONTROL Automated Personalization] qu’ils ne devraient pas voir ? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Voir les détails

Les activités [!UICONTROL Automated Personalization] sont évaluées une fois par session. S’il existe des sessions actives qui se sont qualifiées pour une expérience particulière et que de nouvelles offres y ont été ajoutées, les visiteurs verront le nouveau contenu ainsi que les offres précédemment affichées. Comme ces visiteurs étaient auparavant qualifiés pour ces expériences, ils voient toujours ces expériences au cours de la session. Pour l’évaluer à chaque visite de page, vous devez passer au type d’activité [!UICONTROL Experience Targeting] (XT).

+++

## Puis-je modifier la mesure d’objectif à mi-chemin d’une activité [!UICONTROL Automated Personalization] ? {#change-metric}

+++Voir les détails

[!DNL Adobe] ne vous recommande pas de modifier la mesure d’objectif à mi-chemin d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. [!DNL Adobe] ne garantit pas ce qui se passe si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Automated Personalization] qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source des rapports.

+++

## Puis-je utiliser l’option [!UICONTROL Reset Report Data] lors de l’exécution d’une activité [!UICONTROL Automated Personalization] ?

+++Voir les détails

[!DNL Adobe] ne recommande pas d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Automated Personalization]. Bien qu’elle supprime les données de rapport visibles, cette option ne supprime pas tous les enregistrements d’entraînement du modèle [!UICONTROL Automated Personalization]. Au lieu d’utiliser l’option [!UICONTROL Reset Report Data] pour les activités [!UICONTROL Automated Personalization], créez une activité et désactivez l’activité d’origine. Cette recommandation s’applique également aux activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].

+++

## Comment [!UICONTROL Automated Personalization] crée-t-il des modèles par rapport aux environnements ?

+++Voir les détails

Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic diffusé de manière aléatoire plutôt que d’envoyer tout le trafic à l’expérience gagnante globale. Ce modèle ne prend en compte que les accès et les conversions dans l’environnement par défaut.

Le trafic provenant d’un deuxième ensemble de modèles est créé pour chaque groupe de modélisation ([!UICONTROL Automated Personalization]) ou expérience ([!UICONTROL Auto-Target]). Pour chacun de ces modèles, les accès et les conversions sont pris en compte dans tous les environnements.

Les requêtes sont donc servies avec le même modèle, quel que soit leur environnement. Cependant, la pluralité du trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement du monde réel.

+++
