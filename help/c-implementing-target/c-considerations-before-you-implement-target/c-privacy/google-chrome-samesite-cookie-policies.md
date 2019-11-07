---
keywords: google;samesite;cookies;chrome 80;ietf
description: Informations sur Adobe Target et la norme IETF samesite introduite avec Google Chrome version 80.
title: Stratégies de cookies Adobe Target et Google MameSite
subtopic: Prise en main
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Stratégies de cookie Google Chrome samesite

Google va commencer à imposer de nouvelles stratégies de cookies par défaut pour les utilisateurs à partir de Chrome 80, qui devrait être publié début 2020. Cet article explique tout ce que vous devez savoir sur les nouvelles stratégies de cookies SameSite, comment [!DNL Adobe Target] prend en charge ces stratégies et comment vous pouvez les utiliser [!DNL Target] pour vous conformer aux nouvelles stratégies de cookies SameSite de Google Chrome.

A partir de Chrome 80, les développeurs Web doivent spécifier explicitement quels cookies peuvent fonctionner sur les sites Web. C'est la première de nombreuses annonces que Google prévoit de faire pour améliorer la confidentialité et la sécurité sur le Web.

Étant donné que Facebook a été à la pointe en matière de confidentialité et de sécurité, d'autres acteurs majeurs tels qu'Apple, et maintenant Google, ont rapidement profité de l'opportunité de créer de nouvelles identités en tant que champions de la confidentialité et de la sécurité. Apple a dirigé le pack en annonçant d’abord des modifications à ses politiques de cookies au début de l’année via ITP 2.1 et récemment, ITP 2.2. Dans ITP 2.1, Apple bloque complètement les cookies tiers et conserve les cookies créés dans le navigateur pendant seulement sept jours. Dans ITP 2.2, les cookies ne sont conservés que pendant une journée. L’annonce de Google est loin d’être aussi agressive que celle d’Apple, mais c’est la première étape vers le même objectif final. Pour plus d’informations sur les stratégies d’Apple, voir [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Que sont les cookies et comment sont-ils utilisés ?

Avant de nous plonger dans les modifications apportées par Google à ses stratégies de cookies, nous allons nous intéresser à ce que sont les cookies et à leur utilisation. En d’autres termes, les cookies sont de petits fichiers texte stockés dans le navigateur Web et utilisés pour mémoriser les attributs utilisateur.

Les cookies sont importants car ils améliorent l’expérience de l’utilisateur lorsqu’il navigue sur le Web. Par exemple, si vous faites vos achats sur un site Web de commerce électronique et ajoutez quelque chose à votre panier, mais que vous ne vous connectez pas ou n’achetez pas au cours de cette visite, les cookies mémorisent vos articles et les conservent dans votre panier pour votre prochaine visite. Ou imaginez que vous soyez obligé de saisir à nouveau votre nom d'utilisateur et votre mot de passe chaque fois que vous visitez votre site de médias sociaux préféré. Les cookies résolvent également ce problème, car ils stockent des informations qui aident les sites à identifier votre identité. Ces types de cookies sont appelés cookies propriétaires car ils sont créés et utilisés par le site Web que vous avez visité.

Des cookies tiers existent également. Pour mieux les comprendre, prenons l’exemple suivant :

Supposons qu’une hypothétique société de médias sociaux appelée "Amis" propose un bouton Partager que d’autres sites mettent en oeuvre pour permettre aux utilisateurs de partager le contenu du site sur le flux Amis. Désormais, un utilisateur lit un article d’actualité sur un site Web d’actualités qui utilise le bouton Partager et clique dessus pour le publier automatiquement sur son compte Amis.

Pour ce faire, le navigateur récupère le bouton Partager des amis `platform.friends.com` au chargement de l’article d’actualité. Au cours de ce processus, le navigateur associe les cookies Amis, qui contiennent les informations d’identification de l’utilisateur, à la requête envoyée aux serveurs Amis. Cela permet aux Amis de publier l’article d’actualité dans son flux pour le compte de l’utilisateur sans exiger de l’utilisateur qu’il se connecte.

Tout cela est possible en utilisant des cookies tiers. Dans ce cas, le cookie tiers est enregistré dans le navigateur pour `platform.friends.com`permettre à `platform.friends.com` l’utilisateur d’effectuer la publication dans l’application Amis.

Si vous imaginez un instant comment réaliser cette utilisation sans cookies tiers, l'utilisateur devra suivre de nombreuses étapes manuelles. Tout d'abord, l'utilisateur doit copier le lien vers l'article d'actualité. Ensuite, l’utilisateur doit se connecter séparément à l’application Amis. Ensuite, l’utilisateur cliquera sur le bouton Créer une publication. Ensuite, l’utilisateur copiait et collait le lien dans le champ de texte, puis, enfin, cliquez sur Publier. Comme vous pouvez le constater, les cookies tiers aident énormément l’utilisateur à faire l’expérience, car les étapes manuelles peuvent être considérablement réduites.

