---
keywords: confirmation de commande, orderConfirmPage
description: Informations sur la mise en œuvre d’Adobe Target sans avoir recours à un gestionnaire de balises (Adobe Launch ou Dynamic Tag Management).
title: Mise en œuvre de Target sans gestionnaire de balises
subtopic: Prise en main
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Mise en œuvre de Target sans gestionnaire de balises{#implement-target-without-a-tag-manager}

Informations sur l’implémentation de [!DNL Adobe Target] sans avoir recours à un gestionnaire de balises (Adobe Launch ou Dynamic Tag Management).

## Mise en œuvre de Target sans gestionnaire de balises {#topic_397FFA3D6918456BBE02A9FBE9537894}

Informations sur la mise en œuvre d’Adobe Target sans avoir recours à un gestionnaire de balises (Adobe Launch ou Dynamic Tag Management).

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) est la méthode préconisée pour la mise en œuvre de Target et de la bibliothèque at.js. Les informations suivantes ne s’appliquent pas à l’utilisation d’Adobe Launch pour la mise en œuvre de Target.

## Configurations d’at.js {#concept_2FA0456607D04F82B0539C5BF5309812}

Ces informations vous aident à définir plusieurs paramètres sur la page des paramètres at.js.

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) est la méthode préconisée pour la mise en œuvre de Target et de la bibliothèque at.js. Les informations suivantes ne s’appliquent pas à l’utilisation d’Adobe Launch pour la mise en œuvre de Target.

>[!NOTE]
>
>Vous pouvez remplacer les paramètres de la bibliothèque at.js plutôt que de configurer les paramètres dans l’interface utilisateur de Target Standard/Premium ou en utilisant des API REST. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

Pour ouvrir la page [!UICONTROL Paramètres] :

1. Cliquez sur **[!UICONTROL Configuration]** &gt; **[!UICONTROL Mise en œuvre]**.
1. Sélectionnez **[!UICONTROL at.js]** &gt; **[!UICONTROL Modifier les paramètres at.js]**.

## Paramètres de diffusion de contenu {#section_118D290DFC444509AD8E4AE86C9D92C0}

Contactez le service à la clientèle avant de modifier ces paramètres. Ces paramètres sont requis pour la plupart des implémentations.

| Paramètre | Description |
|--- |--- |
| Créer automatiquement la mbox globale | Indiquez si l’appel de la mbox globale doit être incorporé dans le fichier at.js afin d’être automatiquement déclenché lors de chaque chargement de page.<br>La modification de ce paramètre a un impact sur at.js et mbox.js. |
| Nom de mbox globale | Sélectionnez un nom pour la mbox globale. Par défaut, ce nom est target-global-mbox.<br>Avec at.js, les noms de mbox peuvent contenir des caractères spéciaux, y compris des esperluettes (&amp;).<br>La modification de ce paramètre a un impact sur at.js et mbox.js. |

## Paramètres avancés {#section_33B697B77BA64A01B5939D7EC75231F2}

