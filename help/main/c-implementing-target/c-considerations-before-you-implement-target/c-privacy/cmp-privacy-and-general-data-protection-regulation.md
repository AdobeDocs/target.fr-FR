---
keywords: rgpd;eu;union européenne;confidentialité; faq;questions fréquentes; california consumer privacy act;ccpa;confidentialité;protection des données;opt-out;désinscription;gouvernement;réglementation
description: Learn about [!DNL Target] and the European Union General Data Protection Regulation (GDPR), the California Consumer Privacy Act (CCPA), and other privacy requirements.
title: Comment [!DNL Target] Gérer les réglementations sur la confidentialité et la protection des données ?
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '2209'
ht-degree: 57%

---

# Réglementations relatives à la confidentialité et à la protection des données

Informations sur le Règlement général sur la protection des données (RGPD) de l’Union européenne, la loi sur la protection de la vie privée des consommateurs (CCPA) de Californie et d’autres exigences internationales en matière de confidentialité. Découvrez comment ces réglementations affectent votre organisation et [!DNL Adobe Target].

## Présentation du règlement général sur la protection des données (RGPD)  {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Le 25 mai 2018, le RGPD de l’Union européenne est entré en vigueur. Pour plus d’informations sur ce que ce règlement signifie pour vous, voir [Le RGPD et votre entreprise](https://business.adobe.com/privacy/general-data-protection-regulation.html).

Lorsqu’[!DNL Adobe] fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle traite et stocke dans le cadre de la prestation de ces services. [!DNL Adobe] En tant qu’entité de traitement des données, [!DNL Adobe] traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec [!DNL Adobe]).

