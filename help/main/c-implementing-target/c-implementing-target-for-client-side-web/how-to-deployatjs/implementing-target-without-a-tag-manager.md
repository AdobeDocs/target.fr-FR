---
keywords: implémenter target;implémentation;implémenter at.js;gestionnaire de balises;prise de décision sur les appareils;prise de décision sur les appareils
description: Découvrez comment spécifier les paramètres (détails du compte, méthodes de mise en oeuvre, etc.) mise en oeuvre de l’Adobe [!DNL Target] bibliothèque at.js sans utiliser de gestionnaire de balises.
title: Puis-je implémenter [!DNL Target] sans gestionnaire de balises ?
feature: Implement Server-side
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1834'
ht-degree: 47%

---

# Mise en oeuvre [!DNL Target] sans gestionnaire de balises

Informations sur l’implémentation [!DNL Adobe Target] sans utiliser de gestionnaire de balises ou de balises dans [!DNL Adobe Experience Platform].

>[!NOTE]
>
>Balises dans [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} est la méthode préférée pour implémenter [!DNL Target] et la bibliothèque at.js. Les informations suivantes ne s’appliquent pas lors de l’utilisation de balises dans [!DNL Adobe Experience Platform] mettre en oeuvre [!DNL Target].

Pour accéder au [!UICONTROL Implémentation] page, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.

Vous pouvez définir les paramètres suivants sur cette page :

* Détails du compte
* Méthodes de mise en oeuvre
* API de profil
* Outils de débogage
* Confidentialité

