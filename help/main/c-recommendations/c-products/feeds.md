---
keywords: flux de recommandations;flux;SAINT;ftp;csv;classifications;classifications analytics
description: Découvrez comment les flux importent des entités dans  [!DNL Adobe Target] [!DNL Recommendations] à l’aide de fichiers CSV, du format  [!DNL Google Product Search]  flux et  [!DNL Analytics]  classifications de produits.
title: Comment utiliser [!UICONTROL Feeds] dans  [!DNL Target Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: 5a8b4006a2c43c9cac2d22e7663aa21043f98d9a
workflow-type: tm+mt
source-wordcount: '2613'
ht-degree: 35%

---

# Flux

Utilisez des flux pour importer des entités dans [!DNL Adobe Target] [!DNL Recommendations]. Les entités peuvent être envoyées à l’aide de fichiers CSV, du format de flux [!DNL Google Product Search] et de classifications de produits [!DNL Adobe Analytics].

## Présentation des flux {#concept_D1E9C7347C5D4583AA69B02E79607890}

Les flux vous permettent de transmettre des [Entités](/help/main/c-recommendations/c-products/products.md) ou d’enrichir vos données mbox avec des informations qui ne sont pas disponibles sur la page ou dont l’envoi direct à partir de la page n’est pas sécurisé. Par exemple, la marge, le coût des marchandises vendues (COGS), etc.

Les flux vous permettent également de transmettre des informations détaillées sur les articles aux [!DNL Recommendations], telles que l’ID de produit, la catégorie, le nom, le message et d’autres attributs.

Vous pouvez sélectionner les colonnes de votre fichier de classifications de produits [!DNL Target] ou [!DNL Google Product Search] fichier que vous souhaitez envoyer au serveur de [!DNL Recommendations].

Ces éléments de données sur chaque élément peuvent ensuite être utilisés pour :

* Afficher les valeurs dans les conceptions
* Définir des règles d’inclusion de critères
* Trier les éléments dans différentes collections
* Appliquer des exclusions aux recommandations

Les descriptions d’éléments peuvent être transmises à [!DNL Target] à l’aide de flux ou de mbox. Si [!DNL Target] collecte des données à l’aide d’un flux d’entités et d’une mbox, les données les plus récentes l’emportent. En règle générale, les données les plus récentes proviennent d’une mbox, dans la mesure où elles sont consultées plus souvent. Dans les rares cas où l’accès aux données de flux d’entité et de mbox survient au même moment, ce sont les données de cette dernière qui sont utilisées.

La liste [!UICONTROL Feeds] ( **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]**) fournit des informations sur les flux que vous avez créés.

La page [!UICONTROL Feeds] contient les colonnes suivantes :

* **Nom** : nom du flux spécifié lors de la création. Pour modifier le nom d’un flux, vous devez modifier le flux lui-même. Lorsque vous enregistrez le flux avec le nouveau nom, il est actualisé.
* **État** : [état](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0) actuel du flux.
* **Type** : les types incluent [CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA), [[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF) et [classifications Analytics](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A).
* **Éléments** : affiche le nombre d’éléments dans le flux.
* **Planning** : affiche le planning de mise à jour du flux : [!UICONTROL Daily], [!UICONTROL Weekly], [!DNL Every 2 Weeks] ou [!UICONTROL Never].
* **Dernière mise à jour** : affiche la date et l’heure de la dernière mise à jour du flux, ainsi que le nom de la personne qui l’a effectuée.

Cliquez sur l’icône [!UICONTROL Customize Table] ( ![icône Personnaliser le tableau](/help/main/assets/icons/ColumnSetting.svg) ) pour sélectionner ou désélectionner les colonnes à afficher.

Cliquez sur l’icône [!UICONTROL Information] ( ![icône Infos](/help/main/assets/icons/InfoOutline.svg) ) pour afficher une vignette indiquant la date du dernier chargement et l’URL du flux.

Cliquez sur l’icône [!UICONTROL More Actions] ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) pour accéder aux actions suivantes : [!UICONTROL Deactivate], [!DNL Edit], [!UICONTROL Copy] et [!UICONTROL Delete].

