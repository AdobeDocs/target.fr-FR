---
description: Informations sur le GDPR (General Data Protection Regulations) et la loi CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et Adobe Target.
keywords: gdpr ; eu ; Union européenne ; confidentialité ; faq ; questions fréquentes ; California consumer privacy act ; ccpa
seo-description: Informations sur le GDPR (General Data Protection Regulations) et la loi CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et Adobe Target.
seo-title: General Data Protection Regulations (GDPR), California Consumer Privacy Act (CCPA) et Adobe Target
solution: Target
title: Réglementations relatives à la confidentialité et à la protection des données
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 222fb66f58ea5bcecabfaa2ab966ad9a686dc9ef

---


# Réglementations relatives à la confidentialité et à la protection des données {#privacy-and-general-data-protection-regulation-gdpr}

Informations sur le GDPR (General Data Protection Regulations) et la CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et [!DNL Adobe Target]sur votre organisation.

## Présentation de la confidentialité et du Règlement général sur la protection des données (RGPD) {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Informations sur la manière dont Adobe travaille avec vous pour vous préparer au Règlement général sur la protection des données (RGPD) de l’Union européenne.

### Présentation du RGPD {#section_8C99434A431B4494998B01B869E7EA5D}

Le 25 mai 2018, le GDPR de l'Union européenne a été appliqué. Pour en savoir plus sur les conséquences pour vous, voir [Le RGPD et votre entreprise](https://www.adobe.com/privacy/general-data-protection-regulation.html).

Lorsqu’Adobe fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle traite et stocke dans le cadre de la prestation de ces services. En tant qu’entité de traitement des données, Adobe traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec Adobe).

