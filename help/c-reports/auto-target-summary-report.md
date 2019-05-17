---
description: Informations sur la manière d’interpréter le rapport de synthèse de ciblage automatique.
keywords: rapports;ciblage automatique;ciblage automatique;AT
seo-description: Informations sur la manière d’interpréter le rapport de synthèse de ciblage automatique.
seo-title: Rapport de synthèse de ciblage automatique
solution: Target
subtopic: Test multivarié
title: Rapport de synthèse de ciblage automatique
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Rapport de synthèse de ciblage automatique{#auto-target-summary-report}

Informations sur la manière d’interpréter le rapport de synthèse de ciblage automatique.

L’illustration ci-après indique à quoi ressemble un rapport récapitulatif typique lorsque vous utilisez le ciblage automatique :

![](assets/autotarget.png)

Quelques conseils et considérations lorsque vous interprétez vos rapports de ciblage automatique :

* Les différentes lignes du tableau permettent de mieux comprendre les performances de l’activité.

   * Les deux premières lignes du tableau affiché sur la page du rapport présentent les résultats d’un test A/B entre les visiteurs qui ont été affectés au groupe témoin (c’est-à-dire des expériences livrées au hasard) et les visiteurs qui ont été affectés à l’algorithme de personnalisation. Ces informations permettent de mesurer les performances de l’algorithme de personnalisation par rapport au contrôle délivré au hasard.
   * Les lignes restantes affichent les résultats au niveau de l’expérience. Pour chaque expérience, il existe une comparaison entre la réponse moyenne des visiteurs qui ont assisté à cette expérience servie par un contrôle au hasard et la réponse moyenne des visiteurs qui ont assisté à l’expérience via l’algorithme de personnalisation.

* L’icône de vérification verte en regard du nom de chaque expérience dans le rapport indique qu’un modèle d’apprentissage automatique personnalisé a été généré pour cette expérience. L’icône d’horloge indique que le trafic diffusé n’a pas été suffisant pour générer le modèle.

   * Étant donné que le modèle est construit par l’expérience, il est possible de voir un modèle avec certaines expériences comportant une coche verte et d’autres avec une icône d’horloge.
   * Dans ce cas, pour augmenter la rapidité de construction des modèles par l’activité pour toutes les expériences, le trafic supplémentaire est envoyé aux expériences associées à des modèles non construits.
   * Il doit exister au moins deux expériences comportant des modèles construits (identifiés par une coche verte) pour que la personnalisation puisse débuter.

* Le fait de comparer le taux de conversion de l’expérience A à celui de l’expérience B ne génère pas la comparaison adéquate dans le ciblage automatique. La question est de savoir si l’expérience A fonctionne mieux lorsqu’elle est servie de manière intelligente que de manière aléatoire (autrement dit, par rapport au témoin). Les spécialistes marketing doivent également être prudents dans leur interprétation des effets élévateurs émanant des expériences individuelles, car l’algorithme de personnalisation cherche à optimiser la mesure de succès sur l’ensemble de l’activité, et non sur chaque expérience individuelle.
* Les expériences présentant l’effet élévateur le plus élevé peuvent être interprétées comme ayant la différenciation la plus élevée dans la population. Ceci indique que l’algorithme a trouvé un segment qui aime davantage cette expérience particulière.

