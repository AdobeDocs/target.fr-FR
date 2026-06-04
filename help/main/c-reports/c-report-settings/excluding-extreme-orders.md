---
keywords: Target;rapports;paramètres de rapport;commandes extrêmes;valeurs extrêmes
description: Découvrez comment exclure des valeurs extrêmes de l’impact sur les rapports dans Adobe  [!DNL Target]  que quelques commandes inhabituelles n’affectent pas les résultats de votre activité.
title: Comment exclure des valeurs extrêmes dans les rapports ?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
TQID: https://experienceleague.adobe.com/yQtG4u-sLVJ66PezWW9ZgmY8ZuK177m-hLdQq-zlmfI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 62%

---

# Exclusion des valeurs extrêmes

Vous pouvez exclure des valeurs extrêmes de l’impact sur les rapports dans [!DNL Adobe Target], de sorte que quelques commandes inhabituelles n’affectent pas les résultats de votre activité. Exemple de commande inhabituelle : un entraîneur achetant des uniformes pour toute une équipe plutôt que des acheteurs individuels achetant individuellement des uniformes.

>[!NOTE]
>
>L’indicateur [!UICONTROL Exclure les valeurs extrêmes] s’applique uniquement aux activités avec les types de mesures [!UICONTROL Chiffre d’affaires] et [!UICONTROL Engagement].

Les valeurs extrêmes sont automatiquement signalées, en fonction des règles décrites ci-dessous. Vous pouvez choisir d’afficher ou d’exclure les valeurs extrêmes de vos rapports. Les valeurs extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier.

Une valeur est considérée comme extrême lorsqu’elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne, en utilisant le dernier mois de données (jusqu’au moment où le calcul a été effectué).

Par exemple, le filtre des valeurs extrêmes est souvent utile lors de l’utilisation des recettes par visiteur (RPV). RPV associe le taux de conversion et la valeur de commande moyenne et, souvent, révèle la volatilité de ces mesures. Si vous utilisez RPV et déterminez que les commandes ne semblent pas être distribuées normalement, vous pouvez voir plus de résultats normaux si vous appliquez le filtre des commandes extrêmes.

Lorsqu’une valeur est désignée comme extrême, sa valeur est remplacée par la valeur de commande moyenne de l’expérience pour le dernier mois, extrêmes exclus. L’ordre est également marqué comme extrême dans le rapport [!UICONTROL Détails de la commande] et dans le téléchargement CSV pour les résultats quotidiens.

**Pour exclure les valeurs extrêmes de vos rapports, procédez comme suit :**

1. Ouvrez une activité qui comprend des types de mesures [!UICONTROL Revenu] ou [!UICONTROL Engagement], puis cliquez sur l’onglet **[!UICONTROL Rapports]**.
1. Cliquez sur l’icône Paramètres de rapport ( ![icône Paramètres de rapport](/help/main/assets/icons/Setting.svg) ) pour afficher la boîte de dialogue **[!UICONTROL Paramètres]**.

1. Faites glisser le bouton (bascule) **[!UICONTROL Exclure les valeurs extrêmes]** vers la position « activé » ou « désactivé », selon vos besoins.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