>[!IMPORTANT]
>
>Les entités et attributs d’entité chargés expirent après 61 jours. Autrement dit :
>
>* Votre flux doit s’exécuter au moins une fois par mois pour vous assurer que le contenu de votre catalogue n’expire pas.
>* La suppression d’un élément de votre fichier de flux ne le supprime pas de votre catalogue. Pour supprimer l’élément du catalogue, supprimez manuellement l’élément via l’interface utilisateur ou l’API [!DNL Target]. Vous pouvez également modifier les attributs article (tels que le stock) pour vous assurer que l&#39;article est exclu de la prise en compte.

## Types de Source

Les entités peuvent être envoyées à l’aide de fichiers CSV, du format de flux [!DNL Google Product Search] et de classifications de produits [!DNL Adobe Analytics].

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

Vous pouvez créer un fichier .csv à l’aide du format de téléchargement CSV propriétaire [!DNL Adobe]. Le fichier contient des informations d’affichage sur les attributs personnalisés et réservés pour vos produits. Pour charger des attributs spécifiques à votre mise en œuvre, remplacez `CustomN` sur la ligne d’en-tête par le nom de l’attribut que vous souhaitez utiliser. Dans l’exemple ci-dessous, `entity.Custom1` a été remplacé par : `entity.availability`. Vous pouvez ensuite charger le fichier par lot sur le serveur [!DNL Recommendations].

L’utilisation du format .csv présente les avantages suivants par rapport au format de flux [!DNL Google] :

* Le format .csv ne nécessite pas de mappages de champs.
* Le format .csv prend en charge les attributs à plusieurs valeurs (voir l’exemple ci-dessous).
* Le format .csv prend en charge jusqu’à 100 attributs personnalisés. Si vous avez besoin de plus de 100 attributs personnalisés, vous pouvez créer un deuxième fichier de flux comportant un ensemble différent d’attributs personnalisés spécifiés.

Utilisez la méthode de chargement en masse pour envoyer des informations d’affichage si votre page ne contient pas de mbox ou si vous souhaitez compléter vos informations d’affichage avec des éléments qui ne sont pas disponibles sur votre site. Par exemple, vous pouvez envoyer au module les informations du stock qui ne sont pas publiées sur votre site.

Toutes les données téléchargées à l’aide du fichier .csv, du flux de produit Google ou du flux de classification de produit [!DNL Analytics] remplacent la valeur d’attribut d’entité existante dans la base de données. Si vous envoyez des informations de prix via des requêtes de mbox et que vous envoyez ensuite des valeurs de prix différentes dans le fichier, les valeurs du fichier remplacent les valeurs définies avec la requête de mbox. Une exception à cette règle est l’attribut d’entité `categoryId` où les valeurs de catégorie sont ajoutées au lieu d’être remplacées jusqu’à une limite de 250 caractères.

>[!IMPORTANT]
>
>Dans votre fichier .csv, ne placez pas les valeurs entre guillemets doubles ( &quot; ), sauf si cela est intentionnel. Si vous placez des valeurs entre guillemets doubles, vous devez leur appliquer une séquence d&#39;échappement en les plaçant entre guillemets doubles. Si les guillemets doubles ne sont pas précédés d’un caractère d’échappement, le flux de recommandations ne se charge pas correctement.

Par exemple, la syntaxe suivante est incorrecte :

```
"Apples "Bananas" Grapes"",
```

La syntaxe suivante est correcte :

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>Vous ne pouvez pas remplacer une valeur existante par une valeur vierge. Transmettez une autre valeur à sa place pour remplacer la valeur existante. Dans le cas d’un prix de vente, une solution courante consiste à transmettre un « NULL » réel ou un autre message. Vous pouvez alors écrire une règle de modèle afin d’exclure des éléments comportant cette valeur.

