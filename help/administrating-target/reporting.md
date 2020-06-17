---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Configurez le compositeur d’expérience visuelle d’Adobe Target en spécifiant ses paramètres généraux, la configuration de la fenêtre d’affichage mobile et les sélecteurs CSS.
title: Configuration du rapports dans l’Adobe Target
topic: Standard
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 65%

---


# Configuration du rapports dans Cible

Configurez les paramètres généraux à utiliser dans le rapports de Cible qui s’appliquent à l’ensemble de votre [!DNL Target] compte.

>[!NOTE]
>
>Les informations de cette rubrique ont été mises à jour afin de vous donner un pic de dénivellement lors des modifications de l’interface utilisateur qui se produisent dans la version Target Standard/Premium 20.6.1 (juillet 2020). La plupart des informations présentées dans cette rubrique s’appliquent à l’interface utilisateur actuelle ; toutefois, les options peuvent se trouver à des emplacements légèrement différents.

Pour accéder à la page de configuration du [!UICONTROL Rapports] , cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Rapports].**

Vous pouvez spécifier les paramètres suivants sur cette page :

* La solution Adobe Experience Cloud à utiliser pour le rapports
* Fuseau horaire à utiliser pour le rapports
* Devise à utiliser pour le rapports
* Adresses IP à exclure du rapports
* Indique si l&#39;effet élévateur estimé des recettes doit être affiché dans le rapports
* Autoriser ou non des priorités affinées

![Rapports de page](/help/administrating-target/assets/reporting.png)

## Solution Rapports Cloud

Définissez des options qui déterminent les données utilisées pour vos résultats et rapports.

Sélectionnez [!DNL Target] ou Adobe Analytics comme source de création de rapports pour vos activités. Vous pouvez également choisir de sélectionner votre source de création de rapports pour chaque activité.

Tenez compte des informations suivantes pour le choix de votre source de création de rapports :

* La création, l’activation et la désactivation d’activités d’[!UICONTROL attribution automatique], de [!UICONTROL ciblage automatique] et de [!UICONTROL personnalisation automatisée] (PA) sont autorisées, quelle que soit la source de création de rapports sélectionnée. Ces activités ne sont pas prises en charge lorsque vous choisissez [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Même si vous désignez Analytics comme étant votre source de création de rapports, [!DNL Target] se charge de la création des rapports pour ces activités.
* Si la source de création de rapports désignée est Analytics, vous ne pouvez pas activer une activité dont la source de création de rapports est [!DNL Target] (la désignation de Target comme source de création de rapports se fait activité par activité). Vous devez désigner Analytics comme source de création de rapports directement dans l’activité ou modifier la sélection dans Sélection par activité, dans Configuration > Préférences.
* Si cette option est définie sur [!DNL Target], vous ne pouvez pas activer une activité dont la source de création de rapports est Analytics. Vous devez désigner [!DNL Target] comme source de création de rapports directement dans l’activité ou modifier la sélection dans Sélection par activité, dans Configuration > Préférences.
* Si cette option est définie sur Sélection par activité, vous pouvez créer, activer et désactiver les activités prises en charge par la source de création de rapports sélectionnée. Pour consulter une matrice des activités prises en charge, voir [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Lorsque vous passez du test A/B manuel à l’[!UICONTROL attribution automatique] ou au [!UICONTROL ciblage automatique], toutes les mesures et audiences pour la création de rapports sont perdues, dans le cas où l’activité A/B manuelle n’est pas prise en charge dans les activités d’[!UICONTROL attribution automatique] et de [!UICONTROL ciblage automatique].

## Fuseau horaire du Rapports

Spécifiez le fuseau horaire à utiliser pour le rapports.

## Devise du Rapports

Indiquez la devise à utiliser pour le rapports.

## IP à exclure des données de rapports de Cible

Spécifiez les adresses IP à exclure des données de rapports. Par exemple, l’exclusion des adresses de société internes est un bon moyen de s’assurer que les données de votre rapports reflètent les interactions des clients sur votre site Web.

Entrez chaque adresse IP sur une nouvelle ligne.

## Afficher l’effet élévateur estimé dans les recettes

Vous pouvez choisir d’afficher l’effet élévateur estimé dans les recettes si vous entrez une valeur monétaire pour votre objectif. [!DNL Target] peut estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante. La fonctionnalité d’effet élévateur estimé est désactivée par défaut.

Seuls les utilisateurs administrateurs d’Experience Cloud peuvent l’activer ou la désactiver. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.

Pour plus d’informations, voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Activation des priorités affinées

Autorise les entrées numériques pour une priorité comprise entre 0 et 999.

En fonction de vos paramètres, l’interface utilisateur et les options pour Priorité peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.
