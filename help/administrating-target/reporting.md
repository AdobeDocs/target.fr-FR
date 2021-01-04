---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Configurez les paramètres généraux à utiliser dans le rapports Adobe Target qui s’appliquent à l’ensemble de votre compte de Cible. Vous pouvez configurer la solution Adobe Experience Cloud à utiliser pour le rapports (Cible ou Analytics), le fuseau horaire et le format de devise à utiliser pour le rapports, les adresses IP à exclure du rapports et indiquer si l’effet élévateur estimé des recettes et les priorités affinées doivent être affichés dans le rapports.
title: Configuration du rapports dans Adobe Target
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 30%

---


# Configuration du rapports dans Cible

Configurez les paramètres généraux à utiliser dans le rapports [!DNL Adobe Target] qui s&#39;appliquent à l&#39;ensemble de votre compte [!DNL Target].

Pour accéder à la page de configuration [!UICONTROL Rapports], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Rapports].**

Vous pouvez spécifier les paramètres suivants sur cette page :

* La solution Adobe Experience Cloud à utiliser pour le rapports
* Fuseau horaire à utiliser pour le rapports
* Devise à utiliser pour le rapports
* Adresses IP à exclure du rapports
* Indique si l&#39;effet élévateur estimé des recettes doit être affiché dans le rapports
* Autoriser ou non des priorités affinées

>[!NOTE]
>
>Notez que le fuseau horaire, la devise et les adresses IP à exclure s’appliquent aux activités qui utilisent le rapports [!DNL Target]. Ces paramètres ne s’appliquent pas aux activités qui utilisent [Analytics for Cible (A4T)] comme source de rapports (/help/c-integrating-target-with-mac/a4t/a4t.md).

![Rapports de page](/help/administrating-target/assets/reporting.png)

## Solution rapports Cloud

Définissez des options qui déterminent les données utilisées pour vos résultats et rapports.

Sélectionnez la source du rapports pour vos activités, [!DNL Target] ou [!DNL Adobe Analytics]. Vous pouvez également choisir de sélectionner votre source de création de rapports pour chaque activité.

Tenez compte des informations suivantes pour le choix de votre source de création de rapports :

* Si cette option est définie sur **[!DNL Target]**, vous ne pouvez pas activer une activité dont la source de création de rapports est [!DNL Analytics] Vous devez remplacer la source du rapports par [!DNL Target] dans votre activité ou remplacer la source du rapports par **[!UICONTROL Sélectionner par activité]** dans **[!UICONTROL Administration] > [!UICONTROL Rapports]**.
* Si la source du rapports est définie sur **[!DNL Analytics]** ici, vous n&#39;êtes pas autorisé à activer une activité qui utilise [!DNL Target] comme source du rapports (la source du rapports est spécifiée comme **[!UICONTROL Cible par activité])**. Vous devez remplacer la source du rapports par [!DNL Analytics] dans votre activité ou remplacer le moteur de rapports par **[!UICONTROL Sélectionner par activité]** dans **[!UICONTROL Administration] > [!UICONTROL Rapports]**.
* Si la source du rapports est définie sur **[!UICONTROL Sélectionner par activité]** ici, vous pouvez créer, activer et désactiver les activités prises en charge par la source de rapports sélectionnée. Pour une matrice des activités prises en charge, voir [Types d’activité pris en charge](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) dans *Adobe Analytics en tant que source de rapports pour Adobe Target (A4t)*.
* [!UICONTROL La création, l’activation et la désactivation des activités Automated Personalization]  (AP) sont autorisées, quelle que soit la source de rapports sélectionnée. Les activités d’Automated Personalization ne sont pas prises en charge lorsque vous sélectionnez [Adobe Analytics comme source de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Même si vous spécifiez [!DNL Analytics] comme source de rapports, [!DNL Target] est utilisé comme source de rapports pour les activités Automated Personalization. Pour plus d’informations, voir [Types d’activité pris en charge](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) dans *Adobe Analytics en tant que source de rapports pour Adobe Target (A4t)*.

## Fuseau horaire du Rapports

Spécifiez le fuseau horaire à utiliser pour le rapports.

## Devise du Rapports

Spécifiez la devise à utiliser pour le rapports.

## IP à exclure des données de rapports de Cible

Spécifiez les adresses IP à exclure des données de rapports. Par exemple, l’exclusion des adresses de société internes est un bon moyen de s’assurer que les données de votre rapports reflètent les interactions des clients sur votre site Web.

Entrez chaque adresse IP sur une nouvelle ligne.

## Afficher l’effet élévateur estimé dans les recettes

Vous pouvez choisir d’afficher l’effet élévateur estimé dans les recettes si vous entrez une valeur monétaire pour votre objectif. [!DNL Target] peut estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante. La fonctionnalité d’effet élévateur estimé est désactivée par défaut.

Seuls les [!DNL Experience Cloud] administrateurs peuvent activer ou désactiver cette fonction. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.

Pour plus d’informations, voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Activation des priorités affinées

Autorise les entrées numériques pour une priorité comprise entre 0 et 999.

En fonction de vos paramètres, l’interface utilisateur et les options pour Priorité peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.