En tant que responsable du traitement des données, vous déterminez les données personnelles qu’[!DNL Adobe] traite et stocke pour vous. Si vous utilisez les solutions [!DNL Adobe Experience Cloud], [!DNL Adobe] peut héberger des données personnelles pour vous, en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte [!DNL Adobe Experience Cloud]. Pour obtenir une liste détaillée d’exemples, voir [Confidentialité Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud.html#collect).

[!DNL Adobe Experience Cloud] fournit des API conformes au RGPD aux responsables du traitement des données qui leur permettent d’effectuer les tâches suivantes :

* Accéder aux informations du sujet des données stockées dans [!DNL Target]
* Supprimer les informations du sujet des données stockées dans [!DNL Target]

Pour obtenir plus d’informations, voir :

* [Adobe Privacy Service - Aperçu](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Guide de l’API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Présentation de l’interface utilisateur de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## Présentation du CCPA (California Consumer Privacy Act)

Le CCPA (California Consumer Privacy Act) accorde aux clients de Californie de nouveaux droits concernant leurs informations personnelles et impose des responsabilités en matière de protection des données à certaines entités dont les activités sont basées en Californie. La CCPA est entrée en vigueur le 1er janvier 2020.

À un niveau général, la loi accorde aux Californiens plusieurs droits principaux, notamment les droits de :

* Demander des informations (accès aux données)
* Opt out of the sale of personal information (a broadly defined right to opt out of sharing of information with third parties)
* Supprimer des informations personnelles
* Être informé de la divulgation ou de la vente d’informations personnelles

Si vous étiez occupé à vous préparer à la loi européenne sur la protection de la vie privée (RGPD) l’an dernier, certains de ces droits pourraient vous être familiers et une grande partie du travail que vous avez accompli peut être réorientée.

>[!NOTE]
>
>Accessing and deleting data as it applies to the CCPA follows the same process as for the GDPR.

## Adobe [!DNL Target] et [!DNL Adobe Experience Platform] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] fournit la prise en charge de la fonctionnalité d’opt-in par le biais de balises dans [!DNL Adobe Experience Platform] pour vous aider à prendre en charge votre stratégie de gestion des consentements. La fonctionnalité de souscription (opt-in) permet aux clients de décider comment et à quel moment la balise [!DNL Target] est déclenchée. Une autre option permet, toujours par le biais d’[!DNL Adobe Experience Platform], l’approbation préalable de la balise [!DNL Target]. Pour permettre l’utilisation de la fonctionnalité de souscription dans la bibliothèque at.js [!DNL Target], vous devez utiliser `targetGlobalSettings` et ajouter le paramètre `optinEnabled=true`. In [!DNL Adobe ExperiencePlatform], select &quot;enable&quot; from the [!UICONTROL GDPR Opt-In] drop-down list in the extension installation view. Voir [Mise en oeuvre [!DNL Target] using [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) pour plus d’informations.

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
>Il est recommandé d’utiliser [!DNL Adobe Experience Platform] pour la gestion des souscriptions (opt-in). Further granular control exists in [!DNL Adobe Experience Platform] to hide selected elements of your page before [!DNL Target] firing that are helpful to use as part of your consent strategy.

Lors de l’utilisation de la fonctionnalité d’opt-in, trois scénarios sont à envisager :

1. **La balise [!DNL Target] a préalablement été approuvée par le biais d’[!DNL Adobe Experience Platform] (ou la personne concernée a préalablement approuvé [!DNL Target]) :** L’attente du consentement n’empêche pas le déclenchement de la balise [!DNL Target].
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de `bodyHidingEnabled` est FALSE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Une fois le consentement reçu, [!DNL Target] est appelé et le contenu personnalisé est disponible pour la personne concernée (visiteur). Étant donné que seul le contenu par défaut est disponible avant le consentement, il est important d’utiliser une stratégie appropriée, telle qu’une page de démarrage qui couvre n’importe quelle partie de la page ou du contenu susceptible d’être personnalisé. Ce processus garantit que l’expérience reste cohérente pour le sujet de données (visiteur).
1. **[!DNL Target]La balise n’a PAS été préalablement approuvée et la valeur de `bodyHidingEnabled` est TRUE :** La balise se déclenche seulement après que le client a donné son consentement. [!DNL Target] Avant d’avoir reçu le consentement du client, seul le contenu par défaut est disponible. Cependant, comme le paramètre `bodyHidingEnabled` est défini sur « true », c’est `bodyHiddenStyle` qui définit le contenu qui est masqué jusqu’au déclenchement de la balise (sauf si le sujet de données refuse l’opt-in, ce qui entraînerait l’affichage du contenu par défaut). [!DNL Target] By default, `bodyHiddenStyle` is set to `body { opacity:0;}`, which hides the HTML body tag. La configuration de page recommandée par Adobe est présentée ci-dessous de sorte que tout le corps de la page, autre que la boîte de dialogue du gestionnaire de consentement, soit masqué en plaçant le contenu de la page dans un conteneur et la boîte de dialogue du gestionnaire de consentement dans un conteneur distinct. Cette configuration de [!DNL Target] fait en sorte que seul le conteneur du contenu de la page soit masqué. Voir [Présentation du Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).

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

## FAQ sur les réglementations relatives à la confidentialité et à la protection des données {#concept_41F88DE95D2943178BEC382736B5C038}

Questions fréquentes sur le RGPD (règlement général sur la protection des données) de l’Union européenne, la loi CCPA (California Consumer Privacy Act) et d’autres exigences internationales en matière de confidentialité spécifiques à [!DNL Target].

### What is the [!DNL Adobe] policy for these regulations? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] either already meets or is implementing its obligations as a Data Processor. Adobe dispose d’une base solide de contrôles certifiés de sécurité et de confidentialité par conception et a apporté des améliorations aux produits avant la date limite de mai 2018. Les clients d’Enterprise ont la responsabilité de mettre en oeuvre ces améliorations et de mettre à jour les politiques et procédures nécessaires.

### Mon entreprise, le contrôleur de données, doit-elle envoyer une demande RGPD ou CCPA à chaque [!DNL Adobe Experience Cloud] solution qu’elle utilise ? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Non, [!DNL Adobe] fournit un moyen central d’aider les contrôleurs de données à répondre aux exigences du RGPD et du CCPA. Les contrôleurs de données n’ont pas besoin d’accéder directement à chaque solution.

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], are through a central [!DNL Adobe] API, currently called the GDPR API. L’API effectue ensuite la demande à l’échelle du contrôleur de données. [!DNL Experience Cloud] suite de solutions.

### What information does [!DNL Adobe] enable customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

Les informations relatives à un visiteur individuel dans [!DNL Target] sont contenues dans le profil du visiteur [!DNL Target]. [!DNL Target] permet aux clients de supprimer toutes les données associées à un identifiant dans leur profil de visiteur. Pour obtenir des exemples des magasins [!DNL Target] de données de profil, voir [Profil du visiteur](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Les données agrégées ou rendues anonymes (par exemple, les données des rapports) qui n’identifient pas une personne spécifique, ou les données qui ne sont pas liées à une personne spécifique (par exemple, les données en matière de contenu), ne sont pas concernées par la demande de suppression soumise par un utilisateur.

[!DNL Target]Les profils des visiteurs inactifs depuis 90 jours sont supprimés par défaut, sans aucune intervention nécessaire.

### Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD et du CCPA pour [!DNL Target] ? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target] prend en charge les types d’ID suivants pour localiser un profil client :

| Identifiant utilisateur | Type d’ID d’espace de noms | ID d’espace de noms | Définition |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID], formerly known as Visitor ID or Experience Cloud ID. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID TNT/ID de cookie(TNTID) | Standard | 9 | [!DNL Target]Identifiant défini comme cookie dans le navigateur du visiteur. Vous pouvez utiliser l’API JavaScript pour localiser cet ID (voir les détails ci-dessous). |
| ID tiers/ID de gestion de la relation client (THIRDPARTYID) | [!DNL Target]-Spécifique | S.O. | Si vous fournissez [!DNL Target] avec votre CRM ou d’autres informations d’identification uniques pour vos clients. |

>[!NOTE]
>
>Bien que [!DNL Target] prenne en charge les cookies interdomaines propriétaires et tiers, seuls les cookies [!DNL Target] propriétaires sont recommandés pour le RGPD et le CCPA.

### Comment [!DNL Target] traite-t-il la gestion des consentements ? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR and CCPA do not change when you must get consent, but how you get it. Each customer&#39;s consent strategy depends on its data collection and use practices and its privacy policy. La gestion des consentements n’est pas prise en charge et ne doit pas s’effectuer via [!DNL Target] pour le RGPD et le CCPA.

[!DNL Adobe] n’offre pas actuellement de solution de Gestion des consentements, mais divers outils sont en cours d’élaboration sur le marché pour répondre à certaines des nouvelles exigences. For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] fournit la prise en charge de la fonctionnalité d’opt-in via [!DNL Adobe Experience Platform] pour prendre en charge votre stratégie de gestion des consentements. La fonctionnalité de souscription (opt-in) permet aux clients de décider comment et à quel moment la balise [!DNL Target] est déclenchée. Une autre option permet, toujours par le biais d’[!DNL Adobe Experience Platform], l’approbation préalable de la balise [!DNL Target]. Il est recommandé d’utiliser [!DNL Adobe Experience Platform] pour la gestion des souscriptions (opt-in). Un contrôle granulaire plus poussé existe dans [!DNL Adobe Experience Platform] pour masquer certains éléments de votre page avant l’événement [!DNL Target] déclenchement qui peut s’avérer utile dans le cadre de votre stratégie de consentement.