>[!NOTE]
>
>Vous pouvez remplacer les paramètres de la bibliothèque at.js au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target Standard/Premium], ou utiliser des API REST. Pour plus d’informations, voir [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

## Détails du compte

Vous pouvez afficher les détails du compte suivants. Ces paramètres ne peuvent pas être modifiés.

| Paramètre | Description |
| --- | --- |
| [!UICONTROL Code client] | Le code client est une séquence de caractères propre au client qui est souvent requise lors de l’utilisation des API de [!DNL Target]. |
| [!UICONTROL ID d’organisation IMS] | Cet identifiant associe votre implémentation à votre compte [!DNL Adobe Experience Cloud]. |
| [!UICONTROL Prise de décision sur appareil] | Pour activer la prise de décision sur l’appareil, faites glisser la bascule vers la position &quot;activée&quot;.<br>La prise de décision sur l’appareil vous permet de mettre en cache vos activités A/B et [!UICONTROL Ciblage d’expérience] (XT) campagnes sur votre serveur et prennent des décisions en mémoire à une latence proche de zéro. Pour plus d’informations, voir [Présentation de la prise de décision sur les périphériques](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank} dans la variable *[!DNL Adobe Target]SDK* guide. |
| [!UICONTROL Incluez toutes les activités qualifiées de prise de décision sur l’appareil existantes dans l’artefact.] | (Conditionnel) Cette option s’affiche si vous activez la prise de décision sur l’appareil.<br>Faites glisser le bouton d’activation vers la position &quot;Activé&quot; si vous souhaitez que toutes vos activités Target actives qui remplissent les critères pour la prise de décision sur l’appareil soient automatiquement incluses dans l’artefact.<br>Si vous laissez ce bouton désactivé, vous devez recréer et activer toute activité de prise de décision sur l’appareil afin qu’elle soit incluse dans l’artefact de règles généré. |

## Méthodes de mise en oeuvre

Les paramètres suivants peuvent être configurés dans le panneau Méthodes de mise en oeuvre :

### Paramètres globaux

>[!NOTE]
>
>Ces paramètres s’appliquent à tous les [!DNL Target] Bibliothèques .js. Après avoir apporté des modifications à la section Méthodes de mise en oeuvre , vous devez télécharger la bibliothèque et la mettre à jour dans votre mise en oeuvre.

| Paramètre | Description |
| --- | --- |
| Chargement de page activé (mbox globale de création automatique) | Indiquez si l’appel de la mbox globale doit être incorporé dans le fichier at.js afin d’être automatiquement déclenché lors de chaque chargement de page. |
| mbox globale | Sélectionnez un nom pour la mbox globale. Par défaut, ce nom est target-global-mbox.<br>Avec at.js, les noms de mbox peuvent contenir des caractères spéciaux, y compris des esperluettes (&amp;). |
| Délai d’expiration (secondes) | Si [!DNL Target] ne répond pas avec du contenu dans le délai défini, l’appel au serveur expire et le contenu par défaut est affiché. Des tentatives d’appel supplémentaires sont effectuées pendant la session du visiteur. Le délai par défaut est de 5 secondes.<br>La bibliothèque at.js utilise le paramètre d’expiration défini dans `XMLHttpRequest`. Le délai d’expiration commence lorsque la demande est déclenchée et s’arrête lorsque [!DNL Target] reçoit une réponse du serveur. Pour plus d’informations, reportez-vous à la section [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) du MDN (Mozilla Developer Network, réseau de développeurs Mozilla).<br>Si le délai expire avant la réception de la réponse, le contenu par défaut est affiché et le visiteur peut être compté en tant que participant à une activité parce que la collecte de données survient sur le serveur [!DNL Target] Edge. Si la requête atteint le serveur [!DNL Target] Edge, le visiteur est comptabilisé.<br>Tenez compte de ce qui suit lors de la configuration du paramètre d’expiration :<ul><li>Si la valeur est trop basse, les utilisateurs risquent de voir le contenu par défaut dans la plupart des cas, bien que le visiteur puisse être comptabilisé parmi les participants à l’activité.</li><li>Si la valeur est trop élevée, les visiteurs risquent de voir des zones vierges sur votre page web ou des pages vierges si vous utilisez le masquage du contenu pendant une durée prolongée.</li></ul>Pour une meilleure compréhension du temps de réponse de mbox, consultez l’onglet Réseau dans les Outils de développement de votre navigateur. Vous pouvez également utiliser des outils de surveillance des performances web tiers, tels que Catchpoint.<br>**Remarque**: Le [visitorApiTimeout](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)Le paramètre {target=_blank} garantit que [!DNL Target] n’attend pas trop longtemps la réponse de l’API visiteur. Ce paramètre et le paramètre Expiration de at.js décrit ici n’ont pas d’effet l’un sur l’autre. |
| Durée de vie du profil | Ce paramètre détermine la durée de stockage des profils de visiteur. Par défaut, les profils sont stockés pendant deux semaines. Ce paramètre peut être augmenté jusqu’à 90 jours.<br>Pour modifier le paramètre Durée de vie du profil, contactez le [service à la clientèle](https://helpx.adobe.com/fr/contact/enterprise-support.ec.html). |

### Méthode de mise en oeuvre principale

>[!IMPORTANT]
>
>L’équipe Target prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez la mise à niveau vers la mise à jour la plus récente de l’une des principales versions d’at.js pour vous assurer que vous utilisez une version prise en charge.

Pour télécharger la version d’at.js souhaitée, cliquez sur la **[!UICONTROL Télécharger]** bouton .

Pour modifier les paramètres at.js, cliquez sur **[!UICONTROL Modifier]** en regard de la version d’at.js souhaitée.

>[!IMPORTANT]
>
>Avant de modifier ces paramètres par défaut, consultez [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md) ainsi, vous n’affectez pas votre mise en oeuvre actuelle.

Outre les paramètres décrits ci-dessus, les paramètres at.js spécifiques suivants sont également disponibles :

| Paramètre | Description |
|--- |--- |
| En-tête de bibliothèque personnalisé | Ajoutez du code JavaScript personnalisé à inclure au haut de la bibliothèque. |
| Pied de page de bibliothèque personnalisé | Ajoutez du code JavaScript personnalisé à inclure au bas de la bibliothèque. |

### Méthodes de mise en oeuvre avec la prise de décision sur l’appareil

À compter de la version 2.5.0, at.js propose la prise de décision sur l’appareil. La prise de décision sur appareil vous permet de mettre en cache votre [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) et [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activités sur le navigateur pour effectuer une prise de décision en mémoire sans bloquer la demande réseau au [!DNL Adobe Target] Edge Network.

Pour plus d’informations, voir les rubriques :

* [Prise de décision sur appareil pour le côté client](https://developer.adobe.com/target/implement/client-side/){target=_blank}
* [Prise de décision sur appareil pour le côté serveur](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank}

### API de profil

Activez ou désactivez l’authentification pour la mise à jour des lots via l’API et générez un jeton d’authentification de profil.

Pour plus d’informations, voir [Paramètres de l’API de profil](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/profile-api-settings/).

### Outils de débogage

Génération d’un jeton d’autorisation pour l’utilisation d’un jeton avancé [!DNL Target] outils de débogage. Cliquez sur **[!UICONTROL Générer un nouveau jeton d’authentification]**.

![Générer un nouveau jeton d’authentification](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### Confidentialité

Ces paramètres vous permettent d’utiliser des [!DNL Target] conformément aux lois sur la confidentialité des données en vigueur.

Sélectionnez un paramètre dans la liste déroulante Obscurcir l’adresse IP du visiteur :

* Obscurcissement du dernier octet
* Obscurcissement d’IP complet
* None

Pour plus d’informations, consultez la page [Confidentialité](https://developer.adobe.com/target/before-implement/privacy/privacy/).

>[!NOTE]
>
>L’option Prise en charge du navigateur hérité était disponible dans les versions 0.9.3 et antérieures d’ at.js . Cette option a été supprimée de la version 0.9.4 d’at.js. Pour obtenir une liste des navigateurs pris en charge par at.js, voir [Navigateurs pris en charge](https://developer.adobe.com/target/before-implement/supported-browsers/).<br>Les navigateurs hérités sont d’anciens navigateurs qui ne prennent pas entièrement en charge le partage des ressources cross-origin (CORS). Ces navigateurs comprennent Internet Explorer (versions antérieures à la version 11) et Safari (versions 6 et antérieures). Si la prise en charge du navigateur hérité était désactivée, Target ne diffusait pas de contenu ni ne comptabilisait les visiteurs dans les rapports sur ces navigateurs. Si cette option a été activée, il est recommandé d’effectuer une assurance qualité sur les navigateurs plus anciens afin de garantir une bonne expérience client.

## Téléchargement d’at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions pour télécharger la bibliothèque à l’aide de la méthode [!DNL Target] ou de l’API de téléchargement.

>[!NOTE]
>
>* [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} est la méthode préférée pour implémenter [!DNL Target] et la bibliothèque at.js. Les informations suivantes ne s’appliquent pas lors de l’utilisation de balises dans [!DNL Adobe Experience Platform] mettre en oeuvre [!DNL Target].
>
>* Le [!DNL Target] L’équipe prend en charge at.js 1.*x* et at.js 2.*x*. Effectuez une mise à niveau vers la mise à jour la plus récente de l’une des versions majeures d’at.js pour vous assurer que vous utilisez une version prise en charge. Pour en savoir plus sur le contenu de chaque version, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).


### Téléchargement d’at.js à l’aide du [!DNL Target] interface {#section_1F5EE401C2314338910FC57F9592894E}

Pour télécharger [!DNL at.js] depuis l’interface [!DNL Target], procédez comme suit :

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
1. Dans la [!UICONTROL Méthodes de mise en oeuvre] , cliquez sur le bouton **[!UICONTROL Télécharger]** en regard de la version d’at.js souhaitée.

### Téléchargement d’at.js à l’aide du [!DNL Target] API de téléchargement {#section_C0D9D2A9068144708D08526BA5CA10D0}

Pour télécharger [!DNL at.js] à l’aide de l’API, procédez comme suit :

1. Obtenez votre code client.

   Votre code client figure dans la partie supérieure du **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]** de la [!DNL Target] .

1. Obtenez votre numéro d’administrateur.

   Chargez cette URL :

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Remplacer `client code` avec le code client de l’étape 1.

   Le résultat du chargement de cette URL doit ressembler à l’exemple suivant :

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   Dans cet exemple, le numéro d’administrateur est 6.

1. Télécharger [!DNL at.js].

   Chargez cette URL avec la structure suivante :

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Remplacer `admin number` avec votre numéro d’administrateur.
   * Remplacer `client code` avec le code client de l’étape 1.
   * Remplacer `version number` avec le numéro de version at.js souhaité (par exemple, 2.2).

   >[!IMPORTANT]
   >
   >L’équipe Target gère seulement deux versions d’[!DNL at.js] : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge. Pour en savoir plus sur le contenu de chaque version, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).

   Le chargement de cette URL démarre le téléchargement du fichier [!DNL at.js] personnalisé.

## Implémentation d’at.js {#concept_03CFA86973A147839BEB48A06FEE5E5A}

Vous devez implémenter at.js à `<head>` l’élément de chaque page de votre site web.

Une implémentation classique de Target n’utilisant pas de gestionnaire de balises, comme les balises dans [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/){target=_blank} ressemble à ceci :

```
<!doctype html> 
<html> 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head>
<body> 
    The default content of the page 
</body> 
</html>
```

Tenez compte des remarques importantes suivantes :

* Doctype HTML5 (par exemple, `<!doctype html>`) doit être utilisé. Les anciens attributs ou ceux qui ne sont pas pris en charge pourraient empêcher Target d’émettre des requêtes.
* Les options de préconnexion et de prérécupération peuvent aider vos pages web à charger plus rapidement. Si vous utilisez ces configurations, veillez à remplacer `<client code>` avec votre propre code client, que vous pouvez obtenir à partir de la variable **[!UICONTROL Administration]** > **[!UICONTROL Implémentation] page.
* Si vous possédez une couche de données, l’idéal est d’en définir le plus possible dans la section `<head>`de vos pages, et ce avant le chargement d’at.js. Cet emplacement offre la possibilité maximale d’utiliser ces informations dans Target pour la personnalisation.
* Vous devez définir les fonctions spéciales de Target, telles que `targetPageParams()`, `targetPageParamsAll()`, les fournisseurs de données et `targetGlobalSettings()`, après avoir défini votre couche de données, et avant le chargement d’at.js. Vous pouvez également enregistrer ces fonctions dans la variable [!UICONTROL En-tête de bibliothèque] de la section [!UICONTROL Modification des paramètres at.js] et enregistrée dans le cadre de la bibliothèque at.js elle-même. Pour plus d’informations sur ces fonctions, voir [Fonctions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-functions/).
* Si vous utilisez des bibliothèques d’assistance JavaScript, telles que jQuery, incluez-les avant Target afin que vous puissiez utiliser leur syntaxe et leurs méthodes lors de la création d’expériences Target.
* Incluez at.js dans la section `<head>` de vos pages.

## Suivi des conversions {#task_E85D2F64FEB84201A594F2288FABF053}

La mbox de confirmation de commande enregistre des détails sur les commandes passées sur votre site, puis rend possible la création de rapports en fonction des recettes et des commandes. Elle contribue également aux algorithmes de recommandation, tels que « Les personnes qui ont acheté le produit x ont également acheté le produit y ».

>[!NOTE]
>
>Si les utilisateurs effectuent des achats sur votre site web, Adobe recommande de mettre en oeuvre une mbox de confirmation de commande, même si vous utilisez Analytics for Target (A4T) pour vos rapports.

1. Sur votre page des détails de la commande, insérez un script de mbox en respectant le modèle ci-dessous.
1. Remplacez les MOTS EN LETTRES MAJUSCULES par des valeurs dynamiques ou statiques issues de votre catalogue.

   >[!NOTE]
   >
   >Remarque : Utilisez des virgules de séparation pour séparer plusieurs ID de produit.

   **Conseil :** Vous pouvez également transmettre des informations de commande dans une mbox quelconque (qui n’a pas à être nommée `orderConfirmPage`). Vous pouvez également transmettre les informations de la commande dans plusieurs mbox au sein de la même campagne.

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

La mbox de confirmation de commande utilise les paramètres suivants :

| Paramètre | Description |
|--- |--- |
| orderId | Valeur unique identifiant une commande pour la comptabilisation de la conversion.<br>L’`orderId` doit être unique. Les commandes en double ne sont pas prises en compte dans les rapports. |
| orderTotal | Valeur monétaire de l’achat.<br>Ne transmettez pas le symbole monétaire. Utilisez un point décimal (pas une virgule) pour indiquer les valeurs décimales. |
| productPurchasedId (facultatif) | Liste des ID de produit achetés dans la commande séparés par des virgules.<br>Ces ID de produit s’affichent dans le rapport d’audit pour prendre en charge l’analyse de rapports supplémentaire. |