Le produit est disponible dans l’interface d’administration environ deux heures après le chargement de son entité.

Voici un exemple de code pour un fichier .csv :

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

Le type de flux [!DNL Google Product Search] utilise le format [!DNL Google]. Ce format est différent du format de chargement CSV propriétaire [!DNL Adobe].

Si vous disposez d’un [!DNL Google Product Feed] existant, vous pouvez l’utiliser comme fichier d’importation.

>[!NOTE]
>
>Il n’est pas nécessaire d’utiliser les données [!DNL Google]. [!DNL Recommendations] utilise le même format que [!DNL Google]. Vous pouvez utiliser cette méthode pour envoyer les données dont vous disposez et utiliser les fonctions de planification disponibles. Cependant, vous devez conserver les noms d’attributs prédéfinis [!DNL Google] lors de la configuration du fichier.

La plupart des détaillants chargent des produits sur [!DNL Google]. Ainsi, lorsqu’un visiteur utilise la recherche de produits [!DNL Google], ses produits s’affichent. [!DNL Recommendations] suit exactement la spécification [!DNL Google] pour les flux d’entité. Les flux d’entité peuvent être envoyés à [!DNL Recommendations] via .xml, .txt ou .tsv et peuvent utiliser les attributs [ définis par Google](https://support.google.com/merchants/answer/188494?hl=en&topic=2473824&ctx=topic#US). Vous pouvez rechercher les résultats dans les [[!DNL Google] pages d’achat](https://www.google.com/prdhp).

>[!NOTE]
>
>La méthode POST doit être autorisée sur le serveur hébergeant le contenu du flux [!DNL Google].

Comme [!DNL Recommendations] utilisateurs configurent déjà des flux .xml ou .txt à envoyer aux [!DNL Google] via une URL ou un FTP, les flux d’entités acceptent ces données de produit et les utilisent pour créer le catalogue de recommandations. Indiquez où ce flux existe et où le serveur de Recommandations récupère les données.

Si vous utilisez [!DNL Google Product Search] pour le chargement du flux d’entités, une mbox de page produit doit toujours figurer sur la page si vous souhaitez y afficher des recommandations ou effectuer le suivi des consultations de produit pour la diffusion de l’algorithme en fonction des vues.

Les flux [!DNL Google] ne prennent pas en charge les valeurs multiples pour un attribut personnalisé.

Le flux s’exécute au moment de l’enregistrement et de l’activation. Il s’exécute au moment où vous enregistrez le flux, puis tous les jours une heure plus tard.

Voici un exemple de code pour un fichier .xml de flux [!DNL Google Product Search] :

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

Voici un exemple de code pour un fichier .tsv de flux [!DNL Google Product Search] :

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### Classifications de produit [!DNL Analytics] {#section_79E430D2C75443BEBC9AA0916A337E0A}

La classification de produit [!DNL Adobe Analytics] est la seule classification disponible pour les recommandations. Pour plus d’informations sur ce fichier de classification, voir [À propos des classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=fr) dans le guide *Composants Analytics*. Il est possible que toutes les informations dont vous avez besoin pour les recommandations ne soient pas disponibles dans votre implémentation actuelle. Par conséquent, suivez ce guide d’utilisation si vous souhaitez l’ajouter à votre fichier de classifications.

>[!IMPORTANT]
>
>Avant d’importer des données d’entité dans des [!DNL Recommendations] à l’aide de classifications de produits [!DNL Analytics], sachez que ce n’est pas la méthode recommandée.
>
> Tenez compte des restrictions suivantes :
>
>* Les mises à jour des attributs d’entité exigent un délai supplémentaire de 24 heures.
>* [!DNL Target] ne prend en charge que les [!UICONTROL Product Classifications]. Le SKU du produit [!DNL Analytics] doit correspondre au même niveau que le [!DNL Recommendations] `entity.id`. Les classifications de [!DNL Analytics] personnalisées peuvent être conçues à l’aide de [!UICONTROL Adobe Consulting Services]. Contactez votre gestionnaire de compte pour toute question.

## Création d’un flux {#steps}

Créez un flux pour insérer des informations sur vos produits ou services dans les [!DNL Recommendations].

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**.

1. Entrez un nom explicite pour votre flux.
1. Sélectionnez un **[!UICONTROL Source Type]**.

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   Pour plus d’informations sur les types de flux [!UICONTROL CSV] et [!UICONTROL Google Product Feed], voir [Présentation des flux](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890). Vous pouvez également [télécharger un guide de modèle CSV](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) pour vous aider à formater correctement le flux.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL CSV]** ou **[!UICONTROL Google Product Feed]**, indiquez l’emplacement où le flux est accessible.

   * **FTP** : si vous sélectionnez FTP, fournissez les informations du serveur FTP, les informations d’identification de connexion, le nom du fichier et le répertoire FTP. Vous pouvez utiliser le protocole FTP avec SSL (FTPS) pour des chargements plus sécurisés.

     Paramètres du serveur FTP pris en charge :

      * FTP et FTPS doivent être configurés pour utiliser le FTP passif.
      * Pour FTPS, configurez le serveur pour accepter les connexions FTPS explicites.
      * SFTP n’est pas pris en charge.
      * Vous pouvez spécifier manuellement un port sur lequel lancer la connexion (par exemple, `ftp://ftp.yoursite.com:2121`). Si vous n’indiquez pas de port, le port FTP ou FTPS par défaut est utilisé.

   * **URL** : si vous sélectionnez [!UICONTROL URL], spécifiez l’URL.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Analytics Classifications]**, choisissez la suite de rapports dans la liste déroulante.

