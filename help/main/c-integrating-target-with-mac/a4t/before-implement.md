---
keywords: Recommendations
description: Découvrez les exigences d’implémentation d’Analytics for  [!DNL Target] (A4T) et les éléments à prendre en compte avant d’implémenter cette intégration.
title: Que Dois-Je Savoir Avant De Mettre En Œuvre A4T ?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 656f728ba890f1f5afc0404e22f6acb1a2565fe6
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 24%

---

# Avant d’implémenter Analytics for Target (A4T) avec at.js

Plusieurs modifications se produisent dans votre processus de collecte de données lors de l’activation d’[!DNL Adobe Analytics] en tant que source de création de rapports pour [!DNL Adobe Target] (A4T).

Avant de décider d’utiliser cette intégration, consultez les sections suivantes et tenez compte de l’impact sur vos processus de création de rapports.

>[!NOTE]
>
>Cet article s’applique uniquement aux implémentations d’at.js. Pour plus d’informations sur l’implémentation de [!UICONTROL Analytics for Target] (A4T) avec le [!DNL Adobe Experience Platform Web SDK], consultez [Connexion à Adobe Analytics for Target (A4T) dans Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/a4t/overview-a4t.html){target=_blank}.

## Exigences d’implémentation {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Avant de commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Utilisez le Formulaire de configuration des intégrations Marketing Cloud [&#128279;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} pour demander à être configuré.

Cette intégration A4T nécessite l’implémentation des versions de bibliothèque suivantes (ou plus récentes), selon que vous souhaitez utiliser ou non les offres de redirection avec A4T.

>[!NOTE]
>
>La liste des exigences suivantes répertorie les versions *minimales* d’at.js nécessaires à l’implémentation d’A4T. L’équipe [!DNL Target] ne conserve que deux versions de [!DNL at.js] : la version actuelle et la deuxième version la plus récente. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge. Pour en savoir plus sur le contenu de chaque version, voir [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

### Conditions requises si vous *n*’utilisez pas les offres de redirection avec A4T

Cette intégration requiert que vous mettiez en œuvre les versions suivantes (ou plus récentes) de la bibliothèque si vous ne prévoyez pas d’utiliser les offres de redirection avec A4T. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service] : visitorAPI.js version 1.8.0
* [!DNL Adobe Target] : at.js version 0.9.1
* Adobe Analytics : appMeasurement.js version 1.7.0

