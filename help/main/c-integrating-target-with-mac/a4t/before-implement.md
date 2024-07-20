---
keywords: Recommendations
description: Découvrez les exigences de mise en oeuvre d’Analytics for [!DNL Target] (A4T) et ce que vous devez prendre en compte avant de mettre en oeuvre cette intégration.
title: Que dois-je savoir avant d’implémenter A4T ?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 23%

---

# Avant de mettre en oeuvre Analytics for Target (A4T) avec at.js

Plusieurs modifications se produisent dans votre processus de collecte de données lors de l’activation de [!DNL Adobe Analytics] en tant que source des rapports pour [!DNL Adobe Target] (A4T).

Avant de décider d’utiliser cette intégration, passez en revue les sections suivantes et examinez l’impact sur vos processus de création de rapports.

>[!NOTE]
>
>Cet article s’applique uniquement aux implémentations d’at.js.

## Exigences d’implémentation {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Avant de pouvoir commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Utilisez le [Marketing Cloud Integrations Provisioning Form](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} pour demander à être configuré.

Cette intégration A4T requiert que vous mettiez en oeuvre les versions de bibliothèque suivantes (ou plus récentes), selon que vous souhaitez utiliser ou non les offres de redirection avec A4T.

>[!NOTE]
>
>Les exigences suivantes répertorient les versions *minimum* d’at.js nécessaires à la mise en oeuvre d’A4T. L’équipe [!DNL Target] gère uniquement deux versions de [!DNL at.js] : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge. Pour plus d’informations sur ce qui se trouve dans chaque version, voir [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

### Conditions requises si vous *n*’utilisez pas les offres de redirection avec A4T

Cette intégration requiert que vous mettiez en œuvre les versions suivantes (ou plus récentes) de la bibliothèque si vous ne prévoyez pas d’utiliser les offres de redirection avec A4T. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service] : visitorAPI.js version 1.8.0
* [!DNL Adobe Target] : at.js version 0.9.1
* Adobe Analytics : appMeasurement.js version 1.7.0

Pour plus d’informations sur l’implémentation d’A4T avec [!DNL Platform Web SDK], voir [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

### Conditions requises en cas d’utilisation des offres de redirection avec A4T

Pour utiliser des offres de redirection avec A4T, vous devez mettre en œuvre les versions suivantes (ou plus récentes) de la bibliothèque. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service] : visitorAPI.js version 2.3.0

  >[!NOTE]
  >
  >at.js 1.8.0+ et at.js 2.x+ ne fonctionnent plus avec les versions d’API visiteur antérieures à la version 2.5.0 pour la transmission de paramètres Adobe Audience Manager (AAM).

* [!DNL Adobe Target] : at.js version 1.6.2

* Adobe Analytics : appMeasurement.js version 2.1