En tant que contrôleur des données, vous déterminez les données personnelles qu’Adobe traite et stocke pour vous. Si vous utilisez les solutions Adobe Experience Cloud, Adobe peut héberger des données personnelles pour vous, en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte Adobe Experience Cloud. Pour obtenir une liste détaillée d’exemples, voir [Confidentialité Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

Adobe Experience Cloud fournira aux contrôleurs des données des API conformes au RGPD qui leur permettront d’accomplir les tâches suivantes, avant la date de mise en vigueur du RGPD :

* Accéder aux informations du sujet des données stockées dans Target
* Supprimer les informations du sujet des données stockées dans Target

### Le site web de l’API du règlement général sur la protection des données d’Adobe {#section_51B8FA3CBE234E9592BDA7083B5CE4CD}

Pour obtenir plus d’informations, voir :

* [Site Web de l’API du règlement général sur la protection des données d’Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentation RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Présentation de la loi sur la confidentialité des consommateurs (CCPA) de California Consumer

La loi CCPA (California Consumer Privacy Act) prend effet le 1 er janvier 2020. Par sa conception, la loi confère à l'agent de réglementation California la possibilité d'effectuer des ajustements et de clarifier les détails, ce qui signifie que vous avez naturellement beaucoup de questions. Si vous avez des questions, vous n'êtes pas seul au même endroit que le nombre d'entreprises qui utilisent les incertitudes légales et tentent de comprendre et développer une approche pour répondre aux exigences légales, opérationnelles et techniques.

La CCPA fournit aux clients de Californie de nouveaux droits concernant leurs informations personnelles et impose des responsabilités de protection des données à certaines entités qui effectuent des activités en Californie. A un niveau élevé, la loi offre plusieurs droits clés, dont les droits d'accès : (1) demander des informations (accès aux données), (2) s'exclure de la vente d'informations personnelles (un droit très largement défini pour exclure le partage d'informations avec des tiers), (3) avoir des informations personnelles supprimées et (4) être informé que des informations personnelles sont divulguées ou vendues.

Si vous étiez habitué à la loi sur la confidentialité de l'Europe (GDPR) l'année dernière, certains de ces droits peuvent être familiers et une grande partie du travail que vous avez accompli peut être réinitialisée.

## Fonctionnalité d’opt-in Adobe Target et Adobe Launch {#section_6F7B53F5E40C4425934627B653E831B0}

Target fournit la prise en charge de la fonctionnalité d’opt-in par le biais d’Adobe Launch. Cela facilite la mise en application de votre stratégie de gestion des consentements. La fonctionnalité d’opt-in permet aux clients de décider comment et à quel moment la balise Target est déclenchée. Une autre option permet, toujours par le biais d’Adobe Launch, l’approbation préalable de la balise Target. Pour permettre l’utilisation de la fonction Souscription dans Target at.js, vous devez utiliser `targetGlobalSettings` et ajouter le paramètre `optinEnabled=true`. Dans Launch, vous devez sélectionner « activer » dans la liste déroulante d’inscription GDPR dans la vue d’installation de Target Launch Extension. Consultez la [Documentation de Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) pour plus de détails.

L’extrait de code suivant montre comment activer `optinEnabled=true` le paramètre :

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>La fonctionnalité de souscription est prise en charge dans at. js version 1.7.0 et at. js 2.1.0 ou ultérieure. La souscription n'est pas prise en charge dans at. js version 2.0.0 et 2.0.1.
>
>Nous vous recommandons l’utilisation d’Adobe Launch pour la gestion des opt-in. Il existe un contrôle granulaire plus poussé dans Adobe Launch. Le but est de masquer, préalablement au déclenchement de Target, certains éléments de votre page pouvant servir pour votre stratégie de consentement.

Lors de l’utilisation de la fonctionnalité d’opt-in, trois scénarios sont à envisager :

1. **La balise Target a préalablement été approuvée par le biais d’Adobe Launch (ou le sujet de données a préalablement approuvé Target) :** L’attente du consentement n’empêche pas le déclenchement de la balise Target.
1. **La balise Target n’a PAS été préalablement approuvée et la valeur de`bodyHidingEnabled`est FALSE :** La balise Target se déclenche seulement après que le client a donné son consentement. Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Une fois le consentement reçu, Target est appelé et le contenu personnalisé est disponible pour le sujet de données (visiteur). Il est important de tenir compte du fait que seul le contenu par défaut est disponible avant la réception du consentement, et d’utiliser une stratégie appropriée à la situation. Il s’agit, par exemple, d’utiliser une splash page pour recouvrir les parties ou le contenu d’une page qui pourra être personnalisée. Cela permet de faire en sorte que l’expérience reste cohérente pour le sujet de données (visiteur).
1. **La balise Target n’a PAS été préalablement approuvée et la valeur de`bodyHidingEnabled`est TRUE :** La balise Target se déclenche seulement après que le client a donné son consentement. Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Cependant, comme le paramètre `bodyHidingEnabled` est défini sur « true », c’est `bodyHiddenStyle` qui définit le contenu qui est masqué jusqu’au déclenchement de la balise Target (sauf si le sujet de données refuse l’opt-in, ce qui entraînerait l’affichage du contenu par défaut). Par défaut, le paramètre `bodyHiddenStyle` est défini sur `body { opacity:0;`}, ce qui masque la balise HTML body. Vous trouverez ci-dessous la configuration de page recommandée : masquage de l’ensemble du corps de la page, à l’exception de la boîte de dialogue du gestionnaire de consentement, en les mettant, celle-ci et le contenu de la page, dans deux conteneurs différents. Cette configuration de Target fait en sorte que seul le conteneur du contenu de la page soit masqué. Voir la [documentation Adobe Launch](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html) (en anglais), pour plus d’informations sur la configuration de ces paramètres.

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

## FAQ sur la confidentialité et la protection des données {#concept_41F88DE95D2943178BEC382736B5C038}

Questions fréquentes sur le GDPR (General Data Protection Regulation) et la CCPA (California Consumer Privacy Act) spécifiques à Adobe Target.

### Quelle est la stratégie d'Adobe pour ces réglementations ? {#section_A6849628D6524C80A6E16946DC5D25A9}

Adobe remplit déjà ou est en train de mettre en œuvre nos obligations en tant qu’entité de traitement des données. Nous disposons d’une base solide de contrôles certifiés de sécurité et de confidentialité dès la conception et nous continuerons d’apporter des améliorations aux produits en prévision de l’échéance de mai 2018. Les entreprises clientes auront la responsabilité de mettre en œuvre ces améliorations et de mettre à jour les politiques et procédures nécessaires.

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each Adobe Experience Cloud solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Non, Adobe constitue une manière centralisée d'aider les contrôleurs de données à répondre aux exigences de leur GDDP et CCPA. Les contrôleurs de données n’auront pas besoin d’accéder directement à chaque solution.

Toutes les requêtes GDPR et CCPA dans les solutions Experience Cloud, y compris Target, sont effectuées via une API Adobe centrale, actuellement appelée API GDPR. L’API effectuera alors la requête à travers la suite de solutions Experience Cloud du contrôleur de données.

