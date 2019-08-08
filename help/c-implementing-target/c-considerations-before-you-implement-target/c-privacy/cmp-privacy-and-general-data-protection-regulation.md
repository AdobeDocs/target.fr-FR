---
description: Informations sur le GDPR (General Data Protection Regulations) et la loi CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et Adobe Target.
keywords: gdpr ; eu ; Union européenne ; confidentialité ; faq ; questions fréquentes ; California consumer privacy act ; ccpa ; confidentialité ; protection des données ; exclusion ; exclure ; gouvernement ; réglementation
seo-description: Informations sur le GDPR (General Data Protection Regulations) et la loi CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et Adobe Target.
seo-title: General Data Protection Regulations (GDPR), California Consumer Privacy Act (CCPA) et Adobe Target
solution: Target
title: Réglementations relatives à la confidentialité et à la protection des données
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: aa077c92e0b6aaec27429acd9292a5edcf6c60fa

---


# Réglementations relatives à la confidentialité et à la protection des données {#privacy-and-general-data-protection-regulation-gdpr}

Informations sur le GDPR (General Data Protection Regulations) et la CCPA (California Consumer Privacy Act) et sur l'impact de ces règles sur votre organisation et [!DNL Adobe Target]sur votre organisation.

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Le 25 mai 2018, le GDPR de l'Union européenne a été appliqué. Pour en savoir plus sur les conséquences pour vous, voir [Le RGPD et votre entreprise](https://www.adobe.com/privacy/general-data-protection-regulation.html).

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. Pour obtenir une liste détaillée d’exemples, voir [Confidentialité Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

[!DNL Adobe Experience Cloud] fournissez les API prêtes pour GDPR pour les contrôleurs de données qui permettent de réaliser les tâches suivantes :

* Accéder aux informations du sujet des données stockées dans [!DNL Target]
* Supprimer les informations du sujet des données stockées dans [!DNL Target]

Pour obtenir plus d’informations, voir :

* [Site Web de l’API du règlement général sur la protection des données d’Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentation RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Présentation CCPA (California Consumer Privacy Act)

La loi CCPA (California Consumer Privacy Act) prend effet le 1 er janvier 2020. Par sa conception, la loi confère à l'agent de réglementation California la possibilité d'effectuer des ajustements et de clarifier les détails, ce qui signifie que vous avez naturellement beaucoup de questions à poser. Si vous avez des questions, vous n'êtes pas seul au même endroit que le nombre d'entreprises qui utilisent les incertitudes légales et tentent de comprendre et développer une approche pour répondre aux exigences légales, opérationnelles et techniques.

La CCPA fournit aux clients de Californie de nouveaux droits concernant leurs informations personnelles et impose des responsabilités de protection des données à certaines entités qui effectuent des activités en Californie. A un niveau élevé, la loi offre plusieurs droits clés, dont les droits d'accès :

* Demande d'informations (accès aux données)
* Exclusion de la vente d'informations personnelles (un droit très largement défini pour exclure le partage d'informations avec des tiers)
* Suppression d'informations personnelles
* Soyez informé que les informations personnelles sont divulguées ou vendues

Si vous étiez habitué à la loi sur la confidentialité de l'Europe (GDPR) l'année dernière, certains de ces droits peuvent être familiers et une grande partie du travail que vous avez accompli peut être réinitialisée.

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] fournit la prise en charge des fonctionnalités de souscription par le biais [!DNL Launch] de la prise en charge de votre stratégie de gestion des approbations. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. Consultez la [Documentation de Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) pour plus de détails.

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
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide selected elements of your page prior to [!DNL Target] firing that are helpful to leverage as part of your consent strategy.

Lors de l’utilisation de la fonctionnalité d’opt-in, trois scénarios sont à envisager :

1. **[!DNL Target]La balise est préapprouvée via[!DNL Launch](ou le sujet de données précédemment approuvé[!DNL Target]) :** [!DNL Target] La balise n'est pas conservée pour le consentement et les fonctions comme prévu.
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de`bodyHidingEnabled`est FALSE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). Il est important de tenir compte du fait que seul le contenu par défaut est disponible avant la réception du consentement, et d’utiliser une stratégie appropriée à la situation. Il s’agit, par exemple, d’utiliser une splash page pour recouvrir les parties ou le contenu d’une page qui pourra être personnalisée. Cela permet de faire en sorte que l’expérience reste cohérente pour le sujet de données (visiteur).
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de`bodyHidingEnabled`est TRUE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Cependant, comme le paramètre `bodyHidingEnabled` est défini sur « true », c’est `bodyHiddenStyle` qui définit le contenu qui est masqué jusqu’au déclenchement de la balise  (sauf si le sujet de données refuse l’opt-in, ce qui entraînerait l’affichage du contenu par défaut). [!DNL Target] Par défaut, le paramètre `bodyHiddenStyle` est défini sur `body { opacity:0;`}, ce qui masque la balise HTML body. Vous trouverez ci-dessous la configuration de page recommandée : masquage de l’ensemble du corps de la page, à l’exception de la boîte de dialogue du gestionnaire de consentement, en les mettant, celle-ci et le contenu de la page, dans deux conteneurs différents. This setup configures [!DNL Target] so that it hides the page content container only. Voir la [documentation  Launch](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html) (en anglais), pour plus d’informations sur la configuration de ces paramètres.

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

