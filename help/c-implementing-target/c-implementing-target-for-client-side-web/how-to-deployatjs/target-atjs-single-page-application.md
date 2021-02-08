---
keywords: implémentation d’applications d’une seule page ; implémenter une application d’une seule page ; spa ; at.js 2.x ; at.js ; application d’une seule page ; application d’une seule page ; spa ; SPA
description: Découvrez comment utiliser Adobe Target at.js 2.x pour implémenter la Cible pour les applications d’une seule page (SPA).
title: Puis-je mettre en oeuvre la Cible pour les applications d’une seule page (SPA) ?
feature: Implement Server-side
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Mise en œuvre d’une application d’une seule page

Les sites Web traditionnels fonctionnaient sur des modèles de navigation « page à page », appelés également applications multi-pages dans lesquelles les conceptions de site Web étaient étroitement couplées à des URL et les transitions d’une page Web à une autre nécessitaient un chargement de page. Les applications Web modernes, comme les applications monopages, adoptent plutôt un modèle qui projette rapidement le rendu de l’interface utilisateur du navigateur, ce qui est souvent indépendant des rechargements de page. Ces expériences sont souvent déclenchées par des interactions client, comme faire défiler, cliquer et faire bouger le curseur. À mesure de l’évolution des paradigmes du Web moderne, la pertinence des événements génériques traditionnels, comme le chargement des pages, pour déployer la personnalisation et les expériences ne fonctionnent plus.

![Cycle de vie traditionnel de la page par rapport au cycle de vie d’une application monopage](/help/c-experiences/assets/trad-vs-spa.png)

at.js 2.x offre des fonctionnalités diversifiées qui permettent à votre entreprise d’exécuter la personnalisation sur les technologies côté client de nouvelle génération. Cette version vise à améliorer at.js pour obtenir des interactions harmonieuses avec les applications monopages.

Voici quelques avantages de l’utilisation d’at.js 2.x qui ne sont pas disponibles dans les versions précédentes :

* Capacité à mettre en cache toutes les offres au chargement de la page afin de passer de plusieurs appels serveur à un seul appel serveur.
* Améliorez considérablement l’expérience de vos utilisateurs finaux sur votre site, car les offres sont immédiatement affichées via le cache, sans délai par les appels de serveur traditionnels.
* Une simple ligne de code et une configuration de développement unique pour permettre aux spécialistes marketing de créer et d’exécuter des activités A/B et de ciblage d’expérience (WT) via le VEC sur votre application monopage.

## Vues cibles et applications d’une seule page Adobe Target

Le VEC de Adobe Target pour les applications SPA tire profit d’un nouveau concept nommé Vues : un groupe logique d’éléments visuels qui, ensemble, forment une expérience pour application d’une seule page. Une application d’une seule page (SPA) peut donc être considérée comme une transition entre les vues (et pas entre les URL) basée sur les interactions des utilisateurs. Une Vue peut généralement représenter un site entier ou des éléments visuels regroupés dans un site.

Pour expliquer plus en détail les Vues, parcourez cet hypothétique site d’e-commerce en ligne implémenté dans React et explorez quelques exemples de Vues. Cliquez sur les liens ci-dessous pour ouvrir ce site dans un nouvel onglet du navigateur.

