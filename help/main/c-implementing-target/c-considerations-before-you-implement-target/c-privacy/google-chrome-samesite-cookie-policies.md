---
keywords: google;samesite;cookies;chrome 80;ietf
description: Découvrez comment Adobe [!DNL Target] gère la norme IETF samesite introduite avec Google Chrome version 80 et ce que vous devez faire pour vous conformer à ces politiques.
title: Comment [!DNL Target] Gérer les stratégies de cookies Samesite Google ?
feature: Privacy & Security
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 7%

---

# Stratégies de cookie Google Chrome samesite

Google commencera à imposer de nouvelles stratégies de cookies par défaut pour les utilisateurs, à partir de Chrome 80, qui sera publié début 2020. Cet article explique tout ce que vous devez savoir sur les nouvelles stratégies de cookies SameSite, comment [!DNL Adobe Target] prend en charge ces stratégies et la manière dont vous pouvez les utiliser ; [!DNL Target] pour se conformer aux nouvelles stratégies de cookies SameSite de Google Chrome.

À partir de Chrome 80, les développeurs web doivent spécifier explicitement quels cookies peuvent fonctionner sur plusieurs sites web. Il s’agit de la première des nombreuses annonces que Google prévoit de faire pour améliorer la confidentialité et la sécurité sur le Web.

Étant donné que Facebook est à la pointe en matière de confidentialité et de sécurité, d&#39;autres acteurs majeurs tels qu&#39;Apple, et désormais Google, ont rapidement profité de l&#39;opportunité de créer de nouvelles identités en tant que champions de la confidentialité et de la sécurité. Apple a dirigé le pack en annonçant d’abord les modifications apportées à ses politiques de cookies au début de l’année via ITP 2.1 et, plus récemment, ITP 2.2. Dans ITP 2.1, Apple bloque complètement les cookies tiers et conserve les cookies créés sur le navigateur pendant seulement sept jours. Dans ITP 2.2, les cookies ne sont conservés que pendant une journée. L’annonce de Google est loin d’être aussi agressive que celle d’Apple, mais c’est la première étape vers le même objectif final. Pour plus d’informations sur les stratégies Apple, voir [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Que sont les cookies et comment sont-ils utilisés ?

Avant d’examiner les modifications apportées par Google à ses stratégies de cookies, nous vous conseillons de définir les cookies et leur mode d’utilisation. En d’autres termes, les cookies sont de petits fichiers texte stockés dans le navigateur web qui sont utilisés pour mémoriser les attributs utilisateur.

Les cookies sont importants car ils améliorent l’expérience de l’utilisateur lorsqu’il navigue sur le Web. Par exemple, si vous effectuez des achats sur un site web d’e-commerce et ajoutez quelque chose à votre panier, mais que vous ne vous connectez pas ou n’effectuez pas d’achat au cours de cette visite, les cookies mémorisent vos articles et les conservent dans votre panier pour votre prochaine visite. Ou imaginez que vous soyez obligé de saisir à nouveau votre nom d&#39;utilisateur et votre mot de passe chaque fois que vous visitez votre site de médias sociaux préféré. Les cookies résolvent également ce problème, car ils stockent des informations qui aident les sites à identifier qui vous êtes. Ces types de cookies sont appelés cookies propriétaires, car ils sont créés et utilisés par le site web que vous avez visité.

Des cookies tiers existent également. Pour mieux les comprendre, prenons l’exemple suivant :

Imaginons qu’une hypothétique société de médias sociaux appelée &quot;Amis&quot; propose un bouton Partager que d’autres sites implémentent pour permettre aux utilisateurs Amis de partager le contenu du site sur le flux Amis. Désormais, un utilisateur lit un article sur un site web d’actualités qui utilise le bouton Partager et clique dessus pour le publier automatiquement sur son compte Amis .

Pour ce faire, le navigateur récupère le bouton Partager les amis de `platform.friends.com` lorsque l’article d’actualité est chargé. Au cours de ce processus, le navigateur joint les cookies Amis, qui contiennent les informations d’identification de l’utilisateur, à la demande aux serveurs Amis. Cela permet aux amis de publier l’article d’actualité dans leur flux à la place de l’utilisateur sans que celui-ci doive se connecter.

Cela est possible en utilisant des cookies tiers. Dans ce cas, le cookie tiers est enregistré dans le navigateur pour la variable `platform.friends.com`, de sorte que `platform.friends.com` Vous pouvez effectuer la publication dans l’application Amis pour le compte de l’utilisateur.

Si vous imaginez un instant comment réaliser ce cas d’utilisation sans cookies tiers, l’utilisateur devra suivre de nombreuses étapes manuelles. Tout d’abord, l’utilisateur doit copier le lien vers l’article d’actualité. Deuxièmement, l’utilisateur doit se connecter séparément à l’application Amis. L’utilisateur clique ensuite sur le bouton Créer une publication . Ensuite, l’utilisateur copiait et collait le lien dans le champ de texte, puis, enfin, cliquez sur Publier. Comme vous pouvez le constater, les cookies tiers aident considérablement l’utilisateur à expérimenter, car les étapes manuelles peuvent être considérablement réduites.

