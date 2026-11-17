---
keywords: résolution de problèmes;questions fréquentes;FAQ;FAQ;automated personalization;contrôle;expérience par défaut;bonnes pratiques
description: Explorez une liste de questions fréquentes (FAQ) et de réponses sur les activités [!UICONTROL Automated Personalization] (AP) dans [!UICONTROL Adobe Target].
title: Comment puis-je trouver des questions fréquentes sur les activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 6%
---
# FAQ sur Automated Personalization {#ap-faq}

>[!BEGINSHADEBOX]

**Sur cette page :** Trouvez des réponses aux questions fréquentes sur les activités **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Les questions et réponses suivantes portent sur la configuration des activités **[!UICONTROL Automated Personalization]** dans [!DNL Adobe Target], la création des modèles de personnalisation, l’affectation du trafic et la lecture des résultats.

## Configurer une activité {#set-up-an-activity}

+++ Quelles sont les bonnes pratiques pour configurer une activité [!UICONTROL Automated Personalization] ?

* Surveillez de près la *forme d’activité* (nombre d’emplacements × nombre d’offres), et pas seulement le nombre total d’expériences. Les combinaisons cartésiennes d’emplacements et d’offres affectent plus les performances au moment de la création que le nombre brut d’expériences. Pour des performances et une gérabilité optimales, limitez les activités de **[!UICONTROL Automated Personalization]** et de **[!UICONTROL ciblage automatique]** à 4 à 6 emplacements avec 4 à 6 offres par emplacement, comme décrit dans la question « Quelles sont les limites d’Automated Personalization ? » dans cette section. Des configurations plus volumineuses ne sont pas recommandées et peuvent ralentir le chargement ou la modification du **[!UICONTROL compositeur d’expérience visuelle]**.
* Pour personnaliser une page à faible trafic ou apporter des modifications structurelles à l’expérience que vous personnalisez, pensez à utiliser une [**[!UICONTROL activité de ciblage automatique &#x200B;]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) au lieu de&#x200B;**[!UICONTROL &#x200B; Automated Personalization &#x200B;]**.
* Envisagez d’exécuter une activité de **[!UICONTROL Test A/B]** entre les offres et les emplacements que vous prévoyez d’utiliser dans votre activité **[!UICONTROL Automated Personalization]**, afin de confirmer que les emplacements et les offres ont un impact sur l’objectif d’optimisation. Si l’activité de test **[!UICONTROL A/B]** ne parvient pas à démontrer une différence significative, **[!UICONTROL Automated Personalization]** ne parviendra probablement pas non plus à générer un effet élévateur.

  Si un test A/B...N ne montre aucune différence statistiquement significative entre les expériences, une ou plusieurs des situations suivantes sont probablement responsables :

  * Les offres ne sont probablement pas suffisamment différentes les unes des autres.
  * Les emplacements que vous avez sélectionnés n’ont aucune incidence sur la mesure de succès.
  * L’objectif d’optimisation se trouve trop loin dans le funnel de conversion pour être affecté par les offres sélectionnées.

* Utilisez l’[Estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) pour avoir une idée du temps nécessaire aux modèles de personnalisation pour créer votre activité **[!UICONTROL Automated Personalization]**.
* Décidez de l’affectation entre le trafic de contrôle et le trafic ciblé avant de commencer l’activité, en fonction de vos objectifs. Le tableau suivant répertorie les trois scénarios à prendre en compte, en fonction de l’objectif de votre activité et du type de contrôle que vous avez sélectionné.

  | Objectif de contrôle et d’activité | Allocation recommandée au contrôle | Détails |
  | --- | --- | --- |
  | **[!UICONTROL Expériences aléatoires]** comme contrôle. L’objectif est de tester l’efficacité de l’algorithme de personnalisation | 50% | Cet objectif nécessite une image plus précise de l’effet élévateur. Vous souhaitez également probablement comparer le taux de conversion de vos expériences ou offres avec le taux qu’un simple **[!UICONTROL Test A/B]** (un contrôle diffusé aléatoirement) donnerait. |
  | **[!UICONTROL Expériences aléatoires]** comme contrôle. L’objectif est de maximiser le trafic personnalisé | 10 % à 30 % | Utilisez cette option si vous maîtrisez l’algorithme et souhaitez personnaliser la quantité maximale de trafic. Le compromis est la précision de vos informations d’effet élévateur : les intervalles de confiance du trafic de contrôle sont plus grands, car moins de trafic y circule. |
  | **[!UICONTROL Expérience spécifique]** comme contrôle, avec l’un ou l’autre objectif | 10 % à 30 % | Utilisez cette option pour comparer une expérience spécifique axée sur les spécialistes marketing aux modèles de personnalisation. Lorsque vous sélectionnez une seule expérience comme contrôle, ce trafic n’est pas réparti sur chaque offre ou expérience de l’activité. |

* Utilisez les règles de ciblage avec la plus grande parcimonie possible, car elles peuvent interférer avec la capacité du modèle à s’optimiser. Pour plus d’informations, voir [Offres de personnalisation automatisée Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).
* Les groupes de génération de rapports peuvent limiter le succès de votre activité **[!UICONTROL Automated Personalization]**, utilisez-les donc uniquement dans des conditions spécifiques. Pour plus d’informations, voir [Offrir des groupes de génération de rapports dans Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

  * N’utilisez les groupes de génération de rapports que si toutes les conditions suivantes sont remplies :

    * Vous prévoyez de remplacer ou d’ajouter des offres pendant l’exécution de l’activité.
    * Les offres du groupe de génération de rapports s’adressent aux mêmes visiteurs.
    * Les offres du groupe de reporting ont à peu près le même taux de réponse global.

  * Il n’existe aucune personnalisation entre les offres d’un groupe de génération de rapports. Le modèle de personnalisation traite toutes les offres de la même manière.
  * Ne placez jamais toutes les offres d’une activité dans un seul groupe de génération de rapports. De cette manière, toutes les offres sont diffusées de manière aléatoire et uniforme à tous les visiteurs de l’activité.

+++

+++ Quelles sont les limites de [!UICONTROL Automated Personalization] ?

[!DNL Target] a une limite Hard de 30 000 expériences, mais il fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont créées. La même limite s’applique lorsque l’option **[!UICONTROL Interdire les doublons]** est activée pour l’activité.

Bien que les activités de **[!UICONTROL Automated Personalization]** et de **[!UICONTROL ciblage automatique]** puissent prendre en charge un grand nombre d’expériences, les performances de création dépendent fortement de la *forme d’activité* (nombre d’emplacements × nombre d’offres). Certaines configurations créent des combinaisons cartésiennes volumineuses qui peuvent avoir un impact significatif sur les performances de charge et de modification, même en dessous des limites d’expérience documentées.

Pour des performances et une gérabilité optimales, limitez les activités de **[!UICONTROL ciblage automatique]** et **[!UICONTROL Automated Personalization]** à 4-6 emplacements avec 4-6 offres par emplacement. Des configurations plus volumineuses ne sont pas recommandées et peuvent être restreintes dans l’interface utilisateur [!DNL Target].

Dans l’interface utilisateur [!DNL Target] actuelle, les activités **[!UICONTROL Automated Personalization]** et **[!UICONTROL Ciblage automatique]** sont configurées directement dans l’étape **[!UICONTROL Expériences]**. [!DNL Target] peut afficher des avertissements intégrés ou vous empêcher d’enregistrer une activité lorsque la configuration dépasse les seuils pris en charge et revalide la forme de l’activité sur **[!UICONTROL Suivant]**, **[!UICONTROL Enregistrer]** et **[!UICONTROL Publier]**.

Pour plus d&#39;informations sur les limites de caractères et d&#39;autres limites (taille de l&#39;offre, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et autres éléments dans [!DNL Target], consultez [Limites](/help/main/r-troubleshooting-target/target-limits.md).

+++

+++ Puis-je spécifier une expérience spécifique à utiliser comme contrôle dans une activité [!UICONTROL Automated Personalization] ?

Vous pouvez sélectionner une expérience spécifique à utiliser comme contrôle lors de la création d’une activité de [**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP) ou de [**[!UICONTROL ciblage automatique]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer l’ensemble du trafic de contrôle vers cette expérience, en fonction du pourcentage d’affectation du trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle sur cette expérience.

Pour plus d&#39;informations, voir [Sélectionner l&#39;expérience de pilotage](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

+++ Comment le ciblage au niveau de l’offre est-il mis en œuvre ?

Lorsque chaque visiteur ou visiteuse arrive, les règles de ciblage au niveau de l’offre déterminent le jeu d’offres que le visiteur ou la visiteuse peut voir. L’algorithme choisit ensuite, parmi ces offres, celle que le modèle prédit avoir le meilleur chiffre d’affaires ou la meilleure chance de conversion attendu. Le ciblage des offres affecte l’efficacité des algorithmes de machine learning de [!DNL Target]. Utilisez-les donc avec le moins de précautions possible. Pour plus d’informations, voir [Offres de personnalisation automatisée Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

+++

## Création de modèles et affectation du trafic {#models-and-traffic}

+++ Comment [!UICONTROL Automated Personalization] alloue-t-il le trafic de mon activité ?

**[!UICONTROL Automated Personalization]** achemine les visiteurs vers l’expérience qui a la mesure de succès prévue la plus élevée, en fonction des [modèles de forêt aléatoire](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) les plus récents. Cette prévision est basée sur les informations spécifiques et le contexte de visite du visiteur.

Supposons, par exemple, qu’une activité **[!UICONTROL Automated Personalization]** ait deux emplacements avec deux offres chacun. Sur le premier emplacement, l’offre A présente un taux de conversion prévu de 3 % pour un visiteur spécifique, tandis que l’offre B présente un taux de conversion prévu de 1 %. Sur le second emplacement, l’offre C présente un taux de conversion prévu de 2 % pour le même visiteur, tandis que l’offre D présente un taux de conversion prévu de 5 %. Par conséquent, **[!UICONTROL Automated Personalization]** offre à ce visiteur une expérience avec l’offre A et l’offre D.

+++

+++ Comment [!UICONTROL Automated Personalization] crée-t-il des modèles en ce qui concerne les environnements ?

Un modèle est conçu pour identifier les performances de la stratégie personnalisée par rapport au trafic diffusé de manière aléatoire par rapport à l’envoi de tout le trafic vers l’expérience gagnante globale. Ce modèle prend uniquement en compte les accès et les conversions dans l’environnement par défaut.

Un deuxième ensemble de modèles est créé pour chaque groupe de rapports (**[!UICONTROL Automated Personalization]**) ou expérience (**[!UICONTROL Ciblage automatique]**). Pour chacun de ces modèles, les accès et les conversions dans tous les environnements sont pris en compte.

Les requêtes sont donc diffusées avec le même modèle, quel que soit l’environnement. Cependant, la pluralité du trafic doit provenir de l’environnement par défaut pour s’assurer que l’expérience gagnante globale identifiée est cohérente avec le comportement réel.

+++

+++ Combien de temps dois-je attendre la compilation des modèles ?

Le temps nécessaire aux modèles pour créer votre activité dépend généralement du trafic vers les emplacements d’activité sélectionnés et de la mesure de succès de votre activité. Utilisez l’[estimateur de trafic](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) pour déterminer le temps attendu nécessaire aux modèles pour créer votre activité.

+++

+++ Comment puis-je réduire le temps nécessaire aux modèles pour créer mon activité [!UICONTROL Automated Personalization] ?

Consultez la configuration de votre activité pour identifier les modifications qui améliorent la vitesse de création des modèles. Par exemple, remplacez une mesure de succès RPV par une conversion, choisissez une mesure de succès plus proche de vos expériences d’activité dans le funnel des ventes, supprimez certaines expériences de l’activité ou utilisez une page à trafic plus élevé. Pour plus d&#39;informations, voir [Dépannage d&#39;Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ Un modèle est créé dans mon activité [!UICONTROL Automated Personalization]. Les visites de cette expérience sont-elles personnalisées ?

Non. Au moins deux modèles doivent être créés dans votre activité pour que la personnalisation puisse commencer.

+++

## Résultats et effet élévateur {#results-and-lift}

+++ Quand puis-je consulter les résultats de mon activité [!UICONTROL Automated Personalization] ?

Vous pouvez commencer à consulter les résultats de votre activité **[!UICONTROL Automated Personalization]** après la création de modèles pour au moins deux expériences (indiquées par une coche verte).

+++

+++ Pourquoi mon activité [!UICONTROL Automated Personalization] n’affiche-t-elle pas d’effet élévateur ?

Quatre facteurs sont requis pour qu’une activité **[!UICONTROL Automated Personalization]** génère un effet élévateur :

* Les offres de chaque emplacement doivent être suffisamment différentes pour influencer les visiteurs.
* Les emplacements doivent se trouver à un endroit qui fait la différence dans l’objectif d’optimisation.
* Le trafic et la puissance statistique de l’activité doivent être suffisants pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

La meilleure solution consiste d’abord à s’assurer, à l’aide d’une activité de **[!UICONTROL Test A/B]** simple et non personnalisée, que le contenu et les emplacements qui constituent les expériences de l’activité font réellement la différence sur les taux de réponse globaux. Pour la procédure complète, voir [Dépannage d’Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ Comment puis-je comparer [!UICONTROL Automated Personalization] à une expérience par défaut ?

Il n’existe pas d’option clé en main permettant de comparer **[!UICONTROL Automated Personalization]** à une expérience par défaut. Pour pallier ce problème, s’il existe une offre ou une expérience par défaut dans le cadre de l’activité, cliquez sur le segment **[!UICONTROL Contrôle]** dans les rapports et recherchez cette offre dans le rapport au niveau de l’offre qui en résulte. Le taux de conversion enregistré pour cette offre peut être comparé au taux de conversion de l’ensemble du segment « Forêt aléatoire ». Cette comparaison montre les performances du modèle par rapport à l’offre par défaut.

+++

## Gestion d’une activité dynamique {#manage-live-activity}

+++ Quand dois-je arrêter mon activité [!UICONTROL Automated Personalization] ?

**[!UICONTROL Automated Personalization]** peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’est pas nécessaire d’arrêter votre activité **[!UICONTROL Automated Personalization]**. Si vous souhaitez apporter des modifications substantielles au contenu qui ne sont pas similaires aux offres actuellement dans votre activité, la bonne pratique consiste à démarrer une nouvelle activité. Le démarrage d’une nouvelle activité permet aux autres utilisateurs qui examinent les rapports d’éviter de confondre ou de mettre en relation des résultats antérieurs avec du contenu différent.

+++

+++ Puis-je modifier la mesure d’objectif au cours d’une activité [!UICONTROL Automated Personalization] ?

[!DNL Adobe] ne recommande pas de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur [!DNL Target], démarrez toujours une nouvelle activité à la place. [!DNL Adobe] ne garantit pas ce qui se produit si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’**[!UICONTROL affectation automatique]**, de **[!UICONTROL ciblage automatique]** et d’**[!UICONTROL Automated Personalization]** qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

+++

+++ Puis-je utiliser l’option [!UICONTROL Réinitialiser les données du rapport] lors de l’exécution d’une activité [!UICONTROL Automated Personalization] ?

[!DNL Adobe] ne recommande pas d’utiliser l’option **[!UICONTROL Réinitialiser les données du rapport]** pour les activités **[!UICONTROL Automated Personalization]**. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle **[!UICONTROL Automated Personalization]**. Au lieu d’utiliser l’option **[!UICONTROL Réinitialiser les données du rapport]**, créez une activité et désactivez l’activité d’origine. Ces conseils s’appliquent également aux activités d’**[!UICONTROL affectation automatique]** et de **[!UICONTROL ciblage automatique]**.

+++

+++ Pourquoi les visiteurs voient-ils des expériences pour une activité [!UICONTROL Automated Personalization] qu’ils ne devraient pas voir ?

Les activités **[!UICONTROL Automated Personalization]** sont évaluées une fois par session. Si des sessions actives se sont qualifiées pour une expérience particulière et que de nouvelles offres y ont été ajoutées depuis, les visiteurs voient le nouveau contenu ainsi que les offres précédemment affichées. Ces visiteurs étaient précédemment qualifiés pour ces expériences. Ils voient donc toujours ces expériences au cours de la session. Pour évaluer l’activité à chaque visite de page, modifiez le type d’activité **[!UICONTROL Ciblage d’expérience]** (XT).

+++