**Lien :  [Site d’accueil](https://target.enablementadobe.com/react/demo/#/)**

![page d’accueil](/help/c-experiences/assets/home.png)

Lorsque nous arrivons sur la page d’accueil, nous voyons immédiatement une image à forte identification qui présente les soldes de Pâques ainsi que les produits les plus récents en vente sur le site. Dans ce cas, une Vue peut être définie comme tout le site d’accueil. Ceci est bon à noter comme nous allons le développer dans la section Implémentation d’Adobe Target Views ci-dessous.

**Lien :  [Site de produits](https://target.enablementadobe.com/react/demo/#/products)**

![site produit](/help/c-experiences/assets/product-site.png)

Comme les produits vendus par l’entreprise nous paraissent intéressants, nous décidons de cliquer sur le lien Produits. Comme pour le site d’accueil, l’intégralité du site de produits peut être définie comme une ue.V Nous pouvons nommer cet affichage « produits » comme le nom de chemin d’accès dans `https://target.enablementadobe.com/react/demo/#/products)`.

![site produit 2](/help/c-experiences/assets/product-site-2.png)

Au début de cette section, nous avons défini les vues en tant que site entier ou même un groupe d’éléments visuels sur le site. Comme illustré ci-dessus, les quatre produits affichés sur le site peuvent également être regroupés et considérés comme une vue. Si nous souhaitons donner un nom à cet affichage, nous pouvons l’appeler « Produits ».

![site produit 3](/help/c-experiences/assets/product-site-3.png)

Nous décidons de cliquer sur le bouton Voir Plus pour découvrir d’autres produits sur le site. L’URL du site Web ne change pas dans ce cas. Mais une Vue ici ne représente que la deuxième ligne des produits ci-dessus. Cette Vue peut être appelée « PAGE-PRODUIT-2 ».

**Lien :  [Paiement](https://target.enablementadobe.com/react/demo/#/checkout)**

![page paiement](/help/c-experiences/assets/checkout.png)

Comme nous avons aimé certains produits sur le site, nous avons décidé d’en acheter quelques uns. Sur la page de paiement du site, certaines options permettent de choisir une livraison normale ou express. Parce qu’une Vue peut être n’importe quel groupe d’éléments visuels sur un site, nous pouvons l’appeler « Vue des préférences de livraison ».

De plus, le concept des Vues peut être beaucoup plus étendu. Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, l’affichage peut être appelé « Livraison normale ». Si l’option Livraison express est sélectionnée, l’affichage peut être appelé « Livraison express ».

Désormais, les spécialistes en marketing peuvent exécuter un test A/B pour déterminer si la modification de la couleur du bleu au rouge lorsque la livraison express est sélectionnée peut augmenter les conversions, contrairement au bouton de couleur bleue pour les deux options de livraison.

## Implémentation d’Adobe Target Views

À présent que nous avons examiné le concept d’Adobe Target Views, nous pouvons l’exploiter dans Target pour permettre aux spécialistes du marketing d’exécuter des tests AB et XT sur les applications monopages via le compositeur d’expérience visuelle. Une configuration développeur unique sera nécessaire. Examinons les étapes à suivre.

1. Installez at.js 2.x.

   Tout d’abord, nous devons installer at.js 2.x. Cette version d’at.js a été développée en tenant compte des applications monopages. Les versions précédentes d’at.js et de mbox.js ne prennent pas en charge les affichages d’Adobe Target et le compositeur d’expérience visuelle pour les applications monopages.

   Téléchargez at.js 2.x via l’interface utilisateur Adobe Target située dans [!UICONTROL Administration > Implémentation]. at.js 2.x peut également être déployé via Adobe Launch. Toutefois, les extensions d’Adobe Target ne sont pas encore disponibles ni prises en charge.

1. Implémentez la fonction la plus récente d’at.js 2.x `triggerView()` sur vos sites.

   Après avoir défini les affichages de votre application monopage où vous souhaitez exécuter un test A/B ou XT, implémentez la fonction `triggerView()` d’at.js 2.x avec les affichages transmis sous forme de paramètres. Cela permet aux spécialistes du marketing d’utiliser le compositeur d’expérience visuelle pour concevoir et exécuter les tests A/B et XT pour ces vues définies. Si la fonction `triggerView()` n’est pas définie pour ces affichages, le VEC ne détectera pas les affichages. Les spécialistes en marketing ne peuvent donc pas utiliser le VEC pour concevoir et exécuter des tests A/B et XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Paramètre | Type | Obligatoire ? | Validation | Description |
   | --- | --- | --- | --- | --- |
   | viewName | Chaîne | Oui | 1. Aucun espace à la fin.<br>2. Ne peut pas être vide.<br>3. Le nom de la vue doit être unique pour toutes les pages.<br>4. **Avertissement** : le nom de l’affichage ne doit pas commencer ou se terminer par « `/` ». Cela est dû au fait que le client extrait généralement le nom de la vue à partir du chemin d’URL. Pour nous, « accueil » et « `/home` » sont différents.<br>5. **Avertissement** : la même vue ne doit pas être déclenchée plusieurs fois avec l’option `{page: true}`. | Transmettez n’importe quel nom en tant que type de chaîne que vous souhaitez représenter votre vue. Ce nom d’affichage s’affiche dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
   | Options | Objet | Non |  |  |
   | options > page | Booléen | Non |  | **TRUE** : la valeur par défaut de la page est true. Lorsque `page=true`, des notifications sont envoyées aux serveurs Edge pour incrémenter le nombre d’impressions.<br>**FALSE** : lorsque `page=false`, les notifications ne sont pas envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

   Examinons maintenant quelques exemples d’utilisation pour appeler la fonction `triggerView()` dans React pour notre hypothétique SPA de commerce électronique :

   **Lien :  [Site d’accueil](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   En tant que marketeurs, si nous souhaitons exécuter des tests A/B sur tout le site d’accueil, nous pouvons nommer la vue « accueil » :

```
 function targetView() {
   var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash

   viewName = viewName || 'home'; // view name cannot be empty

   // Sanitize viewName to get rid of any trailing symbols derived from URL
   if (viewName.startsWith('#') || viewName.startsWith('/')) {
     viewName = viewName.substr(1);
   }

   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 // react router v4
 const history = syncHistoryWithStore(createBrowserHistory(), store);
 history.listen(targetView);

 // react router v3
 <Router history={hashHistory} onUpdate={targetView} >
```

**Lien :  [Site Produits](https://target.enablementadobe.com/react/demo/#/products)**

Examinons maintenant un exemple un peu plus complexe. En tant que marketeurs, nous voulons personnaliser la deuxième ligne des produits en modifiant la couleur de l’étiquette « Prix » en rouge après avoir cliqué sur le bouton Charger plus.

![produits React](/help/c-experiences/assets/react4.png)

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Products extends Component {
   render() {
     return (
       <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
     );
   }

   handleLoadMoreClicked() {
     var page = this.state.page + 1; // assuming page number is derived from component’s state
     this.setState({page: page});
     targetView('PRODUCTS-PAGE-' + page);
   }
 }
```

**Lien :  [Paiement](https://target.enablementadobe.com/react/demo/#/checkout)**

![Paiement React](/help/c-experiences/assets/react6.png)

Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, l’affichage peut être appelé « Livraison normale ». Si l’option Livraison express est sélectionnée, l’affichage peut être appelé « Livraison express ».

Les marketeurs souhaitent à présent exécuter un test AB pour déterminer si la modification de la couleur du bleu au rouge augmente les conversations lorsque la livraison express est sélectionnée, au lieu de conserver la couleur du bouton bleu pour les deux options de livraison.

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Checkout extends Component {
   render() {
     return (
       <div onChange={this.onDeliveryPreferenceChanged}>
         <label>
           <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
           <span> Normal Delivery (7-10 business days)</span>
         </label>

         <label>
           <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
           <span> Express Delivery* (2-3 business days)</span>
         </label>
       </div>
     );
   }
   onDeliveryPreferenceChanged(evt) {
     var selectedPreferenceValue = evt.target.value;
     targetView(selectedPreferenceValue);
   }
 }
```

## Diagrammes du système at.js 2.x

Les diagrammes suivants vous aident à comprendre le flux de tâches d’at.js 2.x avec les vues et la manière dont cela améliore l’intégration des applications web monopages. Pour une meilleure présentation des concepts utilisés dans at.js 2.x, voir [Implémentation d’applications monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Flux Target avec at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Étape | Détails |
| --- | --- |
| 1 | L’appel renvoie le [!DNL Experience Cloud ID] si l’utilisateur est authentifié. Un autre appel synchronise l’ID de client. |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>at.js peut également être chargé de manière asynchrone avec une option pré-masquant l’extrait de code implémenté sur la page. |
| 3 | Une demande de chargement de page est faite, incluant tous les paramètres configurés (MCID, SDID et ID client). |
| 4 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. Le magasin demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, audiences partagées depuis Adobe Analytics, Gestion de l’audience, etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 5 | Selon les paramètres de requête d’URL et les données de profil, [!DNL Target] décidez quelles activités et expériences renvoyer au visiteur pour la page active et les futures vues. |
| 6 | Le contenu ciblé est renvoyé à la page, comprenant, éventuellement, les valeurs de profil pour une personnalisation plus poussée.<br>Le contenu ciblé sur la page actuelle est affiché aussi rapidement que possible, sans scintillement du contenu par défaut.<br>Contenu ciblé pour les vues présentées à la suite d’actions de l’utilisateur dans une application d’une seule page cache dans le navigateur, afin qu’elles puissent être appliquées instantanément sans appel au serveur supplémentaire lorsque les vues sont `triggerView()` déclenchées. |
| 7 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 8 | Les données ciblées sont associées aux données d’Analytics par l’intermédiaire du SDID et sont traitées dans le stockage de rapports d’Analytics.<br>Il est alors possible de consulter les données Analytics dans Analytics et dans Target par l’intermédiaire des rapports Analytics for Target (A4T). |

Désormais, où que soit implémenté `triggerView()` sur votre application d’une seule page, les vues et actions sont récupérées depuis le cache et présentées à l’utilisateur sans appel au serveur. `triggerView()` envoie également une demande de notification au serveur principal [!DNL Target] afin d’incrémenter et d’enregistrer le nombre d’impressions.

![Déclencheur d’affichage at.js 2 de flux Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Étape | Détails |
| --- | --- |
| 3 | `triggerView()` est appelée dans l’application d’une seule page pour afficher les vues et appliquer les actions pour modifier les éléments visuels. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 1 | Le contenu ciblé s’affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils [!DNL Target] pour compter le visiteur dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d’A4T. |

## Compositeur d’expérience visuelle pour les applications monopages

Après avoir installé le fichier at.js 2.x et l’avoir ajouté `triggerView()` à votre site, utilisez VEC pour exécuter les activités AB et XT. Pour plus d’informations, reportez-vous au [Compositeur d’expérience visuelle pour application d’une seule page (SPA)](/help/c-experiences/spa-visual-experience-composer.md).

>[!NOTE]
>
>Le compositeur d’expérience visuelle pour applications d’une seule page est en fait le même compositeur d’expérience visuelle que celui que vous utilisez sur les pages web ordinaires, mais certaines fonctionnalités supplémentaires sont disponibles lorsque vous ouvrez une application d’une seule page avec l’implémentation `triggerView()`.

## Utilisez le déclencheur d’affichage pour vérifier que A4T fonctionne correctement avec at.js 2.x et les applications monopages. {#triggerview}

Pour garantir qu’[Analytics pour Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) fonctionne correctement avec at.js 2.x, veillez à envoyer le même SDID dans la requête Target et dans la requête Analytics.

En tant que bonnes pratiques liées aux applications monopages :

* Utilisez des événements personnalisés pour signaler qu’un élément intéressant se produit dans l’application
* Déclenchez un événement personnalisé avant que la vue ne commence le rendu
* Déclenchement d’un événement personnalisé lorsque la vue termine le rendu

at.js 2.x a ajouté une nouvelle fonction API [déclencheur de vue()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md). Vous devez utiliser `triggerView()` pour informer at.js qu’une vue commence le rendu.

Pour découvrir comment combiner des événements personnalisés, at.js 2.x et Analytics, voyons un exemple. Cet exemple suppose que la page HTML contient l’API visiteur, suivie d’at.js 2.x, suivie d’AppMeasurement.

Supposons que les événements personnalisés suivants soient présents :

* `at-view-start` - Lorsque la vue commence le rendu
* `at-view-end` - Lorsque la vue termine le rendu

Pour vérifier qu’A4T fonctionne avec at.js 2.x,

Le gestionnaire de démarrage d’affichage doit se présenter comme suit :

```
document.addEventListener("at-view-start", function(e) {
  var visitor = Visitor.getInstance("<your Adobe Org ID>");
  
  visitor.resetState();
  adobe.target.triggerView("<view name>");
});
```

Le gestionnaire de fin d’affichage doit ressembler à ceci :

```
document.addEventListener("at-view-end", function(e) {
  // s - is the AppMeasurement tracker object
  s.t();
});
```

>[!NOTE]
>
>Vous devez déclencher les événements `at-view-start` et `at-view-end`. Ces événements ne font pas partie des événements personnalisés at.js.

Bien que ces exemples utilisent du code JavaScript, tout cela peut être simplifié si vous utilisez un gestionnaire de balises, tel [qu’Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md).

Si les étapes précédentes sont suivies, vous devez disposer d’une solution A4T robuste pour les applications monopages.

## Meilleures pratiques de mise en oeuvre {#bp}

Les API at.js 2.x vous permettent de personnaliser votre implémentation [!DNL Target] de plusieurs manières, mais il est important de suivre l’ordre correct des opérations au cours de ce processus.

Les informations suivantes décrivent l’ordre des opérations que vous devez suivre lors du chargement d’une application d’une seule page pour la première fois dans un navigateur et pour toute modification de vue qui survient par la suite.

### Ordre des opérations pour le chargement initial de la page

| Étape | Action | Détails |
| --- | --- | --- |
| 3 | Load VisitorAPI JS | Cette bibliothèque est chargée d&#39;affecter un ECID au visiteur. Cet identifiant est ensuite utilisé par d&#39;autres solutions [!DNL Adobe] sur la page Web. |
| 2 | Chargement d’at.js 2.x | at.js 2.x charge toutes les API nécessaires à l’implémentation des requêtes et vues [!DNL Target]. |
| 3 | Exécuter la demande [!DNL Target] | Si vous disposez d’une couche de données, nous vous recommandons de charger les données critiques à envoyer à [!DNL Target] avant d’exécuter une requête [!DNL Target]. Vous pouvez ainsi utiliser `targetPageParams` pour envoyer les données que vous souhaitez utiliser pour le ciblage. Vous devez vous assurer que vous demandez execute > pageLoad ainsi que prefetch > vues dans cet appel d’API. si vous avez défini `pageLoadEnabled` et `viewsEnabled`, les deux variables execute > pageLoad et prefetch > vues se produisent automatiquement à l’étape 2 ; sinon, vous devez utiliser l&#39;API `getOffers()` pour effectuer cette demande. |
| 4 | L’appel `triggerView()` | Dans la mesure où la requête [!DNL Target] que vous avez lancée à l’étape 3 peut renvoyer des expériences pour l’exécution du chargement de page ainsi que pour les Vues, veillez à ce que `triggerView()` soit appelée une fois la requête [!DNL Target] renvoyée et termine l’application des offres au cache. Vous ne devez exécuter cette étape qu’une seule fois par vue. |
| 5 | Appelez la balise de vue de page [!DNL Analytics] | Cette balise envoie le SDID associé aux étapes 3 et 4 à [!DNL Analytics] pour l&#39;assemblage de données. |
| 6 | Appel supplémentaire `triggerView({"page": false})` | Il s’agit d’une étape facultative pour les structures SPA qui peuvent potentiellement rendre à nouveau certains composants de la page sans qu’un changement de vue ne se produise. Dans ce cas, il est important d’appeler cette API pour vous assurer que les expériences [!DNL Target] sont réappliquées une fois que la structure SPA a rendu les composants. Vous pouvez exécuter cette étape autant de fois que vous souhaitez vous assurer que les expériences [!DNL Target] persistent dans vos vues de SPA. |

### Ordre des opérations pour la modification de la vue SPA (pas de rechargement de page complète)

| Étape | Action | Détails |
| --- | --- | --- |
| 3 | L’appel `visitor.resetState()` | Cette API permet de s’assurer que le SDID est régénéré pour la nouvelle vue au cours de son chargement. |
| 2 | Mettre à jour le cache en appelant l&#39;API `getOffers()` | Il s&#39;agit d&#39;une étape facultative à suivre si cette modification de vue peut permettre de qualifier le visiteur actuel pour plus d&#39;activités [!DNL Target] ou de les exclure des activités. À ce stade, vous pouvez également choisir d’envoyer des données supplémentaires à [!DNL Target] pour activer d’autres fonctionnalités de ciblage. |
| 1 | L’appel `triggerView()` | Si vous avez exécuté l’étape 2, vous devez attendre la demande [!DNL Target] et appliquer les offres au cache avant d’exécuter cette étape. Vous ne devez exécuter cette étape qu’une seule fois par vue. |
| 4 | L’appel `triggerView()` | Si vous n’avez pas exécuté l’étape 2, vous pouvez exécuter cette étape dès que vous avez terminé l’étape 1. Si vous avez exécuté les étapes 2 et 3, ignorez cette étape. Vous ne devez exécuter cette étape qu’une seule fois par vue. |
| 5 | Appelez la balise de vue de page [!DNL Analytics] | Cette balise envoie le SDID associé aux étapes 2, 3 et 4 à [!DNL Analytics] pour l&#39;assemblage de données. |
| 6 | Appel supplémentaire `triggerView({"page": false})` | Il s’agit d’une étape facultative pour les structures SPA qui peuvent potentiellement rendre à nouveau certains composants de la page sans qu’un changement de vue ne se produise. Dans ce cas, il est important d’appeler cette API pour vous assurer que les expériences [!DNL Target] sont réappliquées une fois que la structure SPA a rendu les composants. Vous pouvez exécuter cette étape autant de fois que vous souhaitez vous assurer que les expériences [!DNL Target] persistent dans vos vues de SPA. |

## Vidéos de formation

Les vidéos suivantes comprennent davantage d’informations :

### Fonctionnement d’at.js 2  ![badge Aperçu](/help/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Voir [Description du fonctionnement d’at.js 2.x](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) pour plus d’informations.

### Implémentez at.js 2.x dans un SPA ![badge didacticiel](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26248)

Voir [Mise en oeuvre de l’Adobe Target at.js 2.x dans une application d’une seule page (SPA)](https://helpx.adobe.com/target/kt/using/atjs2-single-page-application-technical-video-implement.html) pour plus d’informations.

### Utilisation du compositeur d’expérience visuelle pour SPA en Adobe Target ![badge didacticiel](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Voir [Utilisation du compositeur d’expérience visuelle pour l’application d’une seule page (SPA VEC) dans Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) pour plus d’informations.
