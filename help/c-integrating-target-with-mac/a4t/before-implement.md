---
keywords: Recommandations
description: Découvrez les exigences d’implémentation d’Analytics pour  [!DNL Target] (A4T) et les éléments à prendre en compte avant de mettre en oeuvre cette intégration.
title: Que dois-je savoir avant d’implémenter A4T ?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 34%

---

# Avant l’implémentation

Plusieurs modifications se produisent dans votre processus de collecte de données lors de l’activation de [!DNL Adobe Analytics] en tant que source de rapports pour [!DNL Adobe Target] (A4T).

Avant de décider d’utiliser cette intégration, consultez les sections suivantes et envisagez l’impact sur vos processus de création de rapports :

## Exigences d’implémentation {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Avant de pouvoir commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Utilisez le [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences) pour demander à être mis en service.

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
* Le processus de configuration de [!DNL Analytics] en tant que source de rapports pour [!DNL Target] comprend plusieurs étapes de mise en oeuvre, suivies d’une étape de mise en service. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. Une fois que vous avez terminé ces étapes, vous êtes prêt à utiliser [!DNL Analytics] comme source de rapports lorsqu&#39;elle est activée pour vous. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* [!DNL Visitor ID service] crée un [!DNL Visitor ID] partagé dans [!DNL Adobe Experience Cloud]. Bien qu’il ne remplace pas l’ID [!DNL Target] mboxPC ou l’UUID [!DNL Audience Manager], il remplace la manière dont [!DNL Analytics] identifie les nouveaux visiteurs. Si la configuration est correcte, les visiteurs [!DNL Analytics] renvoyés doivent également être identifiés par leur ancien [!DNL Analytics] identifiant. De même, étant donné que le [!DNL Target] mboxPCid reste intact, aucune donnée de profil de visiteur [!DNL Target] n’est perdue lorsque vous effectuez la mise à niveau vers [!DNL Visitor ID service].
* [!DNL Visitor ID service] doit s&#39;exécuter avant votre code de page [!DNL Analytics] et [!DNL Target]. Assurez-vous que `VisitorAPI.js` apparaît au-dessus des balises pour toutes les autres solutions [!DNL Experience Cloud].

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous aurez 5 à 10 minutes de latence supplémentaires dans [!DNL Analytics]. Cette augmentation de latence permet de stocker les données de [!DNL Analytics] et [!DNL Target] sur le même accès, ce qui vous permet de ventiler les activités par page et par section de site.

Cette augmentation se reflète dans tous les services et outils [!DNL Analytics], y compris le rapports en direct et en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

La latence augmente les débuts après la mise en oeuvre du service d’ID de visiteur [!DNL Experience Cloud], même si vous n’avez pas entièrement mis en oeuvre cette intégration.

## ID supplémentaire {#section_2C1F745A2B7D41FE9E30915539226E3A}

Tous les appels [!DNL Target] utilisés par une activité A4T pour diffuser du contenu ou enregistrer la mesure d’objectif doivent avoir un accès [!DNL Analytics] correspondant qui partage l’ID supplémentaire pour A4T pour fonctionner correctement.

Les accès qui contiennent des données provenant de [!DNL Analytics] et [!DNL Target] contiennent un ID de données supplémentaire. Vous pouvez voir cet ID dans le [débogueur de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) comme paramètre `sdid`. Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.
* Une version de [!DNL mbox.js] qui prend en charge cette intégration est implémentée.

Lorsque [dépannage](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), veillez à confirmer que l’ID supplémentaire est présent sur les accès [!DNL Analytics].

## Journalisation des analyses côté client {#client-side}

Si at.js, [!DNL Experience Cloud Visitor ID Service] et appMeasurement.js se trouvent sur la page [!DNL Analytics] et [!DNL Target] rassemble correctement les événements à des fins de rapports et d’analyse dans le serveur principal tant que l’ID supplémentaire correct est inclus dans la page. Vous n’avez pas besoin de gérer et d’effectuer d’autres opérations pour qu’A4T fonctionne correctement.

Dans certains cas, vous pouvez avoir plus de contrôle sur le moment et la manière d’envoyer des données d’analyse liées à [!DNL Target] à [!DNL Analytics] à des fins de rapports. Vous disposez peut-être d’un outil d’analyse interne que vous utilisez à des fins internes. Cependant, vous souhaitez également envoyer les données d’analyse à [!DNL Analytics] via votre produit d’analyse interne afin que d’autres membres de votre organisation puissent continuer à utiliser [!DNL Analytics] comme source de rapports visuel. Voir [Étape 7 : référencement at.js ou mbox.js sur toutes les pages du site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) dans *Implémentation d’Analytics pour Target* pour plus d’informations.

## Audiences partagées

Lorsque vous remplissez le [Marketing Cloud Integrations Provisioning Form](https://www.adobe.com/go/audiences), tenez compte des informations importantes suivantes concernant l&#39;option [!UICONTROL Audiences partagées] répertoriée sous &quot;[!UICONTROL Pour quelles fonctionnalités demandez-vous de configurer ] ?&quot;

![Formulaire de demande](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Lorsque vous demandez des [!UICONTROL Audiences partagées], vous activez [!UICONTROL Cible] et [!UICONTROL Adobe Audience Manager] (AAM) pour partager des informations, dans ce cas les audiences.

>[!IMPORTANT]
>
>Cette intégration entre [!UICONTROL Cible] et l&#39;AAM comporte des coûts supplémentaires. Vous êtes facturé pour chaque appel [!UICONTROL Cible] en AAM.
