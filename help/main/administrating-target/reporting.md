---
keywords: rapport;rapports;reporting;solution experience cloud;fuseau horaire;fuseau horaire;devise;exclure les adresses IP;effet élévateur estimé dans le chiffre d’affaires;effet élévateur dans le chiffre d’affaires;priorités affinées;affiné
description: Utilisez  [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics]  comme source de création de rapports, spécifiez le fuseau horaire et le format de devise par défaut, ajoutez des adresses IP à exclure des rapports, etc.
title: Comment configurer les rapports dans  [!DNL Target] ?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
TQID: https://experienceleague.adobe.com/Vdi1o6bvCbgrhWUrJfCOyxqN3JkhEe3Rd9J-3NmLVyY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 795
ht-degree: 22%

---

# Configuration des rapports dans [!DNL Target]

Configurez les paramètres généraux à utiliser dans les rapports [!DNL Adobe Target] qui s’appliquent à l’ensemble de votre compte [!DNL Target].

{{permissions-update}}

Pour accéder à la page de configuration [!UICONTROL Reporting], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Vous pouvez définir les paramètres suivants sur cette page :

* La solution Adobe Experience Cloud à utiliser pour le reporting
* Fuseau horaire à utiliser pour la création de rapports
* Devise à utiliser pour la création de rapports
* Adresses IP à exclure des rapports
* Permet d’afficher ou non l’effet élévateur estimé dans le chiffre d’affaires dans les rapports
* Permet d’activer les priorités affinées.

>[!NOTE]
>
>Gardez à l’esprit que les paramètres de fuseau horaire, de devise et d’adresses IP à exclure s’appliquent aux activités qui utilisent la création de rapports [!DNL Target]. Ces paramètres ne s’appliquent pas aux activités qui utilisent [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) ou [!DNL Customer Journey Analytics] comme source de création de rapports.

![Page Reporting](/help/main/administrating-target/assets/reporting.png)

## Solution Reporting Cloud {#solution}

Définissez des options qui déterminent les données utilisées pour vos résultats et rapports.

Sélectionnez la source de création de rapports pour vos activités, [!DNL Target], [!DNL Adobe Analytics] ou [!DNL Adobe Customer Journey Analytics]. Vous pouvez également choisir de sélectionner la source de création de rapports par activité dans le cadre d’un workflow guidé en trois parties lors de la création de l’activité.

Tenez compte des informations suivantes pour le choix de votre source de création de rapports :

* **[!DNL Adobe Target]** : si la source de création de rapports est définie sur **[!DNL Target]** ici, vous n’êtes pas autorisé à créer ou activer une activité qui utilise [!DNL Analytics] ou [!DNL Customer Journey Analytics] comme source de création de rapports. Vous devez modifier la source de création de rapports en **[!UICONTROL Sélectionner par activité]**.
* **[!DNL Adobe Analytics]** : si la source de création de rapports est définie sur **[!DNL Analytics]** ici, vous n’êtes pas autorisé à créer ou activer une activité qui utilise [!DNL Target] ou [!DNL Customer Journey Analytics] comme source de création de rapports. Vous devez modifier la source de création de rapports en **[!UICONTROL Sélectionner par activité]**.
* **[!DNL Adobe Customer Journey Analytics]** : si la source de création de rapports est définie sur **[!DNL Customer Journey Analytics]** ici, vous n’êtes pas autorisé à créer ou activer une activité qui utilise [!DNL Target] ou [!DNL Analytics] comme source de création de rapports. Vous devez modifier la source de création de rapports en **[!UICONTROL Sélectionner par activité]**.
* **Sélectionner par activité** : si la source de rapports est définie sur **[!UICONTROL Sélectionner par activité]** ici, vous pouvez créer et activer des activités prises en charge par la source de rapports sélectionnée.

Lorsque vous déterminez votre source de création de rapports, tenez compte des informations suivantes :

* **[!DNL Analytics]** : pour obtenir une matrice des activités prises en charge à l’aide de [!DNL Analytics] comme source de création de rapports (A4T), voir [Types d’activités pris en charge](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) dans *Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)*.

  La création et l’activation d’activités  (AP) sont autorisées, quelle que soit la source de création de rapports sélectionnée. Les activités  ne sont pas prises en charge lorsque vous choisissez [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Même si vous spécifiez [!DNL Analytics] comme source de création de rapports, [!DNL Target] est utilisé comme source de création de rapports pour les activités [!DNL Automated Personalization].

* **[!DNL Customer Journey Analytics]** : pour obtenir une matrice des activités prises en charge à l’aide des rapports [!DNL Target] dans [!DNL Customer Journey Analytics], consultez [Types d’activité pris en charge](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) dans les rapports *[!DNL Target]dans[!DNL Adobe Customer Journey Analytics]*.

  La création et l’activation des activités  (AP), [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] sont autorisées quelle que soit la source de création de rapports sélectionnée. Ces activités ne sont pas prises en charge lorsque vous choisissez [Adobe Customer Journey Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Même si vous spécifiez [!DNL Customer Journey Analytics] comme source de création de rapports, [!DNL Target] est utilisé comme source de création de rapports pour les activités [!DNL Automated Personalization].

  Si vous spécifiez [!DNL Customer Journey Analytics] comme source de création de rapports pour les activités [!UICONTROL Affectation automatique] ou [!UICONTROL Ciblage automatique], [!DNL Target] ou [!DNL Analytics] peuvent être utilisés comme source de création de rapports.

## Fuseau horaire pour la création de rapports

Spécifiez le fuseau horaire à utiliser pour la création de rapports.

## Devise pour la création de rapports

Spécifiez la devise à utiliser pour la création de rapports.

## Adresses IP à exclure des données de rapports [!DNL Target]

Spécifiez les adresses IP que vous souhaitez exclure des données de rapport. Par exemple, l’exclusion des adresses internes de l’entreprise est un bon moyen de s’assurer que vos données de rapport reflètent les interactions des clients sur votre site web.

Saisissez chaque adresse IP sur une nouvelle ligne.

## Afficher l’effet élévateur estimé dans les recettes

Vous pouvez choisir d’afficher l’effet élévateur estimé dans le chiffre d’affaires si vous saisissez une valeur monétaire pour votre objectif. [!DNL Target] peut estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante. La fonctionnalité d’effet élévateur estimé est désactivée par défaut.

Seuls les utilisateurs administrateurs [!DNL Experience Cloud] peuvent activer ou désactiver cette fonctionnalité. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.

Pour plus d’informations, voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Activation des priorités affinées

Autorise les entrées numériques pour une priorité comprise entre 0 et 999.

Selon vos paramètres, l’interface utilisateur et les options de Priorité varient. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.