Plus généralement, les cookies tiers permettent de stocker des données dans le navigateur d’un utilisateur sans que celui-ci ait à se rendre explicitement sur un site web.

## Questions de sécurité

Bien que les cookies améliorent les expériences utilisateur et la publicité, ils peuvent également introduire des vulnérabilités de sécurité telles que les attaques CSRF (Cross-Site Request Forgery). Par exemple, si un utilisateur se connecte à un site bancaire pour payer les factures de carte de crédit et quitte le site sans se déconnecter, puis accède à un site malveillant au cours de la même session, une attaque CSRF peut se produire. Le site malveillant peut inclure du code qui émet une requête au site bancaire qui s’exécute au chargement de la page. Comme l’utilisateur est toujours authentifié sur le site bancaire, le cookie de session peut être utilisé pour lancer une attaque CSRF afin d’initier un événement de transfert de fonds en dehors du compte bancaire de l’utilisateur. En effet, chaque fois que vous visitez un site, tous les cookies sont joints dans la requête HTTP. Et à cause de ces problèmes de sécurité, Google tente maintenant de les atténuer.

## Comment [!DNL Target] utiliser des cookies ?

Tout cela dit, voyons comment [!DNL Target] utilise des cookies. Pour que vous puissiez utiliser [!DNL Target] tout d’abord, vous devez installer le [!DNL Target] Bibliothèque JavaScript sur votre site. Vous pouvez ainsi placer un cookie propriétaire sur le navigateur de l’utilisateur qui visite votre site. Lorsque votre utilisateur interagit avec votre site web, vous pouvez transmettre ses données de comportement et d’intérêt à [!DNL Target] par le biais de la bibliothèque JavaScript. Le [!DNL Target] La bibliothèque JavaScript utilise des cookies propriétaires pour extraire des informations d’identification sur l’utilisateur à mapper sur le comportement et les données d’intérêt de l’utilisateur. Ces données sont ensuite utilisées par [!DNL Target] pour alimenter vos activités de personnalisation.

Target utilise également (parfois) des cookies tiers. Si vous possédez plusieurs sites web qui se trouvent sur des domaines différents et que vous souhaitez effectuer le suivi du parcours utilisateur sur ces sites, vous pouvez utiliser des cookies tiers en exploitant le suivi inter-domaines. En activant le suivi inter-domaines dans la variable [!DNL Target] Bibliothèque JavaScript, votre compte commencera à utiliser des cookies tiers. Lorsqu’un utilisateur passe d’un domaine à un autre, le navigateur communique avec le serveur principal de [!DNL Target], et dans ce processus, un cookie tiers est créé et placé sur le navigateur de l’utilisateur. Par le biais du cookie tiers qui réside sur le navigateur de l’utilisateur, [!DNL Target] est capable de fournir une expérience cohérente sur différents domaines pour un utilisateur unique.

## Nouvelle recette de cookie de Google

Pour garantir la protection des utilisateurs lors de l’envoi de cookies à l’ensemble des sites, Google prévoit d’ajouter la prise en charge d’une norme IETF appelée SameSite, ce qui oblige les développeurs web à gérer les cookies avec le composant d’attribut SameSite dans l’en-tête Set-Cookie.

Il existe trois valeurs différentes qui peuvent être transmises à l’attribut samesite : Strict, Lax (Permissif) ou None (Aucun).

| Valeur | Description |
| --- | --- |
| Strict | Les cookies avec ce paramètre sont accessibles uniquement lors de la visite du domaine sur lequel il a été initialement défini. En d’autres termes, Strict empêche complètement le cookie d’être utilisé sur plusieurs sites. Cette option est préférable pour les applications nécessitant une sécurité élevée, telles que les banques. |
| Lax | Les cookies avec ce paramètre sont envoyés uniquement sur les requêtes du même site ou sur la navigation de niveau supérieur avec des requêtes HTTP non idempotentes, comme `HTTP GET`. Par conséquent, cette option serait utilisée si le cookie peut être utilisé par des tiers, mais avec un avantage de sécurité supplémentaire qui protège les utilisateurs contre les attaques CSRF. |
| None | Les cookies avec ce paramètre fonctionnent de la même manière que les cookies aujourd’hui. |

En gardant à l’esprit les éléments ci-dessus, Chrome 80 introduit deux paramètres indépendants pour les utilisateurs : &quot;Cookies samesite par défaut&quot; et &quot;Les cookies sans samesite doivent être sécurisés&quot;. Ces paramètres seront activés par défaut dans Chrome 80.