Pour plus d’informations sur l’implémentation d’A4T avec [!DNL Platform Web SDK], consultez la section [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

### Conditions requises en cas d’utilisation des offres de redirection avec A4T

Pour utiliser des offres de redirection avec A4T, vous devez mettre en œuvre les versions suivantes (ou plus récentes) de la bibliothèque. L’ordre indiqué est l’ordre des opérations.

* [!DNL Experience Cloud Visitor ID Service] : visitorAPI.js version 2.3.0

  >[!NOTE]
  >
  >at.js 1.8.0+ et at.js 2.x+ ne fonctionnent plus avec les versions d’API visiteur antérieures à la version 2.5.0 pour la transmission de paramètres Adobe Audience Manager (AAM).

* [!DNL Adobe Target] : at.js version 1.6.2

* Adobe Analytics : appMeasurement.js version 2.1

Les instructions de téléchargement et de déploiement sont répertoriées dans la section [Implémentation d’Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Pour plus d’informations sur l’implémentation d’A4T avec [!DNL Platform Web SDK], consultez la section [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

## Informations à connaître avant l&#39;implémentation {#section_50D49CC52E11414089C89FB67F9B88F5}

* Cette intégration est activée sur les nouvelles activités lorsque vous choisissez d’utiliser [!DNL Analytics] comme source de création de rapports. Après avoir apporté les modifications de mise en œuvre décrites dans ce document, les activités existantes ne sont pas affectées.
* Le processus de configuration d’[!DNL Analytics] comme source de création de rapports pour [!DNL Target] comprend plusieurs étapes d’implémentation, suivies d’une étape d’approvisionnement. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. Une fois ces étapes terminées, vous êtes prêt à utiliser [!DNL Analytics] comme source de création de rapports lorsqu’elle sera activée pour vous. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* L’[!DNL Visitor ID service] crée une [!DNL Visitor ID] partagée sur l’ensemble du [!DNL Adobe Experience Cloud]. Bien qu’il ne remplace pas l’ID mboxPC [!DNL Target] ou l’UUID [!DNL Audience Manager], il remplace la manière dont [!DNL Analytics] identifie les nouveaux visiteurs. S’il est correctement configuré, les visiteurs [!DNL Analytics] récurrents doivent également être identifiés à l’aide de leur ancien identifiant [!DNL Analytics]. De même, comme le mboxPCid [!DNL Target] reste intact, aucune donnée de profil [!DNL Target] visiteur n’est perdue lorsque vous effectuez une mise à niveau vers le [!DNL Visitor ID service] .
* Le [!DNL Visitor ID service] doit s’exécuter avant votre [!DNL Analytics] et [!DNL Target] le code de page. Assurez-vous que `VisitorAPI.js` apparaît au-dessus des balises pour toutes les autres solutions [!DNL Experience Cloud].

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous constaterez 5 à 10 minutes de latence supplémentaires en [!DNL Analytics]. Cette augmentation de la latence permet de stocker les données de [!DNL Analytics] et [!DNL Target] sur le même accès, ce qui vous permet de ventiler les activités par page et section de site.

Cette augmentation se reflète dans tous les services et outils [!DNL Analytics], y compris les rapports en direct et en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actuelles sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

L’augmentation de la latence commence après la mise en œuvre du service d’identification des visiteurs [!DNL Experience Cloud], même si vous n’avez pas entièrement mis en œuvre cette intégration.

## ID supplémentaire {#section_2C1F745A2B7D41FE9E30915539226E3A}

Tous les appels [!DNL Target] utilisés par une activité A4T pour diffuser du contenu ou enregistrer la mesure d’objectif doivent avoir un accès [!DNL Analytics] correspondant qui partage l’ID supplémentaire pour que A4T fonctionne correctement.

Les accès contenant des données provenant de [!DNL Analytics] et [!DNL Target] un ID de données supplémentaire. Cet identifiant apparaît dans [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) comme paramètre `sdid`. Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.

Lors du [dépannage](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), vérifiez que l’ID supplémentaire est présent sur les accès [!DNL Analytics].

## Journalisation d’Analytics côté client {#client-side}

Si at.js, le [!DNL Experience Cloud Visitor ID Service] et appMeasurement.js se trouvent sur la page, [!DNL Analytics] et [!DNL Target] regroupe correctement les événements à des fins de création de rapports et d’analyse dans le serveur principal de , à condition que l’ID supplémentaire correct soit inclus à partir de la page. Vous n’avez pas besoin de gérer et d’effectuer d’autres opérations pour que A4T fonctionne correctement.

Dans certains cas, vous souhaiterez peut-être mieux contrôler quand et comment envoyer les données d’analyse liées à [!DNL Target] à [!DNL Analytics] à des fins de création de rapports. Vous disposez peut-être d’un outil d’analyse interne que vous utilisez à des fins internes. Cependant, vous souhaitez également envoyer les données d’analyse à [!DNL Analytics] [!DNL Analytics] via votre produit d’analyse interne afin que d’autres membres de votre organisation puissent continuer à l’utiliser comme source de rapports visuels. Voir [Étape 7 : référencer at.js sur toutes les pages du site](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) dans *Implémentation d’Analytics for Target* pour plus d’informations.

## Audiences partagées

Lorsque vous remplissez le Formulaire de configuration des intégrations Marketing Cloud [&#128279;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}, tenez compte des informations importantes suivantes concernant l’option [!UICONTROL Shared Audiences] répertoriée sous « [!UICONTROL For which capabilities are you requesting provisioning] ? »

![Formulaire de demande](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Lorsque vous demandez des [!UICONTROL Shared Audiences], vous activez [!UICONTROL Target] et [!UICONTROL Adobe Audience Manager] (AAM) pour partager des informations, dans ce cas des audiences.

>[!IMPORTANT]
>
>Cette intégration entre [!UICONTROL Target] et AAM s’accompagne de coûts supplémentaires. Vous êtes facturé pour chaque appel [!UICONTROL Target] dans AAM.