| Paramètre | Description |
|--- |--- |
| Code client | Le code client est une séquence de caractères propre au client qui est souvent requise lors de l’utilisation des API de Target.<br>Ce paramètre ne peut pas être modifié. |
| ID d’organisation IMS | Cet identifiant associe votre implémentation à votre compte [!DNL Adobe Experience Cloud].<br>Ce paramètre ne peut pas être modifié. |
| Durée de vie du profil | Ce paramètre détermine la durée de stockage des profils de visiteur. Par défaut, les profils sont stockés pendant deux semaines. Ce paramètre peut être réglé jusqu’à 90 jours.<br>Pour modifier le paramètre Durée de vie du profil, contactez le [service à la clientèle](https://helpx.adobe.com/contact/enterprise-support.ec.html). |
| X-Domaine | Détermine si le navigateur définit les cookies dans votre domaine (cookies propriétaires), le domaine de Target ou les deux.<br>La modification de ce paramètre a un impact sur at.js et mbox.js. |
| Expiration | Si [!DNL Target] ne répond pas avec du contenu dans le délai défini, l’appel au serveur expire et le contenu par défaut est affiché. Des tentatives d’appel supplémentaires sont effectuées pendant la session du visiteur. Le délai par défaut est de 5 secondes.<br>La modification de ce paramètre a un impact sur at.js et mbox.js.<br>La bibliothèque at.js utilise le paramètre d’expiration défini dans `XMLHttpRequest`. Le délai d’expiration commence lorsque la demande est déclenchée et s’arrête lorsque Target reçoit une réponse du serveur. Pour plus d’informations, reportez-vous à la section [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) du MDN (Mozilla Developer Network, réseau de développeurs Mozilla).<br>Si le délai expire avant la réception de la réponse, le contenu par défaut est affiché et le visiteur peut être compté en tant que participant à une activité parce que la collecte de données survient sur le serveur [!DNL Target] Edge. Si la requête atteint le serveur [!DNL Target] Edge, le visiteur est comptabilisé.<br>Tenez compte de ce qui suit lors de la configuration du paramètre d’expiration :<ul><li>Si la valeur est trop basse, les utilisateurs risquent de voir le contenu par défaut dans la plupart des cas, bien que le visiteur puisse être comptabilisé parmi les participants à l’activité.</li><li>Si la valeur est trop élevée, les visiteurs risquent de voir des zones vierges sur votre page web ou des pages vierges si vous utilisez le masquage du contenu pendant une durée prolongée.</li></ul>Pour une meilleure compréhension du temps de réponse de mbox, consultez l’onglet Réseau dans les Outils de développement de votre navigateur. Vous pouvez également utiliser des outils de surveillance des performances web tiers, tels que Catchpoint.<br>**Remarque** : le paramètre [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) garantit que [!DNL Target] n’attend pas trop longtemps la réponse de l’API visiteur. Ce paramètre et le paramètre Expiration de at.js décrit ici n’ont pas d’effet l’un sur l’autre. |
| Prise en charge du navigateur hérité | **Remarque :** L’option Prise en charge du navigateur est disponible dans les versions 0.9.3 d’at.js et antérieures. Cette option a été supprimée de la version 0.9.4 d’at.js. Pour obtenir une liste des navigateurs pris en charge par at.js, voir [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).<br>Les navigateurs hérités sont d’anciens navigateurs qui ne prennent pas entièrement en charge le partage des ressources cross-origin (CORS). Ces navigateurs comprennent Internet Explorer (versions antérieures à la version 11) et Safari (versions 6 et antérieures). Si l’option Prise en charge du navigateur hérité est désactivée, Target ne diffuse pas de contenu ni ne comptabilise de visiteurs dans les rapports sur ces navigateurs. Si cette option est activée, il est recommandé d’effectuer un contrôle qualité sur les anciens navigateurs pour garantir une expérience utilisateur de qualité. |

## Paramètres des codes {#section_D41C905D0F8149949F525C85F2CCFF7F}

| Paramètre | Description |
|--- |--- |
| En-tête de bibliothèque | Ajoutez du code JavaScript personnalisé à inclure au haut de la bibliothèque. |
| Pied de page de bibliothèque | Ajoutez du code JavaScript personnalisé à inclure au bas de la bibliothèque. |

## Téléchargement d’at.js{#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions relatives au téléchargement de la bibliothèque à l’aide de l’interface Target ou de l’API de téléchargement.

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) est la méthode préconisée pour la mise en œuvre de Target et de la bibliothèque at.js. Les informations suivantes ne s’appliquent pas à l’utilisation d’Adobe Launch pour la mise en œuvre de Target.