De manière plus générale, les cookies tiers permettent de stocker les données dans le navigateur d’un utilisateur sans exiger qu’il visite explicitement un site Web.

## Problèmes de sécurité

Bien que les cookies améliorent l’expérience des utilisateurs et la publicité sur l’alimentation, ils peuvent également introduire des vulnérabilités de sécurité telles que les attaques CSRF (Cross-Site Request Forgery). Par exemple, si un utilisateur se connecte à un site bancaire pour payer des factures de carte de crédit et quitte le site sans se déconnecter, puis accède à un site malveillant au cours de la même session, une attaque CSRF peut se produire. Le site malveillant peut inclure le code qui envoie une requête au site bancaire qui s’exécute au chargement de la page. L’utilisateur étant toujours authentifié sur le site bancaire, le cookie de session peut être utilisé pour lancer une attaque CSRF afin de déclencher un événement de transfert de fonds en dehors du compte bancaire de l’utilisateur. En effet, chaque fois que vous visitez un site, tous les cookies sont joints dans la requête HTTP. Et à cause de ces problèmes de sécurité, Google tente maintenant de les atténuer.

## Comment Target utilise-t-il les cookies ?

Ceci dit, voyons comment [!DNL Target] utilise les cookies. Pour pouvoir utiliser [!DNL Target] en premier lieu, vous devez installer la bibliothèque [!DNL Target] JavaScript sur votre site. Vous pouvez ainsi placer un cookie propriétaire dans le navigateur de l’utilisateur qui visite votre site. Lorsque votre utilisateur interagit avec votre site Web, vous pouvez transmettre les données de comportement et d’intérêt de l’utilisateur à [!DNL Target] travers la bibliothèque JavaScript. La bibliothèque [!DNL Target] JavaScript utilise des cookies propriétaires pour extraire des informations d’identification sur l’utilisateur afin de les mapper au comportement et aux données d’intérêt de l’utilisateur. Ces données sont ensuite utilisées par [!DNL Target] pour alimenter vos activités de personnalisation.

Target utilise également (parfois) des cookies tiers. Si vous possédez plusieurs sites Web qui résident sur des domaines différents et que vous souhaitez suivre le parcours des utilisateurs sur ces sites Web, vous pouvez utiliser des cookies tiers en exploitant le suivi inter-domaines. En activant le suivi inter-domaines dans la bibliothèque [!DNL Target] JavaScript, votre compte commencera à utiliser des cookies tiers. Lorsqu’un utilisateur passe d’un domaine à un autre, le navigateur communique avec le serveur principal de [!DNL Target]et, dans ce processus, un cookie tiers est créé et placé dans le navigateur de l’utilisateur. Grâce au cookie tiers qui réside dans le navigateur de l’utilisateur, [!DNL Target] vous pouvez offrir une expérience cohérente sur différents domaines pour un utilisateur unique.

## Nouvelle recette de cookie de Google

Afin d’offrir des protections contre l’envoi de cookies sur les sites pour que les utilisateurs soient protégés, Google prévoit d’ajouter la prise en charge d’une norme IETF appelée SameSite, qui oblige les développeurs Web à gérer les cookies avec le composant d’attribut MêmeSite dans l’en-tête Set-Cookie.

Il existe trois valeurs différentes qui peuvent être transmises à l’attribut samesite : Strict, Lax (Permissif) ou None (Aucun).

| Valeur | Description |
| --- | --- |
| Strict | Les cookies avec ce paramètre sont accessibles uniquement lors de la visite du domaine sur lequel il a été initialement défini. En d’autres termes, Strict empêche complètement le cookie d’être utilisé sur plusieurs sites. Cette option est préférable pour les applications nécessitant une haute sécurité, comme les banques. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. Par conséquent, cette option serait utilisée si le cookie pouvait être utilisé par des tiers, mais avec un avantage de sécurité supplémentaire qui protège les utilisateurs contre les attaques CSRF. |
| None | Les cookies associés à ce paramètre fonctionnent de la même manière que les cookies aujourd’hui. |

En gardant à l’esprit ce qui précède, Chrome 80 introduit deux paramètres indépendants pour les utilisateurs : "Les cookies du même site par défaut" et "les cookies sans le même site doivent être sécurisés". Ces paramètres seront activés par défaut dans Chrome 80.