![Boîte de dialogue SameSite](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Cookies samesite par défaut**: Lorsqu’il est défini, tous les cookies qui ne spécifient pas l’attribut samesite sont automatiquement forcés d’utiliser `SameSite = Lax`.
* **Les cookies sans samesite doivent être sécurisés**: Lorsqu’il est défini, les cookies sans attribut SameSite ou avec `SameSite = None` doit être sécurisé. Dans ce contexte, toutes les demandes de navigateur doivent respecter le protocole HTTPS. Les cookies qui ne respectent pas cette exigence sont rejetés. Tous les sites web doivent utiliser HTTPS pour répondre à cette exigence.

## Target respecte les bonnes pratiques de sécurité de Google

En Adobe, nous voulons toujours prendre en charge les dernières bonnes pratiques du secteur en matière de sécurité et de confidentialité. Nous sommes heureux d’annoncer que [!DNL Target] prend en charge les nouveaux paramètres de sécurité et de confidentialité introduits par Google.

Pour le paramètre &quot;Cookies samesite par défaut&quot;, [!DNL Target] continuera à fournir une personnalisation sans aucun impact ni intervention de votre part. [!DNL Target] utilise des cookies propriétaires et continuera à fonctionner correctement lorsque l’indicateur `SameSite = Lax` est appliqué par Google Chrome.

Pour l’option &quot;Les cookies sans samesite doivent être sécurisés&quot;, si vous ne souscrivez pas à la fonctionnalité de suivi inter-domaines dans [!DNL Target], les cookies propriétaires dans [!DNL Target] continuera à travailler.

Cependant, lorsque vous souscrivez à l’utilisation du suivi inter-domaines pour tirer parti de [!DNL Target] sur plusieurs domaines, Chrome nécessite `SameSite = None` et Indicateurs sécurisés à utiliser pour les cookies tiers. Cela signifie que vous devez vous assurer que vos sites utilisent le protocole HTTPS. Bibliothèques côté client dans [!DNL Target] utilise automatiquement le protocole HTTPS et joigne la variable `SameSite = None` et définir des indicateurs sur des cookies tiers dans [!DNL Target] pour s’assurer que toutes les activités continuent de s’exécuter.

## Que dois-je faire ?

Pour comprendre ce que vous devez faire [!DNL Target] Continuez à travailler pour les utilisateurs de Google Chrome 80+. Consultez le tableau ci-dessous, qui comporte les colonnes suivantes :

* **Bibliothèque JavaScript Target**: Si vous utilisez at.js 1.*x* ou at.js 2.*x* sur vos sites.
* **Cookies samesite par défaut = Activé**: Si les cookies &quot;samesite par défaut&quot; sont activés pour vos utilisateurs, comment cela vous affecte-t-il et devez-vous prendre des mesures pour [!DNL Target] pour continuer à travailler.
* **Les cookies sans samesite doivent être sécurisés = Activé**: Si l’option &quot;Les cookies sans samesite doivent être sécurisés&quot; est activée pour vos utilisateurs, comment cela vous affecte-t-il et devez-vous prendre des mesures ? [!DNL Target] continuez à travailler.

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| Paramètres at.js 1.*x* avec cookie propriétaire. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.*x* avec suivi inter-domaines activé. | Aucun impact. | Vous devez activer le protocole HTTPS pour votre site.<br>[!DNL Target] utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers aient la variable `SameSite = None` et l’indicateur sécurisé . L’indicateur Secure exige que vos sites utilisent le protocole HTTPS. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Que faire ? [!DNL Target] Vous devez le faire ?

Alors, que devions-nous faire dans notre plateforme pour vous aider à vous conformer aux nouvelles politiques de cookies Google Chrome 80+ SameSite ?

| Bibliothèque JavaScript Target | Cookies samesite par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé |
| --- | --- | --- |
| Paramètres at.js 1.*x* avec cookie propriétaire. | Aucun impact. | Aucun impact si vous n’utilisez pas le suivi inter-domaines. |
| Paramètres at.js 1.*x* avec suivi inter-domaines activé. | Aucun impact. | Paramètres at.js 1.*x* avec suivi inter-domaines activé. |
| at.js 2.*x* | Aucun impact. | Aucun impact. |

## Quel est l’impact si vous n’utilisez pas le protocole HTTPS ?

Le seul cas d’utilisation qui vous affectera est si vous utilisez la fonctionnalité de suivi inter-domaines dans [!DNL Target] à at.js 1.*x*. Sans passer à HTTPS, qui est une exigence de Google, vous verrez un pic du nombre de visiteurs uniques sur vos domaines, car le cookie tiers que nous utilisons sera ignoré par Google. Et puisque le cookie tiers sera supprimé, [!DNL Target] ne sera pas en mesure de fournir une expérience cohérente et personnalisée à cet utilisateur lorsque celui-ci navigue d’un domaine à un autre. Le cookie tiers est principalement utilisé pour identifier un utilisateur unique naviguant entre les domaines dont vous êtes propriétaire.

## Conclusion

Alors que le secteur s&#39;efforce de créer un site web plus sécurisé pour les consommateurs, [!DNL Adobe] s’engage à aider nos clients à proposer des expériences personnalisées de manière à garantir la sécurité et la confidentialité aux utilisateurs finaux. Tout ce que vous devez faire est de suivre les bonnes pratiques mentionnées ci-dessus et de profiter de [!DNL Target] pour se conformer aux nouvelles stratégies de cookies SameSite de Google Chrome.
