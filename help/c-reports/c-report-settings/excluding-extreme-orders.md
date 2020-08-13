---
keywords: Target;reports;report settings;extreme orders;extreme values
description: 'Vous pouvez exclure les valeurs extrêmes des rapports d’Adobe Target afin que quelques commandes inhabituelles n’affectent pas les résultats de votre activité. Exemple de commande inhabituelle : un entraîneur achetant des uniformes pour toute une équipe plutôt que des acheteurs individuels achetant individuellement des uniformes.'
title: Exclure les valeurs extrêmes dans les rapports Adobe Target
feature: report settings
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 88%

---


# Exclusion des valeurs extrêmes{#exclude-extreme-values}

Vous pouvez exclure les valeurs extrêmes des rapports concernés, de sorte que quelques commandes inhabituelles n’affectent pas les résultats de votre activité. Exemple de commande inhabituelle : un entraîneur achetant des uniformes pour toute une équipe plutôt que des acheteurs individuels achetant individuellement des uniformes.

>[!NOTE]
>
>L’indicateur [!UICONTROL Exclure les valeurs extrêmes] s’applique uniquement aux activités qui ont recours aux mesures de type Recettes et Engagement.

Les valeurs extrêmes sont automatiquement signalées, en fonction des règles décrites ci-dessous. Vous pouvez choisir d’afficher ou d’exclure les valeurs extrêmes de vos rapports. Les valeurs extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier.

Une valeur est considérée comme extrême lorsqu’elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne, en utilisant le dernier mois de données (jusqu’au moment où le calcul a été effectué).

Par exemple, le filtre des valeurs extrêmes est souvent utile lors de l’utilisation des recettes par visiteur (RPV). RPV associe le taux de conversion et la valeur de commande moyenne et, souvent, révèle la volatilité de ces mesures. Si vous utilisez RPV et déterminez que les commandes ne semblent pas être distribuées normalement, vous pouvez voir plus de résultats normaux si vous appliquez le filtre des commandes extrêmes.

Lorsqu’une valeur est désignée comme extrême, sa valeur est remplacée par la valeur de commande moyenne de l’expérience pour le dernier mois, extrêmes exclus. Cette commande est également signalée comme extrême dans le rapport Détails de la commande et dans le téléchargement au format CSV des résultats quotidiens.

**Pour exclure les valeurs extrêmes de vos rapports, procédez comme suit :**

1. Ouvrez une activité qui comprend les mesures de types Recettes ou Engagement, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.
1. Cliquez sur l’icône représentant un engrenage.

   ![Paramètres des rapports](/help/c-reports/c-report-settings/assets/report-settings-gear-icon.png)

   La boîte de dialogue Paramètres [!UICONTROL du] rapport s’affiche.

   ![Résultat d’étape](assets/exclude_extreme_values.png)

1. Activez ou désactivez l’option **[!UICONTROL Exclure les valeurs extrêmes]**, selon vos besoins.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