Questions fréquentes sur [!DNL Target]le GDPR (General Data Protection Regulation) et la CCPA (California Consumer Privacy Act).

### Quelle est la stratégie d'Adobe pour ces réglementations ? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] remplit déjà ou est en train de mettre en œuvre nos obligations en tant qu’entité de traitement des données. Nous disposons d'une solide base des contrôles de sécurité et de confidentialité certifiés par conception et nous avons apporté des améliorations au niveau des produits avant le délai de mai 2018. Les entreprises clientes auront la responsabilité de mettre en œuvre ces améliorations et de mettre à jour les politiques et procédures nécessaires.

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. Les contrôleurs de données n’auront pas besoin d’accéder directement à chaque solution.

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], will be made through a central Adobe API, currently called the GDPR API. The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target] permettra à nos clients de supprimer toutes les données associées à un ID dans leur profil de visiteur. Pour obtenir des exemples de magasins de données [!DNL Target] de profil, voir [Profil du visiteur](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Les données agrégées ou rendues anonymes (par exemple, les données des rapports) qui n’identifient pas une personne spécifique, ou les données qui ne sont pas liées à une personne spécifique (par exemple, les données en matière de contenu), ne sont pas concernées par la demande de suppression soumise par un utilisateur.

[!DNL Target]Les profils des visiteurs inactifs depuis 90 jours sont supprimés par défaut, sans aucune intervention nécessaire.

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] prend en charge les types d’ID suivants pour localiser un profil client :

| Identifiant utilisateur | Type d’ID d’espace de noms | ID d’espace de noms | Définition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Experience Cloud ID d’Adobe, anciennement connu sous le nom d’ID de visiteur ou de Marketing Cloud ID. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID TNT/ID de cookie(TNTID) | Standard | 9 | Identifiant Target défini comme cookie dans le navigateur du visiteur. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID tiers/ID de gestion de la relation client (THIRDPARTYID) | Spécifique à Target | S.O. | Si vous fournissez à Target votre logiciel de gestion de la relation client ou d’autres informations d’identification uniques pour vos clients. |

>[!NOTE]
>
>Bien qu' [!DNL Target] il prenne en charge les cookies interdomaines propriétaires et tiers, seuls les [!DNL Target] cookies propriétaires sont recommandés pour GDPR et CCPA.

### How does [!DNL Target] handle consent management? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR et CCPA ne changent pas lorsque vous devez obtenir le consentement, mais comment vous l'obtenez. La stratégie de consentement de chaque client dépend de sa collecte de données et de ses pratiques d’utilisation, ainsi que de sa politique de confidentialité. Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe] n’offre pas actuellement de solution de Gestion des consentements, mais divers outils sont en cours d’élaboration sur le marché pour répondre à certaines des nouvelles exigences. For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] fournit une prise en charge des fonctionnalités de souscription par le biais [!DNL Launch] de la prise en charge de votre stratégie de gestion des approbations. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### AdobePrivacy.js envoie-t-il des informations à l’API conforme au RGPD ?{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] n’envoie *pas* ces informations à l’API. C’est au client de les soumettre. La bibliothèque ne fournit que les ID stockés dans le navigateur pour ce visiteur spécifique.

### Que supprime removeIdentities ?{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] *supprime uniquement*[!DNL Adobe] ces identités du navigateur, et cela ne dépend que de leur mise en œuvre ou non par la solution 

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

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

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

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

Lorsque plusieurs valeurs sont fournies pour identifier des profils, chaque identifiant valide dispose d’un fichier de profil. The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

A sample [!DNL Target] Profile JSON could look like the following example:

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
| Sample_Parameter | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. Pour plus d'informations, voir [Méthodes pour obtenir des données dans Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Ce champ standard inclut l’heure de la dernière visite récurrente d’un utilisateur. |
| firstSessionStart | Ce champ standard inclut l’heure de début de la première session de l’utilisateur. |
| user.sessionCountScript | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. Dans cet exemple, un script de profil augmente le nombre de sessions que ce visiteur a initiées sur le site du contrôleur des données. Pour plus d’informations, voir [Attributs de script de profil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. Many of the fields of the [!DNL Target] profile are not standard. Les données retournées dépendent des informations figurant dans ce profil de visiteur spécifique.

## Target prend-il en charge l’obscurcissement des adresses IP ? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] prend en charge l'obscurcissement d'IP si vous choisissez de l'utiliser dans le cadre de votre stratégie de mise en œuvre GDPR ou CCPA. Pour plus d’informations, voir  [Confidentialité](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
