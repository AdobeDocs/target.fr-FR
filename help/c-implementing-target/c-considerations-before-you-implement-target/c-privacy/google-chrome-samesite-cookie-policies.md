---
keywords: google;samesite;cookies;chrome 80;ietf
description: Découvrez comment Adobe [!DNL Target] gère la norme IETF de SameSite introduite avec Google Chrome version 80 et ce que vous devez faire pour respecter ces règles.
title: Comment  [!DNL Target] gère-t-on les stratégies de cookies Samesite de Google ?
feature: Confidentialité et sécurité
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 7%

---

# Stratégies de cookie Google Chrome samesite

Google commencera à imposer de nouvelles stratégies de cookies par défaut pour les utilisateurs à partir de Chrome 80, qui devrait être publié début 2020. Cet article explique tout ce que vous devez savoir sur les nouvelles stratégies de cookies de SiteCatalyst, comment [!DNL Adobe Target] les prend en charge et comment vous pouvez utiliser [!DNL Target] pour vous conformer aux nouvelles stratégies de cookies de SiteCatalyst de Google Chrome.

A compter de Chrome 80, les développeurs Web doivent spécifier explicitement quels cookies peuvent fonctionner sur plusieurs sites Web. Il s&#39;agit de la première des nombreuses annonces que Google prévoit de faire pour améliorer la confidentialité et la sécurité sur le Web.

Etant donné que Facebook a été à la pointe en matière de confidentialité et de sécurité, d&#39;autres acteurs majeurs tels qu&#39;Apple, et maintenant Google, ont rapidement profité de l&#39;opportunité de créer de nouvelles identités en tant que champions de la confidentialité et de la sécurité. Apple a pris la tête du pack en annonçant d&#39;abord les modifications de ses règles de cookies au début de l&#39;année via ITP 2.1 et récemment, ITP 2.2. Dans ITP 2.1, Apple bloque complètement les cookies tiers et conserve les cookies créés sur le navigateur pendant seulement sept jours. Dans ITP 2.2, les cookies ne sont conservés que pour une journée. L’annonce de Google est loin d’être aussi agressive que celle d’Apple, mais c’est le premier pas vers le même but final. Pour plus d’informations sur les stratégies d’Apple, voir [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Que sont les cookies et comment sont-ils utilisés ?

Avant de nous plonger dans les modifications apportées par Google à ses stratégies de cookies, nous allons nous intéresser à ce que sont les cookies et à comment ils sont utilisés. En d&#39;autres termes, les cookies sont de petits fichiers texte stockés dans le navigateur Web et utilisés pour mémoriser les attributs utilisateur.

Les cookies sont importants car ils améliorent l’expérience de l’utilisateur lorsqu’il navigue sur le Web. Par exemple, si vous effectuez des achats sur un site Web de commerce électronique et ajoutez quelque chose à votre panier, mais que vous ne vous connectez pas ou n’effectuez pas d’achat au cours de cette visite, les cookies mémorisent vos articles et les conservent dans votre panier pour votre prochaine visite. Ou, imaginez que vous soyez obligé de saisir à nouveau votre nom d&#39;utilisateur et votre mot de passe chaque fois que vous visitez votre site de médias sociaux favori. Les cookies résolvent également ce problème, car ils stockent des informations qui aident les sites à identifier qui vous êtes. Ces types de cookies sont appelés cookies propriétaires car ils sont créés et utilisés par le site Web que vous avez visité.

Des cookies tiers existent également. Pour mieux les comprendre, prenons l’exemple suivant :

Supposons qu’une société hypothétique de médias sociaux appelée &quot;Amis&quot; fournisse un bouton Partager que d’autres sites implémentent pour permettre aux utilisateurs d’Amis de partager le contenu du site sur le flux Amis. Désormais, un utilisateur lit un article d’actualité sur un site Web d’actualités qui utilise le bouton Partager et clique dessus pour le publier automatiquement sur son compte Amis.

