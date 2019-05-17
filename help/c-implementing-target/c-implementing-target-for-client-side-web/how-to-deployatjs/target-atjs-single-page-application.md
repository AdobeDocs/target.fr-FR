---
description: Informations d'utilisation d'at. js 2. x pour implémenter les applications d'une seule page.
keywords: implémentation d'applications d'une seule page ; implémenter une application d'une seule page ; spa ; at. js 2. x
seo-description: Informations permettant d'utiliser Adobe Target at. js 2. x pour implémenter les applications d'une seule page.
seo-title: Mise en œuvre d’une application d’une seule page
solution: Target
title: Mise en œuvre d’une application d’une seule page
topic: standard
uuid: 5887ec53-e5b1-40f9-b469-33685f5c6cd6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Mise en œuvre d’une application d’une seule page{#single-page-application-implementation}

Les sites Web traditionnels fonctionnaient sur des modèles de navigation Page à page, autrement dit des applications multi-page, où les conceptions de site Web étaient étroitement couplées aux URL et aux transitions d&#39;une webpage Web à une autre. Les applications Web modernes, comme les applications monopages, adoptent plutôt un modèle qui projette rapidement le rendu de l’interface utilisateur du navigateur, ce qui est souvent indépendant des rechargements de page. Ces expériences sont souvent déclenchées par des interactions client, comme faire défiler, cliquer et faire bouger le curseur. À mesure de l’évolution des paradigmes du Web moderne, la pertinence des événements génériques traditionnels, comme le chargement des pages, pour déployer la personnalisation et les expériences ne fonctionnent plus.

![Cycle de vie traditionnel de la page par rapport au cycle de vie d’une application monopage](/help/c-experiences/assets/trad-vs-spa.png)

at. js 2. x propose des fonctionnalités riches qui permettent à votre entreprise d&#39;exécuter la personnalisation sur les technologies de nouvelle génération côté client. Cette version vise à améliorer at.js pour obtenir des interactions harmonieuses avec les applications monopages.

Vous trouverez ci-dessous des avantages d&#39;utilisation d&#39;at. js 2. x qui ne sont pas disponibles dans les versions précédentes :

* Capacité à mettre en cache toutes les offres au chargement de la page afin de passer de plusieurs appels serveur à un seul appel serveur.
* Améliorez considérablement l’expérience de vos utilisateurs finaux sur votre site, car les offres sont immédiatement affichées via le cache, sans délai par les appels de serveur traditionnels.
* Une simple ligne de code et une configuration de développement unique pour permettre aux spécialistes marketing de créer et d’exécuter des activités A/B et de ciblage d’expérience (WT) via le VEC sur votre application monopage.

## Vues cibles et applications d’une seule page Adobe Target

Le VEC de Adobe Target pour les applications SPA tire profit d’un nouveau concept nommé Vues : un groupe logique d’éléments visuels qui, ensemble, forment une expérience pour application d’une seule page. Une application d’une seule page (SPA) peut donc être considérée comme une transition entre les vues (et pas entre les URL) basée sur les interactions des utilisateurs. Une Vue peut généralement représenter un site entier ou des éléments visuels regroupés dans un site.

Pour expliquer plus en détail les Vues, parcourez cet hypothétique site d&#39;e-commerce en ligne implémenté dans React et explorez quelques exemples de Vues. Cliquez sur les liens ci-dessous pour ouvrir ce site dans un nouvel onglet du navigateur.

**Lien :[Site d&#39;accueil](https://target.enablementadobe.com/react/demo/#/)**

![page d’accueil](/help/c-experiences/assets/home.png)

Lorsque nous arrivons sur la page d’accueil, nous voyons immédiatement une image à forte identification qui présente les soldes de Pâques ainsi que les produits les plus récents en vente sur le site. Dans ce cas, une Vue peut être définie comme tout le site d&#39;accueil. Ceci est bon à noter comme nous allons le développer dans la section Implémentation d&#39;Adobe Target Views ci-dessous.

**Lien :[Site produit](https://target.enablementadobe.com/react/demo/#/products)**

![site produit](/help/c-experiences/assets/product-site.png)

Comme les produits vendus par l’entreprise nous paraissent intéressants, nous décidons de cliquer sur le lien Produits. Comme pour le site d&#39;accueil, l&#39;intégralité du site de produits peut être définie comme une ue.V Nous pouvons nommer cet affichage « produits » comme le nom de chemin d’accès dans `https://target.enablementadobe.com/react/demo/#/products)`.

![site produit 2](/help/c-experiences/assets/product-site-2.png)

Au début de cette section, nous avons défini les vues en tant que site entier ou même un groupe d&#39;éléments visuels sur le site. Comme illustré ci-dessus, les quatre produits affichés sur le site peuvent également être regroupés et considérés comme une vue. Si nous souhaitons donner un nom à cet affichage, nous pouvons l’appeler « Produits ».

![site produit 3](/help/c-experiences/assets/product-site-3.png)

Nous décidons de cliquer sur le bouton Voir Plus pour découvrir d’autres produits sur le site. L&#39;URL du site Web ne change pas dans ce cas. Mais une Vue ici ne représente que la deuxième ligne des produits ci-dessus. Cette Vue peut être appelée « PAGE-PRODUIT-2 ».

**Lien :[Paiement](https://target.enablementadobe.com/react/demo/#/checkout)**

![page paiement](/help/c-experiences/assets/checkout.png)

Comme nous avons aimé certains produits sur le site, nous avons décidé d&#39;en acheter quelques uns. Sur la page de paiement du site, certaines options permettent de choisir une livraison normale ou express. Parce qu’une Vue peut être n’importe quel groupe d’éléments visuels sur un site, nous pouvons l’appeler « Vue des préférences de livraison ».

De plus, le concept des Vues peut être beaucoup plus étendu. Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, l’affichage peut être appelé « Livraison normale ». Si l&#39;option Livraison express est sélectionnée, l’affichage peut être appelé « Livraison express ».

Désormais, les spécialistes en marketing peuvent exécuter un test A/B pour déterminer si la modification de la couleur du bleu au rouge lorsque la livraison express est sélectionnée peut augmenter les conversions, contrairement au bouton de couleur bleue pour les deux options de livraison.

## Implémentation d&#39;Adobe Target Views

À présent que nous avons examiné le concept d&#39;Adobe Target Views, nous pouvons l&#39;exploiter dans Target pour permettre aux spécialistes du marketing d&#39;exécuter des tests AB et XT sur les applications monopages via le compositeur d&#39;expérience visuelle. Une configuration développeur unique sera nécessaire. Examinons les étapes à suivre.

1. Installez at. js 2. x.

   D&#39;abord, nous devons installer at. js 2. x. Cette version d&#39;at. js a été développée avec les SPAS à l&#39;esprit. Les versions précédentes d’at.js et de mbox.js ne prennent pas en charge les affichages d’Adobe Target et le compositeur d’&#39;expérience visuelle pour les applications monopages.

   Téléchargez at. js 2. x via l&#39;interface utilisateur d&#39;Adobe Target située dans [!UICONTROL Configuration &gt; Implémentation]. at. js 2. x peut également être déployé via Adobe Launch. Toutefois, les extensions d’Adobe Target ne sont pas encore disponibles ni prises en charge.

1. Implémentez la fonction la plus récente d&#39;at. js 2. x `triggerView()` sur vos sites.

   Après avoir défini les vues de votre SPA dans lesquelles vous souhaitez exécuter un test A/B ou XT, implémentez `triggerView()` la fonction at. js 2. x avec les vues transmises sous forme de paramètre. Cela permet aux spécialistes du marketing d&#39;utiliser le compositeur d&#39;expérience visuelle pour concevoir et exécuter les tests A/B et XT pour ces vues définies. Si la fonction `triggerView()` n’est pas définie pour ces affichages, le VEC ne détectera pas les affichages. Les spécialistes en marketing ne peuvent donc pas utiliser le VEC pour concevoir et exécuter des tests A/B et XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Paramètre | Type | Obligatoire ? | Validation | Description |
   | --- | --- | --- | --- | --- |
   | viewName | Chaîne | Oui | 1. Aucun espace à la fin.<br>2. Ne peut pas être vide.<br>3. Le nom de la vue doit être unique pour toutes les pages.<br>4. **Avertissement**: le nom de l’affichage ne doit pas commencer ou se terminer par « `/` ». Cela est dû au fait que le client extrait généralement le nom de la vue à partir du chemin d&#39;URL. Pour nous, « accueil » et « `/home` » sont différents.<br>5. **Avertissement**: la même vue ne doit pas être déclenchée plusieurs fois avec l&#39;option `{page: true}`. | Transmettez n’importe quel nom en tant que type de chaîne que vous souhaitez représenter votre vue. Ce nom d’affichage s’affiche dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
   | Options | Objet | Non |
   | options &gt; page | Booléen | Non | **TRUE**: la valeur par défaut de la page est true. Lorsque `page=true`, des notifications sont envoyées aux serveurs Edge pour incrémenter le nombre d’impressions.<br>**FALSE**: lorsque `page=false`, les notifications ne sont pas envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

   Examinons maintenant quelques exemples d’utilisation pour appeler la fonction `triggerView()` dans React pour notre hypothétique SPA de commerce électronique :

   **Lien :[Site d&#39;accueil](https://target.enablementadobe.com/react/demo/#/)**

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

**Lien :[Site Produits](https://target.enablementadobe.com/react/demo/#/products)**

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

**Lien :[Paiement](https://target.enablementadobe.com/react/demo/#/checkout)**

![Paiement React](/help/c-experiences/assets/react6.png)

Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, l’affichage peut être appelé « Livraison normale ». Si l&#39;option Livraison express est sélectionnée, l&#39;affichage peut être appelé « Livraison express ».

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

## Diagrammes système at. js 2. x

Les diagrammes suivants vous aident à comprendre le flux de travaux de at. js 2. x avec les vues et la manière dont cette intégration améliore l&#39;intégration des applications monopages. Pour obtenir une meilleure introduction aux concepts utilisés dans at. js 2. x, reportez-vous [à la section Implémentation d&#39;application mono-page](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Flux Target avec at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Étape | Détails |
| --- | --- |
| 1 | L’appel renvoie le [!DNL Experience Cloud ID] si l’utilisateur est authentifié. Un autre appel synchronise l’ID de client. |
| 2 | La bibliothèque at.js se charge de manière synchrone et masque le corps du document.<br>at.js peut également être chargé de manière asynchrone avec une option pré-masquant l’extrait de code implémenté sur la page. |
| 3 | Une demande de chargement de page est faite, incluant tous les paramètres configurés (MCID, SDID et ID client). |
| 4 | Les scripts de profil s’exécutent, puis sont introduits dans le magasin de profils. Le magasin demande des audiences qualifiées auprès de la bibliothèque d’audiences (par exemple, audiences partagées depuis Adobe Analytics, Gestion de l’audience, etc.).<br>Les attributs du client sont envoyés par lot dans le magasin de profils. |
| 5 | Selon les paramètres de requête d&#39;URL et les données de profil, [!DNL Target] décidez quelles activités et expériences renvoyer au visiteur pour la page active et les futures vues. |
| 6 | Le contenu ciblé est renvoyé à la page, comprenant, éventuellement, les valeurs de profil pour une personnalisation plus poussée.<br>Le contenu ciblé sur la page actuelle est affiché aussi rapidement que possible, sans scintillement du contenu par défaut.<br>Contenu ciblé pour les vues présentées à la suite d’actions de l&#39;utilisateur dans une application d’une seule page cache dans le navigateur, afin qu&#39;elles puissent être appliquées instantanément sans appel au serveur supplémentaire lorsque les vues sont `triggerView()` déclenchées. |
| 7 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 8 | Les données ciblées sont associées aux données d&#39;Analytics par l’intermédiaire du SDID et sont traitées dans le stockage de rapports d&#39;Analytics.<br>Il est alors possible de consulter les données Analytics dans Analytics et dans Target par l’intermédiaire des rapports Analytics for Target (A4T). |

Désormais, où que soit implémenté `triggerView()` sur votre application d’une seule page, les vues et actions sont récupérées depuis le cache et présentées à l’utilisateur sans appel au serveur. `triggerView()` envoie également une demande de notification au serveur principal [!DNL Target] afin d’incrémenter et d’enregistrer le nombre d’impressions.

![Target flow at. js 2. x triggerview](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Étape | Détails |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour afficher les vues et appliquer les actions pour modifier les éléments visuels. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s&#39;affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils [!DNL Target] pour compter le visiteur dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d&#39;A4T. |

## Compositeur d’expérience visuelle pour les applications monopages

Après avoir installé at. js 2. x et ajouté `triggerView()` à votre site, utilisez le compositeur d&#39;expérience visuelle pour exécuter les activités A/B et XT. Pour plus d’informations, reportez-vous au [Compositeur d’expérience visuelle pour application d’une seule page (SPA)](/help/c-experiences/spa-visual-experience-composer.md).

>[!NOTE]
>
>Le compositeur d’expérience visuelle pour applications d’une seule page est en fait le même compositeur d’expérience visuelle que celui que vous utilisez sur les pages web ordinaires, mais certaines fonctionnalités supplémentaires sont disponibles lorsque vous ouvrez une application d’une seule page avec l’implémentation `triggerView()`.

## Utilisez triggerview pour vérifier que A 4 T fonctionne correctement avec at. js 2. x et spas. {#triggerview}

Pour garantir qu&#39; [Analytics pour Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A 4 T) fonctionne correctement avec at. js 2. x, veillez à envoyer le même SDID dans la requête Target et dans la requête Analytics.

En tant que bonnes pratiques liées aux SPAS :

* Utilisez des événements personnalisés pour signaler qu&#39;un élément intéressant se produit dans l&#39;application
* Déclenchez un événement personnalisé avant que la vue ne commence le rendu.
* Déclenchement d&#39;un événement personnalisé lorsque la vue termine le rendu

at. js 2. x a ajouté une nouvelle fonction API [triggerview ()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) . Vous devez utiliser `triggerView()` pour informer at. js qu&#39;une vue commence le rendu.

Pour découvrir comment combiner des événements personnalisés, at. js 2. x et Analytics, voyons un exemple. Cet exemple suppose que la page HTML contient l&#39;API visiteur, suivie d&#39;at. js 2. x, suivie d&#39;appmeasurement.

Supposons que les événements personnalisés suivants soient présents :

* `at-view-start` - Lorsque la vue commence le rendu
* `at-view-end` - Lorsque la vue termine le rendu

Pour vérifier qu&#39;A 4 T fonctionne avec at. js 2. x,

Le gestionnaire de démarrage d&#39;affichage doit se présenter comme suit :

```
document.addEventListener("at-view-start", function(e) {
  var visitor = Visitor.getInstance("<your Adobe Org ID>");
  
  visitor.resetState();
  adobe.target.triggerView("<view name>");
});
```

Le gestionnaire de fin d&#39;affichage doit ressembler à ceci :

```
document.addEventListener("at-view-end", function(e) {
  // s - is the AppMeasurement tracker object
  s.t();
});
```

>[!NOTE]
>
>Vous devez déclencher les `at-view-start` événements et `at-view-end` les événements. Ces événements ne font pas partie des événements personnalisés at. js.

Bien que ces exemples utilisent du code JavaScript, tout cela peut être simplifié si vous utilisez un gestionnaire de balises, tel [qu&#39;Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md).

Si les étapes précédentes sont suivies, vous devez disposer d&#39;une solution A 4 T robuste pour les applications monopages.

## Vidéos de formation

Les vidéos suivantes comprennent davantage d’informations :

### Fonctionnement de at. js 2. x

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Voir [Description de la manière dont at. js 2. x fonctionne](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) pour plus d&#39;informations.

### Implémentation d&#39;at. js 2. x dans une application d&#39;une seule page

>[!VIDEO](https://video.tv.adobe.com/v/26248)

Voir [Mise en œuvre du fichier at. js 2. x d&#39;Adobe Target dans une application de page unique](https://helpx.adobe.com/target/kt/using/atjs2-single-page-application-technical-video-implement.html) pour plus d&#39;informations.

### Utilisation du compositeur d’expérience visuelle pour les applications monopages dans Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Pour plus d&#39;informations, voir [Utilisation du compositeur d&#39;expérience visuelle pour application d&#39;une seule page dans Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) .