---
keywords: e-mail;ESP;fournisseur de messagerie électronique;rawbox;API de diffusion;modèle de téléchargement uniquement;modèle d’e-mail;traitement par lots;e-mail au moment de la génération
description: Découvrez comment intégrer la messagerie à Adobe [!DNL Target Recommendations], notamment en utilisant l’API de diffusion [!DNL Target], les modèles rawbox et les modèles de téléchargement uniquement.
title: Comment intégrer Recommandations aux e-mails ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 25%
---
# Intégrer [!DNL Recommendations] à la messagerie {#integrate-recs-email}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez les méthodes d’intégration de [!DNL Target Recommendations] à un fournisseur de service de messagerie (ESP) pour la personnalisation de l’heure d’envoi des recommandations par e-mail.

>[!ENDSHADEBOX]

[!DNL Adobe Target] prend en charge la personnalisation au moment de l’envoi des recommandations dans les e-mails. La personnalisation en temps ouvert des recommandations n’est pas prise en charge.

Trois méthodes sont disponibles pour intégrer [!DNL Target Recommendations] à un fournisseur de service de messagerie. Les fonctionnalités du fournisseur de service de messagerie déterminent la méthode à utiliser, et le gestionnaire de compte ou le consultant peut vous aider à choisir la meilleure option.

