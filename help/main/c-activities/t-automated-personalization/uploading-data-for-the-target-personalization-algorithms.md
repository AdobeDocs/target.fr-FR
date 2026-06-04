---
keywords: Automated Personalization;ap;charger des données;données hors ligne;algorithme de personnalisation;ciblage automatique;ciblage automatique;bonnes pratiques
description: Découvrez comment charger des données hors ligne lors de la création de modèles de personnalisation dans les activités  [!DNL Adobe Target] [!UICONTROL ] (AP) et [!UICONTROL Ciblage automatique].
title: Comment télécharger des données pour les algorithmes de Personalization ?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 323
ht-degree: 12%

---

# Chargement de données pour les algorithmes de personnalisation [!DNL Target]

Les données hors ligne, telles que les informations CRM ou les scores de propension à l’attrition client, peuvent s’avérer extrêmement précieuses lors de la création de modèles de personnalisation dans [!DNL Adobe Target] activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique].

Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation  (AP) et [!UICONTROL Ciblage automatique]. Outre les méthodes de la section [Méthodes pour importer des données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}, [!DNL Experience Cloud] audiences partagées ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) et les audiences de création de rapports en activité sont également utilisées dans les algorithmes [!DNL Target].

Pour plus d’informations sur les données automatiquement collectées et utilisées par les algorithmes de personnalisation  et [!UICONTROL Ciblage automatique], consultez [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bonnes pratiques {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La liste suivante présente les bonnes pratiques pour le chargement de données pour les algorithmes de personnalisation [!DNL Target] :

* Plus la qualité des données disponibles pour [!DNL Target] les algorithmes de personnalisation est élevée, plus les modèles obtenus dans vos activités [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] sont de qualité.
* Limitez l’utilisation d’attributs ou de scripts de profil multiples servant le même objectif.
* Ne transmettez pas d’ID unique, tel qu’un ID de session si nécessaire.
* Vérifiez les données que [!DNL Target] collecte automatiquement ( [collecte de données pour les algorithmes Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) afin de ne pas envoyer d’informations en double. Par exemple, [!DNL Target] utilise des adresses IP pour déterminer les codes postaux des visiteurs. Il n’est pas nécessaire de transmettre ces informations sous la forme d’une variable distincte.
* Ne transmettez pas plusieurs valeurs dans le même attribut ou la même variable. Si plusieurs variables sont concaténées, [!DNL Target] algorithmes de personnalisation traitent chaque chaîne comme une valeur unique, ce qui réduit la valeur des informations à personnaliser.
* Utilisez une convention de nommage mémorisable et significative pour rendre vos [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) plus compréhensibles.
