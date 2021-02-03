---
keywords: Recommandations
description: Plusieurs modifications se produisent dans le processus de collecte de données lors de l’activation d’Analytics en tant que source des rapports pour Target (A4T).
title: Avant de mettre en oeuvre Analytics en tant que source du Rapports (A4T)
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 54%

---


# Avant l’implémentation{#before-you-implement}

Plusieurs modifications se produisent dans votre processus de collecte de données lors de l’activation de [!DNL Analytics] en tant que source de rapports pour [!DNL Target] (A4T).

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

Les instructions de téléchargement et de déploiement sont répertoriées dans [Analytics for Cible Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Informations à connaître avant l’implémentation {#section_50D49CC52E11414089C89FB67F9B88F5}

* Cette intégration est activée sur les nouvelles activités lorsque vous choisissez d’utiliser [!DNL Analytics] comme source de rapports. Après avoir apporté les modifications de mise en œuvre décrites dans ce document, les activités existantes ne sont pas affectées.
* Le processus de configuration de [!DNL Analytics] en tant que source de rapports pour [!DNL Target] comprend plusieurs étapes de mise en oeuvre, suivies d’une étape de mise en service. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. Une fois ces étapes terminées, vous serez prêt à utiliser [!DNL Analytics] comme source de rapports dès qu&#39;il sera activé pour vous. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* [!DNL Visitor ID service] crée un [!DNL Visitor ID] partagé dans [!DNL Adobe Experience Cloud]. Bien qu’il ne remplace pas l’ID [!DNL Target] mboxPC ou l’UUID [!DNL Audience Manager], il remplace la manière dont [!DNL Analytics] identifie les nouveaux visiteurs. Si la configuration est correctement effectuée, les visiteurs [!DNL Analytics] de retour doivent également être identifiés par leur ancien [!DNL Analytics] identifiant afin d’éviter la recherche de valeur par le visiteur. De même, étant donné que le [!DNL Target] mboxPCid reste intact, aucune donnée de profil de visiteur [!DNL Target] n’est perdue lorsque vous effectuez la mise à niveau vers [!DNL Visitor ID service].
* [!DNL Visitor ID service] doit s&#39;exécuter avant votre code de page [!DNL Analytics] et [!DNL Target]. Assurez-vous que `VisitorAPI.js` apparaît au-dessus des balises pour toutes les autres solutions [!DNL Experience Cloud].

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous subirez 5 à 10 minutes supplémentaires de latence dans [!DNL Analytics]. Cette augmentation de latence permet de stocker les données de [!DNL Analytics] et [!DNL Target] sur le même accès, ce qui vous permet de ventiler les activités par page et par section de site.

Cette augmentation se reflète dans tous les services et outils [!DNL Analytics], y compris le rapports en direct et en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Sachez que la latence augmente les débuts après la mise en oeuvre du service d’identification des visiteurs [!DNL Experience Cloud], même si vous n’avez pas entièrement mis en oeuvre cette intégration.

## ID supplémentaire {#section_2C1F745A2B7D41FE9E30915539226E3A}

Tous les appels [!DNL Target] utilisés par une activité A4T pour diffuser du contenu ou enregistrer la mesure d’objectif doivent avoir un accès [!DNL Analytics] correspondant qui partage le même ID supplémentaire pour A4T pour fonctionner correctement.

Les accès qui contiennent des données provenant de [!DNL Analytics] et [!DNL Target] contiennent un ID de données supplémentaire. Vous pouvez voir cet ID dans le [débogueur de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) comme paramètre `sdid`. Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.
* Une version de [!DNL mbox.js] qui prend en charge cette intégration est implémentée.

Lorsque [dépannage](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), veillez à confirmer que l’ID supplémentaire est présent sur les accès [!DNL Analytics].

## Journalisation des analyses côté client {#client-side}

Par défaut, lorsque at.js, le [!DNL Experience Cloud Visitor ID Service], et appMeasurement.js se trouvent sur la page, [!DNL Analytics] et [!DNL Target] associent correctement les événements à des fins de création de rapports et d’analyses dans le serveur principal tant que le bon ID supplémentaire est inclus à partir de la page, comme mentionné ci-dessus. Il n’est pas nécessaire de gérer et d’effectuer des opérations supplémentaires pour que A4T fonctionne correctement.

Cependant, il se peut que vous souhaitiez mieux contrôler quand et comment envoyer des données d’analyse liées à [!DNL Target] vers [!DNL Analytics] à des fins de création de rapports. Il se peut que vous disposiez d’un outil d’analyse interne que vous utilisez à des fins internes, mais que vous souhaitiez également envoyer les données d’analyse vers [!DNL Analytics] à l’aide de votre produit d’analyse interne afin que d’autres membres de votre organisation puissent continuer à l’utiliser [!DNL Analytics] comme source de création de rapports visuelle. Voir [Étape 7 : référencement at.js ou mbox.js sur toutes les pages du site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) dans *Implémentation d’Analytics pour Target* pour plus d’informations.

## Audiences partagées

Lorsque vous remplissez le [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences), tenez compte des informations importantes suivantes concernant l&#39;option [!UICONTROL Audiences partagées] répertoriée sous &quot;[!UICONTROL Pour quelles fonctionnalités demandez-vous de configurer ] ?&quot;

![Formulaire de demande](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Lorsque vous demandez des [!UICONTROL Audiences partagées], vous activez [!UICONTROL Cible] et [!UICONTROL Adobe Audience Manager] (AAM) pour partager des informations, dans ce cas les audiences.

>[!IMPORTANT]
>
>Cette intégration entre [!UICONTROL Cible] et AAM comporte des coûts supplémentaires. Vous serez facturé pour chaque appel [!UICONTROL Cible] en AAM.
