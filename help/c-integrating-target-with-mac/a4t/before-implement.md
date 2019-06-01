---
description: Plusieurs modifications se produisent dans le processus de collecte de données lors de l’activation d’Analytics en tant que source des rapports pour Target (A4T).
keywords: Recommandations
seo-description: Plusieurs modifications se produisent dans le processus de collecte de données lors de l’activation d’Analytics en tant que source des rapports pour Target (A4T).
seo-title: Avant l’implémentation Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)
solution: Target
title: Avant l’implémentation
topic: Premium
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: f3d4963da631c668fb53a3939df53c80adff468b

---


# Avant l’implémentation{#before-you-implement}

Plusieurs modifications se produisent dans le processus de collecte de données lors de l’activation d’Analytics en tant que source des rapports pour Target (A4T).

Avant de décider d’utiliser cette intégration, consultez les sections suivantes et envisagez l’impact sur vos processus de création de rapports :

## Exigences en matière d&#39;implémentation {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Avant de commencer à utiliser A4T, vous devez demander que votre compte soit configuré pour l’intégration. Pour ce faire, utilisez [ce formulaire](https://www.adobe.com/go/audiences).

Cette intégration A 4 T requiert que vous implémentiez les versions de bibliothèque suivantes (ou plus récentes), selon que vous souhaitez utiliser des offres de redirection avec A 4 T ou non :

### Conditions requises si *vous n* &#39;utilisez pas les offres de redirection avec A 4 T

Cette intégration requiert que vous implémentiez les versions de bibliothèque suivantes (ou plus récentes) si vous n&#39;envisagez pas d&#39;utiliser des offres de redirection avec A 4 T. L&#39;ordre indiqué est l&#39;ordre des opérations.

* Service d’identification des visiteurs Experience Cloud : visitorAPI.js version 1.8.0
* Adobe Target (selon votre mise en œuvre) : at.js version 0.9.1 ou mbox.js version 61.
* Adobe Analytics : appMeasurement.js version 1.7.0

### Conditions requises en cas d&#39;utilisation des offres de redirection avec A 4 T

Pour utiliser des offres de redirection avec A 4 T, vous devez implémenter les versions de bibliothèque suivantes (ou plus récentes). L&#39;ordre indiqué est l&#39;ordre des opérations.

* Service d’identification des visiteurs Experience Cloud : visitorAPI.js version 2.3.0
* Adobe Target : at. js version 1.6.2

   **Remarque :** La bibliothèque mbox.js ne prend pas en charge les offres de redirection avec A4T. Votre mise en œuvre doit utiliser at.js.

* Adobe Analytics : appMeasurement.js version 2.1

Les instructions de téléchargement et de déploiement sont répertoriées dans [Adobe pour implémentation de Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_a4timplementation.html).

## Informations à connaître avant l&#39;implémentation {#section_50D49CC52E11414089C89FB67F9B88F5}

* Cette intégration est activée sur les nouvelles activités lorsque vous sélectionnez Analytics en tant que source de création de rapports. Après avoir apporté les modifications de mise en œuvre décrites dans ce document, les activités existantes ne sont pas affectées.
* Le processus de configuration d’Analytics en tant que source de création de rapports pour Target inclut plusieurs étapes d’implémentation suivies d’une étape d’attribution des privilèges d’accès. Il est préférable de lire le processus décrit ci-dessous avant de procéder à l’implémentation. Une fois que vous avez terminé ces étapes, vous êtes prêt à utiliser Analytics en tant que source de création de rapports dès que l’application est activée. Le processus d’attribution des privilèges d’accès peut prendre jusqu’à cinq jours ouvrables.
* Le service d’identification des visiteurs crée un identifiant visiteur partagé sur l’ensemble d’Experience Cloud. Bien qu’il ne remplace pas l’ID mboxPC de Target ni l’UUID d’Audience Manager, il remplace néanmoins la façon dont Analytics identifie les nouveaux visiteurs. Quand la configuration est correcte, les visiteurs Analytics récurrents devraient également être identifiés grâce à leur ancien identifiant Analytics afin d’éviter qu’ils ne soient considérés comme de nouveaux visiteurs. De même, puisque l’identifiant mboxPC reste intact, aucune donnée des profils de visiteur Target n’est perdue lorsque vous passez au service d’identification des visiteurs.
* Le service Identifiant visiteur doit être exécuté avant votre code de page Analytics et Target. Assurez-vous que `VisitorAPI.js` s’affiche au-dessus des balises de tous les produits Experience Cloud.

## Latence {#section_9489BE6FD21641A4844E591711E3F813}

Une fois cette intégration activée, vous subirez 5 à 10 minutes supplémentaires de latence dans Adobe Analytics. Cette augmentation de la latence permet aux données provenant d’Analytics et de Target d’être stockées sur le même accès, permettant de ventiler les tests par page et par section de site.

Cette augmentation se reflète dans tous les services et outils d’Adobe Analytics, notamment la diffusion en continu active et la création de rapports en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Gardez à l’esprit que l’augmentation de latence débute une fois que vous avez implémenté le service d’identification des visiteurs d’Experience Cloud, même si vous n’avez pas entièrement implémenté cette intégration.

## ID supplémentaire  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Tous les appels Target utilisés par une activité Analytics pour Target (A4T) pour diffuser du contenu ou enregistrer la mesure d’objectif doivent avoir un accès Analytics correspondant partageant le même ID supplémentaire pour Analytics pour Target pour fonctionner correctement.

Les accès qui contiennent des données provenant d’Analytics et de Target contiennent un ID de données supplémentaire. Vous pouvez voir cet ID dans [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger) sous la forme du paramètre `sdid`. Par exemple :`sdid=2F3C18E511F618CC-45F83E994AEE93A0` Cet ID est généré chaque fois que les critères suivants sont respectés :

* Le service d’identification des visiteurs est implémenté.
* Une version de [!DNL mbox.js] qui prend en charge cette intégration est implémentée.

Lors du dépannage, veillez à confirmer que l’ID supplémentaire est présent sur les accès Analytics.

## Journalisation Analytics côté client {#client-side}

Par défaut, lorsque at. js, le [!DNL Experience Cloud Visitor ID Service]fichier appmeasurement. js se trouve sur la page et [!DNL Adobe Analytics] qu&#39;il convient d&#39;associer [!DNL Target] correctement les événements à des fins de création de rapports et analyses dans le serveur principal tant que l&#39;ID supplémentaire de l&#39;ID supplémentaire est inclus dans la page, comme mentionné ci-dessus. Il n&#39;est pas nécessaire de gérer et d&#39;effectuer des opérations supplémentaires pour que A 4 T fonctionne correctement.

Cependant, il se peut que vous souhaitiez mieux contrôler quand et comment envoyer des données d&#39;analyse liées à [!DNL Target][!DNL Analytics] des fins de création de rapports. Vous pouvez utiliser un outil d&#39;analyse interne que vous utilisez à des fins internes, mais souhaitez également envoyer les données d&#39;analyse à [!DNL Analytics] l&#39;aide de votre produit d&#39;analyse interne afin que d&#39;autres membres de votre organisation puissent continuer à l&#39;utiliser [!DNL Analytics] comme source de création de rapports visuelle. Voir [étape 7 : Pour plus d&#39;informations, référencez at. js ou mbox. js sur toutes les pages](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) du site dans *Analytics pour l&#39;implémentation* de Target.