Pour ce faire, le navigateur récupère le bouton Partager des amis de `platform.friends.com` lorsque l’article d’actualité est chargé. Dans ce processus, le navigateur associe les cookies amis, qui contiennent les informations d’identification de l’utilisateur, à la requête envoyée aux serveurs Friends. Cela permet aux Amis de publier l’article d’actualité dans son flux pour le compte de l’utilisateur sans exiger de ce dernier qu’il se connecte.

Tout cela est possible en utilisant des cookies tiers. Dans ce cas, le cookie tiers est enregistré dans le navigateur pour `platform.friends.com`, de sorte que `platform.friends.com` puisse effectuer la publication dans l’application Amis pour le compte de l’utilisateur.

Si vous imaginez un instant comment réaliser cette utilisation sans cookies tiers, l&#39;utilisateur devra suivre de nombreuses étapes manuelles. Tout d&#39;abord, l&#39;utilisateur doit copier le lien vers l&#39;article d&#39;actualité. Ensuite, l’utilisateur doit se connecter séparément à l’application Amis. Ensuite, l’utilisateur cliquera sur le bouton Créer une publication. Ensuite, l’utilisateur copiait et collait le lien dans le champ de texte, puis, enfin, cliquez sur Publier. Comme vous pouvez le constater, les cookies tiers aident énormément l’utilisateur à découvrir que les étapes manuelles peuvent être considérablement réduites.

Plus généralement, les cookies tiers permettent de stocker des données dans le navigateur d’un utilisateur sans exiger qu’il visite explicitement un site Web.

## Problèmes de sécurité

Bien que les cookies améliorent l’expérience des utilisateurs et la publicité, ils peuvent également introduire des vulnérabilités de sécurité telles que les attaques CSRF (Cross Site Request Forgery). Par exemple, si un utilisateur se connecte à un site bancaire pour payer des factures de carte de crédit et quitte le site sans se déconnecter puis accède à un site malveillant au cours de la même session, une attaque CSRF peut se produire. Le site malveillant peut inclure un code qui envoie une requête au site bancaire qui s’exécute au chargement de la page. L’utilisateur étant toujours authentifié sur le site bancaire, le cookie de session peut être utilisé pour lancer une attaque CSRF afin de déclencher un événement de transfert de fonds en dehors du compte bancaire de l’utilisateur. En effet, chaque fois que vous visitez un site, tous les cookies sont joints dans la requête HTTP. Et à cause de ces problèmes de sécurité, Google tente maintenant de les atténuer.

## Comment [!DNL Target] utilise-t-il les cookies ?

Ceci étant dit, voyons comment [!DNL Target] utilise les cookies. Pour pouvoir utiliser [!DNL Target] en premier lieu, vous devez installer la bibliothèque JavaScript [!DNL Target] sur votre site. Cela vous permet de placer un cookie propriétaire dans le navigateur de l’utilisateur qui consulte votre site. Lorsque votre utilisateur interagit avec votre site Web, vous pouvez transmettre les données de comportement et d’intérêt de l’utilisateur à [!DNL Target] par l’intermédiaire de la bibliothèque JavaScript. La bibliothèque JavaScript [!DNL Target] utilise des cookies propriétaires pour extraire des informations d’identification sur l’utilisateur à mapper au comportement et aux données d’intérêt de l’utilisateur. Ces données sont ensuite utilisées par [!DNL Target] pour alimenter vos activités de personnalisation.

La cible utilise également (parfois) des cookies tiers. Si vous possédez plusieurs sites Web qui résident sur des domaines différents et que vous souhaitez effectuer le suivi du parcours utilisateur sur ces sites Web, vous pouvez utiliser des cookies tiers en exploitant le suivi interdomaines. En activant le suivi inter-domaines dans la bibliothèque JavaScript [!DNL Target], votre compte début à l’aide de cookies tiers. Lorsqu’un utilisateur passe d’un domaine à l’autre, le navigateur communique avec le serveur principal [!DNL Target] et, dans ce processus, un cookie tiers est créé et placé dans le navigateur de l’utilisateur. Grâce au cookie tiers qui réside dans le navigateur de l’utilisateur, [!DNL Target] peut fournir une expérience cohérente dans différents domaines pour un utilisateur unique.

