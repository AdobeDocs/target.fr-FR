---
keywords: rgpd;eu;union européenne;confidentialité; faq;questions fréquentes; california consumer privacy act;ccpa;confidentialité;protection des données;opt-out;désinscription;gouvernement;réglementation
description: Découvrez la Cible et le Règlement général sur la protection des données (RGPD) de l'Union européenne, la Loi sur la protection des renseignements personnels des consommateurs (LPCPC) de Californie et d'autres exigences en matière de confidentialité.
title: Comment la Cible gère-t-elle les règlements sur la protection de la vie privée et des données ?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Réglementations relatives à la confidentialité et à la protection des données

Informations sur le RGPD (règlement général sur la protection des données), le CCPA (California Consumer Privacy Act) et d’autres exigences internationales en matière de confidentialité, ainsi que sur l’impact de ces réglementations sur votre entreprise et [!DNL Adobe Target].

## Présentation du règlement général sur la protection des données (RGPD) {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Le 25 mai 2018, le RGPD de l’Union européenne est entré en vigueur. Pour en savoir plus sur les conséquences pour vous, voir [Le RGPD et votre entreprise](https://www.adobe.com/privacy/general-data-protection-regulation.html).

Lorsqu’[!DNL Adobe] fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle traite et stocke dans le cadre de la prestation de ces services. [!DNL Adobe] En tant qu’entité de traitement des données, [!DNL Adobe] traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec [!DNL Adobe]).