| Méthode | Détails |
| --- | --- |
| [Méthode 1 : [!DNL Adobe Target Delivery API]](#delivery-api) (privilégiée) | Utilisez [!DNL Adobe Target Delivery API] pour effectuer des demandes de recommandations par client et par e-mail. |
| [Méthode 2 :  [!DNL Adobe Rawbox API]](#rawbox) | Utilisez [!DNL Adobe Target Rawbox API] pour effectuer des demandes de recommandations par client et par e-mail. |
| [Méthode 3 : [!DNL Recommendations Download API]](#download-api) | Utilisez [!DNL Recommendations Download API] pour demander des recommandations en bloc pour une liste de produits ou de catégories au format CSV. |

Les méthodes 1 et 2 nécessitent que l’ESP effectue des appels à une API externe par client et par e-mail, et qu’il attende que le contenu soit renvoyé. Tous les fournisseurs de service de messagerie ne prennent pas en charge ces méthodes. Vous devez donc contacter le fournisseur pour déterminer s’il est compatible avec ce modèle d’intégration.

La méthode 3 nécessite que le fournisseur de service de messagerie rejoigne une liste de recommandations par ID de produit ou ID de catégorie à la liste des e-mails. Cette jointure peut être basée sur un attribut tel que le dernier produit consulté, le dernier produit acheté ou la catégorie la plus consultée du client. Le fournisseur de service de messagerie doit avoir accès à ces données dans son profil client pour effectuer la jointure. Il doit donc être contacté pour déterminer s’il a accès à ces données et s’il est compatible avec ce modèle d’intégration.

>[!IMPORTANT]
>
>Les instructions de capacité suivantes s’appliquent aux méthodes de l’API de diffusion et du modèle d’e-mail rawbox (méthodes 1 et 2) :
>
>* Le débit des requêtes doit être limité à la plus faible des 1 000 requêtes par seconde ou 25 fois le trafic quotidien de pointe.
>* Le trafic doit être augmenté par paliers de 200 requêtes par seconde chaque minute.
>
>Pour utiliser des limites de taux plus élevées, contactez le gestionnaire de compte.

## Méthode 1 : utilisation de l’API de diffusion (privilégiée) {#delivery-api}

L’API de diffusion est une requête POST qui fonctionne avec les e-mails au moment de la création. Cette option est la méthode privilégiée pour le courrier électronique au moment de la génération.

La plupart des clients de messagerie n’autorisant pas les requêtes POST, cette API n’est pas recommandée pour les cas d’utilisation à l’ouverture. Certains clients de messagerie, tels que Gmail ou Outlook, peuvent mettre en cache le contenu ou bloquer l’image et exiger que le destinataire autorise l’image de manière proactive pour qu’elle s’affiche.

Le contenu par défaut ne peut pas être renvoyé avec l’API de diffusion.

Le code suivant est un exemple de requête de diffusion d’API, où `clientcode` est le code client [!DNL Target] :

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

>[!NOTE]
>
>Fournissez une valeur unique pour `sessionId` et pour `tntId` ou `thirdPartyId` pour chaque destinataire d’e-mail (pour chaque appel API). Sans valeurs uniques pour ces champs, la réponse de l’API peut ralentir ou échouer en raison du grand nombre d’événements générés dans un seul profil.

Pour plus d’informations, consultez la [documentation de l’API de diffusion](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=fr){target=_blank}.

## Méthode 2 : utilisation d’un modèle d’e-mail rawbox {#rawbox}

Une rawbox est similaire à une demande de mbox, à ceci près qu’elle concerne les environnements non web, tels que les fournisseurs de service de messagerie (ESP). [!DNL Adobe Experience Platform Web SDK] et [!DNL at.js] ne sont pas disponibles pour les demandes de rawbox, les demandes doivent donc être créées manuellement. Les exemples suivants expliquent comment utiliser les demandes de rawbox dans les e-mails.

Cette approche permet de suivre les performances des recommandations dans les e-mails, de les tester normalement avec une recommandation et de poursuivre le suivi sur le site.

>[!NOTE]
>
>Lors de l’utilisation d’une rawbox et de [!DNL Target], consultez l’avis de sécurité important sous [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

1. Configurez une activité [!DNL Recommendations] dans [!DNL Target], avec l’option [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

1. Pour l’emplacement , sélectionnez le nom de la mbox utilisée dans la demande de rawbox provenant du fournisseur de service de messagerie.

1. Sélectionnez une conception qui offre l’aspect souhaité pour l’e-mail.

Au moment de la création du message, le fournisseur de service de messagerie lance un appel aux serveurs [!DNL Target] pour chaque rawbox dans chaque message généré. Le fournisseur de service de messagerie doit avoir un moyen d’inclure l’HTML renvoyée dans l’e-mail envoyé.

Le système de messagerie doit être en mesure de gérer les scénarios suivants.

### Une réponse valide est reçue, mais il n’y a aucune recommandation.

* La réponse est la valeur définie dans le paramètre `mboxDefault`. Voir la description de ce paramètre dans le tableau des paramètres requis.
* Le fournisseur de services de messagerie doit avoir un bloc HTML de recommandations par défaut à utiliser dans ce cas.

### Le serveur [!DNL Target] expire et aucune donnée n’est renvoyée.

* Le serveur [!DNL Target] renvoie le contenu suivant :

  `//ERROR: application server timeout`

* L’application de messagerie doit rechercher le texte et être capable de gérer l’erreur. Le fournisseur de services de messagerie électronique peut gérer ce cas de plusieurs façons :

  * Émettre immédiatement un autre appel de serveur (recommandé, éventuellement avec un compteur de tentatives)
  * Ignorer cet e-mail et passer au suivant.
  * Mettre cet e-mail en file d’attente et réexécuter les e-mails en échec sous forme de lot à la fin de l’exécution initiale.

### Exemple d’URL de requête

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Paramètres requis {#reqparams}

>[!NOTE]
>
>Pour utiliser [!DNL Recommendations] dans un e-mail, l’appel Rawbox doit généralement inclure l’élément `entity.id` ou le `entity.categoryId`, ou les deux, selon le type de critère de recommandation. L’exemple d’appel ci-dessus inclut les deux paramètres.

| Paramètre | Valeur | Description | Validation |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Code client utilisé dans [!DNL Recommendations]. Le consultant Adobe peut fournir cette valeur. |  |
| `mbox` | *mboxName* | Nom de la mbox utilisée pour le ciblage. | Même validation que pour tous les appels de mbox.<br>250 caractères max.<br>Ne peut pas contenir les caractères suivants : `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | désactivé | Empêche la réponse de définir un cookie dans un environnement non web. |  |
| `entity.id`<br>(Requis pour certains types de critères : affichage/affichage, affichage/achat, achat/achat) | *entity_id* | ProductId sur lequel la recommandation est basée, par exemple un produit abandonné dans le panier ou un achat précédent.<br>Si le critère l’exige, l’appel de rawbox doit inclure le paramètre `entity.id`. |  |
| `entity.event.detailsOnly` | true | Si `entity.id` est transmis, il est vivement recommandé de transmettre ce paramètre pour empêcher la requête d’incrémenter le nombre de pages vues comptabilisées pour un élément, afin de ne pas biaiser les algorithmes basés sur les pages vues du produit. |  |
| `entity.categoryId`<br>(Requis pour certains types de critères : les plus consultés par catégorie et les plus vendus par catégorie) | *category_id* | Catégorie sur laquelle est basée la recommandation (par exemple, les objets les plus vendus dans une catégorie).<br>Si le critère l’exige, l’appel de rawbox doit inclure le paramètre `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Si le paramètre `mboxNoRedirect` est absent, `mboxDefault` doit être une URL absolue qui renvoie le contenu par défaut si aucune recommandation n’est disponible. Il peut s’agir d’une image ou d’un autre contenu statique.<br>Si le paramètre `mboxNoRedirect` est présent, `mboxDefault` peut être n’importe quel texte indiquant qu’il n’y a aucune recommandation, par exemple `no_content`.<br>Le fournisseur de messagerie doit gérer le cas où cette valeur est renvoyée et insérer l’HTML par défaut dans l’e-mail.<br>Voir les bonnes pratiques de sécurité sous les tableaux. |  |
| `mboxHost` | *mbox_host* | Domaine qui est ajouté à l’environnement par défaut (groupe d’hôtes) lors du déclenchement de l’appel. |  |
| `mboxPC` | Vide | (Obligatoire pour les recommandations qui utilisent le profil d’un visiteur.)<br>Si aucun « thirdPartyId » n’a été fourni, un nouvel tntId est généré et renvoyé dans le cadre de la réponse. Dans le cas contraire, la valeur reste vide.<br>Voir la remarque sur les valeurs uniques sous les tableaux. | 1 &lt; Longueur &lt; 128<br>Ne peut pas contenir plus d’un seul « . » (point).<br>Le seul point autorisé est pour le suffixe de l&#39;emplacement du profil. |

### Paramètres facultatifs

| Paramètre | Valeur | Description | Validation |
|--- |--- |--- |--- |
| `mboxPC`<br>(facultatif) | *mboxPCId* | L’identifiant visiteur [!DNL Target]. Utilisez cette valeur pour effectuer le suivi d’un utilisateur en cercle complet sur le site au cours de plusieurs visites ou lors de l’utilisation d’un paramètre de profil utilisateur.<br>Cette valeur doit correspondre au PCID [!DNL Adobe Target] réel de l&#39;utilisateur, qui est exporté du site web vers le CRM. Le fournisseur de services de messagerie récupère cet identifiant à partir du CRM ou de l’entrepôt de données et l’utilise comme valeur de ce paramètre.<br>La valeur `mboxPC` est également utile pour le suivi du comportement des visiteurs du site au cours de plusieurs visites et pour le suivi des mesures, lorsqu’une recommandation fait partie d’une activité A/B.<br>Voir la remarque sur les valeurs uniques sous les tableaux. | 1 &lt; Longueur &lt; 128<br>Ne peut pas contenir plus d’un seul « . » (point).<br>Le seul point autorisé est pour le suffixe de l&#39;emplacement du profil. |
| `mboxNoRedirect`<br>(facultatif) | 1 | Par défaut, l’appelant est redirigé quand aucun contenu livrable n’est trouvé. Utilisez ce paramètre pour désactiver le comportement par défaut. |  |
| `mbox3rdPartyId` | *xxx* | Utilisez cette option pour spécifier un identifiant visiteur personnalisé pour le ciblage du profil. |  |

Pour `mboxSession` et `mboxPC`, fournissez une valeur unique pour chaque destinataire d’e-mail (pour chaque appel API). Sans valeurs uniques pour ces champs, la réponse de l’API peut ralentir ou échouer en raison du grand nombre d’événements générés dans un seul profil.

En guise de bonne pratique de sécurité pour `mboxDefault`, utilisez des hôtes autorisés pour placer sur la liste autorisée les domaines d&#39;URL de redirection par défaut. Si le domaine utilisé dans l’URL `mboxDefault` n’est pas, le risque d’une vulnérabilité de redirection ouverte peut être exposé. Les hôtes autorisés évitent l&#39;utilisation non autorisée de liens de redirection ou `mboxDefault` par des tiers. [!DNL Target] utilise des hôtes pour placer sur la liste autorisée les domaines vers lesquels les redirections sont autorisées. Pour plus d’informations, reportez-vous à l’avis de sécurité au début de cette section.

### Réponses potentielles du serveur [!DNL Target]

| Réponse | Description |
|--- |--- |
| //ERROR: | Généré par la répartition de charge lorsqu’elle ne peut pas renvoyer de contenu. |
| Succès | Le paramètre `mboxNoRedirect` est défini sur « true » et le serveur ne renvoie aucune recommandation (il n’existe aucune correspondance pour la mbox ou le cache du serveur n’est pas initialisé). |
| bad request | Il manque le paramètre `mbox`.<ul><li>Le paramètre `mboxDefault` ou `mboxNoRedirect` n’est pas spécifié.</li><li>Le paramètre de requête `mboxTrace` est spécifié, mais `mboxNoRedirect` ne l&#39;est pas.</li><li>Le paramètre `mboxTarget` n’est pas spécifié lorsque les noms de mbox se terminent par le suffixe `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` n’est pas spécifié lorsqu’il n’existe aucune correspondance pour la requête et que le paramètre `mboxNoRedirect` n’est pas spécifié. |
| `Invalid mbox name:= MBOX_NAME` | Le paramètre `mbox` contient des caractères non valides. |
| `Mbox name [MBOX_NAME] is too long` | Le paramètre `mbox` dépasse 250 caractères. |

## Méthode 3 : utilisation de l’API de téléchargement de Recommandations {#download-api}

Configurez une recommandation comme vous le faites habituellement, mais choisissez **télécharger uniquement** dans la section de présentation au lieu d’une combinaison modèle/mbox. Fournissez ensuite au fournisseur de service de messagerie l’identifiant de la recommandation qui a été créée. Le fournisseur de service de messagerie accède aux données de recommandation par le biais de l’API. Ces données indiquent les articles à recommander pour une catégorie ou un article clé, tels que les articles d’un panier abandonné. L’ESP stocke ces données, les connecte avec sa propre apparence, affiche des informations sur chaque élément et les diffuse dans les e-mails.

Avec cette option, le serveur de recommandations ne peut pas suivre directement les performances d’une recommandation ou répartir le trafic entre plusieurs combinaisons d’algorithmes et de modèles. En outre, les recommandations ne sont liées à aucun profil du visiteur.

Pour plus d’informations sur l’API de téléchargement, consultez [API héritées > Téléchargement](/help/main/assets/adobe-recommendations-classic.pdf).