Pour plus d’informations sur le RGPD, le CCPA et [!DNL Adobe Experience Platform], voir [La bibliothèque JavaScript Adobe Privacy et le RGPD](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). Voir également la section *Inclusion dans Adobe Target et Adobe Experience Platform* ci-dessus.

### `AdobePrivacy.js` envoie-t-il des informations à l’API conforme au RGPD ? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] n’envoie *pas* ces informations à l’API. C’est au client de les soumettre. La bibliothèque ne fournit que les ID stockés dans le navigateur pour ce visiteur spécifique.

### Que faire ? `removeIdentities` remove ? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] *supprime uniquement* ces identités du navigateur, et cela ne dépend que de leur mise en œuvre ou non par la [!DNL Adobe] solution 

Par exemple, [!DNL Target] supprime les cookies qui stockent ses ID, mais [!DNL Adobe Audience Manager] (AAM) ne supprime pas l’ID demdex stocké dans un cookie tiers.

### What information must be included in a [!DNL Target] GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

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

### What types of responses can I expect from [!DNL Target] via the GDPR API? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Statut de la requête | [!DNL Target] Message de réponse | Scénario |
|--- |--- |--- |
| Traitement | Traitement | [!DNL Target] a reçu la requête RGPD ou CCPA et la traite. |
| Complete | Non applicable - contexte d’entreprise non applicable | L’identifiant IMS dans la requête RGPD ou CCPA n’est mappé à aucun [!DNL Target] client.<br>Some companies have multiple IMS IDs. Envoyez l’identifiant IMS où [!DNL Target] est configuré. |
| Terminer | Non applicable - contexte utilisateur introuvable | L’ID fourni dans la requête RGPD ou CCPA pour le visiteur ou la personne concernée spécifique n’est pas présent dans la variable [!DNL Target] banque de profils.<br>Ce résultat est également renvoyé si vous tentez d’envoyer un type d’ID d’espace de noms non pris en charge par [!DNL Target] (voir ci-dessus pour les ID pris en charge). |
| Erreur | Message d’erreur (les détails dépendent du type d’erreur) | Erreur lors de la récupération ou de la suppression du profil du sujet de données demandé.<br>Erreur lors du chargement vers Azure pour la demande d’accès. |