### Quelles informations Adobe permettra-t-il à nos clients de supprimer en réponse à une demande d’un sujet des données/utilisateur ? {#section_4B51D00924EC4166B2442218B69214F0}

Les informations relatives à un visiteur individuel dans Target sont contenues dans le profil du visiteur Target. Adobe Target permettra à nos clients de supprimer toutes les données associées à un ID dans leur profil de visiteur. Pour des exemples de données de profil stockées par Adobe Target, voir [Profil du visiteur](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Les données agrégées ou rendues anonymes (par exemple, les données des rapports) qui n’identifient pas une personne spécifique, ou les données qui ne sont pas liées à une personne spécifique (par exemple, les données en matière de contenu), ne sont pas concernées par la demande de suppression soumise par un utilisateur.

Les profils des visiteurs Target inactifs depuis 90 jours sont supprimés par défaut, sans aucune intervention nécessaire.

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

Target prend en charge les types d’ID suivants pour localiser un profil client :

| Identifiant utilisateur | Type d’ID d’espace de noms | ID d’espace de noms | Définition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Experience Cloud ID d’Adobe, anciennement connu sous le nom d’ID de visiteur ou de Marketing Cloud ID. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID TNT/ID de cookie(TNTID) | Standard | 9 | Identifiant Target défini comme cookie dans le navigateur du visiteur. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID tiers/ID de gestion de la relation client (THIRDPARTYID) | Spécifique à Target | S.O. | Si vous fournissez à Target votre logiciel de gestion de la relation client ou d’autres informations d’identification uniques pour vos clients. |

>[!NOTE]
>
>Bien qu'Adobe Target prenne en charge les cookies interdomaines propriétaires et tiers, les cookies Adobe Target propriétaires sont uniquement recommandés pour GDPR et CCPA.

### Comment Adobe Target traite-t-il la gestion des consentements ?{#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR et CCPA ne changent pas lorsque vous devez obtenir le consentement, mais comment vous l'obtenez. La stratégie de consentement de chaque client dépend de sa collecte de données et de ses pratiques d’utilisation, ainsi que de sa politique de confidentialité. La gestion des autorisations n'est pas prise en charge et ne doit pas être obtenue via Target pour GDPR et CCPA.

Adobe n’offre pas actuellement de solution de Gestion des consentements, mais divers outils sont en cours d’élaboration sur le marché pour répondre à certaines des nouvelles exigences. Pour de plus amples renseignements sur les outils de confidentialité en général, y compris les gestionnaires de consentement, voir le [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) (soit le rapport sur les fournisseurs offrant des technologies de confidentialité) sur le site web de l’Association internationale des professionnels de la protection de la vie privée (IAPP).

Adobe Target fournit la prise en charge de la fonctionnalité d’opt-in par le biais d’Adobe Launch. Cela vous permet de mettre en application votre stratégie de gestion des consentements. La fonctionnalité d’opt-in permet aux clients de décider comment et à quel moment la balise Adobe Target est déclenchée. Une autre option permet, toujours par le biais d’Adobe Launch, l’approbation préalable de la balise Adobe Target. Nous vous recommandons l’utilisation d’Adobe Launch pour la gestion des opt-in. Il existe un contrôle granulaire plus poussé dans Adobe Launch. Le but est de masquer, préalablement au déclenchement d’Adobe Target, certains éléments de votre page pouvant servir pour votre stratégie de consentement.

For more information on GDPR, CCPA and Adobe Launch, see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Référez-vous également à la section « Fonctionnalité d’opt-in Adobe Target et Adobe Launch » ci-avant.

### AdobePrivacy.js envoie-t-il des informations à l’API conforme au RGPD ?{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] n’envoie *pas* ces informations à l’API. C’est au client de les soumettre. La bibliothèque ne fournit que les ID stockés dans le navigateur pour ce visiteur spécifique.

### Que supprime removeIdentities ?{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *supprime uniquement* ces identités du navigateur, et cela ne dépend que de leur mise en œuvre ou non par la solution Adobe.

Par exemple, Target supprime les cookies qui stockent ses ID, mais Adobe Audience Manager (AAM) ne supprime pas l’ID demdex stocké dans un cookie tiers.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Outre les exigences du service de confidentialité Central, un message GDPR ou CCPA valide pour Target contient les éléments suivants :

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
| Traitement | Traitement | Target a reçu la demande GDPR ou CCPA et est en cours de traitement. |
| Complete | Non applicable - contexte d’entreprise non applicable | L'ID IMS dans la requête GDPR ou CCPA n'est associé à aucun client Target.<br>Certaines entreprises disposent de plusieurs ID IMS. Vous devez envoyer l’ID IMS où Target est approvisionné. |
| Complete | Non applicable - contexte utilisateur introuvable | L'ID fourni dans la demande GDPR ou CCPA pour le sujet ou le sujet de données spécifique n'est pas présent dans le magasin de profils Target.<br>Notez que ce résultat est également retourné si vous tentez d’envoyer un type d’ID d’espace de noms non pris en charge par Target (voir ci-dessus les ID pris en charge). |
| Erreur | Message d’erreur (les détails dépendent du type d’erreur) | Erreur lors de la récupération ou de la suppression du profil du sujet de données demandé.<br>Erreur lors du chargement vers Azure pour la demande d’accès. |

### Quelle réponse Target envoie-t-il à l’API conforme au RGPD pour une demande d’accès ?{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Les réponses aux demandes d’accès aux données contiennent un résumé du profil Target pour le visiteur en question. Notez que ce retour est envoyé à l’API conforme au RGPD Experience Cloud, qui à son tour envoie une réponse aux contrôleur de données.

Un exemple de réponse de l’API à Target pour la demande d’accès pourrait ressembler à ceci :

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
| jobId | Indique l'ID de tâche GDPR ou CCPA depuis l'API GDPR Central. |
| imsOrgID | Fournit un identifiant unique pour votre entreprise. |
| namespace | Également appelé source de données. Voir Quels identifiants sont pris en charge pour aider les clients à compléter une demande d'accès GDPR ou CCPA pour Target ?  » » dans cette rubrique. |
| type | Type d'identifiant pour lequel vous avez demandé l'accès aux données GDPR ou CCPA. Target accepte plusieurs types d’ID, dont certains sont standard et d’autres spécifiques à Target. Voir Quels identifiants sont pris en charge pour aider les clients à compléter une demande d'accès GDPR ou CCPA pour Target ?  » » dans cette rubrique. |
| value | L’ID de l’espace de noms/la source de données. Voir Quels identifiants sont pris en charge pour aider les clients à compléter une demande d'accès GDPR ou CCPA pour Target ?  » » pour les valeurs acceptées. |
| integration code | Les codes d’intégration sont des noms conviviaux pour vos sources de données et vous aident à suivre vos sources de données plus facilement qu’en utilisant des ID de sources de données. |

Lorsque plusieurs valeurs sont fournies pour identifier des profils, chaque identifiant valide dispose d’un fichier de profil. Le ou les fichiers de profil sont envoyés au Azure Blob RGPD via l’API centrale RGPD, sous le format d’une réponse JSON de profil Target.

Voici un exemple de réponse JSON de profil Target :

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
| Sample_Parameter | De nombreuses informations du profil Target sont chargées ou directement fournies par le contrôleur des données. Dans cet exemple, un paramètre a été chargé dans le profil Target à l’aide de l’API de mise à jour du profil. Pour plus d’informations, voir [Méthodes de transfert de données dans Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Ce champ standard inclut l’heure de la dernière visite récurrente d’un utilisateur. |
| firstSessionStart | Ce champ standard inclut l’heure de début de la première session de l’utilisateur. |
| user.sessionCountScript | De nombreuses informations du profil Target sont chargées ou directement fournies par le contrôleur des données. Dans cet exemple, un script de profil augmente le nombre de sessions que ce visiteur a initiées sur le site du contrôleur des données. Pour plus d’informations, voir [Attributs de script de profil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Il s’agit d’une version abrégée d’un profil Target au format JSON à des fins d’illustration. De nombreux champs du profil Target ne sont pas standard. Les données retournées dépendent des informations figurant dans ce profil de visiteur spécifique.

## Target prend-il en charge l’obscurcissement des adresses IP ? {#section_428907B0CD9842D9B245B38C66A53C6A}

Target prend en charge l'obscurcissement d'IP dans Target si vous choisissez de l'utiliser dans le cadre de votre stratégie de mise en œuvre GDPR ou CCPA. Pour plus d’informations, voir  [Confidentialité](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
