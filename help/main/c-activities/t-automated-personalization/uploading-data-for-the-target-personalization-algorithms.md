---
keywords: Automated Personalization;ap;charger des données;données hors ligne;algorithme de personnalisation;ciblage automatique;ciblage automatique;bonnes pratiques
description: Découvrez comment charger des données hors ligne lors de la création de modèles de personnalisation dans des activités  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target].
title: Comment télécharger des données pour les algorithmes de Personalization ?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 10%

---

# Chargement de données pour les algorithmes de personnalisation [!DNL Target]

Les données hors ligne, telles que les informations CRM ou les scores de propension à l’attrition client, peuvent s’avérer extrêmement précieuses lors de la création de modèles de personnalisation dans des activités [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target].

Il existe plusieurs façons de saisir des données dans [!UICONTROL Automated Personalization] (AP) et de [!UICONTROL Auto-Target] des algorithmes de personnalisation. Outre les méthodes de la section [Méthodes pour importer des données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}, [!DNL Experience Cloud] audiences partagées ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) et les audiences de création de rapports en activité sont également utilisées dans les algorithmes de [!DNL Target].

Pour plus d’informations sur les données automatiquement collectées et utilisées par les algorithmes de personnalisation [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target], voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bonnes pratiques {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La liste suivante présente les bonnes pratiques pour le chargement de données pour les algorithmes de personnalisation [!DNL Target] :

* Plus les données disponibles pour [!DNL Target] les algorithmes de personnalisation sont de haute qualité, meilleure est la qualité des modèles résultants dans vos activités de [!UICONTROL Automated Personalization] et de [!UICONTROL Auto-Target].
* Limitez l’utilisation d’attributs ou de scripts de profil multiples servant le même objectif.
* Ne transmettez pas d’ID unique, tel qu’un ID de session si nécessaire.
* Vérifiez les données que [!DNL Target] collecte automatiquement ( [collecte de données pour les algorithmes Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) afin de ne pas envoyer d’informations en double. Par exemple, [!DNL Target] utilise des adresses IP pour déterminer les codes postaux des visiteurs. Il n’est pas nécessaire de transmettre ces informations sous la forme d’une variable distincte.
* Ne transmettez pas plusieurs valeurs dans le même attribut ou la même variable. Si plusieurs variables sont concaténées, [!DNL Target] algorithmes de personnalisation traitent chaque chaîne comme une valeur unique, ce qui réduit la valeur des informations à personnaliser.
* Utilisez une convention de nommage mémorisable et significative pour rendre vos [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) plus compréhensibles.
