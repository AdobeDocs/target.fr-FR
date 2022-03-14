---
keywords: Target;rapports;paramètres de rapport;commandes extrêmes;valeurs extrêmes
description: Découvrez comment exclure les valeurs extrêmes des rapports d’Adobe [!DNL Target] par conséquent, quelques commandes inhabituelles n’affectent pas les résultats de votre activité.
title: Comment exclure les valeurs extrêmes des rapports ?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 72%

---

# Exclusion des valeurs extrêmes

Vous pouvez exclure des valeurs extrêmes de l’incidence sur les rapports dans [!DNL Adobe Target] par conséquent, quelques commandes inhabituelles n’affectent pas les résultats de votre activité. Exemple de commande inhabituelle : un entraîneur achetant des uniformes pour toute une équipe plutôt que des acheteurs individuels achetant individuellement des uniformes.

>[!NOTE]
>
>L’indicateur [!UICONTROL Exclure les valeurs extrêmes] s’applique uniquement aux activités qui ont recours aux mesures de type Recettes et Engagement.

Les valeurs extrêmes sont automatiquement signalées, en fonction des règles décrites ci-dessous. Vous pouvez choisir d’afficher ou d’exclure les valeurs extrêmes de vos rapports. Les valeurs extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier.

Une valeur est considérée comme extrême lorsqu’elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne, en utilisant le dernier mois de données (jusqu’au moment où le calcul a été effectué).

Par exemple, le filtre des valeurs extrêmes est souvent utile lors de l’utilisation des recettes par visiteur (RPV). RPV associe le taux de conversion et la valeur de commande moyenne et, souvent, révèle la volatilité de ces mesures. Si vous utilisez RPV et déterminez que les commandes ne semblent pas être distribuées normalement, vous pouvez voir plus de résultats normaux si vous appliquez le filtre des commandes extrêmes.

Lorsqu’une valeur est désignée comme extrême, sa valeur est remplacée par la valeur de commande moyenne de l’expérience pour le dernier mois, extrêmes exclus. L’ordre est également marqué comme extrême dans la variable [!UICONTROL Détails de la commande] et dans le téléchargement CSV pour les résultats quotidiens.

**Pour exclure les valeurs extrêmes de vos rapports, procédez comme suit :**

1. Ouvrez une activité qui comprend les mesures de types Recettes ou Engagement, puis cliquez sur l’onglet **[!UICONTROL Rapports]**.
1. Cliquez sur l’icône d’engrenage pour afficher la variable **[!UICONTROL Paramètres]** de la boîte de dialogue

   ![Résultat d’étape](assets/exclude_extreme_values.png)

1. Glisser le **[!UICONTROL Exclusion des valeurs extrêmes]** basculez sur la position &quot;activé&quot; ou &quot;désactivé&quot;, suivant vos besoins.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