## Nouvelle recette de cookie de Google

Afin de fournir des protections sur le moment où les cookies sont envoyés sur les sites pour que les utilisateurs soient protégés, Google prévoit d&#39;ajouter la prise en charge d&#39;une norme IETF appelée SameSite, qui demande aux développeurs Web de gérer les cookies avec le composant d&#39;attribut MêmeSite dans l&#39;en-tête Set-Cookie.

Il existe trois valeurs différentes qui peuvent être transmises à l’attribut samesite : Strict, Lax (Permissif) ou None (Aucun).

| Valeur | Description |
| --- | --- |
| Strict | Les cookies avec ce paramètre sont accessibles uniquement lors de la visite du domaine sur lequel il a été initialement défini. En d’autres termes, Strict empêche complètement le cookie d’être utilisé sur plusieurs sites. Cette option est préférable pour les applications nécessitant une haute sécurité, telles que les banques. |
| Lax | Les cookies avec ce paramètre sont envoyés uniquement sur des requêtes du même site ou sur une navigation de niveau supérieur avec des requêtes HTTP non puissantes, comme `HTTP GET`. Par conséquent, cette option serait utilisée si le cookie peut être utilisé par des tiers, mais avec un avantage de sécurité supplémentaire qui protège les utilisateurs contre les attaques CSRF. |
| None | Les cookies dotés de ce paramètre fonctionnent de la même manière que les cookies aujourd’hui. |

En gardant à l’esprit ce qui précède, Chrome 80 propose deux paramètres indépendants pour les utilisateurs : &quot;Même site par défaut&quot; et &quot;Cookies sans SameSite doivent être sécurisés&quot;. Ces paramètres seront activés par défaut dans Chrome 80.