>[!IMPORTANT]
>
>L’équipe Target gère seulement deux versions d’[!DNL at.js] : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge. Pour en savoir plus sur le contenu de chaque version, voir [Informations détaillées sur les versions d’at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

## Téléchargement du fichier at.js à l’aide de l’interface Target {#section_1F5EE401C2314338910FC57F9592894E}

Pour télécharger [!DNL at.js] depuis l’interface [!DNL Target], procédez comme suit :

1. Cliquez sur **[!UICONTROL Configuration]** &gt; **[!UICONTROL Implémentation]**.
1. Sélectionnez **[!UICONTROL at.js]**.
1. Cliquez sur **[!UICONTROL Télécharger at.js]**.

## Téléchargement d’at.js à l’aide de l’API de téléchargement Target {#section_C0D9D2A9068144708D08526BA5CA10D0}

Pour télécharger [!DNL at.js] à l’aide de l’API, procédez comme suit :

1. Obtenez votre code client.

   Votre code client figure en haut de la page **[!UICONTROL Configuration]** &gt; **[!UICONTROL Implémentation]** **[!UICONTROL Modifier les paramètres de at.js]** de [!DNL Target]l’interface.

1. Obtenez votre numéro d’administrateur.

   Chargez cette URL :

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace `client code` with the client code from Step 1.

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
   https://admin<varname>admin number</varname>>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code </varname>version=<version number>
   ```

   * Replace `admin number` with your admin number.
   * Replace `client code` with the client code from Step 1.
   * Replace `version number` with the desired at.js version number (for example, 2.2).
   >[!IMPORTANT]
   >
   >L’équipe Target gère seulement deux versions d’[!DNL at.js] : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge. Pour en savoir plus sur le contenu de chaque version, voir [Informations détaillées sur les versions d’at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

   Le chargement de cette URL démarre le téléchargement du fichier [!DNL at.js] personnalisé.

## Implémentation d’at.js {#concept_03CFA86973A147839BEB48A06FEE5E5A}

Vous devez implémenter at.js à `<head>` l’élément de chaque page de votre site web.

Une implémentation standard de Target n’utilisant pas de gestionnaire de balises comme [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) ou [Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) ressemble à ceci :

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

* Vous devez utiliser le Doctype HTML5 (`<!doctype html>` par exemple). Les anciens attributs ou ceux qui ne sont pas pris en charge pourraient empêcher Target d’émettre des requêtes.
* Les options de préconnexion et de prérécupération peuvent aider vos pages web à charger plus rapidement. Lors de l’utilisation de ces configurations, assurez-vous de bien remplacer `<client code>` par votre propre code client. Vous pouvez obtenir ce code sur la page **[!UICONTROL Configuration]** &gt; **[!UICONTROL Mise en œuvre]** &gt; **[!UICONTROL Modifier les paramètres at.js]**.
* Si vous possédez une couche de données, l’idéal est d’en définir le plus possible dans la section `<head>`de vos pages, et ce avant le chargement d’at.js. Ce placement permet d’exploiter au maximum ces informations dans Target pour la personnalisation.
* Vous devez définir les fonctions spéciales de Target, telles que `targetPageParams()`, `targetPageParamsAll()`, les fournisseurs de données et `targetGlobalSettings()`, après avoir défini votre couche de données, et avant le chargement d’at.js. Vous pouvez également enregistrer ces fonctions spéciales dans la section [!UICONTROL En-tête de bibliothèque] de la page [!UICONTROL Modifier les paramètres at.js], ou même directement dans la bibliothèque at.js. Pour plus d’informations sur ces fonctions, voir [Fonctions d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* Lorsque vous utilisez des bibliothèques de fonctions JavaScript, comme jQuery, incluez-les avant Target, de façon à pouvoir exploiter leurs syntaxes et leurs méthodes au moment de créer vos expériences Target.
* Incluez at.js dans la section `<head>` de vos pages.

## Suivi des conversions {#task_E85D2F64FEB84201A594F2288FABF053}

La mbox de confirmation de commande enregistre des détails sur les commandes passées sur votre site, puis rend possible la création de rapports en fonction des recettes et des commandes. Elle contribue également aux algorithmes de recommandation, tels que « Les personnes qui ont acheté le produit x ont également acheté le produit y ».

<!-- 

ov/t_create_orderconfirm-page-mbox-atjs.xml

 -->

>[!NOTE]
>
>Remarque : Si les utilisateurs effectuent des achats sur votre site web, il est recommandé de mettre en œuvre une mbox de confirmation de commande, même si vous utilisez Analytics for Target (A4T) pour créer vos rapports.

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