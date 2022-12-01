---
keywords: Automated Personalization;ap;télécharger des données;données hors ligne;algorithme de personnalisation;ciblage automatique;ciblage automatique;bonnes pratiques
description: Découvrez comment charger des données hors ligne, telles que des informations de gestion de la relation client, lors de la création de modèles de personnalisation dans Adobe [!DNL Target] Activités Automated Personalization (AP).
title: Comment télécharger des données pour les algorithmes de personnalisation ?
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 65%

---

# Chargement de données pour le [!DNL Target] algorithmes de personnalisation

Les données hors ligne, telles que les informations de gestion de la relation client ou les scores de propension à l’attrition des clients, peuvent s’avérer particulièrement utiles lors de la création de modèles de personnalisation dans [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP).

Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation de [!UICONTROL personnalisation automatisée] et de [!UICONTROL ciblage automatique. ] Outre les méthodes de la section [Méthodes de transfert de données dans Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}, les audiences partagées Experience Cloud (Adobe Analytics, Gestion de l’audience){target=_blank} et les audiences de création de rapports dans l’activité sont également utilisées dans nos algorithmes.

Pour plus d’informations sur les données collectées automatiquement et utilisées par les algorithmes Personnalisation automatisée de Target, voir [Collecte de données de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bonnes pratiques {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La liste suivante présente les bonnes pratiques de téléchargement de données pour les algorithmes de personnalisation Target :

* Plus il y a de données de haute qualité disponibles pour les algorithmes de personnalisation Target, meilleure est la qualité des modèles résultants dans vos activités PA et de ciblage automatique.
* Limitez l’utilisation d’attributs ou de scripts de profil multiples servant le même objectif.
* Ne transmettez pas d’ID unique, tel qu’un ID de session, si cela n’est pas nécessaire.
* Examinez les données que Target collecte automatiquement ( [Collecte de données pour les algorithmes de personnalisation de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) afin de ne pas envoyer deux fois les mêmes informations. Par exemple, Target utilise des adresses IP pour déterminer les codes postaux des visiteurs. Il n’est pas nécessaire de transmettre ces informations sous la forme d’une variable distincte.
* Ne transmettez pas plusieurs valeurs dans le même attribut/la même variable. Si plusieurs variables sont concaténées, les algorithmes de personnalisation Target traitent chaque chaîne comme une valeur unique, réduisant ainsi la valeur des informations à personnaliser.
* Utilisez une convention d’attribution de nom mémorisable et explicite pour faire votre choix [Rapports Informations sur la personnalisation](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) plus compréhensibles.