1. Cliquez sur la flèche **[!UICONTROL Next]** pour afficher les options [!UICONTROL Schedule].

1. Choisissez une option de mise à jour :

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never] : ne planifiez pas de mise à jour. Sélectionnez cette option si vous voulez empêcher l’exécution de ce flux.

1. Indiquez l’heure à laquelle vous souhaitez que votre flux s’exécute.

   Cette option se base sur le fuseau horaire utilisé par votre navigateur. Si vous voulez utiliser l’heure d’un fuseau horaire différent, vous devez calculer cette heure selon votre fuseau horaire.

1. Cliquez sur la flèche **[!UICONTROL Next]** pour afficher les options de [!UICONTROL Mapping], puis indiquez comment vous souhaitez mapper vos données aux définitions de [!DNL Target].

1. (Facultatif) Si vous souhaitez que les flux appartiennent à un environnement (un groupe d’hôtes), sélectionnez le groupe d’hôtes en question.

   Par défaut, le flux appartient à tous les groupes d’hôtes. Cela garantit que les éléments du flux sont disponibles dans tous les environnements. Pour plus d’informations, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

1. Cliquez sur **[!UICONTROL Save]**.

Une fois que vous avez créé ou modifié un flux, il s’exécute immédiatement. Le flux est ensuite mis à jour en fonction des paramètres que vous avez définis. Il faut un certain temps pour que l&#39;information soit disponible. Le flux doit tout d’abord être synchronisé, puis traité et indexé pour pouvoir être publié et rendu disponible. Le statut actuel apparaît sous [Statut du flux](/help/main/c-recommendations/c-products/feeds.md#status) dans la liste des [!UICONTROL Feeds]. Vous pouvez fermer [!DNL Target] avant que le processus soit terminé et ce dernier se poursuit.

Lorsque l’indexation est en cours, les produits et les en-têtes du flux apparaissent avant que les valeurs individuelles aient été indexées. Vous pouvez ainsi rechercher et afficher des produits afin de créer des collections, des exclusions, des conceptions et des activités avant la fin de l’indexation.

