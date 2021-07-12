---
keywords: rapport;rapports;création de rapports;solution experience cloud;fuseau horaire;devise;exclure les adresses IP;effet élévateur estimé dans les recettes;effet élévateur dans les recettes;priorités affinées;granularité fine
description: Utilisez  [!DNL Target] ou Adobe Analytics comme source de création de rapports, spécifiez le fuseau horaire et le format de devise par défaut, ajoutez des adresses IP à exclure de la création de rapports, etc.
title: Comment configurer les rapports dans Target ?
feature: Administration et configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 30%

---

# Configuration de la création de rapports dans Target

Configurez les paramètres généraux à utiliser dans les rapports [!DNL Adobe Target] qui s’appliquent à l’ensemble de votre compte [!DNL Target].

Pour accéder à la page de configuration [!UICONTROL Reporting], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Vous pouvez définir les paramètres suivants sur cette page :

* Solution Adobe Experience Cloud à utiliser pour la création de rapports
* Fuseau horaire à utiliser pour la création de rapports
* Devise à utiliser pour la création de rapports
* Adresses IP à exclure des rapports
* Indique si l’effet élévateur estimé dans les recettes est affiché dans les rapports.
* Activation ou non des priorités affinées

>[!NOTE]
>
>N’oubliez pas que les paramètres de fuseau horaire, de devise et d’adresses IP à exclure s’appliquent aux activités qui utilisent la création de rapports [!DNL Target]. Ces paramètres ne s’appliquent pas aux activités qui utilisent [Analytics for Target (A4T)] comme source des rapports (/help/c-integrating-target-with-mac/a4t/a4t.md).

![Page Rapports](/help/administrating-target/assets/reporting.png)

## Solution Reporting Cloud

Définissez des options qui déterminent les données utilisées pour vos résultats et rapports.

Sélectionnez la source des rapports pour vos activités, [!DNL Target] ou [!DNL Adobe Analytics]. Vous pouvez également choisir de sélectionner votre source de création de rapports pour chaque activité.

Tenez compte des informations suivantes pour le choix de votre source de création de rapports :

* Si cette option est définie sur **[!DNL Target]**, vous ne pouvez pas activer une activité dont la source de création de rapports est [!DNL Analytics] Vous devez remplacer la source des rapports par [!DNL Target] dans votre activité ou modifier la source des rapports par **[!UICONTROL Sélectionner par activité]** dans **[!UICONTROL Administration] > [!UICONTROL Création de rapports]**.
* Si la source de création de rapports est définie sur **[!DNL Analytics]** ici, vous ne pouvez pas activer une activité qui utilise [!DNL Target] comme source de création de rapports (la source de création de rapports est spécifiée sous la forme **[!UICONTROL Cible par activité])**. Vous devez remplacer la source des rapports par [!DNL Analytics] dans votre activité ou remplacer le moteur des rapports par **[!UICONTROL Sélectionner par activité]** dans **[!UICONTROL Administration] > [!UICONTROL Création de rapports]**.
* Si cette option est définie sur **[!UICONTROL Sélectionner par activité]**, vous pouvez créer, activer et désactiver les activités prises en charge par la source de création de rapports sélectionnée. Pour une matrice des activités prises en charge, voir [Types d’activités pris en charge](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) dans *Adobe Analytics comme source de création de rapports pour Adobe Target (A4t)*.
* [!UICONTROL La création, l’activation et la désactivation d’une activité Automated Personalization]  (AP) sont autorisées, quelle que soit la source de création de rapports sélectionnée. Les activités Automated Personalization ne sont pas prises en charge lorsque vous choisissez [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Même si vous spécifiez [!DNL Analytics] comme source de création de rapports, [!DNL Target] est utilisé comme source de création de rapports pour les activités Automated Personalization. Pour plus d’informations, voir [Types d’activité pris en charge](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) dans *Adobe Analytics comme source de création de rapports pour Adobe Target (A4t)*.

## Fuseau horaire pour la création de rapports

Spécifiez le fuseau horaire à utiliser pour la création de rapports.

## Devise de création de rapports

Spécifiez la devise à utiliser pour la création de rapports.

## IP à exclure des données de rapport [!DNL Target]

Indiquez les adresses IP que vous souhaitez exclure des données de rapport. Par exemple, l’exclusion des adresses internes de la société est un bon moyen de s’assurer que les données de rapport reflètent les interactions des clients sur votre site web.

Saisissez chaque adresse IP sur une nouvelle ligne.

## Afficher l’effet élévateur estimé dans les recettes

Vous pouvez choisir d’afficher l’effet élévateur estimé dans les recettes si vous saisissez une valeur monétaire pour votre objectif. [!DNL Target] peut estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante. La fonctionnalité d’effet élévateur estimé est désactivée par défaut.

Seuls les [!DNL Experience Cloud] administrateurs peuvent activer ou désactiver cette fonctionnalité. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.

Pour plus d’informations, voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Activation des priorités affinées

Autorise les entrées numériques pour une priorité comprise entre 0 et 999.

En fonction de vos paramètres, l’interface utilisateur et les options pour Priorité peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.
