---
description: Informations sur Target et la norme IETF samesite utilisée à partir de Google Chrome version 76.
keywords: google;samesite; cookies ; chrome 80 ; ietf
seo-description: Informations sur Adobe Target et la norme IETF samesite introduite avec Google Chrome version 80.
seo-title: Stratégies de cookie samesite d'Adobe Target et de Google
solution: Target
subtopic: Prise en main
title: Stratégies de cookie Google Chrome samesite
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Stratégies de cookie Google Chrome samesite

Google commence à imposer de nouvelles stratégies de cookie par défaut pour les utilisateurs commençant par Chrome 80, qui sont publiés début 2020. Cet article explique tout ce que vous devez savoir sur les nouvelles stratégies de cookies samesite, comment [!DNL Adobe Target] prend en charge ces stratégies et comment vous pouvez utiliser [!DNL Target] les nouvelles stratégies de cookies samesite de Google Chrome.

A compter de Chrome 80, les développeurs Web doivent spécifier explicitement les cookies pouvant fonctionner sur plusieurs sites Web. C'est la première des nombreuses annonces que Google prévoit d'effectuer pour améliorer la confidentialité et la sécurité sur le Web.

Compte tenu du fait que Facebook a eu accès à la confidentialité et à la sécurité, d'autres lecteurs majeurs tels qu'Apple, et maintenant Google, ont été rapidement capitalisés sur la possibilité de créer des identités en tant que défenseurs de la confidentialité et de la sécurité. Apple a dirigé le pack en annonçant d'abord les modifications apportées à ses stratégies de cookie début cette année via ITP 2.1 et récemment, ITP 2.2. Dans ITP 2.1, Apple bloque complètement les cookies tiers et conserve les cookies créés dans le navigateur pendant sept jours seulement. Dans ITP 2.2, les cookies sont conservés pendant un seul jour. L'annonce de Google n'est pas aussi agressive que celle d'Apple, mais c'est la première étape vers le même objectif final. Pour plus d'informations sur les stratégies Apple, voir [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Que sont les cookies et comment sont-ils utilisés ?

Avant d'analyser les modifications apportées à Google dans les stratégies de cookies, nous pouvons déterminer les cookies et leur mode d'utilisation. En d'autres termes, les cookies sont de petits fichiers texte stockés dans le navigateur Web qui sont utilisés pour mémoriser les attributs utilisateur.

Les cookies sont importants car ils améliorent l'expérience de l'utilisateur lorsqu'il navigue sur le Web. Par exemple, si vous faites des emplettes sur un site Web de commerce électronique et ajoutez un élément à votre panier, mais que vous ne vous connectez pas ou que vous ne vous connectez pas au cours de cette visite, les cookies mémorisent vos articles et les conservent dans votre panier pour votre prochaine visite. Vous pouvez également imaginer si vous avez à nouveau saisi votre nom d'utilisateur et votre mot de passe chaque fois que vous visitez votre site Web préféré sur les réseaux sociaux. Les cookies résolvent également ce problème, car ils stockent des informations qui aident les sites à identifier qui vous êtes. Ces types de cookies sont appelés cookies propriétaires, car ils sont créés et utilisés par le site Web que vous avez visité.

Des cookies tiers existent également. Pour mieux comprendre les choses, examinons cet exemple :

Imaginons qu'une société de réseaux sociaux hypothétique nommée « Amis » fournisse un bouton Partager que d'autres sites implémentent pour permettre aux utilisateurs d'amis de partager le contenu du site sur le flux Amis. Désormais, un utilisateur lit un article Actualités sur un site Web d'actualités qui utilise le bouton Partager et le clique pour publier automatiquement sur son compte Amis.

Pour ce faire, le navigateur récupère le bouton Partager le partage depuis `platform.friends.com` le chargement de l'article Actualités. Dans ce processus, le navigateur associe les cookies Amis, qui contiennent les informations d'identification de l'utilisateur connecté, à la demande aux serveurs Amis. Cela permet à Friends de publier l'article Actualités dans son flux au nom de l'utilisateur sans que l'utilisateur ne puisse se connecter.

Cela est possible à l'aide de cookies tiers. Dans ce cas, le cookie tiers est enregistré dans le navigateur pour `platform.friends.com`que cette publication `platform.friends.com` soit effectuée dans l'application Amis au nom de l'utilisateur.

Si vous imaginez un moment pour obtenir ce cas d'utilisation sans cookies tiers, l'utilisateur devra suivre de nombreuses étapes manuelles. Tout d'abord, l'utilisateur doit copier le lien vers l'article Actualités. Ensuite, l'utilisateur doit se connecter à l'application Amis séparément. Ensuite, l'utilisateur cliquait sur le bouton Créer une publication. Ensuite, l'utilisateur copiez et collez le lien dans le champ de texte, puis cliquez sur Publier. Comme vous pouvez le constater, les cookies tiers facilitent considérablement l'expérience de l'utilisateur en tant que procédure manuelle considérablement réduite.

En règle générale, les cookies tiers permettent de stocker les données dans le navigateur d'un utilisateur sans que l'utilisateur ne visite explicitement un site Web.

## Problèmes de sécurité

Bien que les cookies améliorent les expériences utilisateur et la publication de courant, ils peuvent également introduire des vulnérabilités de sécurité, telles que des attaques CSRF (Cross-Site Request Forgery). Si, par exemple, un utilisateur se connecte à un site bancaire pour payer les factures de carte de crédit et quitte le site sans se déconnecter puis se rend sur un site malveillant au cours de la même session, une attaque CSRF peut se produire. Le site malveillant peut inclure du code qui envoie une requête au site bancaire qui s'exécute au chargement de la page. Etant donné que l'utilisateur est toujours authentifié sur le site bancaire, le cookie de session peut être utilisé pour lancer une attaque CSRF afin de lancer un événement de transfert de financement en dehors du compte bancaire de l'utilisateur. En effet, chaque fois que vous visitez un site, tous les cookies sont joints dans la requête HTTP. En raison de ces problèmes de sécurité, Google tente désormais de les atténuer.

## Comment Target utilise-t-il les cookies ?

Ainsi, nous voyons comment [!DNL Target] utiliser les cookies. Pour ce faire, [!DNL Target] vous devez installer la bibliothèque [!DNL Target] JavaScript sur votre site. Cela vous permet de placer un cookie propriétaire sur le navigateur de l'utilisateur qui consulte votre site. Lorsque votre utilisateur interagit avec votre site Web, vous pouvez transmettre les données comportementales et d'intérêt de l'utilisateur à [!DNL Target] l'aide de la bibliothèque JavaScript. La bibliothèque [!DNL Target] JavaScript utilise des cookies propriétaires pour extraire des informations d'identification sur l'utilisateur à mettre en correspondance avec le comportement de l'utilisateur et les données d'intérêt. Ces données sont ensuite utilisées par [!DNL Target] pour alimenter vos activités de personnalisation.

Target utilise également des cookies tiers. Si vous possédez plusieurs sites Web qui vivent sur des domaines différents et que vous souhaitez suivre le parcours des utilisateurs sur ces sites Web, vous pouvez utiliser des cookies tiers en exploitant le suivi inter-domaines. En activant le suivi inter-domaines dans la bibliothèque [!DNL Target] JavaScript, votre compte commencera à utiliser des cookies tiers. Lorsqu'un utilisateur passe d'un domaine à un autre, le navigateur communique avec le serveur principal de [!DNL Target]. Dans ce processus, un cookie tiers est créé et placé dans le navigateur de l'utilisateur. Grâce au cookie tiers qui réside dans le navigateur de l'utilisateur, [!DNL Target] il peut offrir une expérience cohérente dans différents domaines pour un utilisateur unique.

## Nouvelle recette de cookie de Google

Pour protéger les cookies lorsque des cookies sont envoyés sur plusieurs sites, Google prévoit d'ajouter la prise en charge d'une norme IETF appelée samesite, ce qui nécessite que les développeurs Web gèrent les cookies avec le composant d'attribut samesite dans l'en-tête Set-Cookie.

Il existe trois valeurs différentes qui peuvent être transmises à l’attribut samesite : Strict, Lax (Permissif) ou None (Aucun).

| Valeur | Description |
| --- | --- |
| Strict | Les cookies avec ce paramètre sont accessibles uniquement lors de la visite du domaine sur lequel il a été initialement défini. En d’autres termes, Strict empêche complètement le cookie d’être utilisé sur plusieurs sites. Cette option est préférable pour les applications nécessitant une sécurité élevée, telles que les banques. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. C'est pourquoi cette option est utilisée si le cookie peut être utilisé par des tiers, mais avec un avantage de sécurité qui protège les utilisateurs contre les attaques CSRF. |
| None | Les cookies avec ce paramètre fonctionnent de la même manière que les cookies aujourd'hui. |

En gardant à l'esprit ce qui précède, Chrome 80 propose deux paramètres indépendants pour les utilisateurs : « Samesite par défaut » et « Cookies sans samesite doivent être sécurisés.  » » Ces paramètres seront activés par défaut dans Chrome 80.

![Boîte de dialogue samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Samesite par défaut : Lorsqu'elle est définie, tous les cookies qui n'indiquent pas l'attribut samesite seront automatiquement utilisés**.`SameSite = Lax`
* **Les cookies sans samesite doivent être sécurisés**: Lorsqu'elle est définie, les cookies sans l'attribut samesite ou dont `SameSite = None` la protection doit être sécurisée. Dans ce contexte, toutes les demandes de navigateur doivent respecter le protocole HTTPS. Les cookies qui ne respectent pas cette exigence sont rejetés. Tous les sites Web doivent utiliser HTTPS pour répondre à cette exigence.

## Target respecte les bonnes pratiques de sécurité de Google

Chez Adobe, nous voulons toujours prendre en charge les meilleures pratiques de sécurité et de confidentialité du secteur. We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

Pour le paramètre « samesite par défaut », [!DNL Target] continuera à fournir la personnalisation sans aucun impact et intervention de votre part. [!DNL Target] utilise des cookies propriétaires et continuera à fonctionner correctement lorsque l’indicateur `SameSite = Lax` est appliqué par Google Chrome.

Pour l'option « Cookies sans samesite doit être sécurisé », si vous n'incluez pas la fonction de suivi inter-domaines dans [!DNL Target], les cookies propriétaires continueront [!DNL Target] de fonctionner.

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. Cela signifie que vous devez vous assurer que vos sites utilisent le protocole HTTPS. Les bibliothèques côté client activent [!DNL Target] automatiquement le protocole HTTPS et attachent les indicateurs `SameSite = None` et les indicateurs Secure à des cookies tiers afin [!DNL Target] de garantir que toutes les activités continuent de diffuser.

## Que dois-je faire ?

Pour comprendre ce que vous devez faire pour [!DNL Target] continuer à travailler pour les utilisateurs de Google Chrome 80 +, consultez le tableau ci-dessous, dont vous verrez les colonnes suivantes :

* **Bibliothèque JavaScript Target**: Si vous utilisez mbox. js, at. js 1.*x* ou at.js 2.*x* sur vos sites.
* **Samesite par défaut cookies = Activé**: Si les cookies par défaut sont activés pour vos utilisateurs, comment cela s'applique-t-il à vous et qu'il y a tout ce que vous devez faire pour [!DNL Target] continuer à travailler.
* **Les cookies sans samesite doivent être sécurisés = Activé**: Si vos utilisateurs disposent de « Cookies sans samesite doivent être sécurisés », comment cela s'applique-t-il à vous et qu'il y a tout ce que vous devez faire pour [!DNL Target] continuer à travailler.

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox. js avec cookies propriétaires uniquement. | Aucun impact. | Aucun impact si vous n'utilisez pas le suivi inter-domaines. |
| mbox. js avec suivi inter-domaines activé. | Aucun impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers possèdent `SameSite = None` un indicateur et un indicateur Secure. L'indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| at.js 1.*x* avec cookie propriétaire. | Aucun impact. | Aucun impact si vous n'utilisez pas le suivi inter-domaines. |
| at.js 1.*x* avec le suivi inter-domaines activé. | Aucun impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers possèdent `SameSite = None` un indicateur et un indicateur Secure. L'indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Que fait Target ?

Que devons-nous faire dans notre plate-forme pour vous aider à vous conformer aux nouvelles stratégies de cookies Google Chrome 80 + samesite ?

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox. js avec cookies propriétaires uniquement. | Aucun impact. | Aucun impact si vous n'utilisez pas le suivi inter-domaines. |
| mbox. js avec suivi inter-domaines activé. | Aucun impact. | [!DNL Target] ajoute `SameSite = None` et secure indicateur au cookie tiers lorsque [!DNL Target] les serveurs sont appelés. |
| at.js 1.*x* avec cookie propriétaire. | Aucun impact. | Aucun impact si vous n'utilisez pas le suivi inter-domaines. |
| at.js 1.*x* avec le suivi inter-domaines activé. | Aucun impact. | at.js 1.*x* avec le suivi inter-domaines activé. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Quel est l'impact si vous ne passez pas à l'utilisation du protocole HTTPS ?

Le seul cas d'utilisation cela affectera vous-même si vous utilisez la fonction de suivi inter-domaines dans [!DNL Target] mbox. js ou at. js 1.*x*. Sans passer au protocole HTTPS, qui est une exigence de Google, vous constaterez un pic de visiteurs uniques dans vos domaines, car le cookie tiers utilisé sera abandonné par Google. Et comme le cookie tiers est abandonné, [!DNL Target] ne permet pas de fournir une expérience cohérente et personnalisée à cet utilisateur lorsque l'utilisateur navigue d'un domaine à l'autre. Le cookie tiers est principalement utilisé pour identifier un seul utilisateur qui navigue sur les domaines que vous possédez.

## Conclusion

Tandis que le secteur fait des progrès pour créer un Web plus sécurisé pour les consommateurs, [!DNL Adobe] il est absolument attaché à aider nos clients à fournir des expériences personnalisées de manière à garantir la sécurité et la confidentialité de la fin - les utilisateurs. Il vous suffit de suivre les pratiques recommandées mentionnées ci-dessus et de tirer parti [!DNL Target] des nouvelles stratégies de cookies samesite de Google Chrome.