Lorsque l’état indique « Succès », cela signifie que le fichier a été trouvé et analysé correctement. Les informations ne sont pas disponibles pour une utilisation dans les [!DNL Recommendations] tant que le fichier n’a pas été indexé, ce qui peut prendre du temps, selon la taille du fichier. Si le processus échoue, cela signifie que le fichier n’a pas été trouvé. Par exemple, vous avez utilisé une URL incorrecte, vos informations FTP étaient incorrectes ou une erreur d’analyse s’est produite.

## États de flux et indicateurs {#concept_E475986720D1400999868B3DFD14A7A0}

Information à propos des états possibles des flux et leurs indicateurs.

### États du flux {#status}

Un flux peut avoir les états suivants :

| État | Description |
|--- |--- |
| [!UICONTROL Syncing] | Les détails de la configuration du flux sont enregistrés dans [!DNL Target]. |
| [!UICONTROL Sync Failed] | Impossible d’enregistrer les détails de la configuration de flux dans [!DNL Target]. Essayez à nouveau. |
| [!UICONTROL No Feed Run] | Vous avez créé un flux mais il n’a pas été planifié (la fréquence est définie sur Jamais). |
| Planifié à *date et heure* | Le flux n’a pas été exécuté, mais il doit s’exécuter à la date et à l’heure spécifiées. |
| [!UICONTROL Waiting for Download] | [!DNL Target] se prépare à télécharger le fichier de flux. |
| [!UICONTROL Downloading Feed File] | [!DNL Target] télécharge le fichier de flux. |
| [!UICONTROL Importing Items] | [!DNL Target] importe des éléments à partir du fichier de flux. |
| Flux importé avec succès à l’*heure* | [!DNL Target] a importé le fichier de flux dans son système de diffusion de contenu. Des modifications ont été apportées aux attributs d’élément dans le système de diffusion de contenu et seront bientôt répercutées dans les recommandations diffusées. Si les modifications attendues ne s’affichent pas, réessayez et actualisez la page contenant les recommandations.<br>Remarques :<ul><li>Si les modifications apportées aux attributs d’un élément entraînent l’exclusion d’un élément des recommandations, l’exclusion est immédiatement répercutée. Si un élément vient d’être ajouté ou si des modifications sont apportées à des attributs, un élément n’est *plus* exclu des recommandations. Il n’est reflété que lors de la prochaine mise à jour de l’algorithme, qui se produit dans les 24 heures.</li><li>Lorsque ce statut s’affiche, les mises à jour peuvent ne pas encore être reflétées dans l’interface utilisateur de [!UICONTROL Catalog Search]. Un statut distinct est répertorié dans [!UICONTROL Catalog Search] indiquant la dernière fois que le catalogue consultable a été mis à jour.</li></ul> |
| Échec de l’importation partielle | Auparavant, lorsque toutes les lignes n’étaient pas chargées, le flux était toujours marqué comme réussi. Cela crée une fausse impression que toutes les lignes ont été chargées lorsque le flux s’affiche avec succès.<P>Voici un scénario expliquant pourquoi vous pouvez rencontrer une importation de flux partielle :<ul><li>Vous avez chargé un fichier de flux pour l’environnement de production, par exemple 100 lignes.</li><li>Le flux a exécuté et chargé 80 de ces lignes et en a ignoré 20 en raison d’une mise en forme incorrecte, d’un champ contenant plus de caractères, etc.</li><li>Le flux a été marqué comme réussi dans l’interface utilisateur, ce qui vous donne l’impression que les 100 lignes ont toutes été chargées.</li><li>Vous attendez certains de ces 20 produits dans la livraison d&#39;une activité, mais ce n&#39;est pas le cas.</li><li> Vous êtes perplexe à ce stade, car vous avez chargé le flux qui contient les détails du produit en question. Vous ne le voyez pas sur le serveur principal lorsque vous effectuez une requête via l’API d’entité, qui vous indique qu’il ne se trouve pas sur le serveur principal.</li></ul>Pour supprimer cette confusion, le message est amélioré pour indiquer exactement ce qui s’est passé avec le flux. Au lieu de le marquer comme une réussite, il est maintenant marqué comme un échec d’importation partiel. |
| [!UICONTROL Failed to Index] | L’opération d’index a échoué. Essayez à nouveau. |
| [!UICONTROL Server Not Found] | Les destinations FTP ou URL sont incorrectes ou inaccessibles. |

