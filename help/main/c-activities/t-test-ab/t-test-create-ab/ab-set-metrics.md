---
keywords: A/B;mesures d’activité;mesures;définir des mesures;mesure d’objectif;paramètres d’activité;mesure de succès;conversion;recettes;engagement
description: Découvrez comment définir des mesures dans une activité A/B, de ciblage d’expérience ou de test multivarié pour déterminer le succès de la visite, y compris [!UICONTROL la conversion], [!UICONTROL le chiffre d’affaires] et [!UICONTROL l’engagement].
title: Comment définir les mesures d’objectif dans une activité A/B ?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 24%
---
# Définition de mesures {#ab-set-metrics}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment définir la mesure d’objectif et les mesures supplémentaires d’une activité A/B, de ciblage d’expérience (XT) ou de test multivarié (MVT), ainsi que les caractères non autorisés dans les noms de mesure.

>[!ENDSHADEBOX]

Utilisez des mesures dans une activité [!DNL Adobe Target] A/B, [!UICONTROL Ciblage d’expérience] (XT) ou [!UICONTROL Test multivarié] (MVT) pour déterminer le moment où une visite est réussie. Pour plus d’informations sur les mesures de succès, voir [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

>[!NOTE]
>
>Cette page s’applique lorsque [!DNL Adobe Target] est la source de création de rapports. Pour les autres sources de création de rapports, consultez [[!DNL Adobe Analytics]  comme source de création de rapports pour [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [[!DNL Target] les rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## Définition d’une mesure {#set-a-metric}

1. Dans la section **[!UICONTROL Paramètres de rapports]** de la page **[!UICONTROL Objectifs et paramètres]**, sélectionnez une [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

   L’option **[!UICONTROL Sélectionner des mesures]** répertorie les mesures de succès que vous pouvez choisir pour votre activité. Les mesures de succès sont regroupées dans les catégories suivantes :

   * **[!UICONTROL Conversion]**
   * **[!UICONTROL Recettes]**
   * **[!UICONTROL Engagement]**

   Vous pouvez utiliser n’importe quelle mesure de succès préconfigurée ou en créer une personnalisée. Vous pouvez également marquer une mesure de succès comme mesure principale. Par défaut, les rapports et les cartes Experience Cloud présentent la mesure principale, si elle est définie.

   ![](../../assets/metric-1.png)

1. Indiquez les paramètres de vos mesures. Les paramètres disponibles dépendent de la mesure de succès que vous utilisez.

1. Si cette option est activée, la **[!UICONTROL Valeur estimée de la conversion]** fournit une valeur pour votre objectif :

   * La valeur permet à [!DNL Target] de calculer une augmentation estimée du chiffre d’affaires.
   * Le champ est facultatif. Toutefois, les revenus incrémentiels pour toute mesure sans revenus ne peuvent pas être calculés sans celui-ci.
   * Le champ n’est pas disponible pour les mesures **[!UICONTROL Score de page]**.
   * Les données sont de type devise.
   * Le champ s’affiche progressivement une fois que l’utilisateur a indiqué l’action entreprise pour atteindre l’objectif.

   Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations. La configuration correcte des mesures de succès est essentielle pour vous assurer d’obtenir les données attendues.

   ![](../../assets/metric-2.png)

1. (Facultatif) Pour suivre plus que la mesure d’objectif, cliquez sur **[!UICONTROL Ajouter une nouvelle mesure]**, puis sélectionnez et configurez chaque mesure supplémentaire comme décrit dans les étapes précédentes.

1. Lorsque vous avez terminé de définir vos mesures, cliquez sur **[!UICONTROL Continuer]** dans une activité XT ou sur **[!UICONTROL Enregistrer et fermer]** dans une activité MVT.

## Caractères non autorisés dans les noms de mesure {#metric-name-rules}

![](../../assets/metric-3.png)

Lorsque vous nommez ou renommez une mesure, les caractères suivants ne sont pas autorisés :


| Caractère | Description |
|--- |--- |
| `/` | Barre oblique |
| `?` | Point d’interrogation |
| `#` | Croisillon |
| `:` | Deux-points |
| `=` | Égal |
| `+` | Plus |
| `-` | Moins |
| `@` | Arobase |
