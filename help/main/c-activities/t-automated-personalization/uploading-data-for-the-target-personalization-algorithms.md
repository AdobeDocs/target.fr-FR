---
keywords: Automated Personalization;ap;charger des données;données hors ligne;algorithme de personnalisation;ciblage automatique;ciblage automatique;bonnes pratiques
description: Découvrez comment charger des données hors ligne lors de la création de modèles de personnalisation dans les activités [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique].
title: Comment télécharger des données pour les algorithmes de Personalization ?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: 'https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 7%
---
# Charger des données pour les algorithmes de personnalisation [!DNL Target] {#upload-data-personalization}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment envoyer des données hors ligne et personnalisées aux algorithmes de **[!UICONTROL ciblage automatique]** et **[!UICONTROL Automated Personalization]**, ainsi que les bonnes pratiques à suivre.

>[!ENDSHADEBOX]

Les données hors ligne, telles que les informations CRM ou les scores de propension à l’attrition client, peuvent s’avérer extrêmement précieuses lorsque vous créez des modèles de personnalisation dans des activités de [!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP) et de **[!UICONTROL ciblage automatique]**.

Il existe plusieurs façons de saisir des données dans les algorithmes de personnalisation **[!UICONTROL Automated Personalization]** (AP) et **[!UICONTROL Ciblage automatique]**. Outre les méthodes décrites dans [Méthodes d’obtention de données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}, les audiences partagées [!DNL Experience Cloud] (**[!UICONTROL Adobe Analytics]**, [!DNL Audience Manager]) et les audiences de rapports en activité sont également utilisées dans les algorithmes [!DNL Target].

Pour plus d’informations sur les données automatiquement collectées et utilisées par les algorithmes de personnalisation **[!UICONTROL Automated Personalization]** et **[!UICONTROL Ciblage automatique]**, voir [Collecte de données Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Bonnes pratiques {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

Suivez ces bonnes pratiques lorsque vous chargez des données pour les algorithmes de personnalisation [!DNL Target] :

* Plus les algorithmes de personnalisation [!DNL Target] disposeront de données de haute qualité, meilleure sera la qualité des modèles obtenus dans vos activités de **[!UICONTROL ciblage automatique]** et **[!UICONTROL Automated Personalization]**.
* Limitez l’utilisation de plusieurs scripts ou attributs de profil ayant le même objectif.
* Ne transmettez pas d’ID unique, tel qu’un ID de session, s’il n’est pas nécessaire.
* Vérifiez quelles données [!DNL Target] collectent automatiquement ([Collecte de données pour les algorithmes Personalization cibles](/help/main/c-activities/t-automated-personalization/ap-data.md)) afin de ne pas envoyer d&#39;informations en double. Par exemple, [!DNL Target] utilise des adresses IP pour déterminer les codes postaux des visiteurs. Il n’est pas nécessaire de transmettre ces informations sous la forme d’une variable distincte.
* Ne transmettez pas plusieurs valeurs dans le même attribut ou la même variable. Si plusieurs variables sont concaténées, les algorithmes de personnalisation [!DNL Target] traitent chaque chaîne comme une valeur unique, ce qui réduit la valeur des informations à personnaliser.
* Utilisez une convention de nommage mémorisable et significative pour rendre vos [rapports Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) plus compréhensibles.