Pour mettre à jour un flux (par exemple, pour apporter des modifications à votre configuration de flux ou fichier de flux), ouvrez le flux, apportez les modifications souhaitées, puis cliquez sur **[!UICONTROL Save]**.

>[!IMPORTANT]
>
>Le délai d’expiration des entités téléchargées est de 61 jours. Cela signifie que votre fichier de flux doit être téléchargé au moins tous les 60 jours pour éviter toute interruption de vos activités de recommandations. Si un élément n’est pas inclus dans un fichier de flux (ou une autre méthode de mise à jour d’entité) au moins une fois tous les 60 jours, [!DNL Target] en déduit que l’élément n’est plus pertinent et le supprime du catalogue.

### Indicateurs de l’état du flux {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

Les indicateurs de statut des flux suivants s’affichent dans la colonne [!UICONTROL Status] :

| Indicateur d’état | Description |
|--- |--- |
| Indicateur d’état vert | Une fois l’indexation du flux terminée, celui-ci est marqué d’un point vert pour indiquer que son état est Succès. |
| Indicateur d’état jaune | Lorsqu’un index de flux ou un flux est retardé de 25 % par rapport à la fréquence du flux, un point d’état jaune s’affiche. Par exemple, un point jaune s’affiche pour qu’un jeu de flux s’exécute tous les jours si l’index ne s’est pas terminé six heures après l’heure planifiée. Remarque : une fois que le statut du flux est « En attente de la file d’attente de l’index », les valeurs nouvellement mises à jour sont disponibles dans la diffusion et le traitement des critères. |
| Indicateur d’état blanc | Lorsqu’un flux n’est pas planifié, un point d’état blanc indique que le flux n’a pas encore été exécuté. |
| Indicateur d’état rouge | Si le flux ne parvient pas à charger les données sur le serveur, un indicateur de statut rouge s’affiche. |

Prenons les exemples suivants :

**Exemple 1 :**

* Premier jour : processus quotidiens d’alimentation à 9 h (heure du Pacifique).
* 2e jour : il est 15 h 30 et le flux n’a pas été exécuté depuis hier à 9 h 00.

L’état doit être jaune car l’index aurait dû s’exécuter il y a environ 6,5 heures. 6,5 heures +24 = 127 % de l’intervalle d’exécution du flux.

**Exemple 2 :**

* 1er janvier : processus mensuels d&#39;alimentation à 9 h (heure du Pacifique)
* 3 février : il est 10h00 et le flux n&#39;a pas fonctionné depuis un mois, un jour et une heure auparavant.

L’état doit être jaune car l’index aurait dû s’exécuter il y a environ un jour et une heure. Même si cela représente seulement (31+(1/25))/30 = 1,03 % du paramètre de fréquence, le délai d’un jour maximum a été dépassé.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Présentation des flux dans Recommendations (3:01) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo traite des sujets suivants :

* Comprendre l’objectif des flux
* Comprendre la valeur des flux

>[!VIDEO](https://video.tv.adobe.com/v/33898?captions=fre_fr)

### Créer un flux (6:44) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Configurer un flux
* Déterminer le type de flux à utiliser

>[!VIDEO](https://video.tv.adobe.com/v/33897?captions=fre_fr)
