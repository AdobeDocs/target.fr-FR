---
description: Le compositeur d’expérience visuelle (VEC) pour applications d’une seule page (SPA) permet aux marketeurs de créer des tests et de personnaliser le contenu des SPA eux-mêmes sans dépendances de développement continu. Le VEC peut être utilisé pour créer des activités sur la plupart des structures populaires, telles que React et Angular.
keywords: vec pour application d’une seule page;react;angular;react.js;compositeur d’expérience visuelle pour application d’une seule page;options du compositeur d’expérience pour application d’une seule page;applications d’une seule page;application d’une seule page;spa;options du compositeur mobile;vue cible
seo-description: Le Compositeur d’Expérience Visuelle (VEC) pour applications d’une seule page (SPA) dans Adobe Target permet aux marketeurs de créer des tests et de personnaliser le contenu des SPA eux-mêmes sans dépendances de développement continu. Le VEC peut être utilisé pour créer des activités sur la plupart des structures populaires, telles que React et Angular.
seo-title: Compositeur d’expérience visuelle pour application d’une seule page
solution: Target
title: Compositeur d’expérience visuelle pour application d’une seule page
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
translation-type: tm+mt
source-git-commit: 62552bfe5a6eb65dc1760b17543a0f5c84f0ecc5

---


# Compositeur d’expérience visuelle pour application d’une seule page{#single-page-app-spa-visual-experience-composer}

Dans [!DNL Adobe Target], le [!UICONTROL compositeur d’expérience visuelle] (VEC) offre aux marketeurs une fonctionnalité pratique pour créer des activités et personnaliser les expériences qui peuvent être diffusées dynamiquement sur les applications multipage classiques via la mbox globale d’Adobe Target. Toutefois, cela dépend de la récupération des offres au chargement de la page ou des appels serveur suivants, qui introduit une latence, comme illustré dans le diagramme ci-dessous. Cette approche ne fonctionne pas bien avec les applications monopages, car elle altère l’expérience utilisateur et les performances de l’application.

