---
keywords: Recommendations
description: Plusieurs modifications se produisent dans le processus de collecte de données lors de l’activation d’Analytics en tant que source des rapports pour Target (A4T).
title: Avant d’implémenter Adobe Analytics en tant que source de rapports pour Adobe Target (A4T)
feature: a4t implementation
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 54%

---


# Avant l’implémentation{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

Avant de décider d’utiliser cette intégration, consultez les sections suivantes et envisagez l’impact sur vos processus de création de rapports :

## Exigences d’implémentation {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Avant de commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Utilisez le [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences) pour demander à être mis en service.

Cette intégration A4T requiert que vous mettiez en œuvre les versions suivantes de la bibliothèque (ou plus récentes) selon que vous souhaitez utiliser des offres de redirection ou non avec A4T :

### Conditions requises si vous *n*’utilisez pas les offres de redirection avec A4T

Cette intégration requiert que vous mettiez en œuvre les versions suivantes (ou plus récentes) de la bibliothèque si vous ne prévoyez pas d’utiliser les offres de redirection avec A4T. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 1.8.0
* [!DNL Adobe Target] (selon votre mise en œuvre) : at.js version 0.9.1 ou mbox.js version 61.
* Adobe Analytics : appMeasurement.js version 1.7.0

### Conditions requises en cas d’utilisation des offres de redirection avec A4T

Pour utiliser des offres de redirection avec A4T, vous devez mettre en œuvre les versions suivantes (ou plus récentes) de la bibliothèque. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js version 2.3.0
* [!DNL Adobe Target]: at.js version 1.6.2

   **Remarque :** La bibliothèque mbox.js ne prend pas en charge les offres de redirection avec A4T. Votre mise en œuvre doit utiliser at.js.

* Adobe Analytics : appMeasurement.js version 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Informations à connaître avant l’implémentation {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. Après avoir apporté les modifications de mise en œuvre décrites dans ce document, les activités existantes ne sont pas affectées.
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* Le [!DNL Visitor ID service] crée un partage [!DNL Visitor ID] sur l’ensemble du [!DNL Adobe Experience Cloud]. Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* L&#39; [!DNL Visitor ID service] objet doit s&#39;exécuter avant votre [!DNL Analytics] code de page et votre code de [!DNL Target] page. Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous subirez 5 à 10 minutes supplémentaires de latence dans [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## ID supplémentaire {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.
* Une version de [!DNL mbox.js] qui prend en charge cette intégration est implémentée.

When [troubleshooting](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## Journalisation des analyses côté client {#client-side}

Par défaut, lorsque at.js, le [!DNL Experience Cloud Visitor ID Service], et appMeasurement.js se trouvent sur la page, [!DNL Analytics] et [!DNL Target] associent correctement les événements à des fins de création de rapports et d’analyses dans le serveur principal tant que le bon ID supplémentaire est inclus à partir de la page, comme mentionné ci-dessus. Il n’est pas nécessaire de gérer et d’effectuer des opérations supplémentaires pour que A4T fonctionne correctement.

Cependant, il se peut que vous souhaitiez mieux contrôler quand et comment envoyer des données d’analyse liées à [!DNL Target] vers [!DNL Analytics] à des fins de création de rapports. Il se peut que vous disposiez d’un outil d’analyse interne que vous utilisez à des fins internes, mais que vous souhaitiez également envoyer les données d’analyse vers [!DNL Analytics] à l’aide de votre produit d’analyse interne afin que d’autres membres de votre organisation puissent continuer à l’utiliser [!DNL Analytics] comme source de création de rapports visuelle. Voir [Étape 7 : référencement at.js ou mbox.js sur toutes les pages du site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) dans *Implémentation d’Analytics pour Target* pour plus d’informations.

## Audiences partagées

Lorsque vous remplissez le formulaire [d&#39;approvisionnement d&#39;intégrations de](https://www.adobe.com/go/audiences)Marketing Cloud, tenez compte des informations importantes suivantes concernant l&#39;option Audiences  partagées répertoriée sous &quot;[!UICONTROL Pour quelles fonctionnalités demandez-vous de configurer]?&quot;

![Formulaire de demande](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Lorsque vous demandez des Audiences partagées, vous activez [!UICONTROL Cible] et [!UICONTROL Adobe Audience Manager] (AAM) pour partager des informations, dans ce cas les audiences.

>[!IMPORTANT]
>
>Cette intégration entre [!UICONTROL Cible] et AAM entraîne des coûts supplémentaires. Vous serez facturé pour chaque appel [!UICONTROL Cible] en AAM.