En tant que responsable du traitement des données, vous déterminez les données personnelles qu’[!DNL Adobe] traite et stocke pour vous. Si vous utilisez les solutions [!DNL Adobe Experience Cloud], [!DNL Adobe] peut héberger des données personnelles pour vous, en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte [!DNL Adobe Experience Cloud]. Pour obtenir une liste détaillée d’exemples, voir [Confidentialité Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

[!DNL Adobe Experience Cloud] fournissent des API conformes au RGPD aux responsables du traitement des données qui permettent d’effectuer les tâches suivantes :

* Accéder aux informations du sujet des données stockées dans [!DNL Target]
* Supprimer les informations du sujet des données stockées dans [!DNL Target]

Pour obtenir plus d’informations, voir :

* [Site Web de l’API du règlement général sur la protection des données d’Adobe](https://www.adobe.io/apis/experienceplatform/gdpr.html)
* [Documentation RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Présentation du CCPA (California Consumer Privacy Act)

Le CCPA (California Consumer Privacy Act) accorde aux clients de Californie de nouveaux droits concernant leurs informations personnelles et impose des responsabilités en matière de protection des données à certaines entités dont les activités sont basées en Californie. Le CCPA entrera en vigueur le 1er janvier 2020.

À un niveau général, la loi accorde aux Californiens plusieurs droits principaux, notamment les droits de :

* Demander des informations (accès aux données)
* S’exclure de la vente d’informations personnelles (un droit très largement défini pour s’exclure du partage d’informations avec des tiers)
* Supprimer des informations personnelles
* Être informé de la divulgation ou de la vente d’informations personnelles

Si vous vous prépariez l’année dernière pour le réglement européen sur la confidentialité (RGPD), vous devez déjà connaître certains de ces droits et pouvez réutiliser une grande partie du travail déjà accompli.

>[!NOTE]
>
>L&#39;accès et la suppression des données en ce qui concerne l&#39;ACCP suivent le même processus que pour le RMCP.

## [!DNL Experience Platform Launch]Fonctionnalité de souscription (opt-in) Adobe Target et {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] fournit la prise en charge de la fonctionnalité de souscription (opt-in) par le biais d’[!DNL Launch]. Cela facilite la mise en application de votre stratégie de gestion des consentements. La fonctionnalité de souscription (opt-in) permet aux clients de décider comment et à quel moment la balise [!DNL Target] est déclenchée. Une autre option permet, toujours par le biais d’[!DNL Launch], l’approbation préalable de la balise [!DNL Target]. Pour permettre l’utilisation de la fonctionnalité de souscription dans la bibliothèque at.js [!DNL Target], vous devez utiliser `targetGlobalSettings` et ajouter le paramètre `optinEnabled=true`. Dans [!DNL Launch], vous devez sélectionner « activer » dans la liste déroulante [!UICONTROL d’inscription RGPD] dans la vue d’installation de Extension [!DNL Launch]. Consultez la [Documentation de Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) pour plus de détails.

L’extrait de code suivant montre comment activer `optinEnabled=true` le paramètre :

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>La fonctionnalité de souscription (opt-in) est prise en charge dans at.js version 1.7.0 et at.js 2.1.0 et versions ultérieures. Elle n’est pas prise en charge dans at.js versions 2.0.0 et 2.0.1.
>
>Il est recommandé d’utiliser [!DNL Experience Platform Launch] pour la gestion des souscriptions (opt-in). Il existe un contrôle granulaire plus poussé dans [!DNL Launch]. Le but est de masquer, préalablement au déclenchement de [!DNL Target], certains éléments de votre page pouvant servir pour votre stratégie de consentement.

Lors de l’utilisation de la fonctionnalité d’opt-in, trois scénarios sont à envisager :

1. **La balise [!DNL Target] a préalablement été approuvée par le biais d’[!DNL Launch] (ou la personne concernée a préalablement approuvé [!DNL Target]) :** L’attente du consentement n’empêche pas le déclenchement de la balise [!DNL Target].
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de `bodyHidingEnabled` est FALSE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Une fois le consentement reçu, [!DNL Target] est appelé et le contenu personnalisé est disponible pour la personne concernée (visiteur). Il est important de tenir compte du fait que seul le contenu par défaut est disponible avant la réception du consentement, et d’utiliser une stratégie appropriée à la situation. Il s’agit, par exemple, d’utiliser une splash page pour recouvrir les parties ou le contenu d’une page qui pourra être personnalisée. Cela permet de faire en sorte que l’expérience reste cohérente pour le sujet de données (visiteur).
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de `bodyHidingEnabled` est TRUE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Cependant, comme le paramètre `bodyHidingEnabled` est défini sur « true », c’est `bodyHiddenStyle` qui définit le contenu qui est masqué jusqu’au déclenchement de la balise (sauf si le sujet de données refuse l’opt-in, ce qui entraînerait l’affichage du contenu par défaut). [!DNL Target] Par défaut, `bodyHiddenStyle` est défini sur `body { opacity:0;}`, ce qui masque la balise de corps HTML. Vous trouverez ci-dessous la configuration de page recommandée : masquage de l’ensemble du corps de la page, à l’exception de la boîte de dialogue du gestionnaire de consentement, en les mettant, celle-ci et le contenu de la page, dans deux conteneurs différents. Cette configuration de [!DNL Target] fait en sorte que seul le conteneur du contenu de la page soit masqué. Voir la [documentation  Launch](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html) (en anglais), pour plus d’informations sur la configuration de ces paramètres.

   La configuration de page recommandée pour le troisième scénario est la suivante :

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   En supposant que `bodyHiddenStyle` soit :

   ```
   #pageContent { opacity:0;}
   ```

## FAQ sur les réglementations relatives à la confidentialité et à la protection des données{#concept_41F88DE95D2943178BEC382736B5C038}

Questions fréquentes sur le RGPD (règlement général sur la protection des données) de l’Union européenne, la loi CCPA (California Consumer Privacy Act) et d’autres exigences internationales en matière de confidentialité spécifiques à Target.

### Quelle est la politique d’Adobe concernant ces réglementations ? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] remplit déjà ou est en train de mettre en œuvre nos obligations en tant qu’entité de traitement des données. Nous disposons d’une base solide de contrôles certifiés de sécurité et de confidentialité dès la conception et nous avons apporté des améliorations aux produits en prévision de l’échéance de mai 2018. Les entreprises clientes auront la responsabilité de mettre en œuvre ces améliorations et de mettre à jour les politiques et procédures nécessaires.

### Mon entreprise, l’entité responsable du traitement des données, doit-elle envoyer une requête RGPD pour chaque solution [!DNL Adobe Experience Cloud] qu’elle utilise ? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Non, [!DNL Adobe] fournit un système central pour aider les responsables du traitement des données à répondre aux exigences du RGPD et du CCPA. Les contrôleurs de données n’auront pas besoin d’accéder directement à chaque solution.

Toutes les requêtes RGPD et CCPA à travers les solutions [!DNL Experience Cloud], y compris [!DNL Target], seront effectuées via une API Adobe centrale, actuellement nommée API conforme au RGPD. L’API effectuera alors la requête à travers la suite de solutions [!DNL Experience Cloud] du responsable du traitement des données.

### Quelles informations [!DNL Adobe] permettra-t-il à nos clients de supprimer en réponse à une demande d’une personne concernée/utilisateur ? {#section_4B51D00924EC4166B2442218B69214F0}

Les informations relatives à un visiteur individuel dans [!DNL Target] sont contenues dans le profil du visiteur [!DNL Target]. [!DNL Target] permettra à nos clients de supprimer toutes les données associées à un ID dans leur profil de visiteur. Pour obtenir des exemples des magasins [!DNL Target] de données de profil, voir [Profil du visiteur](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Les données agrégées ou rendues anonymes (par exemple, les données des rapports) qui n’identifient pas une personne spécifique, ou les données qui ne sont pas liées à une personne spécifique (par exemple, les données en matière de contenu), ne sont pas concernées par la demande de suppression soumise par un utilisateur.

[!DNL Target]Les profils des visiteurs inactifs depuis 90 jours sont supprimés par défaut, sans aucune intervention nécessaire.

### Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD et du CCPA pour [!DNL Target] ? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] prend en charge les types d’ID suivants pour localiser un profil client :

| Identifiant utilisateur | Type d’ID d’espace de noms | ID d’espace de noms | Définition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Experience Cloud ID d’Adobe, anciennement connu sous le nom d’ID de visiteur ou de Marketing Cloud ID. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID TNT/ID de cookie(TNTID) | Standard | 9 | Identifiant Target défini comme cookie dans le navigateur du visiteur. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID tiers/ID de gestion de la relation client (THIRDPARTYID) | Spécifique à Target | S.O. | Si vous fournissez à Target votre logiciel de gestion de la relation client ou d’autres informations d’identification uniques pour vos clients. |

>[!NOTE]
>
>Bien que [!DNL Target] prenne en charge les cookies interdomaines propriétaires et tiers, seuls les cookies [!DNL Target] propriétaires sont recommandés pour le RGPD et le CCPA.

### Comment [!DNL Target] traite-t-il la gestion des consentements ?{#section_C86BF5EE4FAA47039659850E7594A6BA}

Le RGPD et le CCPA ne changent pas lorsque vous devez obtenir un consentement, mais c’est le cas quand il est question de la façon de l’obtenir. La stratégie de consentement de chaque client dépend de sa collecte de données et de ses pratiques d’utilisation, ainsi que de sa politique de confidentialité. La gestion des consentements n’est pas prise en charge et ne doit pas s’effectuer via [!DNL Target] pour le RGPD et le CCPA.

[!DNL Adobe] n’offre pas actuellement de solution de Gestion des consentements, mais divers outils sont en cours d’élaboration sur le marché pour répondre à certaines des nouvelles exigences. Pour plus d&#39;informations sur les outils de protection de la vie privée en général, y compris les gestionnaires de consentement, consultez le [Rapport 2017 du fournisseur des technologies de protection de la vie privée](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) sur le *site Web de l&#39;Association internationale des professionnels de la protection de la vie privée (iaap)*.

[!DNL Target] fournit la prise en charge de la fonctionnalité de souscription (opt-in) par le biais d’[!DNL Launch]. Cela vous permet de mettre en application votre stratégie de gestion des consentements. La fonctionnalité de souscription (opt-in) permet aux clients de décider comment et à quel moment la balise [!DNL Target] est déclenchée. Une autre option permet, toujours par le biais d’[!DNL Launch], l’approbation préalable de la balise [!DNL Target]. Il est recommandé d’utiliser [!DNL Launch] pour la gestion des souscriptions (opt-in). Il existe un contrôle granulaire plus poussé dans [!DNL Launch]. Le but est de masquer, préalablement au déclenchement d’[!DNL Target], certains éléments de votre page pouvant servir pour votre stratégie de consentement.

Pour plus d&#39;informations sur le RGMD, l&#39;ACCP et [!DNL Launch], voir [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Référez-vous également à la section *Fonctionnalité de souscription (opt-in) Adobe Target et Experience Platform Launch* ci-dessus.

### AdobePrivacy.js envoie-t-il des informations à l’API conforme au RGPD ?{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] n’envoie *pas* ces informations à l’API. C’est au client de les soumettre. La bibliothèque ne fournit que les ID stockés dans le navigateur pour ce visiteur spécifique.

### Que supprime removeIdentities ?{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *supprime uniquement* ces identités du navigateur, et cela ne dépend que de leur mise en œuvre ou non par la [!DNL Adobe] solution 

Par exemple, [!DNL Target] supprime les cookies qui stockent ses ID, mais [!DNL Adobe Audience Manager] (AAM) ne supprime pas l’ID demdex stocké dans un cookie tiers.

### Quelles informations doivent être incluses dans une requête RGPD ou CCPA Target ? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Outre les conditions requises pour le service de confidentialité central, un message RGPD ou CCPA valide pour [!DNL Target] contient :

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### Quels types de réponse puis-je attendre de Target via l’API conforme au RGPD ? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Statut de la requête | Message de la réponse Target | Scénario |
|--- |--- |--- |
| Traitement | Traitement | Target a reçu la requête RGPD ou CCPA et la traite. |
| Complete | Non applicable - contexte d’entreprise non applicable | L’ID IMS dans la requête RGPD ou CCPA n’est associé à aucun client Target.<br>Certaines entreprises disposent de plusieurs ID IMS. Vous devez envoyer l’ID IMS où Target est approvisionné. |
| Complete | Non applicable - contexte utilisateur introuvable | L’ID fourni dans la requête RGPD ou CCPA pour le visiteur ou la personne concernée spécifique ne figure pas dans le magasin de profils Target.<br>Notez que ce résultat est également retourné si vous tentez d’envoyer un type d’ID d’espace de noms non pris en charge par Target (voir ci-dessus les ID pris en charge). |
| Erreur | Message d’erreur (les détails dépendent du type d’erreur) | Erreur lors de la récupération ou de la suppression du profil du sujet de données demandé.<br>Erreur lors du chargement vers Azure pour la demande d’accès. |

### Quelle réponse Target envoie-t-il à l’API conforme au RGPD pour une demande d’accès ?{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Les réponses aux demandes d’accès aux données contiennent un résumé du profil [!DNL Target] pour le visiteur en question. Notez que ce retour est envoyé à l’API RGPD [!DNL Experience Cloud], qui à son tour envoie une réponse aux responsables du traitement des données.

Un exemple de réponse de l’API à [!DNL Target] pour la demande d’accès pourrait ressembler à ceci :

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| Champ | Description |
|--- |--- |
| jobId | Indique l’ID de tâche RGPD ou CCPA à partir de l’API centrale relative au RGPD. |
| imsOrgID | Fournit un identifiant unique pour votre entreprise. |
| namespace | Également appelé source de données. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour Target ? » dans cette rubrique. |
| type | Le type d’ID pour lequel vous avez demandé l’accès aux données en vertu du RGPD ou du CCPA. Target accepte plusieurs types d’ID, dont certains sont standard et d’autres spécifiques à Target. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour Target ? » dans cette rubrique. |
| value | L’ID de l’espace de noms/la source de données. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour Target ? » pour les valeurs acceptées. |
| integration code | Les codes d’intégration sont des noms conviviaux pour vos sources de données et vous aident à suivre vos sources de données plus facilement qu’en utilisant des ID de sources de données. |

Lorsque plusieurs valeurs sont fournies pour identifier des profils, chaque identifiant valide dispose d’un fichier de profil. Le ou les fichiers de profil sont envoyés au Azure Blob RGPD via l’API centrale RGPD, sous le format d’une réponse JSON de profil [!DNL Target].

Voici un exemple de réponse JSON de profil [!DNL Target] :

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

Le tableau suivant contient la description des champs illustratifs JSON du profil :

| Champ | Description |
|--- |--- |
| Sample_Parameter | De nombreuses informations du profil [!DNL Target] sont chargées ou directement fournies par le responsable du traitement des données. Dans cet exemple, un paramètre a été chargé dans le profil [!DNL Target] à l’aide de l’API de mise à jour du profil. Pour plus d’informations, voir [Méthodes pour obtenir des données dans Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Ce champ standard inclut l’heure de la dernière visite récurrente d’un utilisateur. |
| firstSessionStart | Ce champ standard inclut l’heure de début de la première session de l’utilisateur. |
| user.sessionCountScript | De nombreuses informations du profil [!DNL Target] sont chargées ou directement fournies par le responsable du traitement des données. Dans cet exemple, un script de profil augmente le nombre de sessions que ce visiteur a initiées sur le site du contrôleur des données. Pour plus d’informations, voir [Attributs de script de profil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Il s’agit d’une version abrégée d’un profil [!DNL Target] au format JSON à des fins d’illustration. De nombreux champs du profil [!DNL Target] ne sont pas standard. Les données retournées dépendent des informations figurant dans ce profil de visiteur spécifique.

### Target prend-il en charge l’obscurcissement des adresses IP ?  {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] prend en charge l’obscurcissement des adresses IP si vous choisissez de l’utiliser dans le cadre de votre stratégie de mise en œuvre du RGPD ou du CCPA. Pour plus d’informations, voir [Confidentialité](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).

### Dois-je faire quelque chose pour empêcher que mes données ne soient partagées ou vendues à des tiers ?

La cible n&#39;a pas la capacité de permettre aux clients de partager ou de vendre directement des données de Cible à des tiers, de sorte qu&#39;il n&#39;y a pas d&#39;exclusion de la vente pour Cible.