Les instructions de téléchargement et de déploiement sont répertoriées dans [Implémentation d’Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Pour plus d’informations sur l’implémentation d’A4T avec [!DNL Platform Web SDK], voir [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

## Informations à connaître avant l&#39;implémentation {#section_50D49CC52E11414089C89FB67F9B88F5}

* Cette intégration est activée sur les nouvelles activités lorsque vous choisissez d’utiliser [!DNL Analytics] comme source de création de rapports. Après avoir apporté les modifications de mise en œuvre décrites dans ce document, les activités existantes ne sont pas affectées.
* Le processus de configuration de [!DNL Analytics] en tant que source de création de rapports pour [!DNL Target] comprend plusieurs étapes d’implémentation, suivies d’une étape de mise en service. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. Une fois ces étapes terminées, vous êtes prêt à utiliser [!DNL Analytics] comme source de création de rapports lorsqu’elle est activée pour vous. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* [!DNL Visitor ID service] crée un [!DNL Visitor ID] partagé sur l&#39;ensemble de [!DNL Adobe Experience Cloud]. Bien qu&#39;il ne remplace pas l&#39;identifiant mboxPC [!DNL Target] ou l&#39;UUID [!DNL Audience Manager], il remplace la manière dont [!DNL Analytics] identifie les nouveaux visiteurs. Si la configuration est correcte, les visiteurs [!DNL Analytics] récurrents doivent également être identifiés via leur ancien [!DNL Analytics] ID. De même, comme le mboxPCid [!DNL Target] reste intact, aucune donnée de profil du visiteur [!DNL Target] n’est perdue lorsque vous effectuez la mise à niveau vers [!DNL Visitor ID service].
* L’ [!DNL Visitor ID service] doit s’exécuter avant le code de page [!DNL Analytics] et [!DNL Target]. Assurez-vous que `VisitorAPI.js` s’affiche au-dessus des balises pour toutes les autres solutions [!DNL Experience Cloud].

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous remarquerez une latence supplémentaire de 5 à 10 minutes dans [!DNL Analytics]. Cette augmentation de latence permet aux données de [!DNL Analytics] et [!DNL Target] d’être stockées sur le même accès, ce qui vous permet de ventiler les activités par page et par section de site.

Cette augmentation se reflète dans tous les services et outils [!DNL Analytics], y compris les rapports en continu et en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

L’augmentation de latence débute une fois que vous avez implémenté le service d’identification des visiteurs [!DNL Experience Cloud], même si vous n’avez pas entièrement implémenté cette intégration.

## ID supplémentaire {#section_2C1F745A2B7D41FE9E30915539226E3A}

Tous les appels [!DNL Target] utilisés par une activité A4T pour diffuser du contenu ou enregistrer la mesure d’objectif doivent avoir un accès [!DNL Analytics] correspondant partageant l’ID supplémentaire pour qu’A4T fonctionne correctement.

Les accès qui contiennent des données provenant de [!DNL Analytics] et [!DNL Target] contiennent un ID de données supplémentaire. Vous pouvez voir cet ID dans le [débogueur Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) comme paramètre `sdid` . Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.

Lors de la [résolution des problèmes](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), veillez à confirmer que l’ID supplémentaire est présent sur les accès [!DNL Analytics].

## Journalisation Analytics côté client {#client-side}

Si at.js, [!DNL Experience Cloud Visitor ID Service] et appMeasurement.js se trouvent sur la page, [!DNL Analytics] et [!DNL Target] assemblent correctement les événements à des fins de création de rapports et d’analyse dans le serveur principal tant que le bon ID supplémentaire est inclus à partir de la page. Vous n’avez pas besoin de gérer et d’effectuer des opérations supplémentaires pour que A4T fonctionne correctement.

Dans certains cas, vous souhaiterez peut-être mieux contrôler quand et comment envoyer des données d’analyse liées à [!DNL Target] vers [!DNL Analytics] à des fins de création de rapports. Vous pouvez disposer d’un outil d’analyse interne que vous utilisez à des fins internes. Cependant, vous souhaitez également envoyer les données d’analyse à [!DNL Analytics] via votre produit d’analyse interne afin que d’autres membres de votre organisation puissent continuer à utiliser [!DNL Analytics] comme source de création de rapports visuelle. Pour plus d’informations, voir [Étape 7 : référencer at.js sur toutes les pages du site](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) dans *Implémentation d’Analytics pour Target*.

## Audiences partagées

Lors du remplissage du [ Marketing Cloud Integrations Provisioning Form](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}, prenez connaissance des informations importantes suivantes concernant l’option [!UICONTROL Shared Audiences] répertoriée sous &quot;[!UICONTROL For which capabilities are you requesting provisioning]?&quot;

![Formulaire de demande](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Lorsque vous demandez [!UICONTROL Shared Audiences], vous activez [!UICONTROL Target] et [!UICONTROL Adobe Audience Manager] (AAM) pour partager des informations, dans ce cas des audiences.

>[!IMPORTANT]
>
>Cette intégration entre [!UICONTROL Target] et AAM comporte des coûts supplémentaires. Vous êtes facturé pour chaque appel [!UICONTROL Target] dans AAM.
