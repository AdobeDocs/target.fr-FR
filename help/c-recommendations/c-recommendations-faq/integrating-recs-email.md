---
keywords: e-mail;ESP;fournisseur de messagerie électronique;rawbox;API de diffusion;modèle de téléchargement uniquement;modèle d’e-mail;traitement par lots;e-mail au moment de la génération
description: Découvrez comment intégrer la messagerie électronique dans l’API Delivery Adobe [!DNL Target Recommendations], including using the [!DNL Target] , les modèles Rawbox et les modèles en téléchargement uniquement.
title: Comment intégrer Recommendations aux e-mails ?
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: ht
source-wordcount: '1712'
ht-degree: 100%

---

# ![PREMIUM](/help/assets/premium.png) Intégration de [!DNL Recommendations] aux e-mails

[!DNL Adobe Target] prend en charge la personnalisation au moment de l’envoi des recommandations dans les e-mails.

Trois méthodes sont disponibles pour intégrer [!DNL Target Recommendations] à votre fournisseur de service de messagerie (ESP). Les capacités de votre fournisseur de service de messagerie déterminent la méthode à utiliser. Votre gestionnaire de compte ou votre consultant peut vous aider à choisir l’option qui vous convient le mieux.

| Méthode | Détails |
| --- | --- |
| [Méthode 1 : [!DNL Adobe Target Delivery API]](#delivery-api) (privilégiée) | Utilisez l’[!DNL Adobe Target Delivery API] pour effectuer des demandes par client/par e-mail pour des recommandations. |
| [Méthode 2 :  [!DNL Adobe Rawbox API]](#rawbox) | Utilisez l’[!DNL Adobe Target Rawbox API] pour effectuer des demandes par client/par e-mail pour des recommandations. |
| [Méthode 3 : [!DNL Recommendations Download API]](#download-api) | Utilisez l’API de téléchargement Recommendations pour demander des recommandations en bloc pour une liste de produits ou de catégories au format CSV. |

L’utilisation de la méthode 1 ou de la méthode 2 nécessite que votre fournisseur de service de messagerie effectue des appels à une API externe par client/par e-mail et attende que le contenu soit renvoyé. Ces méthodes ne sont pas prises en charge par tous les fournisseurs de service de messagerie. Contactez votre fournisseur pour déterminer s’il est compatible avec ce modèle d’intégration.

L’utilisation de la méthode 3 nécessite que votre fournisseur de service de messagerie rejoigne une liste de recommandations par ID de produit ou ID de catégorie à votre liste d’e-mails. Cette méthode peut être basée sur un attribut tel que le dernier produit consulté par le client, le dernier produit acheté ou la catégorie la plus consultée. Cependant, votre fournisseur de service de messagerie doit avoir accès à ces données dans son profil client pour effectuer la jointure. Contactez votre fournisseur de service de messagerie pour déterminer s’il a accès à ces données et s’il est compatible avec ce modèle d’intégration.

La personnalisation en temps ouvert des recommandations n’est pas prise en charge par [!DNL Adobe Target].

>[!IMPORTANT]
>
>Les instructions de capacité suivantes s’appliquent aux méthodes de l’API de diffusion et de modèle d’e-mail rawbox décrites ci-dessous (méthodes 1 et 2) :
>
>* Une limitation du débit doit être appliquée aux 1 000 requêtes par seconde inférieures ou à 25 fois votre trafic de pointe quotidien.
>* Chaque minute, augmentez le trafic par incréments de 200 requêtes par seconde.

> 
>Contactez votre gestionnaire de compte si vous souhaitez utiliser des limites de débit plus élevées.

## Méthode 1 : utilisation de l’API de diffusion (privilégiée) {#delivery-api}

L’API de diffusion est une requête POST qui fonctionne avec un courrier électronique au moment de la génération. Cette option est la méthode privilégiée pour le courrier électronique au moment de la génération.

Peu de clients de messagerie autorisant les requêtes POST, il est déconseillé d’utiliser cette API pour les cas d’utilisation à l’ouverture. Certains clients de messagerie, dont Gmail et Outlook, peuvent mettre en cache le contenu ou bloquer l’image et exiger que le destinataire autorise l’image de manière proactive pour qu’elle s’affiche.

Vous ne pouvez pas renvoyer le contenu par défaut à l’aide de l’API de diffusion.

Le code suivant est un exemple de requête de diffusion d’API :

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

Où `clientcode` est votre code client [!DNL Target].

>[!NOTE]
>
>Veillez à renseigner une valeur unique pour `sessionId` et `tntId` ou `thirdPartyId` pour chaque destinataire d’e-mail (par exemple, pour chaque appel d’API). Si vous ne fournissez pas de valeurs uniques pour ces champs, la réponse de l’API peut ralentir ou échouer en raison du grand nombre d’événements générés dans un seul profil.

Pour plus d’informations, consultez la [documentation relative à l’API de diffusion](https://developers.adobetarget.com/api/#server-side-delivery).

## Méthode 2 : utilisation d’un modèle d’e-mail rawbox {#rawbox}

Une rawbox est identique à une demande de mbox, à ceci près qu’elle concerne les environnements non web, comme les fournisseurs de service de messagerie (ESP). Puisque vous n’utilisez pas de fichier [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js] dans les demandes de rawbox, vous devez créer les demandes manuellement. Consultez les exemples ci-dessous pour savoir comment fonctionnent les demandes de rawbox dans les e-mails.

>[!NOTE]
>
>Lors de l’utilisation d’une rawbox et de [!DNL Target], consultez l’avis de sécurité important sous [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à [!DNL Target]](/help/administrating-target/hosts.md#allowlist).

Cette approche vous permet de suivre les performances des recommandations dans les e-mails, de les tester normalement avec une recommandation et de continuer le suivi sur le site.

Configurez une activité [!DNL Recommendations] dans [!DNL Target] en utilisant l’option [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E). Pour l’emplacement, sélectionnez le nom de la mbox que vous avez choisi d’utiliser dans la demande de rawbox issue du fournisseur de service de messagerie électronique. Choisissez un modèle d’e-mail. Au moment de la création du message, le fournisseur de service de messagerie lance un appel aux serveurs [!DNL Target] pour chaque rawbox dans chaque message généré. Votre fournisseur de service de messagerie électronique doit avoir un moyen d’inclure le code HTML renvoyé dans le message électronique envoyé.

Le système de messagerie que vous utilisez doit pouvoir gérer les scénarios suivants :

### Une réponse valide est reçue, mais il n’y a aucune recommandation.

* Dans ce cas, la réponse correspond à la valeur du paramètre `mboxDefault` défini. Consultez l’explication de ce paramètre ci-dessous.
* Le fournisseur de services de messagerie doit avoir un bloc HTML de recommandations par défaut à utiliser dans ce cas.

### Le serveur [!DNL Target] expire et aucune donnée n’est renvoyée.

* Dans ce cas, le serveur [!DNL Target] renvoie le contenu suivant :

   `//ERROR: application server timeout`

* L’application de messagerie doit rechercher le texte et être capable de gérer l’erreur. Le fournisseur de services de messagerie électronique peut gérer ce cas de plusieurs façons :

   * Émettre immédiatement un autre appel de serveur (recommandé, éventuellement avec un compteur de tentatives)
   * Ignorer ce message électronique et passer au suivant
   * Mettre cet e-mail en file d’attente et réexécuter les e-mails en échec sous la forme d’un lot à la fin de la première exécution

### Exemple d’URL de requête

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Paramètres requis : {#reqparams}

>[!NOTE]
>
>Pour utiliser [!DNL Recommendations] dans un e-mail, l’appel Rawbox doit généralement inclure l’`entity.id` ou le `entity.categoryId`, ou les deux, selon le type de critère de recommandation. L’exemple d’appel ci-dessus inclut les deux paramètres.

| Paramètre | Valeur | Description | Validation |
|--- |--- |--- |--- |
| `client_code` | *client_code* | Code du client utilisé dans Recommendations. Votre conseiller Adobe peut vous fournir cette valeur. |  |
| `mbox` | *mboxName* | Nom de la mbox utilisée pour le ciblage. | Même validation que pour tous les appels de mbox.<br>250 caractères maximum.<br>Ne peut pas contenir les caractères suivants : `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | désactivé | Empêche la réponse de définir un cookie dans un environnement non web. |  |
| `entity.id`<br>(Requis pour certains types de critères : affichage/affichage, affichage/achat, achat/achat) | *entity_id* | productId sur lequel repose la recommandation (produit abandonné dans le panier ou achat précédent, par exemple).<br>Si le critère l’exige, l’appel de rawbox doit inclure le paramètre `entity.id`. |  |
| `entity.event.detailsOnly` | true | Si `entity.id` est transmis, il est vivement recommandé de transmettre également ce paramètre afin d’empêcher que la requête n’incrémente le nombre d’affichages de page comptés pour un article, et de ne pas fausser les algorithmes basés sur l’affichage des produits. |  |
| `entity.categoryId`<br>(Requis pour certains types de critères : les plus consultés par catégorie et les plus vendus par catégorie) | *category_id* | Catégorie sur laquelle repose la recommandation (meilleurs vendeurs dans une catégorie, par exemple).<br>Si le critère l’exige, l’appel de rawbox doit inclure le paramètre `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Si le paramètre `mboxNoRedirect` est absent, `mboxDefault` doit être une URL absolue qui renvoie le contenu par défaut si aucune recommandation n’est disponible. Il peut s’agir d’une image ou d’un autre contenu statique.<br>Si le paramètre `mboxNoRedirect` est présent, `mboxDefault` peut être n’importe quel texte indiquant qu’il n’y a aucune recommandation, par exemple `no_content`.<br>Le fournisseur de messagerie doit gérer le cas où cette valeur est renvoyée et insérer le code HTML par défaut dans l’e-mail. <br> **Bonne pratique en matière de sécurité** : si le domaine utilisé dans l’URL `mboxDefault` n’est pas placé sur la liste autorisée, vous pouvez être exposé à un risque de vulnérabilité de redirection ouverte. Pour éviter l’utilisation non autorisée de liens de redirection ou `mboxDefault` par des tiers, Adobe recommande d’utiliser des « hôtes autorisés » pour placer les domaines d’URL de redirection par défaut sur la liste autorisée. Target utilise des hôtes pour placer sur la liste autorisée les domaines vers lesquels vous souhaitez autoriser les redirections. Pour plus d’informations, consultez [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à  [!DNL Target]](/help/administrating-target/hosts.md#allowlist) dans *Hôtes*. |  |
| `mboxHost` | *mbox_host* | Domaine qui est ajouté à l’environnement par défaut (groupe d’hôtes) lors du déclenchement de l’appel. |  |
| `mboxPC` | Vide | (Obligatoire pour les recommandations qui utilisent un profil de visiteur.)<br>Si aucun « thirdPartyId » n’a été fourni, un nouvel tntId est généré et renvoyé dans la réponse. Sinon, il reste vide.<br>**Remarque** : veillez à fournir une valeur unique pour `mboxSession` et `mboxPC` pour chaque destinataire d’e-mail (par exemple, pour chaque appel API). Si vous ne fournissez pas de valeurs uniques pour ces champs, la réponse de l’API peut ralentir ou échouer en raison du grand nombre d’événements générés dans un seul profil. | 1 &lt; Longueur &lt; 128<br>ne peut pas contenir plus d’un seul « . » point ( . ).<br>Le seul point autorisé est utilisé pour le suffixe d’emplacement du profil. |

### Paramètres facultatifs

| Paramètre | Valeur | Description | Validation |
|--- |--- |--- |--- |
| `mboxPC`<br>(facultatif) | *mboxPCId* | Identifiant visiteur Target. Utilisez cette valeur pour effectuer le suivi du cycle complet d’un utilisateur qui revient sur votre site au cours de plusieurs visites ou lors de l’utilisation d’un paramètre de profil utilisateur.<br>Cette valeur doit correspondre au PCID [!DNL Adobe Target] réel de l’utilisateur, qui serait exporté du site web vers votre système GRC. Le fournisseur de services de messagerie récupère cet identifiant auprès de votre système GRC ou Data Warehouse, puis l’utilise comme valeur de ce paramètre.<br>La valeur `mboxPC` s’avère également utile pour le suivi du comportement des visiteurs du site au cours de plusieurs visites et pour le suivi des mesures quand une recommandation fait partie d’une activité A/B.<br>**Remarque** : veillez à fournir une valeur unique pour `mboxSession` et `mboxPC` pour chaque destinataire d’e-mail (par exemple, pour chaque appel API). Si vous ne fournissez pas de valeurs uniques pour ces champs, la réponse de l’API peut ralentir ou échouer en raison du grand nombre d’événements générés dans un seul profil. | 1 &lt; Longueur &lt; 128<br>Ne peut pas contenir plus d’un seul « . » point ( . ).<br>Le seul point autorisé est utilisé pour le suffixe d’emplacement du profil. |
| `mboxNoRedirect`<br>(facultatif) | 1 | Par défaut, l’appelant est redirigé quand aucun contenu livrable n’est trouvé. Utilisez-le pour désactiver le comportement par défaut. |  |
| `mbox3rdPartyId` | *xxx* | Utilisez cette option si vous utilisez votre propre ID de visiteur personnalisé pour le ciblage des profils. |  |

### Réponses potentielles du serveur [!DNL Target]

| Réponse | Description |
|--- |--- |
| //ERROR: | Générée par l’équilibreur de charge quand il ne peut renvoyer aucun contenu. |
| Succès | Le paramètre `mboxNoRedirect` est défini sur « true » (vrai) et le serveur ne renvoie aucune recommandation (c.-à-d. qu’il n’y a aucune correspondance pour la mbox ou que la mémoire cache du serveur n’est pas initialisée). |
| bad request | Il manque le paramètre `mbox`.<ul><li>Le paramètre `mboxDefault` ou `mboxNoRedirect` n’est pas spécifié.</li><li>Le paramètre de requête `mboxTrace` est spécifié, mais pas `mboxNoRedirect`.</li><li>Le paramètre `mboxTarget` n’est pas spécifié si les noms de mbox se terminent par le suffixe `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` non spécifié quand il n’existe aucune correspondance pour la demande et que le paramètre `mboxNoRedirect` n’est pas spécifié. |
| `Invalid mbox name:= MBOX_NAME` | Indique que le paramètre `mbox` contient des caractères incorrects. |
| `Mbox name [MBOX_NAME] is too long` | Indique que le paramètre `mbox` contient plus de 250 caractères. |

## Méthode 3 : utilisation de l’API de téléchargement Recommendations {#download-api}

Configurez une recommandation comme vous le faites habituellement, mais choisissez **télécharger uniquement** dans la section de présentation au lieu d’une combinaison modèle/mbox. Indiquez ensuite au fournisseur de services de messagerie le code de recommandation que vous avez créé. Le fournisseur de services de messagerie accède aux données de la recommandation au moyen d’une API. Ces données indiquent les articles à recommander pour une catégorie ou un article clé, tels que les articles d’un panier abandonné. Le fournisseur de services de messagerie stocke ces données, les associe à sa propre apparence, affiche des informations sur chaque article, puis les envoie dans les messages.

Avec cette option, le serveur de recommandations ne peut pas directement suivre les performances d’une recommandation, ni répartir le trafic entre plusieurs combinaisons algorithme/modèle. En outre, les recommandations ne sont liées à aucun profil du visiteur.

Pour plus d’informations sur l’API de téléchargement, voir  [API héritées > Téléchargement](/help/assets/adobe-recommendations-classic.pdf).
