---
keywords: flux de recommandations;flux;SAINT;ftp;sftp;csv;classifications;classifications analytics
description: Découvrez comment les flux importent des entités dans [!DNL Adobe Target] [!DNL Recommendations] à l’aide de fichiers CSV, du format de flux [!DNL Google Product Search] et de classifications de produits [!DNL Analytics].
title: Comment utiliser les [!UICONTROL flux] dans [!DNL Target Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
TQID: 'https://experienceleague.adobe.com/lXXX8XEXGtt1DDMI63Ck4AbCGDjzkxs60oW2nEnc0Go'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 22eb14463a76adc797e57420cac0f646be3d3f00
workflow-type: tm+mt
source-wordcount: '2810'
ht-degree: 25%
---
# Flux {#feeds}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment les flux importent des entités dans [!DNL Adobe Target Recommendations], quels types de sources sont disponibles et comment créer et surveiller un flux.

>[!ENDSHADEBOX]

Utilisez les flux pour importer des entités dans [!DNL Adobe Target Recommendations]. Les entités peuvent être envoyées à l’aide de fichiers CSV, du format de flux [!DNL Google Product Search] et de classifications de produits [!DNL Adobe Analytics].

## Présentation des flux {#concept_D1E9C7347C5D4583AA69B02E79607890}

Les flux vous permettent de transmettre [entités](/help/main/c-recommendations/c-products/products.md) ou d’enrichir vos données mbox avec des informations qui ne sont pas disponibles sur la page ou dont l’envoi direct à partir de la page n’est pas sécurisé. Par exemple, la marge, le coût des marchandises vendues (COGS), etc. Les flux vous permettent également de transmettre des informations détaillées sur les articles dans [!DNL Recommendations], telles que l’ID de produit, la catégorie, le nom, le message et d’autres attributs.

Vous pouvez sélectionner les colonnes de votre fichier de classifications de produits [!DNL Target] ou de votre fichier [!DNL Google Product Search] à envoyer au serveur [!DNL Recommendations].

Ces éléments de données sur chaque élément peuvent ensuite être utilisés pour :

* Afficher les valeurs dans les conceptions
* Définir des règles d’inclusion de critères
* Trier les éléments dans différentes collections
* Appliquer des exclusions aux recommandations

Les descriptions d’élément peuvent être transmises à [!DNL Target] à l’aide de flux ou de mbox. Si [!DNL Target] collecte des données à l’aide d’un flux d’entités et d’une mbox, les données les plus récentes l’emportent. En règle générale, les données les plus récentes proviennent d’une mbox, dans la mesure où elles sont consultées plus souvent. Dans le cas rare où les données du flux d’entités et les données mbox arrivent en même temps, les données mbox sont utilisées.

Les entités et attributs d’entité chargés expirent après 61 jours. Autrement dit :

* Votre flux doit s’exécuter au moins une fois par mois pour vous assurer que le contenu de votre catalogue n’expire pas.

* La suppression d’un élément de votre fichier de flux ne le supprime pas de votre catalogue. Pour supprimer l’élément du catalogue, supprimez manuellement l’élément via l’interface utilisateur ou l’API [!DNL Target]. Vous pouvez également modifier les attributs article (tels que le stock) pour vous assurer que l&#39;article est exclu de la prise en compte.

* Chargez votre fichier de flux au moins tous les 60 jours pour éviter d’interrompre vos activités de recommandations. Si un élément n&#39;est pas inclus dans un fichier de flux (ou une autre méthode de mise à jour d&#39;entité) au moins une fois tous les 60 jours, [!DNL Target] en déduit que l&#39;élément n&#39;est plus pertinent et le supprime du catalogue.

### Liste des flux

La liste [!UICONTROL Flux] (**[!UICONTROL Recommendations]** > **[!UICONTROL Flux]**) fournit des informations sur les flux que vous avez créés. Il contient les colonnes suivantes :

| Colonne | Description |
|---|---|
| **Nom** | Nom du flux spécifié lors de la création. Pour modifier le nom d’un flux, vous devez modifier le flux lui-même. Lorsque vous enregistrez le flux avec le nouveau nom, il est actualisé. |
| **État** | État actuel du flux [1}.](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0) |
| **Type** | Les types comprennent les [classifications CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA), [[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF) et [Analytics](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A). |
| **Éléments** | Affiche le nombre d’éléments dans le flux. |
| **Planification** | Affiche le planning de mise à jour du flux : **[!UICONTROL Quotidien]**, **[!UICONTROL Hebdomadaire]**, **[!DNL Every 2 Weeks]** ou **[!UICONTROL Jamais]**. |
| **Dernière Mise À Jour** | Affiche la date et l’heure de la dernière mise à jour du flux, ainsi que le nom de la personne qui l’a mise à jour. |

* Cliquez sur l’icône **[!UICONTROL Personnaliser le tableau]** ( ![Icône Personnaliser le tableau](/help/main/assets/icons/ColumnSetting.svg) ) pour sélectionner ou désélectionner les colonnes à afficher.
* Cliquez sur l’icône **[!UICONTROL Informations]** ( ![Icône Infos](/help/main/assets/icons/InfoOutline.svg) ) pour afficher une vignette qui affiche la date du dernier chargement et l’URL du flux.
* Cliquez sur l’icône **[!UICONTROL Autres actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) pour accéder aux actions suivantes : **[!UICONTROL Désactiver]**, **[!DNL Edit]**, **[!UICONTROL Copier]** et **[!UICONTROL Supprimer]**.

## Types de Source {#source-types}

Les sections suivantes décrivent les types de sources que vous pouvez utiliser pour envoyer des entités.

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

Vous pouvez créer un fichier .csv à l’aide du format de chargement CSV propriétaire [!DNL Adobe]. Le fichier contient des informations d’affichage sur les attributs personnalisés et réservés pour vos produits. Pour charger des attributs spécifiques à votre mise en œuvre, remplacez `CustomN` sur la ligne d’en-tête par le nom de l’attribut que vous souhaitez utiliser. Dans l’exemple ci-dessous, `entity.Custom1` a été remplacé par : `entity.availability`. Vous pouvez ensuite charger le fichier par lot sur le serveur [!DNL Recommendations].

L’utilisation du format .csv présente les avantages suivants par rapport au format de flux [!DNL Google] :

* Le format .csv ne nécessite pas de mappages de champs.
* Le format .csv prend en charge les attributs à plusieurs valeurs (voir l’exemple ci-dessous).
* Le format .csv prend en charge jusqu’à 100 attributs personnalisés. Si vous avez besoin de plus de 100 attributs personnalisés, vous pouvez créer un deuxième fichier de flux comportant un ensemble différent d’attributs personnalisés spécifiés.

Utilisez la méthode de chargement en masse pour envoyer des informations d’affichage si votre page ne contient pas de mbox ou si vous souhaitez compléter vos informations d’affichage avec des éléments qui ne sont pas disponibles sur votre site. Par exemple, vous pouvez envoyer au module les informations du stock qui ne sont pas publiées sur votre site.

Toutes les données chargées à l’aide du fichier .csv, du flux de produits Google ou du flux de classification de produits [!DNL Analytics] remplacent la valeur d’attribut d’entité existante dans la base de données. Si vous envoyez des informations de prix via des requêtes de mbox et que vous envoyez ensuite des valeurs de prix différentes dans le fichier, les valeurs du fichier remplacent les valeurs définies avec la requête de mbox. Une exception à cette règle est l’attribut d’entité `categoryId` où les valeurs de catégorie sont ajoutées au lieu d’être remplacées jusqu’à une limite de 250 caractères.

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

Notez que vous ne pouvez pas remplacer une valeur existante par une valeur vide. Transmettez une autre valeur à sa place pour remplacer la valeur existante. Dans le cas d’un prix de vente, une solution courante consiste à transmettre un « NULL » réel ou un autre message. Vous pouvez alors écrire une règle de modèle afin d’exclure des éléments comportant cette valeur.

Le produit est disponible dans l’interface d’administration environ deux heures après le chargement de son entité.

+++ Exemple de fichier .csv

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

+++

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

>[!NOTE]
>
>Vous n&#39;avez pas besoin d&#39;envoyer vos données à [!DNL Google]. Vous pouvez importer vos propres données et planifier des mises à jour, à condition que le fichier utilise les noms d&#39;attributs [!DNL Google] prédéfinis.

Le type de flux [!DNL Google Product Search] utilise le format [!DNL Google] plutôt que le format CSV propriétaire [!DNL Adobe]. Vous pouvez réutiliser un [!DNL Google Product Feed] existant pour importer des données de produit dans [!DNL Recommendations].

[!DNL Recommendations] accepte les fichiers .xml, .txt et .tsv conformes à la spécification de flux [!DNL Google] et utilisant les [ attributs définis par Google](https://support.google.com/merchants/answer/188494?hl=en&topic=2473824&ctx=topic#US). Indiquez l’URL ou l’emplacement FTP du flux afin que le serveur [!DNL Recommendations] puisse récupérer le fichier et créer votre catalogue.

Notez que le serveur hébergeant le flux [!DNL Google] doit autoriser la méthode POST.

Gardez à l’esprit les exigences et restrictions suivantes :

* Une mbox de page produit est toujours nécessaire pour afficher des recommandations sur cette page ou effectuer le suivi des consultations de produits pour les algorithmes basés sur les vues.
* [!DNL Google] flux ne prennent pas en charge les valeurs multiples pour un attribut personnalisé.

Le flux s’exécute lorsque vous l’enregistrez et l’activez, puis quotidiennement une heure plus tard que l’heure d’exécution initiale.

+++ Exemple de flux [!DNL Google Product Search] au format .xml

```xml
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

+++

+++ Exemple de flux [!DNL Google Product Search] au format .tsv

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

+++

### [!DNL Analytics] classifications de produits {#section_79E430D2C75443BEBC9AA0916A337E0A}

La classification de produit [!DNL Adobe Analytics] est la seule classification disponible pour les recommandations. Pour plus d’informations sur ce fichier de classification, voir [À propos des classifications](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html) dans le guide *Composants Analytics*. Il est possible que toutes les informations dont vous avez besoin pour les recommandations ne soient pas disponibles dans votre implémentation actuelle. Par conséquent, suivez ce guide d’utilisation si vous souhaitez l’ajouter à votre fichier de classifications.

>[!IMPORTANT]
>
>Avant d&#39;importer des données d&#39;entité dans [!DNL Recommendations] à l&#39;aide de classifications de produits [!DNL Analytics], sachez que ce n&#39;est pas la méthode préférée.
>
> Tenez compte des restrictions suivantes :
>
>* Les mises à jour des attributs d’entité exigent un délai supplémentaire de 24 heures.
>* [!DNL Target] prend uniquement en charge **[!UICONTROL classifications de produits]**. Le SKU du produit [!DNL Analytics] doit correspondre au même niveau que le [!DNL Recommendations] `entity.id`. Les classifications personnalisées [!DNL Analytics] peuvent être créées à l’aide des **[!UICONTROL services Adobe Consulting]**. Contactez votre gestionnaire de compte pour toute question.

## Créer un flux {#steps}

Créez un flux pour insérer des informations sur vos produits ou services dans les [!DNL Recommendations].

La source détermine où [!DNL Recommendations] récupère les données d&#39;entité qui créent votre catalogue.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Flux]** > **[!UICONTROL Créer un flux]**.

   ![Créer une page de flux](../assets/feeds_1.png)

1. Entrez un nom explicite pour votre flux.

1. Sélectionnez un **[!UICONTROL type Source]**.

   * **[!UICONTROL CSV]**
   * **[!UICONTROL Flux de produits Google]**
   * **[!UICONTROL Classifications Analytics]**

   Pour plus d’informations sur les types de flux **[!UICONTROL CSV]** et **[!UICONTROL Google]**, voir [Types de Source](#source-types). Vous pouvez également [télécharger un guide de modèle CSV](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) pour vous aider à formater correctement le flux.

   ![Créer une page de flux](../assets/feeds_2.png)

1. (Sous condition) Si vous avez sélectionné **[!UICONTROL CSV]** ou **[!UICONTROL Flux de produit Google]**, indiquez l’emplacement où le flux est accessible.

   * **FTP** : si vous sélectionnez FTP, fournissez les informations du serveur FTP, les informations d’identification de connexion, le nom du fichier et le répertoire FTP. Vous pouvez utiliser le protocole FTP avec SSL (FTPS) pour des chargements plus sécurisés.

     +++ Paramètres du serveur FTP pris en charge

     * FTP et FTPS doivent être configurés pour utiliser le FTP passif.
     * Pour FTPS, configurez le serveur pour accepter les connexions FTPS explicites.
     * Vous pouvez spécifier manuellement un port sur lequel lancer la connexion (par exemple, `ftp://ftp.yoursite.com:2121`). Si vous n’indiquez pas de port, le port FTP ou FTPS par défaut est utilisé.

     +++

   * **SFTP** : saisissez le nom d’hôte ou l’adresse IP de votre serveur SFTP, le port (22 par défaut), le nom d’utilisateur, le répertoire et le nom de fichier. Pour l’authentification, fournissez un mot de passe, une clé privée SSH, ou les deux.

     +++ Paramètres et limitations du serveur SFTP pris en charge

     * L&#39;authentification utilise un mot de passe, une clé privée SSH ou les deux. Au moins un est requis.
     * Le client génère et est propriétaire de la paire de clés. Installez la clé publique dans le fichier `authorized_keys` de l’utilisateur SFTP, puis collez la clé privée dans Target en tant que texte PEM. Les types de clés acceptés sont RSA, Ed25519 et ECDSA, au format PEM (`-----BEGIN RSA PRIVATE KEY-----`), PKCS#8 (`-----BEGIN PRIVATE KEY-----`) ou OpenSSH (`-----BEGIN OPENSSH PRIVATE KEY-----`).
     * Les clés privées protégées par une phrase secrète ne sont pas prises en charge, un flux ne peut pas être enregistré avec une clé privée.
     * Target stocke la clé privée chiffrée et ne l’affiche plus. Pour le faire pivoter, modifiez le flux et saisissez la nouvelle clé.
     * Entrez un nom d&#39;hôte ou une adresse IP nu, sans préfixe, port ou chemin `sftp://`. Utilisez le champ Port pour un port autre que le port par défaut.
     * La clé d’hôte du serveur est acceptée lors de la première connexion. Aucun échange d’empreintes digitales avec Adobe n’est nécessaire.
     * Le protocole SFTP est disponible dans l’interface de Target et l’API Recommendations, mais pas dans l’interface d’administration Recommendations Classic héritée. Adobe n’héberge pas de point d’entrée SFTP, utilisez un serveur hébergé par le client.
     * Le serveur SFTP doit être accessible à partir d’Internet et autoriser les connexions entrantes à partir des adresses de téléchargement Adobe Target.

     +++

   * **URL** : si vous sélectionnez **[!UICONTROL URL]**, spécifiez l’URL.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Classifications Analytics]**, choisissez la suite de rapports dans la liste déroulante.

1. Cliquez sur la flèche **[!UICONTROL Suivant]** pour afficher les options **[!UICONTROL Planifier]** et sélectionnez une option de mise à jour :

   * **[!UICONTROL Quotidienne]**
   * **[!UICONTROL Hebdomadaire]**
   * **[!UICONTROL Toutes Les 2 Semaines]**
   * **[!UICONTROL Jamais]** : ne planifiez pas de mise à jour. Sélectionnez cette option si vous voulez empêcher l’exécution de ce flux.

   ![Créer une page de flux](../assets/feeds_3.png)

1. Indiquez l’heure à laquelle vous souhaitez que votre flux s’exécute.

   Cette option se base sur le fuseau horaire utilisé par votre navigateur. Si vous voulez utiliser l’heure d’un fuseau horaire différent, vous devez calculer cette heure selon votre fuseau horaire.

1. Cliquez sur la flèche **[!UICONTROL Suivant]** pour afficher les options **[!UICONTROL Mappage]**, puis indiquez comment vous souhaitez mapper vos données aux définitions [!DNL Target].

   ![Créer une page de flux](../assets/feeds_4.png)

1. (Facultatif) Si vous souhaitez que les flux appartiennent à un environnement (un groupe d’hôtes), sélectionnez le groupe d’hôtes en question.

   Par défaut, le flux appartient à tous les groupes d’hôtes. Cela garantit que les éléments du flux sont disponibles dans tous les environnements. Pour plus d’informations, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Une fois que vous avez créé ou modifié un flux, il s’exécute immédiatement, puis est mis à jour en fonction de vos paramètres. Le flux doit se synchroniser, être traité et indexer avant que ses données ne soient disponibles. Le traitement se poursuit même si vous fermez [!DNL Target], et vous pouvez suivre la progression dans la liste **[!UICONTROL Flux]** avec le [statut de flux](/help/main/c-recommendations/c-products/feeds.md#status).

Pendant l’indexation, les produits et les en-têtes de flux apparaissent avant les valeurs individuelles. Vous pouvez donc déjà rechercher des produits et créer des collections, des exclusions, des conceptions et des activités.

Le statut « Succès » signifie que le fichier a été trouvé et analysé correctement. Ses données ne sont disponibles qu’après l’indexation, qui prend plus de temps pour les fichiers plus volumineux. Un échec peut provenir d’une URL ou d’informations FTP incorrecte, d’un fichier manquant ou d’une erreur d’analyse.

## Statuts et indicateurs des flux {#concept_E475986720D1400999868B3DFD14A7A0}

Cette section décrit les statuts de flux possibles et leurs indicateurs.

### Statuts des flux {#status}

Un flux peut avoir les états suivants :

| État | Description |
|--- |--- |
| **[!UICONTROL Synchronisation]** | Les détails de la configuration du flux sont en cours d’enregistrement dans [!DNL Target]. |
| **[!UICONTROL Échec De La Synchronisation]** | Impossible d&#39;enregistrer les détails de configuration du flux dans [!DNL Target]. Essayez à nouveau. |
| **[!UICONTROL Aucune Exécution De Flux]** | Vous avez créé un flux mais il n’a pas été planifié (la fréquence est définie sur Jamais). |
| Planifié à *date et heure* | Le flux n’a pas été exécuté, mais il doit s’exécuter à la date et à l’heure spécifiées. |
| **[!UICONTROL En attente de téléchargement]** | [!DNL Target] se prépare à télécharger le fichier de flux. |
| **[!UICONTROL Téléchargement Du Fichier De Flux]** | [!DNL Target] télécharge le fichier de flux. |
| **[!UICONTROL Importation D&#39;Éléments]** | [!DNL Target] importe des éléments à partir du fichier de flux. |
| Flux importé avec succès à l’*heure* | [!DNL Target] a importé le fichier de flux dans son système de diffusion de contenu. Des modifications ont été apportées aux attributs d’élément dans le système de diffusion de contenu et seront bientôt répercutées dans les recommandations diffusées. Si vous ne voyez pas les modifications attendues, réessayez et actualisez la page contenant les recommandations.<br>Remarques :<ul><li>Si les modifications apportées aux attributs d’un élément entraînent l’exclusion d’un élément des recommandations, l’exclusion est immédiatement répercutée. Si un élément vient d’être ajouté ou si des modifications sont apportées aux attributs, un élément n’est *plus exclu* des recommandations, il n’est pas reflété avant la prochaine mise à jour de l’algorithme, qui se produit dans les 24 heures.</li><li>Lorsque ce statut s’affiche, les mises à jour peuvent ne pas encore être reflétées dans l’interface utilisateur de la **[!UICONTROL recherche catalogue]**. Un statut distinct est répertorié dans **[!UICONTROL Recherche catalogue]** indiquant la dernière fois que le catalogue consultable a été mis à jour.</li></ul> |
| Échec de l’importation partielle | Certaines lignes du fichier de flux n’ont pas été chargées. Voir [Échec de l’importation partielle](#partial-import-failed). |
| **[!UICONTROL Échec de l&#39;indexation]** | L’opération d’index a échoué. Essayez à nouveau. |
| Serveur **[!UICONTROL Introuvable]** | Les emplacements FTP, SFTP ou URL ne sont pas valides ou sont inaccessibles. |

#### Échec de l’import partiel {#partial-import-failed}

Auparavant, lorsque toutes les lignes n’étaient pas chargées, le flux était toujours marqué comme réussi. Cela donnait la fausse impression que toutes les lignes avaient été chargées. Le message indique maintenant ce qui s’est passé : le flux est marqué comme échec de l’importation partielle au lieu de réussite.

Le scénario suivant montre pourquoi une importation de flux partielle peut se produire :

* Vous avez chargé un fichier de flux pour l’environnement de production, par exemple 100 lignes.
* Le flux a exécuté et chargé 80 de ces lignes et en a ignoré 20 en raison d’une mise en forme incorrecte, d’un champ contenant plus de caractères, etc.
* Le flux a été marqué comme réussi dans l’interface utilisateur, ce qui vous donne l’impression que les 100 lignes ont toutes été chargées.
* Vous attendez certains de ces 20 produits dans la livraison d&#39;une activité, mais ce n&#39;est pas le cas.
* Le flux que vous avez chargé contient les détails des produits en question, mais vous ne les voyez pas en arrière-plan lorsque vous effectuez une requête via l’API Entity, ce qui indique qu’ils ne se trouvent pas en arrière-plan.

Pour mettre à jour un flux (par exemple, pour apporter des modifications à la configuration ou au fichier du flux), ouvrez le flux, apportez les modifications souhaitées, puis cliquez sur **[!UICONTROL Enregistrer]**. Le délai d’expiration des entités téléchargées est de 61 jours. Consultez la remarque dans la [Présentation des flux](#concept_D1E9C7347C5D4583AA69B02E79607890) pour connaître la fréquence de chargement.

### Indicateurs de statut du flux {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

Les indicateurs de l’état du flux suivants s’affichent dans la colonne **[!UICONTROL État]** :

| Indicateur d’état | Description |
|--- |--- |
| Indicateur d’état vert | Une fois l’indexation du flux terminée, celui-ci est marqué d’un point vert pour indiquer que son état est Succès. |
| Indicateur d’état jaune | Lorsqu’un index de flux ou un flux est retardé de 25 % par rapport à la fréquence du flux, un point d’état jaune s’affiche. Par exemple, un point jaune s’affiche pour qu’un jeu de flux s’exécute tous les jours si l’index ne s’est pas terminé six heures après l’heure planifiée. Remarque : une fois que le statut du flux est « En attente de la file d’attente de l’index », les valeurs nouvellement mises à jour sont disponibles dans la diffusion et le traitement des critères. |
| Indicateur d’état blanc | Lorsqu’un flux n’est pas planifié, un point d’état blanc indique que le flux n’a pas encore été exécuté. |
| Indicateur d’état rouge | Si le flux ne parvient pas à charger les données sur le serveur, un indicateur de statut rouge s’affiche. |

Prenons les exemples suivants :

**Exemple 1 :**

* Premier jour : processus quotidiens d’alimentation à 9 h (heure du Pacifique).
* Jour deux : il est 15h30 et le flux n&#39;a pas fonctionné depuis hier à 9h00.

L’état doit être jaune car l’index aurait dû s’exécuter il y a environ 6,5 heures. 6,5 heures +24 = 127 % de l’intervalle d’exécution du flux.

**Exemple 2 :**

* 1er janvier : processus mensuels d&#39;alimentation à 9 h (heure du Pacifique)
* 3 février : il est 10h00 et le flux n&#39;a pas fonctionné depuis un mois, un jour et une heure auparavant.

L’état doit être jaune car l’index aurait dû s’exécuter il y a environ un jour et une heure. Même si cela représente seulement (31+(1/25))/30 = 1,03 % du paramètre de fréquence, le délai d’un jour maximum a été dépassé.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

+++ Comprendre les flux dans Recommendations

Cette vidéo traite des sujets suivants :

* Comprendre l’objectif des flux
* Comprendre la valeur des flux

>[!VIDEO](https://video.tv.adobe.com/v/27695)

+++

+++ Créer un flux

Cette vidéo traite des sujets suivants :

* Configurer un flux
* Déterminer le type de flux à utiliser

>[!VIDEO](https://video.tv.adobe.com/v/27696)

+++
