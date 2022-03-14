---
keywords: vec pour application d’une seule page;react;angular;react.js;compositeur d’expérience visuelle pour application d’une seule page;options du compositeur d’expérience pour application d’une seule page;applications d’une seule page;application d’une seule page;spa;options du compositeur mobile;vue cible
description: Découvrez comment utiliser le SPA VEC dans Adobe [!DNL Target] pour créer des tests et personnaliser le contenu d’SPA à votre propre manière sans dépendances de développement continu.
title: Comment utiliser le compositeur d’expérience visuelle pour application d’une seule page (SPA VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '3698'
ht-degree: 90%

---

# Compositeur d’expérience visuelle pour application d’une seule page

Dans [!DNL Adobe Target], le [!UICONTROL compositeur d’expérience visuelle] (VEC) offre aux marketeurs une fonctionnalité pratique pour créer des activités et personnaliser les expériences qui peuvent être diffusées dynamiquement sur les applications multipage classiques via la mbox globale d’Adobe Target. Toutefois, cela dépend de la récupération des offres au chargement de la page ou des appels serveur suivants, qui introduit une latence, comme illustré dans le diagramme ci-dessous. Cette approche ne fonctionne pas bien avec les applications monopages, car elle altère l’expérience utilisateur et les performances de l’application.

![Cycle de vie traditionnel par rapport au cycle de vie d’une application d’une seule page](/help/main/c-experiences/assets/trad-vs-spa.png)

Avec la nouvelle version, nous présentons désormais le compositeur d’expérience visuelle pour les applications monopages. Le compositeur d’expérience visuelle (VEC) pour applications d’une seule page (SPA) permet aux marketeurs de créer des tests et de personnaliser le contenu des SPA eux-mêmes sans dépendances de développement continu. Le compositeur d’expérience visuelle peut être utilisé pour créer [des activités de ](/help/main/c-activities/t-test-ab/test-ab.md)test AB et [de ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) sur les infrastructures les plus populaires, telles que React et Angular.

## Adobe [!DNL Target] Vues et applications d’une seule page

Le VEC de Adobe Target pour les applications SPA tire profit d’un nouveau concept nommé Vues : un groupe logique d’éléments visuels qui, ensemble, forment une expérience pour application d’une seule page. Une application d’une seule page (SPA) peut donc être considérée comme une transition entre les vues (et pas entre les URL) basée sur les interactions des utilisateurs. Une Vue peut généralement représenter un site entier ou des éléments visuels regroupés dans un site.

Pour expliquer plus en détail les Vues, parcourez cet hypothétique site d’e-commerce en ligne implémenté dans React et explorez quelques exemples de Vues. Cliquez sur les liens ci-dessous pour ouvrir ce site dans un nouvel onglet du navigateur.

**Lien : [Site d’accueil](https://target.enablementadobe.com/react/demo/#/)**

![Site d’accueil](/help/main/c-experiences/assets/home.png)

Lorsqu’on accède au site d’accueil, on voit immédiatement une image à forte identification ayant pour but de promouvoir une vente de Pâques ainsi que les produits les plus récents vendus sur le site. Dans ce cas, une Vue peut être définie comme tout le site d’accueil. Ceci est bon à noter comme nous allons le développer dans la section Implémentation d’Adobe Target Views ci-dessous.

**Lien : [Site du produit](https://target.enablementadobe.com/react/demo/#/products)**

![site de produit](/help/main/c-experiences/assets/product-site.png)

Alors que les produits nous intéressent davantage, nous décidons de cliquer sur le lien Produits. Comme pour le site d’accueil, l’intégralité du site de produits peut être définie comme une Vue. Nous pouvons nommer cet affichage « produits » comme le nom de chemin d’accès dans `https://target.enablementadobe.com/react/demo/#/products`.

![site produit 2](/help/main/c-experiences/assets/product-site-2.png)

Au début de cette section, nous avons défini les vues en tant que site entier ou même un groupe d’éléments visuels sur le site. Comme illustré ci-dessus, les quatre produits affichés sur le site peuvent également être regroupés et considérés comme une vue. Si nous souhaitons nommer cette Vue, nous pouvons la nommer « produits ».

![site produit 3](/help/main/c-experiences/assets/product-site-3.png)

Nous décidons de cliquer sur le bouton Charger plus pour explorer d’autres produits sur le site. L’URL du site Web ne change pas dans ce cas. Mais une Vue ici ne représente que la deuxième ligne des produits ci-dessus. Le nom de la Vue peut être appelé « PRODUCTS-PAGE-2 ».

**Lien : [Passage en caisse](https://target.enablementadobe.com/react/demo/#/checkout)**

![page paiement](/help/main/c-experiences/assets/checkout.png)

Comme nous avons aimé certains produits sur le site, nous avons décidé d’en acheter quelques uns. Sur la page de paiement du site, certaines options permettent de choisir une livraison normale ou express. Comme une Vue peut représenter n’importe quel groupe d’éléments visuels d’un site, nous pouvons la nommer « Préférences de livraison de la Vue ».

De plus, le concept des Vues peut être beaucoup plus étendu. Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, la Vue peut être nommée « Livraison normale ». Si l’option Livraison express est sélectionnée, la Vue peut être nommée « Livraison express ».

Les marketeurs souhaitent à présent exécuter un test AB pour déterminer si la modification de la couleur du bleu au rouge augmente les conversations lorsque la livraison express est sélectionnée, au lieu de conserver la couleur du bouton bleu pour les deux options de livraison.

## Implémentation de l’Adobe [!DNL Target] Vues

À présent que nous avons examiné le concept d’Adobe Target Views, nous pouvons l’exploiter dans Target pour permettre aux spécialistes du marketing d’exécuter des tests AB et XT sur les applications monopages via le compositeur d’expérience visuelle. Une configuration développeur unique sera nécessaire. Examinons les étapes à suivre.

1. Installez at.js 2.x.

   Tout d’abord, nous devons installer at.js 2.x. Cette version d’at.js a été développée en tenant compte des applications monopages. Les versions précédentes d’at.js et ne prennent pas en charge Adobe Target Views et le compositeur d’expérience visuelle pour les applications monopages.

   ![Boîte de dialogue Détails de mise en œuvre](/help/main/c-experiences/assets/imp-200.png)

   Téléchargez at.js 2.x via l’interface utilisateur d’Adobe Target située dans [!UICONTROL Administration > Mise en oeuvre]. at.js 2.x peut également être déployé via des balises dans [Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Toutefois, les extensions Adobe Target ne sont actuellement pas à jour et prises en charge.

1. Implémentez la fonction la plus récente d’at.js 2.x : [triggerView()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) sur vos sites.

   Après avoir défini les affichages de votre application monopage où vous souhaitez exécuter un test A/B ou XT, implémentez la fonction `triggerView()` d’at.js 2.x avec les affichages transmis sous forme de paramètre. Cela permet aux spécialistes du marketing d’utiliser le compositeur d’expérience visuelle pour concevoir et exécuter les tests A/B et XT pour ces vues définies. Si la fonction `triggerView()` n’est pas définie pour ces affichages, le VEC ne détectera pas les affichages. Les spécialistes en marketing ne peuvent donc pas utiliser le VEC pour concevoir et exécuter des tests A/B et XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Paramètre | Type | Obligatoire ? | Validation | Description |
   | --- | --- | --- | --- | --- |
   | viewName | Chaîne | Oui | 1. Aucun espace à la fin.<br>2. Ne peut pas être vide.<br>3. Le nom de la vue doit être unique pour toutes les pages.<br>4. **Avertissement** : le nom de l’affichage ne doit pas commencer ou se terminer par « `/` ». Cela est dû au fait que le client extrait généralement le nom de la vue à partir du chemin d’URL. Pour nous, « accueil » et « `/home` » sont différents.<br>5. **Avertissement** : la même vue ne doit pas être déclenchée plusieurs fois avec l’option `{page: true}`. | Transmettez n’importe quel nom en tant que type de chaîne que vous souhaitez représenter votre vue. Ce nom d’affichage s’affiche dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
   | Options | Objet | Non |  |  |
   | options > page | Booléen | Non |  | **TRUE** : la valeur par défaut de la page est true. Lorsque `page=true`, des notifications sont envoyées aux serveurs Edge pour incrémenter le nombre d’impressions.<br>**FALSE** : lorsque `page=false`, les notifications ne sont pas envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

   Examinons maintenant quelques exemples d’utilisation pour appeler la fonction `triggerView()` dans React pour notre hypothétique application e-commerce monopage :

   **Lien : [Site d’accueil](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   En tant que marketeurs, si vous souhaitez exécuter des tests AB sur tout le site d’accueil, vous voudrez peut être nommer la vue pouvant être extraite de l’URL : « accueil ».

   ```javascript
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

   **Lien : [Site Produits](https://target.enablementadobe.com/react/demo/#/products)**

   Examinons maintenant un exemple un peu plus complexe. En tant que spécialistes du marketing, vous souhaitez personnaliser la deuxième ligne des produits en changeant la couleur de l’étiquette de prix en rouge après qu’un utilisateur ait cliqué sur le bouton Charger plus.

   ![réaction aux produits](/help/main/c-experiences/assets/react4.png)

   ```javascript
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

   **Lien : [Passage en caisse](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![Paiement React](/help/main/c-experiences/assets/react6.png)

   Si les marketeurs souhaitent personnaliser le contenu du site selon la préférence de livraison sélectionnée, une Vue peut être créée pour chaque préférence de livraison. Dans ce cas, lorsque vous sélectionnez Livraison normale, la Vue peut être nommée « Livraison normale ». Si l’option Livraison express est sélectionnée, la Vue peut être nommée « Livraison express ».

   Les marketeurs souhaitent à présent exécuter un test AB pour déterminer si la modification de la couleur du bleu au rouge augmente les conversations lorsque la livraison express est sélectionnée, au lieu de conserver la couleur du bouton bleu pour les deux options de livraison.

   ```javascript
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

Le panneau [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) et les actions du VEC offrent deux améliorations majeures au niveau du VEC qui permettent à celui-ci de fonctionner correctement avec les applications monopages.

**Panneau des modifications**

Comme illustré ci-dessous, le panneau [!UICONTROL Modifications] capture les actions créées pour une vue donnée. Notez que toutes les actions d’une vue sont regroupées sous cette vue.

**Actions**

Cliquer sur une action met en évidence l’élément de la page sur lequel cette action sera appliquée. Chaque action du VEC créée sous une vue comporte les icônes suivantes, comme illustré ci-dessous : Informations, Modifier, Cloner, Déplacer et Supprimer.

![Modifications](/help/main/c-experiences/assets/modifications.png)

Le tableau suivant décrit chaque action :

| Page | Description |
| --- | --- |
| Informations | Affiche les détails de cette action. |
| Modifier | Permet de modifier directement les propriétés de cette action. |
| Dupliquer | Cloner l’action vers une ou plusieurs vues figurant dans le panneau [!UICONTROL Modifications] ou vers une ou plusieurs vues que vous avez parcourues et auxquelles vous avez accédé dans le VEC. L’action n’a pas nécessairement besoin d’exister dans le panneau [!UICONTROL Modifications].<br>**Remarque** : Après une opération de clonage, vous devez accéder à la vue dans le VEC via [!UICONTROL Parcourir] pour vérifier si l’action clonée a été une opération valide. Si l’action ne peut pas être appliquée à l’affichage, une erreur s’affiche. |
| Déplacer | Déplace l’action vers un événement de chargement de page ou tout autre vue existant dans le panneau Modifications.<br>[!UICONTROL Événement de chargement de page] : Toutes les actions correspondant à l’événement de chargement de page sont appliquées au chargement initial de la page de votre application Web.<br>**Remarque** : Après avoir effectué une opération de déplacement, vous devez accéder à la vue dans le VEC via Parcourir pour vérifier si le déplacement a été une opération valide. Si l’action ne peut pas être appliquée à la vue, une erreur s’affiche. |
| Supprimer | Supprime l’action. |

>[!NOTE]
>
>Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans le VEC, ou même si le chargement de la page échoue. Les actions qu’il n’est pas possible de modifier avant le chargement complet du site sont désactivées dans l’interface utilisateur.sp

**Exemple 1**

Reportez-vous à l’exemple ci-dessus lorsque vous avez créé une vue d’accueil. Notre objectif est d’obtenir deux effets pour cette vue :

1. Remplacez les boutons « Ajouter au panier » et « J’aime » par une couleur bleue plus claire. Cela doit avoir lieu lors d’un « chargement de page », car vous changez les composants de l’en-tête.
1. Remplacez l’étiquette « Derniers produits de 2019 » par « Produits dernier cri de 2019 » et modifiez la couleur du texte en violet.

Pour exécuter ces objectifs, dans le VEC, cliquez sur [!UICONTROL Composer] et appliquez ces modifications dans la vue d’accueil.

![Exemple 1](/help/main/c-experiences/assets/example1.png)

**Exemple 2**

Reportez-vous à l’exemple ci-dessus lorsque vous avez créé une vue PAGE-PRODUITS-2. Votre objectif est de remplacer le libellé « Prix » par « Prix de vente » et de modifier la couleur de l’étiquette en rouge.

1. Cliquez sur [!UICONTROL Parcourir], puis sur le lien [!UICONTROL Produits] dans l’en-tête.
1. Cliquez une fois sur [!UICONTROL Charger plus] pour accéder à la deuxième ligne de produits.
1. Cliquez sur [!UICONTROL Composer].
1. Appliquez les actions pour remplacer le libellé du texte par « Prix de la vente » et modifier la couleur en rouge.

![Exemple 2](/help/main/c-experiences/assets/example2.png)

**Exemple 3**

Enfin, comme mentionné précédemment, les vues peuvent être définies à un niveau plus détaillé. Les vues peuvent être un état ou une option d’un bouton radio. Auparavant, vous aviez créé les vues pour les PAIEMENTS-EXPRESS et les PAIEMENTS-STANDARD. Notre objectif est de modifier la couleur du bouton en rouge pour la vue PAIEMENT-EXPRESS.

1. Cliquez sur [!UICONTROL Parcourir].
1. Ajoutez deux produits au panier.
1. Cliquez sur l’icône de panier dans le coin supérieur droit.
1. Cliquez sur Payer votre commande.
1. Cliquez sur le bouton radio Livraison express.
1. Cliquez sur [!UICONTROL Composer].
1. Modifiez la dénomination du bouton « Paiement » en « Terminer la commande » et la couleur en rouge.

![Exemple 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>La vue PAIEMENT-EXPRESS n’apparaîtra pas dans le panneau de modification tant que vous n’avez pas cliqué sur le bouton radio Livraison express. Cela est dû au fait que `triggerView()` la fonction est déclenchée lorsque le bouton radio Livraison express est sélectionné et que cette fonction n’est disponible que lorsque le compositeur d’expérience visuelle sait qu’une vue s’affiche dans le panneau de modification.

## Exploration approfondie d’at.js et des applications à page unique

**Comment récupérer les vues des dernières données d’audience hydratées par des actions, après le chargement initial de la page sur mon application monopage ?**

Le workflow type d’at.js 2.x survient lors du chargement de votre site, lorsque toutes vos vues et actions sont mises en cache afin que les actions suivantes de l’utilisateur sur votre site ne déclenchent pas d’appels au serveur pour récupérer les offres. Si vous souhaitez récupérer les vues en fonction des données de profil les plus récentes, actualisées selon les actions de l’utilisateur, vous pouvez appeler `getOffers()` et `applyOffers()` avec les dernières données utilisateur ou données de profil transmises.

Supposons, par exemple, que vous soyez une société de télécommunications et que vous ayez une application d’une seule page utilisant at.js 2.x. En tant qu’entreprise, vous souhaitez atteindre les objectifs suivants :

* Pour un utilisateur déconnecté ou anonyme, affichez la dernière promotion de l’entreprise, telle que l’affichage d’une offre à forte identification « Premier mois offert » sur `http://www.telecom.com/home`.
* Pour un utilisateur connecté, affichez une offre promotionnelle de mise à niveau pour les utilisateurs dont les contrats arrivent à expiration, tels que « Vous êtes éligible pour recevoir un smartphone gratuit ». on `http://www.telecom.com/loggedIn/home`.

Désormais, vos développeurs nomment les vues et appellent `triggerView()` de la manière suivante :

* Pour `http://www.telecom.com/home`, le nom de la vue est « Déconnecté de l’accueil »
   * `triggerView(“Logged Out Home”)` est appelée.
* Pour `http://www.telecom.com/loggedIn/home` le nom de la vue est « Connecté à l’accueil »
   * `triggerView(“Logged In Home”)` est appelée lors de la modification.

Les marketeurs exécutent ensuite les activités AB suivantes via le compositeur d’expérience visuelle :

* L’activité A/B comportant l’offre « Premier mois gratuit » pour les audiences ayant le paramètre « `loggedIn= false` » à afficher dans `http://www.telecom.com/home`, lorsque le nom de la vue est Déconnecté de l’accueil.
* Activité AB comportant l’offre « Vous êtes éligible pour obtenir un smartphone gratuit ». pour les audiences dont le paramètre est « `loggedIn=true` » à afficher dans `http://www.telecom.com/loggedIn/home` et dont le nom de vue est Connecté - Offre à forte identification.

Examinons maintenant ce flux d’utilisateurs :

1. Un utilisateur déconnecté anonyme arrive sur votre page.
1. Puisque vous utilisez at.js 2.x, vous transmettez le paramètre « `loggedIn = false` » au chargement de la page pour récupérer toutes les vues présentes dans les activités actives qui remplissent les critères lorsque l’audience possède le paramètre « `loggedIn = false` ».
1. at.js 2.x récupère ensuite la vue Déconnecté de l’accueil pour afficher l’offre « Premier mois gratuit » et la stocke dans le cache.
1. Lors de l’appel de `triggerView(“Logged Out Home”)`, l’offre « Premier mois gratuit » est récupérée depuis le cache et s’affiche sans appel au serveur.
1. L’utilisateur clique à présent sur « Connexion » et fournit ses informations d’identification.
1. Étant donné que votre site web est une application d’une seule page, vous n’effectuez pas de chargement de page complet et redirigez votre utilisateur vers `http://www.telecom.com/loggedIn/home`.

Mais voici le problème. L’utilisateur se connecte et vous rencontrez `triggerView(“Logged In Home”)` parce que la route du code a été modifiée. Cela indique à at.js 2.x de récupérer la vue et les actions du cache, mais la seule vue qui existe dans le cache est Déconnecté de l’accueil.

Ainsi, comment récupérer la vue Connecté et afficher le message « Vous êtes éligible pour recevoir un smartphone gratuit » ? offer? Et comme toutes les actions suivantes sur votre site dépendent du point de vue de l’utilisateur connecté, comment pouvez-vous vérifier que toutes les actions suivantes conduisent à des offres personnalisées pour les utilisateurs connectés ?

Vous pouvez utiliser les nouvelles fonctions `getOffers()` et `applyOffers()` prises en charge dans at.js 2.x :

```javascript
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

Transmettez la réponse de `getOffers()` à `applyOffers()` et toutes les vues et actions associées à « loggedIn = true » mettront à présent à jour le cache at.js.

En d’autres termes, at.js 2.x prend en charge la récupération des vues, des actions et des offres avec les données d’audience les plus récentes selon un modèle On-demand.

**at.js 2.x prend-il en charge Analytics for Target (A4T) pour les applications d’une seule page ?**

Oui, at.js 2.x prend en charge A4T pour l’application d’une seule page via la fonction `triggerView()`, étant donné que vous avez implémenté Adobe Analytics et le service d’identification des visiteurs Experience Cloud. Voir le diagramme ci-dessous avec des descriptions détaillées.

![Flux cible](/help/main/c-experiences/assets/atjs-spa-flow.png)

| Étape | Description |
| --- | --- |
| 1 | `triggerView()` est appelée dans l’application d’une seule page pour rendre une vue et appliquer des actions pour modifier les éléments visuels associés à la vue. |
| 2 | Le contenu ciblé pour la vue est lu à partir du cache. |
| 3 | Le contenu ciblé s’affiche aussi rapidement que possible, sans scintillement du contenu par défaut. |
| 4 | La demande de notification est envoyée au magasin de profils Target pour compter le nombre de visiteurs dans l’activité et incrémenter les mesures. |
| 5 | Les données Analytics sont envoyées aux serveurs de collecte de données. |
| 6 | Les données Target sont associées aux données Analytics par l’intermédiaire du SDID et sont traitées dans le magasin de rapports Analytics. Il est alors possible de consulter les données Analytics à la fois dans Analytics et Target, par l’intermédiaire des rapports d’A4T. |

>[!NOTE]
>Si vous ne souhaitez pas envoyer de notifications à Adobe Analytics pour le comptage d’impressions chaque fois qu’une vue est déclenchée, transmettez `{page: false}` à la fonction `triggerView()` afin que le comptage d’impressions ne soit pas gonflé lorsqu’une vue est déclenchée plusieurs fois pour un composant qui effectue un rendu constant. Par exemple :
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Activités prises en charge

| Type d’activité | Pris en charge ? |
| --- | --- |
| [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |
| [Recommandations en tant qu’activités de ](/help/main/c-recommendations/recommendations-as-an-offer.md)<br>test A/B et de ciblage d’expérience | Oui |
| [affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Oui |
| [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) | Oui |
| [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Non |
| [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Non |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Non |
| [Recommandations](/help/main/c-recommendations/recommendations.md) | Non |

**Si nous avons installé at.js 2.x et implémenté `triggerView()` sur nos sites, comment exécuter les activités A/B de ciblage automatique étant donné que le compositeur d’expérience visuelle pour application d’une seule page ne prend pas en charge le ciblage automatique ?**

Si vous souhaitez utiliser des activités AB de ciblage automatique, vous pouvez déplacer toutes vos actions à exécuter lors de l’événement de chargement de page dans le compositeur d’expérience visuelle. Passez la souris sur chaque action, puis cliquez sur le bouton [!UICONTROL Déplacer vers l’événement] de chargement de la page. Ensuite, à l’étape suivante, vous pouvez sélectionner Ciblage automatique pour la méthode d’affectation du trafic.

## Intégrations prises en charge

| Intégration | Pris en charge ? |
| --- | --- |
| [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | Oui |
| [Audiences Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md) | Oui |
| [Attributs du client](/help/main/c-target/c-visitor-profile/working-with-customer-attributes.md) | Oui |
| [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Oui |

## Fonctionnalités prises en charge {#supported-features}

| Fonctionnalité | Pris en charge ? |
| --- | --- |
| [Espaces de travail et propriétés](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) | Oui |
| [Liens d’assurance qualité](/help/main/c-activities/c-activity-qa/activity-qa.md) | Oui |
| [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) | Non |
| [Code personnalisé ](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Oui |
| [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | Toutes |
| [Suivi des clics](/help/main/c-activities/r-success-metrics/click-tracking.md) | Oui |
| [Diffusion multi-activité](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) | Oui |

## Paramètres de diffusion de page pour le SPA VEC {#page-delivery-settings}

Les paramètres de [!UICONTROL Diffusion de page] vous permettent de configurer des règles afin de déterminer quand une activité Target doit être remplie et exécutée pour une audience.

Pour accéder aux options de [!UICONTROL Diffusion de page] depuis le workflow de l’activité guidé en trois parties du VEC, à partir de l’étape **[!UICONTROL Expériences]**, cliquez sur **[!UICONTROL Configurer]** (icône d’engrenage) > **[!UICONTROL Diffusion de page]**.

![Boîte de dialogue Options de diffusion de page](/help/main/c-experiences/assets/page-delivery.png)

Par exemple, comme défini par les paramètres de [!UICONTROL Diffusion de page] ci-dessus, une activité Target est admissible et s’exécute lorsqu’un visiteur arrive directement sur `https://www.adobe.com` *ou* lorsqu’un visiteur arrive sur une URL qui contient `https://www.adobe.com/products`. Cela fonctionne parfaitement pour toute application multi-page dans laquelle chaque interaction avec la page appelle un rechargement de page, pour lequel at.js récupère les activités qui remplissent les critères de l’URL à laquelle l’utilisateur accède.

Cependant, comme les SPA fonctionnent différemment, les paramètres de [!UICONTROL Diffusion de page] doivent être configurés de manière à permettre l’application aux vues de toutes les actions définies dans l’activité du SPA VEC.

### Exemple d’utilisation

Considérez cet exemple d’utilisation :

![Panneau Modifications du SPA VEC](/help/main/c-experiences/assets/page-delivery-example.png)

Les modifications suivantes ont été apportées :

* Modification de la couleur d’arrière-plan dans la vue Accueil, située sous l’URL : [/#/](https://target.enablementadobe.com/react/demo/#/)https://target.enablementadobe.com/react/demo/#/.
* Modification de la couleur du bouton dans la vue Produits, située sous l’URL : [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).

En gardant l’exemple ci-dessus à l’esprit, que se passerait-il lorsque nous configurerions [!UICONTROL Diffusion de page] pour inclure uniquement les paramètres suivants : [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/) dans un SPA avec at.js 2.*x* ?

![Boîte de dialogue Diffusion de page](/help/main/c-experiences/assets/spa-page-delivery.png)

L’illustration suivante illustre la demande Flux cible - Chargement de page dans at.js 2.*x* :

![Flux cible : demande de chargement de page at.js 2.0](/help/main/c-experiences/assets/page-load-request.png)

**Parcours d’utilisateur n°1**

* Un utilisateur accède directement à [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* at.js 2.*x* effectue une requête sur le Edge pour déterminer si une activité doit s’exécuter pour l’URL : [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* À l’étape 6, le Target Edge renvoie les actions de la vue Accueil et Produits pour qu’elles soient mises en cache dans le navigateur.

**Résultat** : L’utilisateur voit la couleur d’arrière-plan verte dans la vue Accueil. Lorsque l’utilisateur accède ensuite à [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products, la couleur d’arrière-plan bleue du bouton est affichée car l’action est mise en cache dans le navigateur sous la vue Produits.

Remarque : L’utilisateur accédant à [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) n’a pas déclenché de chargement de page.

**Parcours d’utilisateur n°2**

* Un utilisateur accède directement à [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* at.js 2.*x* effectue une requête sur le Edge pour déterminer si une activité doit s’exécuter pour l’URL : [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Aucune activité n’est qualifiée pour [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Puisqu’aucune activité n’est qualifiée, aucune action ni vue ne peut être mise en cache pour at.js 2.*x* à partir duquel déclencher.

**Résultat** : Même si vous avez défini `triggerView()` pour la vue Produits et effectué une action sur la vue Produits via le SPA VEC, vous ne verrez pas l’action attendue puisque vous n’avez pas créé de règle incluant [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products dans les paramètres de remise de page.

### Bonne pratique

Vous pouvez constater que la gestion du parcours des utilisateurs peut s’avérer difficile lorsque les utilisateurs peuvent accéder à n’importe quelle URL de votre SPA et accéder à n’importe quelle autre page. Par conséquent, il est préférable de spécifier une règle de diffusion de page qui inclut l’URL de base afin qu’elle inclue l’intégralité de votre SPA. Ainsi, il n’est pas nécessaire de penser à tous les parcours et chemins empruntés par un utilisateur pour atteindre une page sur laquelle vous souhaitez afficher une activité de test A/B ou de ciblage d’expérience (XT).

Par exemple, pour résoudre le problème ci-dessus, nous pouvons spécifier l’URL de base dans les paramètres de diffusion de page en tant que telle :

![Boîte de dialogue Diffusion de page](/help/main/c-experiences/assets/conclusion.png)

Ainsi, chaque fois qu’un visiteur arrive sur la SPA et accède à la page d’accueil ou à la vue de page, il verra les actions appliquées.

Désormais, lorsque vous ajoutez une action à une vue dans le SPA VEC, nous vous montrerons le message contextuel suivant pour vous rappeler de réfléchir aux règles de [!UICONTROL Diffusion de page].

![Message Paramètres de Diffusion de page](/help/main/c-experiences/assets/pop-up-message.png)

Ce message s’affiche lorsque vous ajoutez la première action à une vue pour chaque nouvelle activité que vous créez. Ce message permet de s’assurer que tous les membres de votre organisation apprennent à appliquer correctement ces règles de [!UICONTROL Diffusion de page].

## Vidéo de formation : utilisation du compositeur d’expérience visuelle pour les applications monopages dans Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Voir [Utilisation du compositeur d’expérience visuelle pour application d’une seule page (SPA VEC) dans Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) pour plus d’informations.
