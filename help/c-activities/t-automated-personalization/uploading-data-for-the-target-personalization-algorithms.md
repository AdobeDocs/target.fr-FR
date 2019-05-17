---
description: Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension de l’attrition client, peuvent être extrêmement utiles pour la création des modèles de personnalisation.
seo-description: Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension de l’attrition client, peuvent être extrêmement utiles pour la création des modèles de personnalisation.
seo-title: Chargement de données pour les algorithmes de personnalisation de Target
solution: Target
title: Chargement de données pour les algorithmes de personnalisation de Target
topic: Premium
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Chargement de données pour les algorithmes de personnalisation de Target{#upload-data-for-target-s-personalization-algorithms}

Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension de l’attrition client, peuvent être extrêmement utiles pour la création des modèles de personnalisation.

Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation de personnalisation automatisée et de ciblage automatique. Outre les méthodes figurant dans  [Les méthodes permettant d’intégrer des données dans Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), les audiences partagées Experience Cloud (Adobe Analytics, gestion de l’audience) et les audiences avec création de rapports dans l’activité sont également utilisées dans nos algorithmes.

Pour plus d’informations sur les données collectées automatiquement et utilisées par les algorithmes Personnalisation automatisée de Target, voir [Collecte de données de personnalisation automatisée](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Bonnes pratiques {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La liste suivante présente les bonnes pratiques de téléchargement de données pour les algorithmes de personnalisation Target :

* Plus il y a de données de haute qualité disponibles pour les algorithmes de personnalisation Target, meilleure est la qualité des modèles résultants dans vos activités PA et de ciblage automatique.
* Limitez l’utilisation d’attributs ou de scripts de profil multiples servant le même objectif.
* Ne transmettez pas d’ID unique, tel qu’un ID de session, si cela n’est pas nécessaire.
* Examinez les données que Target collecte automatiquement ( [Collecte de données pour les algorithmes de personnalisation de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)) afin de ne pas envoyer deux fois les mêmes informations. Par exemple, Target utilise des adresses IP pour déterminer les codes postaux des visiteurs. Il n’est pas nécessaire de transmettre ces informations sous la forme d’une variable distincte.
* Ne transmettez pas plusieurs valeurs dans le même attribut/la même variable. Si plusieurs variables sont concaténées, les algorithmes de personnalisation Target traitent chaque chaîne comme une valeur unique, réduisant ainsi la valeur des informations à personnaliser.
* Utilisez une convention d’attribution de nom mémorisable et explicite pour faire votre choix  [Rapports Informations sur la personnalisation](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) plus compréhensibles.