![Même site, boîte de dialogue](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Même site par défaut, cookies**: Lorsqu’il est défini, tous les cookies qui ne spécifient pas l’attribut Même site sont automatiquement forcés d’utiliser `SameSite = Lax`.
* **Les cookies sans SameSite doivent être sécurisés**: Lorsqu’il est défini, les cookies sans attribut MêmeSite ou avec `SameSite = None` besoin d’être sécurisés. Dans ce contexte, toutes les demandes de navigateur doivent respecter le protocole HTTPS. Les cookies qui ne respectent pas cette exigence sont rejetés. Tous les sites Web doivent utiliser HTTPS pour répondre à cette exigence.

## Target respecte les bonnes pratiques de sécurité de Google

Chez Adobe, nous souhaitons toujours prendre en charge les meilleures pratiques du secteur en matière de sécurité et de confidentialité. We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

Pour le paramètre "Même site par défaut", [!DNL Target] continuez à fournir la personnalisation sans impact ni intervention de votre part. [!DNL Target] utilise des cookies propriétaires et continuera à fonctionner correctement lorsque l’indicateur `SameSite = Lax` est appliqué par Google Chrome.

Pour l’option "Les cookies sans SiteIdentique doivent être sécurisés", si vous ne vous inscrivez pas à la fonctionnalité de suivi inter-domaines dans [!DNL Target], les cookies propriétaires dans [!DNL Target] continueront à fonctionner.

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. Cela signifie que vous devez vous assurer que vos sites utilisent le protocole HTTPS. Les bibliothèques côté client dans [!DNL Target] utiliseront automatiquement le protocole HTTPS et associeront les indicateurs `SameSite = None` et Secure aux cookies tiers dans [!DNL Target] pour s’assurer que toutes les activités continuent à être diffusées.

## Que dois-je faire ?

Pour comprendre ce que vous devez faire pour que [!DNL Target] les utilisateurs de Google Chrome 80+ continuent à travailler, consultez le tableau ci-dessous, dont vous verrez les colonnes suivantes :

* **Bibliothèque** JavaScript Target : Si vous utilisez mbox.js, at.js 1.*x* ou at.js 2.*x* sur vos sites.
* **Même site par défaut cookies = Activé**: Si les cookies "Même site par défaut" sont activés pour vos utilisateurs, quel impact cela a-t-il sur vous et y a-t-il quelque chose à faire pour [!DNL Target] continuer à fonctionner ?
* **Les cookies sans SameSite doivent être sécurisés = Activé**: Si l’option "Cookies sans SameSite doivent être sécurisés" est activée pour vos utilisateurs, quel impact cela a-t-il sur vous et qu’il y a-t-il quelque chose que vous devez faire pour continuer à [!DNL Target] fonctionner ?

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox.js avec cookie propriétaire uniquement. | Pas d'impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| mbox.js avec le suivi inter-domaines activé. | Pas d'impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers disposent `SameSite = None` d’un indicateur sécurisé. L’indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| Paramètres at.js 1.*x* avec cookie propriétaire. | Pas d'impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.*x* avec le suivi inter-domaines activé. | Pas d'impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers disposent `SameSite = None` d’un indicateur sécurisé. L’indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| at.js 2.*x* | Pas d'impact. | Pas d'impact. |

## Que doit faire Target ?

Alors, qu'avons-nous donc dû faire dans notre plateforme pour vous aider à respecter les nouvelles règles de cookie Google Chrome 80+ SameSite ?

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox.js avec cookie propriétaire uniquement. | Pas d'impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| mbox.js avec le suivi inter-domaines activé. | Pas d'impact. | [!DNL Target] ajoute `SameSite = None` et Secure au cookie tiers lorsque [!DNL Target] des serveurs sont appelés. |
| Paramètres at.js 1.*x* avec cookie propriétaire. | Pas d'impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.*x* avec le suivi inter-domaines activé. | Pas d'impact. | Paramètres at.js 1.*x* avec le suivi inter-domaines activé. |
| at.js 2.*x* | Pas d'impact. | Pas d'impact. |

## Quel est l’impact si vous ne passez pas à l’utilisation du protocole HTTPS ?

Le seul cas d’utilisation qui vous affectera est si vous utilisez la fonctionnalité de suivi inter-domaines dans mbox.js [!DNL Target] ou at.js 1.*x*. Sans passer au protocole HTTPS, qui est une exigence de Google, vous verrez un pic de visiteurs uniques dans vos domaines car le cookie tiers que nous utilisons sera abandonné par Google. Et comme le cookie tiers sera supprimé, [!DNL Target] il ne pourra pas fournir une expérience cohérente et personnalisée à cet utilisateur lorsque celui-ci naviguera d’un domaine à un autre. Le cookie tiers est principalement utilisé pour identifier un utilisateur unique naviguant entre les domaines que vous détenez.

## Conclusion

Alors que le secteur fait des progrès pour créer un site Web plus sécurisé pour les consommateurs, [!DNL Adobe] il s’engage à aider ses clients à offrir des expériences personnalisées de manière à garantir la sécurité et la confidentialité des utilisateurs finaux. Tout ce que vous devez faire est de suivre les meilleures pratiques mentionnées ci-dessus et de profiter de [!DNL Target] pour vous conformer aux nouvelles politiques de cookie SameSite de Google Chrome.
