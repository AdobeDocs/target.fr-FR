---
keywords: Recommendations ; paramètres ; préférences ; secteur industriel vertical ; critères de filtrage incompatibles ; groupe d’hôtes par défaut ; URL de base de la miniature ; jeton API de Recommendations
description: 'Découvrez comment implémenter des activités Recommendations dans Adobe Target. '
title: Comment Mettre En Oeuvre Des Activités Recommendations ?
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: fc2a9641b4b949b4d1308a5d17deff1754960bad
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 36%

---

# ![PREMIUM](/help/main/assets/premium.png) Planification et implémentation [!DNL Recommendations]

Avant de configurer votre premier [!DNL Recommendations] activité dans [!DNL Adobe Target], procédez comme suit :

1. [Mise en oeuvre [!DNL Target]](#implement-target) sur le web et les applications mobiles, les surfaces que vous souhaitez utiliser pour capturer le comportement des utilisateurs et diffuser des recommandations.
1. [Configurez vos [!DNL Recommendations] catalogue](#rec-catalog) de produits ou de contenu que vous souhaitez recommander à vos utilisateurs.
1. [Transmission des informations comportementales et du contexte](#pass-behavioral) to [!DNL Target Recommendations] pour lui permettre de fournir des recommandations personnalisées.
1. [Configuration des exclusions globales](#exclusions).
1. [Configurer [!DNL Recommendations] paramètres](#concept_C1E1E2351413468692D6C21145EF0B84).

## Mise en œuvre [!DNL Target] {#implement-target}

[!DNL Target Recommendations] nécessite que vous mettiez en oeuvre le [!DNL Adobe Experience Platform Web SDK] ou at.js 0.9.2 (ou version ultérieure). Voir [Mise en oeuvre [!DNL Target]](/help/main/c-implementing-target/implementing-target.md) pour plus d’informations.

## Configuration de votre catalogue Recommendations {#rec-catalog}

Pour fournir des recommandations de grande qualité, [!DNL Target] doivent connaître les produits ou le contenu que vous souhaitez recommander. Votre catalogue doit généralement inclure trois types d’informations sur les articles que vous souhaitez recommander. Supposons que vous recommandiez des films. Insérez les éléments suivants :

1. Données que vous souhaitez afficher pour l’utilisateur recevant la recommandation Vous pouvez, par exemple, afficher le nom du film et l’URL d’une miniature de l’affiche du film.
1. Données qui s’avèrent utiles pour appliquer des contrôles marketing et de marchandisage Par exemple, vous pouvez afficher la note du film afin de ne pas recommander de films NC-17.
1. Données utiles pour déterminer la similarité d’éléments avec d’autres éléments d’éléments. Vous pouvez, par exemple, afficher le genre du film et le réalisateur du film.

[!DNL Target] propose plusieurs options d’intégration pour compléter votre catalogue. Ces options peuvent être utilisées conjointement pour mettre à jour différents éléments du catalogue ou pour mettre à jour différents attributs d’élément sur différentes fréquences.

| Méthode | Qu’est-ce que c’est ? | Quand l’utiliser | Informations supplémentaires |
| --- | --- | --- | --- |
| Flux de catalogue | Planification d’un flux (CSV, Google Product XML, ou [!DNL Analytics Product Classifications]) à charger et à ingérer quotidiennement. | Pour envoyer des informations sur plusieurs éléments à la fois. Pour envoyer des informations qui changent rarement. | Voir [Flux](/help/main/c-recommendations/c-products/feeds.md). |
| API Entités | Appelez une API pour envoyer des mises à jour instantanées pour un seul élément. | Pour envoyer des mises à jour lorsqu’elles surviennent sur un élément à la fois. Pour envoyer des informations qui changent fréquemment (par exemple, le prix, le stock/le niveau de stock). | Voir [Documentation destinée aux développeurs de l’API Entities](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| Transmission des mises à jour sur la page | Envoyez les mises à jour instantanées d’un seul élément à l’aide de JavaScript sur la page ou de l’API de diffusion. | Pour envoyer des mises à jour lorsqu’elles surviennent sur un élément à la fois. Pour envoyer des informations qui changent fréquemment (par exemple, le prix, le stock/le niveau de stock). | Voir [Consultations d’articles/pages de produits](#items-product-pages) ci-dessous. |

La plupart des clients doivent mettre en oeuvre au moins un flux. Vous pouvez ensuite choisir de compléter votre flux avec des mises à jour pour les attributs ou éléments fréquemment modifiés à l’aide de l’API Entités ou de la méthode sur la page.

## Transmission des informations comportementales et du contexte {#pass-behavioral}

Les informations comportementales et le contexte auxquels vous devez transmettre [!DNL Target] dépend de l’action effectuée par le visiteur, souvent associée au type de page avec lequel le visiteur interagit.

### Consultations d’articles/pages de produits {#items-product-pages}

Sur les pages où un visiteur consulte un seul élément, comme une page des détails du produit, vous devez transmettre l’identité de l’élément que le visiteur consulte. Vous devez également transmettre la catégorie la plus granulaire de l’élément que le visiteur consulte, afin de permettre le filtrage des recommandations sur la catégorie actuelle.

Vous pouvez également transmettre certains attributs qui changent rapidement sur la page de produits elle-même. Par exemple, vous pouvez transmettre le prix (`value`) et au niveau du stock/du stock.

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### Vues de catégorie/pages de catégorie

Sur une page de catégorie, il est probable que vous souhaitiez limiter vos recommandations aux produits ou au contenu de cette catégorie. Pour ce faire, veillez à transmettre l’identité de la catégorie actuellement consultée.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### Ajouts au panier/consultations de panier/pages de passage en caisse {#cart}

Sur une page de panier, vous pouvez recommander des articles en fonction du contenu du panier actuel du visiteur. Pour ce faire, transmettez les identifiants de tous les éléments du panier actuel du visiteur à l’aide du paramètre spécial . `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": "352,223,23432,432,553"
      }
}
```

Pour plus d’informations sur [!UICONTROL Basé sur le panier] recommandations, voir [Basé sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) in *Baser la recommandation sur une clé de recommandation*.

### Exclure les éléments déjà présents dans le panier du visiteur

Sur les pages de votre site, vous pouvez exclure certains éléments des recommandations. Par exemple, vous pouvez ne pas recommander des articles qui se trouvent déjà dans le panier actuel du visiteur. Pour ce faire, transmettez les identifiants de tous les éléments que vous souhaitez exclure à l’aide du paramètre spécial . `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": "352,223,23432,432,553"
      }
}
```

### Pages de confirmation des achats/commandes

Lorsqu’un événement d’achat se produit, transmettez l’identité du ou des articles achetés. Voir [Suivi des conversions](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) in *Mise en oeuvre [!DNL Target] sans gestionnaire de balises*.

## Configuration des exclusions globales {#exclusions}

Excluez tous les éléments à un niveau global que vous ne souhaitez jamais recommander à un visiteur. Voir [Exclusions](/help/main/c-recommendations/c-products/exclusions.md).

## Configurer [!DNL Recommendations] paramètres {#concept_C1E1E2351413468692D6C21145EF0B84}

Utilisez les paramètres pour gérer votre implémentation de [!DNL Recommendations].

Pour accéder au [!UICONTROL Paramètres Recommendations] options, ouvrir [!DNL Target] dans le [!DNL Adobe Experience Cloud], puis cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Paramètres]**.

![](assets/recs_settings.png)

Les options disponibles sont les suivantes :

| Paramètre | Description |
|--- |--- |
| Mbox globale personnalisée | (Facultatif) Indiquez la mbox globale personnalisée utilisée pour les activités [!DNL Target]. Par défaut, la mbox globale utilisée par [!DNL Target] est utilisé pour [!DNL Recommendations].<br>Remarque : Cette option est définie sur la variable [!DNL Target] [!UICONTROL Administration] page. Ouvrir [!DNL Target], puis cliquez sur [!UICONTROL Administration] > [!UICONTROL Compositeur d’expérience visuelle]. |
| Secteur industriel vertical | Le secteur industriel vertical permet de classer les critères de recommandations. Ces informations aident les membres de votre équipe à trouver des critères logiques pour une page spécifique, tels que les critères les mieux adaptés à la page du panier ou à une page multimédia. |
| Filtrer les critères incompatibles | Activez cette option pour afficher uniquement les critères pour lesquels la page sélectionnée transmet les données requises. Tous les critères ne s’exécutent pas correctement sur chaque page. La page ou la mbox doit être transmise `entity.id` ou `entity.categoryId` pour que les recommandations d’élément/de catégorie actuel(le) soient compatibles. En général, il est préférable de n’afficher que les critères compatibles. Néanmoins, si vous souhaitez que des critères incompatibles soient disponibles pour l’activité, décochez l’option.<br>Il est recommandé de désactiver cette option si vous utilisez une solution de gestion des balises.<br>Pour plus d’informations sur cette option, voir [Forum aux questions (FAQ) de Recommandations](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md). |
| Groupe d’hôtes par défaut | Sélectionnez votre groupe d’hôtes par défaut.<br>Le groupe d’hôtes peut servir à séparer les éléments disponibles dans votre catalogue pour différents usages. Par exemple, vous pouvez utiliser des groupes d’hôtes pour les environnements de développement et de production, des marques différentes ou différentes zones géographiques. Par défaut, les résultats d’aperçu dans la recherche de catalogue, les collections et les exclusions sont basés sur le groupe d’hôtes par défaut. (Vous pouvez également sélectionner un autre groupe d’hôtes pour prévisualiser les résultats à l’aide du filtre Environnement.) Par défaut, les éléments nouvellement ajoutés sont disponibles dans tous les groupes d’hôtes, sauf si un identifiant d’environnement est spécifié lors de la création ou de la mise à jour de l’élément. Les recommandations fournies dépendent du groupe d’hôtes spécifié dans la requête.<br>Si vos produits ne sont pas répertoriés, vérifiez que vous utilisez le groupe d’hôtes approprié. Si, par exemple, vous configurez votre recommandation pour utiliser un environnement d’évaluation et que vous définissez votre groupe d’hôtes sur Évaluation, il se peut que vous deviez recréer vos collections dans l’environnement d’évaluation pour les produits à afficher. Pour voir quels produits sont disponibles dans chaque environnement, utilisez la recherche catalogue pour chaque environnement. Vous pouvez également prévisualiser le contenu des collections et exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).<br>**Remarque :** après avoir modifié l’environnement sélectionné, vous devez cliquer sur Rechercher pour mettre à jour les résultats renvoyés.<br>Le filtre [!UICONTROL Environnement] est disponible à partir des emplacements suivants dans l’interface utilisateur de [!DNL Target] :<ul><li>Recherche catalogue (Recommandations > Recherche catalogue)</li><li>Boîte de dialogue Créer une collection ([!UICONTROL Recommandations > Collections > Créer nouveau])</li><li>Boîte de dialogue Mettre à jour la collection ([!UICONTROL Recommandations > Collections > Modifier])</li><li>Boîte de dialogue Créer une exclusion ([!UICONTROL Recommandations > Exclusions > Créer nouveau])</li><li>Boîte de dialogue Mettre à jour l’exclusion ([!UICONTROL Recommandations > Exclusions > Modifier])</li></ul>Pour plus d’informations, voir [Hôtes](/help/main/administrating-target/hosts.md). |
| URL de base de la miniature | La définition d’une URL de base pour votre catalogue de produits rend possible l’utilisation d’URL relatives lors de la spécification de miniatures de vos produits lors du transfert de votre URL de miniature.<br>Par exemple :<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>définit une URL relative à l’URL de base de la miniature. |
| Jeton API de Recommendations | Utilisez ce jeton dans les appels à l’API de recommandations, comme l’API de téléchargement. |