![Cycle de vie traditionnel par rapport au cycle de vie d’une application d&#39;une seule page](/help/c-experiences/assets/trad-vs-spa.png)

Avec la nouvelle version, nous présentons désormais le compositeur d’expérience visuelle pour les applications monopages. Le compositeur d’expérience visuelle (VEC) pour applications d’une seule page (SPA) permet aux marketeurs de créer des tests et de personnaliser le contenu des SPA eux-mêmes sans dépendances de développement continu. Le compositeur d’expérience visuelle peut être utilisé pour créer [des activités de ](/help/c-activities/t-test-ab/test-ab.md)test AB et [de ciblage d’expérience](/help/c-activities/t-experience-target/experience-target.md) (XT) sur les infrastructures les plus populaires, telles que React et Angular.

## Vues cibles et applications d’une seule page Adobe Target

Le VEC de Adobe Target pour les applications SPA tire profit d’un nouveau concept nommé Vues : un groupe logique d’éléments visuels qui, ensemble, forment une expérience pour application d’une seule page. Une application d’une seule page (SPA) peut donc être considérée comme une transition entre les vues (et pas entre les URL) basée sur les interactions des utilisateurs. Une Vue peut généralement représenter un site entier ou des éléments visuels regroupés dans un site.

Pour expliquer plus en détail les Vues, parcourez cet hypothétique site d&#39;e-commerce en ligne implémenté dans React et explorez quelques exemples de Vues. Cliquez sur les liens ci-dessous pour ouvrir ce site dans un nouvel onglet du navigateur.

**Lien :[Site d&#39;accueil](https://target.enablementadobe.com/react/demo/#/)**

![Site d’accueil](/help/c-experiences/assets/home.png)

Lorsqu’on accède au site d’accueil, on voit immédiatement une image à forte identification ayant pour but de promouvoir une vente de Pâques ainsi que les produits les plus récents vendus sur le site. Dans ce cas, une Vue peut être définie comme tout le site d’accueil. Ceci est bon à noter comme nous allons le développer dans la section Implémentation d&#39;Adobe Target Views ci-dessous.

**Lien :[Site produit](https://target.enablementadobe.com/react/demo/#/products)**

![site de produit](/help/c-experiences/assets/product-site.png)

Alors que les produits nous intéressent davantage, nous décidons de cliquer sur le lien Produits. Comme pour le site d’accueil, l’intégralité du site de produits peut être définie comme une Vue. Nous pouvons nommer cet affichage « produits » comme le nom de chemin d’accès dans `https://target.enablementadobe.com/react/demo/#/products`.

![site produit 2](/help/c-experiences/assets/product-site-2.png)

Au début de cette section, nous avons défini les vues en tant que site entier ou même un groupe d&#39;éléments visuels sur le site. Comme illustré ci-dessus, les quatre produits affichés sur le site peuvent également être regroupés et considérés comme une vue. Si nous souhaitons nommer cette Vue, nous pouvons la nommer « produits ».

![site produit 3](/help/c-experiences/assets/product-site-3.png)

Nous décidons de cliquer sur le bouton Charger plus pour explorer d’autres produits sur le site. L’URL du site Web ne change pas dans ce cas. Mais une Vue ici ne représente que la deuxième ligne des produits ci-dessus. Le nom de la Vue peut être appelé « PRODUCTS-PAGE-2 ».

**Lien :[Paiement](https://target.enablementadobe.com/react/demo/#/checkout)**

![page paiement](/help/c-experiences/assets/checkout.png)

Comme nous avons aimé certains produits sur le site, nous avons décidé d&#39;en acheter quelques uns. Sur la page de paiement du site, certaines options permettent de choisir une livraison normale ou express. Comme une Vue peut représenter n’importe quel groupe d’éléments visuels d’un site, nous pouvons la nommer « Préférences de livraison de la Vue ».

De plus, le concept des Vues peut être beaucoup plus étendu. Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, la Vue peut être nommée « Livraison normale ». Si l&#39;option Livraison express est sélectionnée, la Vue peut être nommée « Livraison express ».

Les marketeurs souhaitent à présent exécuter un test AB pour déterminer si la modification de la couleur du bleu au rouge augmente les conversations lorsque la livraison express est sélectionnée, au lieu de conserver la couleur du bouton bleu pour les deux options de livraison.

## Implémentation d’Adobe Target Views

À présent que nous avons examiné le concept d&#39;Adobe Target Views, nous pouvons l&#39;exploiter dans Target pour permettre aux spécialistes du marketing d&#39;exécuter des tests AB et XT sur les applications monopages via le compositeur d&#39;expérience visuelle. Une configuration développeur unique sera nécessaire. Examinons les étapes à suivre.

1. Installez at. js 2. x.

   D&#39;abord, nous devons installer at. js 2. x. Cette version d&#39;at. js a été développée avec les SPAS à l&#39;esprit. Les versions précédentes d’at.js et mbox.js ne prennent pas en charge Adobe Target Views et le compositeur d’expérience visuelle pour les applications monopages.

   ![Boîte de dialogue des détails d’implémentation](/help/c-experiences/assets/imp-200.png)

   Téléchargez at. js 2. x via l&#39;interface utilisateur d&#39;Adobe Target située dans [!UICONTROL Configuration &gt; Implémentation]. at. js 2. x peut également être déployé via [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Toutefois, les extensions Adobe Target ne sont actuellement pas à jour et prises en charge.

1. Implémentation de la fonction la plus récente d&#39;at. js 2. x : [Triggerview ()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) sur vos sites.

   Après avoir défini les vues de votre SPA dans lesquelles vous souhaitez exécuter un test A/B ou XT, implémentez `triggerView()` la fonction at. js 2. x avec les vues transmises sous forme de paramètre. Cela permet aux spécialistes du marketing d&#39;utiliser le compositeur d&#39;expérience visuelle pour concevoir et exécuter les tests A/B et XT pour ces vues définies. Si la fonction `triggerView()` n’est pas définie pour ces affichages, le VEC ne détectera pas les affichages. Les spécialistes en marketing ne peuvent donc pas utiliser le VEC pour concevoir et exécuter des tests A/B et XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Paramètre | Type | Obligatoire ? | Validation | Description |
   | --- | --- | --- | --- | --- |
   | viewName | Chaîne | Oui | 1. Aucun espace à la fin.<br>2. Ne peut pas être vide.<br>3. Le nom de la vue doit être unique pour toutes les pages.<br>4. **Avertissement**: le nom de l’affichage ne doit pas commencer ou se terminer par « `/` ». Cela est dû au fait que le client extrait généralement le nom de la vue à partir du chemin d&#39;URL. Pour nous, « accueil » et « `/home` » sont différents.<br>5. **Avertissement**: la même vue ne doit pas être déclenchée plusieurs fois avec l&#39;option `{page: true}`. | Transmettez n’importe quel nom en tant que type de chaîne que vous souhaitez représenter votre vue. Ce nom d’affichage s’affiche dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
   | Options | Objet | Non |
   | options &gt; page | Booléen | Non | **TRUE**: la valeur par défaut de la page est true. Lorsque `page=true`, des notifications sont envoyées aux serveurs Edge pour incrémenter le nombre d’impressions.<br>**FALSE**: lorsque `page=false`, les notifications ne sont pas envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

   Examinons maintenant quelques exemples d’utilisation pour appeler la fonction `triggerView()` dans React pour notre hypothétique application e-commerce monopage :

   **Lien :[Site d&#39;accueil](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   En tant que marketeurs, si vous souhaitez exécuter des tests AB sur tout le site d&#39;accueil, vous voudrez peut être nommer la vue pouvant être extraite de l’URL : « accueil ».

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

   Examinons maintenant un exemple un peu plus complexe. En tant que spécialistes du marketing, vous souhaitez personnaliser la deuxième ligne des produits en changeant la couleur de l’étiquette de prix en rouge après qu’un utilisateur ait cliqué sur le bouton Charger plus.

   ![réaction aux produits](/help/c-experiences/assets/react4.png)

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

   Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, la Vue peut être nommée « Livraison normale ». Si l&#39;option Livraison express est sélectionnée, la Vue peut être nommée « Livraison express ».

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

1. Lancez des activités AB ou XT via le VEC.

   Lorsque `adobe.target.triggerView()` est implémenté sur votre application à page unique, avec les noms de Vue transmis en tant que paramètres, le VEC peut détecter ces vues et permettre aux utilisateurs de créer des actions et des modifications pour leurs activités AB ou de ciblage d’expérience.

   >[!NOTE]
   >
   >Le VEC pour les applications monopages est en fait le même VEC que celui que vous utilisez sur les pages Web ordinaires, mais certaines fonctionnalités supplémentaires sont disponibles lorsque vous ouvrez une application à page unique avec l’implémentation de `triggerView()`.

Le panneau [Modifications](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) et les actions du VEC offrent deux améliorations majeures au niveau du VEC qui permettent à celui-ci de fonctionner correctement avec les applications monopages.

**Panneau des modifications**

Comme illustré ci-dessous, le panneau [!UICONTROL Modifications] capture les actions créées pour une vue donnée. Notez que toutes les actions d&#39;une vue sont regroupées sous cette vue.

**Actions**

Cliquer sur une action met en évidence l’élément de la page sur lequel cette action sera appliquée. Chaque action du compositeur d&#39;expérience visuelle créée sous une vue comporte quatre icônes comme illustré ci-dessous : Informations, modification, déplacement et suppression.

![Modifications](/help/c-experiences/assets/modifications-new.png)

Le tableau suivant décrit chaque action :

| Page | Description |
| --- | --- |
| Informations | Affiche les détails de cette action. |
| Modifier  | Permet de modifier directement les propriétés de cette action. |
| Déplacer  | Déplace l&#39;action vers un événement de chargement de page ou tout autre affichage existant dans le panneau Modifications.<br>[!UICONTROL Événement] de chargement de page : toute action correspondant à l&#39;événement de chargement de page est appliquée au chargement initial de la page de votre application Web.<br>**Remarque** Après avoir effectué une opération de déplacement, vous devez accéder à l&#39;affichage dans le compositeur d&#39;expérience visuelle via Parcourir pour vérifier si le déplacement a été une opération valide. Si l&#39;action ne peut pas être appliquée à l&#39;affichage, une erreur s&#39;affiche |
| Supprimer | Supprime l&#39;action. |

>[!NOTE]
>
>Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans le compositeur d&#39;expérience visuelle ou même si le chargement de la page échoue. Les actions qu’il n’est pas possible de modifier avant le chargement complet du site sont désactivées dans l’interface utilisateur de 

**Exemple 1**

Reportez-vous à l&#39;exemple ci-dessus lorsque vous avez créé une vue d&#39;accueil. Notre objectif est d’obtenir deux effets pour cette vue :

1. Remplacez les boutons « Ajouter au panier » et « J&#39;aime » par une couleur bleue plus claire. Cela doit avoir lieu lors d’un « chargement de page », car vous changez les composants de l’en-tête.
1. Remplacez l&#39;étiquette « Derniers produits de 2019 » par « Produits dernier cri de 2019 » et modifiez la couleur du texte en violet.

Pour exécuter ces objectifs, dans le VEC, cliquez sur [!UICONTROL Composer] et appliquez ces modifications dans la vue d’accueil.

![Exemple 1](/help/c-experiences/assets/example1.png)

**Exemple 2**

Reportez-vous à l’exemple ci-dessus lorsque vous avez créé une vue PAGE-PRODUITS-2. Votre objectif est de remplacer le libellé « Prix » par « Prix de vente » et de modifier la couleur de l’étiquette en rouge.

1. Cliquez sur [!UICONTROL Parcourir], puis sur le lien [!UICONTROL Produits] dans l’en-tête.
1. Cliquez une fois sur [!UICONTROL Charger plus] pour accéder à la deuxième ligne de produits.
1. Cliquez sur [!UICONTROL Composer].
1. Appliquez les actions pour remplacer le libellé du texte par « Prix de la vente » et modifier la couleur en rouge.

![Exemple 2](/help/c-experiences/assets/example2.png)

**Exemple 3**

Enfin, comme mentionné précédemment, les vues peuvent être définies à un niveau plus détaillé. Les vues peuvent être un état ou une option d’un bouton radio. Auparavant, vous aviez créé les vues pour les PAIEMENTS-EXPRESS et les PAIEMENTS-STANDARD. Notre objectif est de modifier la couleur du bouton en rouge pour la vue PAIEMENT-EXPRESS.

1. Cliquez sur [!UICONTROL Parcourir].
1. Ajoutez deux produits au panier.
1. Cliquez sur l’icône de panier dans le coin supérieur droit.
1. Cliquez sur Payer votre commande.
1. Cliquez sur le bouton radio Livraison express.
1. Cliquez sur [!UICONTROL Composer].
1. Modifiez la dénomination du bouton « Paiement » en « Terminer la commande » et la couleur en rouge.

![Exemple 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>La vue PAIEMENT-EXPRESS n&#39;apparaîtra pas dans le panneau de modification tant que vous n&#39;avez pas cliqué sur le bouton radio Livraison express. Cela est dû au fait que `triggerView()` la fonction est déclenchée lorsque le bouton radio Livraison express est sélectionné et que cette fonction n’est disponible que lorsque le compositeur d&#39;expérience visuelle sait qu’une vue s’affiche dans le panneau de modification.

## Exploration approfondie d&#39;at.js et des applications à page unique

**Comment récupérer les vues des dernières données d’audience hydratées par des actions, après le chargement initial de la page sur mon application monopage ?**

Le flux de travaux type d&#39;at. js 2. x est le chargement de votre site, toutes vos vues et actions sont mises en cache afin que les actions suivantes de l&#39;utilisateur sur votre site ne déclenchent pas les appels au serveur pour récupérer les offres. Si vous souhaitez récupérer les vues en fonction des données de profil les plus récentes, actualisées selon les actions de l&#39;utilisateur, vous pouvez appeler `getOffers()` et `applyOffers()` avec les dernières données utilisateur ou données de profil transmises.

Par exemple, supposons que vous soyez une société de télécommunications et que vous disposez d&#39;une application d&#39;une seule page utilisant at. js 2. x. En tant qu&#39;entreprise, vous souhaitez atteindre les objectifs suivants :

* Pour un utilisateur déconnecté ou anonyme, affichez la dernière promotion de l’entreprise, telle que l’affichage d’une offre à forte identification « Premier mois offert » sur `http://www.telecom.com/home`.
* Pour un utilisateur connecté, affichez une offre promotionnelle de mise à niveau pour les utilisateurs dont les contrats arrivent à expiration, tels que « Vous êtes éligible pour recevoir un smartphone gratuit ». on `http://www.telecom.com/loggedIn/home`.

Désormais, vos développeurs nomment les vues et appellent `triggerView()` de la manière suivante :

* Pour `http://www.telecom.com/home`, le nom de la vue est « Déconnecté de l&#39;accueil »
   * `triggerView(“Logged Out Home”)` est appelée.
* Pour `http://www.telecom.com/loggedIn/home` le nom de la vue est « Connecté à l&#39;accueil »
   * `triggerView(“Logged In Home”)` est appelée lors de la modification.

Les marketeurs exécutent ensuite les activités AB suivantes via le compositeur d’expérience visuelle :

* L&#39;activité A/B comportant l’offre « Premier mois gratuit » pour les audiences ayant le paramètre « `loggedIn= false` » à afficher dans `http://www.telecom.com/home`, lorsque le nom de la vue est Déconnecté de l&#39;accueil.
* Activité AB comportant l’offre « Vous êtes éligible pour obtenir un smartphone gratuit ». pour les audiences dont le paramètre est « `loggedIn=true` » à afficher dans `http://www.telecom.com/loggedIn/home` et dont le nom de vue est Connecté - Offre à forte identification.

Examinons maintenant ce flux d&#39;utilisateurs :

1. Un utilisateur déconnecté anonyme arrive sur votre page.
1. Puisque vous utilisez at. js 2. x, vous transmettez le paramètre « `loggedIn = false` » au chargement de la page pour récupérer toutes les vues présentes dans les activités actives qui remplissent les critères lorsque l&#39;audience possède le paramètre « `loggedIn = false` ».
1. at. js 2. x récupère ensuite la vue d&#39;accueil déconnecté et l&#39;action pour afficher l&#39;offre « Le premier mois gratuit » et la stocke dans le cache.
1. Lors de l&#39;appel de `triggerView(“Logged Out Home”)`, l&#39;offre « Premier mois gratuit » est récupérée depuis le cache et s&#39;affiche sans appel au serveur.
1. L&#39;utilisateur clique à présent sur « Connexion » et fournit ses informations d’identification.
1. Étant donné que votre site web est une application d’une seule page, vous n’effectuez pas de chargement de page complet et redirigez votre utilisateur vers `http://www.telecom.com/loggedIn/home`.

Mais voici le problème. L&#39;utilisateur se connecte et vous rencontrez `triggerView(“Logged In Home”)` parce que la route du code a été modifiée. Cela indique à at. js 2. x de récupérer la vue et les actions du cache, mais la seule vue qui existe dans le cache est Déconnecté d&#39;accueil.

Ainsi, comment récupérer la vue Connecté et afficher le message « Vous êtes éligible pour recevoir un smartphone gratuit » ? offer? Et comme toutes les actions suivantes sur votre site dépendent du point de vue de l&#39;utilisateur connecté, comment pouvez-vous vérifier que toutes les actions suivantes conduisent à des offres personnalisées pour les utilisateurs connectés ?

Vous pouvez utiliser les nouvelles `getOffers()` et `applyOffers()` les fonctions prises en charge dans at. js 2. x :

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

Transmettez la réponse de `getOffers()` à `applyOffers()` et toutes les vues et actions associées à « loggedin = true » mettront à présent à jour le cache at.js.

En d&#39;autres termes, at. js 2. x prend en charge la récupération d&#39;affichages, d&#39;actions et d&#39;offres avec les données d&#39;audience les plus récentes d&#39;une manière à la demande.

**at. js 2. x prend-il en charge A 4 T pour les applications d&#39;une seule page ?**

Oui, at. js 2. x prend en charge A 4 T pour l&#39;application d&#39;une seule page via `triggerView()` la fonction étant donné que vous avez mis en œuvre Adobe Analytics et le service d&#39;identification des visiteurs Experience Cloud. Voir le diagramme ci-dessous avec des descriptions détaillées.

![Flux cible](/help/c-experiences/assets/atjs-spa-flow.png)

| Étape | Description |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour rendre une vue et appliquer des actions pour modifier les éléments visuels associés à la vue. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s&#39;affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils Target pour compter le nombre de visiteurs dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d&#39;A4T. |

>[!NOTE]
>Si vous ne souhaitez pas envoyer de notifications à Adobe Analytics pour le comptage d&#39;impressions chaque fois qu&#39;une vue est déclenchée, transmettez `{page: false}` à la fonction `triggerView()` afin que le comptage d&#39;impressions ne soit pas gonflé lorsqu&#39;une vue est déclenchée plusieurs fois pour un composant qui effectue un rendu constant. Par exemple :
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Activités prises en charge

| Type d’activité | Pris en charge ? |
| --- | --- |
| [Test A/B](/help/c-activities/t-test-ab/test-ab.md) | Oui |
| [Recommandations en tant qu’activités de ](/help/c-recommendations/recommendations-as-an-offer.md)<br>test A/B et de ciblage d’expérience | Oui |
| [affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Oui |
| [Ciblage d’expérience](/help/c-activities/t-experience-target/experience-target.md) | Oui |
| [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Non |
| [ciblage automatique](/help/c-activities/auto-target-to-optimize.md) | Non |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) | Non |
| [Recommandations](/help/c-recommendations/recommendations.md) | Non |

**Si nous avons installé at. js 2. x et implémenté`triggerView()`sur nos sites, comment exécuter les activités A/B auto-ciblage parce que le compositeur d&#39;expérience visuelle ne prend pas en charge le ciblage automatique ?**

Si vous souhaitez utiliser des activités AB de ciblage automatique, vous pouvez déplacer toutes vos actions à exécuter lors de l&#39;événement de chargement de page dans le compositeur d’expérience visuelle. Passez la souris sur chaque action, puis cliquez sur le bouton [!UICONTROL Déplacer vers l&#39;événement] de chargement de la page. Ensuite, à l’étape suivante, vous pouvez sélectionner Ciblage automatique pour la méthode d’affectation du trafic.

## Intégrations prises en charge

| Intégration | Pris en charge ? |
| --- | --- |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Oui |
| [Audiences Experience Cloud](/help/c-integrating-target-with-mac/mmp.md) | Oui |
| [Attributs du client](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Oui |
| [Fragments d’expérience AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | Oui |

## Fonctionnalités prises en charge {#supported-features}

| Fonctionnalité | Pris en charge ? |
| --- | --- |
| [Espaces de travail et propriétés](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Oui |
| [Liens d&#39;assurance qualité](/help/c-activities/c-activity-qa/activity-qa.md) | Oui |
| [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) | Non |
| [Code personnalisé ](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Oui |
| [Options du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Toutes |
| [Suivi des clics](/help/c-activities/r-success-metrics/click-tracking.md) | Oui |
| [Diffusion multi-activité](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | Oui |

## Vidéo de formation : Utilisation du compositeur d&#39;expérience visuelle pour les applications monopages dans Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Pour plus d&#39;informations, voir [Utilisation du compositeur d&#39;expérience visuelle pour application d&#39;une seule page dans Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) .