### Quelle réponse ? [!DNL Target] envoyer à l’API relative au RGPD pour une demande d’accès ? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Les réponses aux demandes d’accès aux données contiennent un résumé du profil [!DNL Target] pour le visiteur en question. Ce retour est envoyé au [!DNL Experience Cloud] API RGPD, qui à son tour envoie une réponse aux responsables du traitement des données.

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
| namespace | Également appelé source de données. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour [!DNL Target]?&quot; dans cette rubrique. |
| type | Le type d’ID pour lequel vous avez demandé l’accès aux données en vertu du RGPD ou du CCPA. [!DNL Target] accepts several ID types, some of which are standard and some of which are specific to [!DNL Target]. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour [!DNL Target]?&quot; dans cette rubrique. |
| value | L’ID de l’espace de noms/la source de données. Voir « Quels ID sont pris en charge pour aider les clients à remplir une demande d’accès et de suppression en vertu du RGPD ou du CCPA pour [!DNL Target]?&quot; pour les valeurs acceptées. |
| integration code | Les codes d’intégration sont des noms conviviaux pour vos sources de données et vous aident à suivre vos sources de données plus facilement qu’en utilisant des ID de sources de données. |

Lorsque plusieurs valeurs sont fournies pour identifier des profils, chaque identifiant valide dispose d’un fichier de profil. Un ou plusieurs fichiers de profil sont envoyés au Azure Blob RGPD via l’API centrale RGPD, au format [!DNL Target] Réponse JSON du profil.

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
| Sample_Parameter | De nombreuses informations du profil [!DNL Target] sont chargées ou directement fournies par le responsable du traitement des données. Dans cet exemple, un paramètre a été chargé dans le profil [!DNL Target] à l’aide de l’API de mise à jour du profil. Pour plus d’informations, voir [Méthodes pour obtenir des données dans [!DNL Target]](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Ce champ standard inclut l’heure de la dernière visite récurrente d’un utilisateur. |
| firstSessionStart | Ce champ standard inclut l’heure de début de la première session de l’utilisateur. |
| user.sessionCountScript | De nombreuses informations du profil [!DNL Target] sont chargées ou directement fournies par le responsable du traitement des données. Dans cet exemple, un script de profil augmente le nombre de sessions que ce visiteur a initiées sur le site du contrôleur des données. Pour plus d’informations, voir [Attributs de script de profil](/help/main/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Cet exemple de code est une version abrégée d’une [!DNL Target] profile JSON à titre d’illustration. De nombreux champs du profil [!DNL Target] ne sont pas standard. Les données retournées dépendent des informations figurant dans ce profil de visiteur spécifique.

### Does [!DNL Target] support IP obfuscation? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] prend en charge l’obscurcissement des adresses IP si vous choisissez de l’utiliser dans le cadre de votre stratégie de mise en œuvre du RGPD ou du CCPA. Pour plus d’informations, voir [Confidentialité](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).

### Dois-je faire quelque chose pour empêcher que mes données ne soient partagées ou vendues à des tiers ?

[!DNL Target] ne permet pas aux clients de partager ou de vendre des données directement à partir de [!DNL Target] aux tiers, il n’y a donc pas d’opposition à la vente [!DNL Target].