![MêmeSite, boîte de dialogue](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Même site par défaut, cookies** : Une fois défini, tous les cookies qui ne spécifient pas l’attribut MêmeSite seront automatiquement forcés d’utiliser  `SameSite = Lax`.
* **Les cookies sans SameSite doivent être sécurisés** : Lorsqu’elle est définie, les cookies ne comportant pas l’attribut MêmeSite ou ayant  `SameSite = None` besoin d’être sécurisés. Dans ce contexte, toutes les demandes de navigateur doivent respecter le protocole HTTPS. Les cookies qui ne respectent pas cette exigence sont rejetés. Tous les sites Web doivent utiliser le protocole HTTPS pour répondre à cette exigence.

## Target respecte les bonnes pratiques de sécurité de Google

En Adobe, nous voulons toujours soutenir les meilleures pratiques de l’industrie en matière de sécurité et de protection de la vie privée. Nous sommes heureux d&#39;annoncer que [!DNL Target] prend en charge les nouveaux paramètres de sécurité et de confidentialité introduits par Google.

Pour le paramètre &quot;Même site par défaut&quot;, [!DNL Target] continuera à fournir la personnalisation sans impact ni intervention de votre part. [!DNL Target] utilise des cookies propriétaires et continuera à fonctionner correctement lorsque l’indicateur `SameSite = Lax` est appliqué par Google Chrome.

Pour l’option &quot;Cookies sans SameSite must be secure&quot;, si vous ne vous inscrivez pas à la fonctionnalité de suivi inter-domaines de [!DNL Target], les cookies propriétaires de [!DNL Target] continueront à fonctionner.

Cependant, lorsque vous optez pour le suivi inter-domaines afin d’exploiter [!DNL Target] sur plusieurs domaines, Chrome requiert `SameSite = None` et des indicateurs Secure pour être utilisés pour les cookies tiers. Cela signifie que vous devez vous assurer que vos sites utilisent le protocole HTTPS. Les bibliothèques côté client de [!DNL Target] utiliseront automatiquement le protocole HTTPS et associeront les indicateurs `SameSite = None` et Secure à des cookies tiers dans [!DNL Target] pour s&#39;assurer que toutes les activités continuent à diffuser.

## Que dois-je faire ?

Pour comprendre ce que vous devez faire pour que [!DNL Target] continue à fonctionner pour les utilisateurs de Google Chrome 80+, consultez le tableau ci-dessous, dont vous verrez les colonnes suivantes :

* **Bibliothèque** JavaScript cible : Si vous utilisez mbox.js, at.js 1.*x* ou at.js 2.** xon vos sites.
* **SameSite par défaut cookies = Activé** : Si les cookies &quot;Même site par défaut&quot; sont activés pour vos utilisateurs, quel impact cela a-t-il sur vous et y a-t-il tout ce que vous devez faire  [!DNL Target] pour continuer à travailler ?
* **Les cookies sans SameSite doivent être sécurisés = Activé** : Si l’option &quot;Cookies sans SameSite doivent être sécurisés&quot; est activée pour vos utilisateurs, quel impact cela a-t-il sur vous et y a-t-il quelque chose que vous devez faire pour que  [!DNL Target] ça continue à fonctionner ?

| Bibliothèque JavaScript cible | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox.js avec cookie propriétaire uniquement. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| mbox.js avec le suivi inter-domaines activé. | Aucun impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers possèdent  `SameSite = None` et l’indicateur Secure. L&#39;indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| Paramètres at.js 1.*cookie* propriétaire xwith. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.** xwith inter-domaines tracking enabled. | Aucun impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers possèdent  `SameSite = None` et l’indicateur Secure. L&#39;indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Que doit faire [!DNL Target] ?

Alors, qu&#39;avons-nous dû faire dans notre plateforme pour vous aider à respecter les nouvelles politiques de cookies Google Chrome 80+ SameSite ?

| Bibliothèque JavaScript cible | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| mbox.js avec cookie propriétaire uniquement. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| mbox.js avec le suivi inter-domaines activé. | Aucun impact. | [!DNL Target] ajoute  `SameSite = None` et Secure au cookie tiers lorsque  [!DNL Target] des serveurs sont appelés. |
| Paramètres at.js 1.*cookie* propriétaire xwith. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.** xwith inter-domaines tracking enabled. | Aucun impact. | Paramètres at.js 1.** xwith inter-domaines tracking enabled. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Quel est l’impact si vous ne passez pas à l’utilisation du protocole HTTPS ?

Le seul cas d’utilisation qui aura un impact sur vous est si vous utilisez la fonction de suivi inter-domaines dans [!DNL Target] via mbox.js ou at.js 1.*x*. Sans passer au protocole HTTPS, qui est requis par Google, vous verrez un pic de visiteurs uniques sur vos domaines car le cookie tiers que nous utilisons sera supprimé par Google. Et comme le cookie tiers sera supprimé, [!DNL Target] ne pourra pas fournir une expérience cohérente et personnalisée à cet utilisateur lorsque celui-ci navigue d’un domaine à l’autre. Le cookie tiers est principalement utilisé pour identifier un utilisateur unique naviguant entre les domaines que vous détenez.

## Conclusion

À mesure que l&#39;industrie avance dans la création d&#39;un site Web plus sécurisé pour les consommateurs, [!DNL Adobe] s&#39;engage à aider ses clients à offrir des expériences personnalisées de manière à garantir la sécurité et la confidentialité des utilisateurs finaux. Il vous suffit de suivre les meilleures pratiques mentionnées ci-dessus et de tirer parti de [!DNL Target] pour vous conformer aux nouvelles politiques de cookies de Google Chrome pour SameSite.
