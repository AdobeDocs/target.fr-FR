---
description: Informations sur Target et la norme IETF samesite utilisée commençant par Google Chrome version 76.
keywords: google ; samesite
seo-description: Informations sur Adobe Target et la norme IETF samesite introduite avec Google Chrome version 76.
seo-title: Stratégies de cookie Adobe Target et samesite
solution: Target
subtopic: Prise en main
title: Stratégies de cookie Google Chrome samesite
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Stratégies de cookie Google Chrome samesite

Google a récemment annoncé qu'à compter de Chrome 76 (période du 30 juillet 2019), les développeurs doivent spécifier explicitement quels cookies peuvent fonctionner sur plusieurs sites Web et quels cookies peuvent suivre les utilisateurs.

## Présentation samesite

Pour protéger les cookies lorsque les utilisateurs peuvent être envoyés sur plusieurs sites, Google ajoute la prise en charge d'une norme IETF appelée « samesite » dans Google Chrome 76 (et versions ultérieures). SameSite requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

Il existe trois valeurs différentes qui peuvent être transmises à l'attribut samesite : Strict, Lax ou Aucun.

| Valeur | Description |
| --- | --- |
| Strict | Les cookies avec ce paramètre sont accessibles uniquement lors de la visite du domaine sur lequel il a été initialement défini. En d'autres termes, Strict empêche complètement le cookie d'être utilisé sur plusieurs sites. Cette option est préférable pour les applications nécessitant une sécurité élevée, telles que les banques. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| Aucune | Les cookies avec ce paramètre fonctionnent de la même manière que les cookies aujourd'hui. |

En gardant à l'esprit les points ci-dessus, Chrome 76 (et versions ultérieures) introduit deux paramètres : « Samesite par défaut » et « Cookies sans samesite doivent être sécurisés.  » » Les utilisateurs peuvent activer soit le paramètre, soit les deux paramètres.

| Paramètre | Description |
| --- | --- |
| Samesite par défaut | When set, all cookies that don't specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| Les cookies sans samesite doivent être sécurisés | When set, cookies without the SameSite attribute or with `SameSite = None`, must be Secure. Dans ce contexte, toutes les demandes de navigateur doivent respecter le protocole HTTPS. Les cookies qui ne respectent pas cette exigence sont rejetés. |

![Page Paramètres samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## Target respecte les meilleures pratiques de sécurité de Google

Avec Target, nous voulons veiller à ce que vous réussissiez en prenant toujours en charge les dernières pratiques recommandées du secteur pour la sécurité. Nous sommes heureux de vous annoncer que Target prend en charge les nouveaux paramètres de sécurité introduits dans Google Chrome 76.

Lorsque vos visiteurs ont activé le paramètre « samesite par défaut », Target continue à fournir la personnalisation sans aucun impact et sans intervention de votre part. Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

Lorsque les visiteurs activent l'option « Cookies sans samesite doivent être sécurisés » et que vous n'incluez pas la fonction de suivi inter-domaines de Target, les cookies directs de Target continuent à fonctionner. However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. Cela signifie que vous devez veiller à ce que vos sites utilisent le protocole HTTPS. Target's client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## Que devez-vous faire ?

Consultez le tableau suivant pour comprendre ce que vous devez faire pour que Target continue à fonctionner pour les utilisateurs de Google Chrome 76 +.

Le tableau contient les colonnes suivantes :

* **Bibliothèque côté client cible**: Que vous utilisiez mbox. js, at. js 1.*x* ou at. js 2.*x* sur vos sites et la manière dont les paramètres Google Chrome vous affectent
* **Samesite par défaut cookies = Activé**: Si les visiteurs ont activé « samesite par défaut activée » sur Chrome 76 +, comment cela s'applique-t-il à vous et qu'il y a tout ce que vous devez faire pour que Target continue à fonctionner ?
* **Les cookies sans samesite doivent être sécurisés = Activé**: Si vos visiteurs disposent de « Cookies sans samesite doivent être sécurisés » sur Chrome 76 +, comment cela s'applique-t-il à vous et qu'il y a tout ce que vous devez faire pour que Target continue à fonctionner ?
* **Suivi inter-domaines d'Adobe Target = Activé**: Si les visiteurs disposent de « même site par cookies par défaut » activé et que « Les cookies sans samesite doivent être sécurisés » sur Chrome 76 + et que vous utilisez Target pour le suivi inter-domaines, comment cela vous affectera-t-il et qu'il y a tout ce que vous devez faire pour que Target continue à fonctionner ?

| Bibliothèque côté client Target | Samesite par cookies par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé | Suivi inter-domaines d'Adobe Target = Activé |
| --- | --- | --- | --- |
| mbox.js | Aucun impact, car mbox. js utilise un cookie propriétaire. | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Les clients doivent activer le protocole HTTPS pour leur site.<br>Target utilise un cookie tiers pour suivre les utilisateurs et Google exige que les cookies tiers aient `SameSite = None` et que les sites utilisent le protocole HTTPS. |
| at.js 1.*x* | Aucun impact car at. js 1.*x* utilise un cookie propriétaire | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Les clients doivent activer le protocole HTTPS pour leur site.<br>Target utilise un cookie tiers pour effectuer le suivi des utilisateurs et Google exige que les cookies tiers aient `SameSite = None` et que les sites utilisent le protocole HTTPS. |
| at.js 2.*x* | Aucun impact car at. js 2.*x* utilise un cookie propriétaire | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Le suivi inter-domaines n'est pas pris en charge dans at. js 2.*x* et, par conséquent, aucun impact sur les clients |

## Qu'est-ce qu'Adobe doit faire ?

| Bibliothèque côté client Target | Samesite par cookies par défaut = Activé | Les cookies sans samesite doivent être sécurisés = Activé | Suivi inter-domaines d'Adobe Target = Activé |
| --- | --- | --- | --- |
| mbox.js | Aucun impact, car mbox. js utilise un cookie propriétaire. | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1.*x* | Aucun impact car at. js 1.*x* utilise un cookie propriétaire | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2.*x* | Aucun impact car at. js 2.*x* utilise un cookie propriétaire | Aucun impact car les clients n'utilisent pas le suivi inter-domaines | Le suivi inter-domaines n'est pas pris en charge dans at. js 2.*x* |

## Conclusion

Tandis que le secteur fait des progrès pour créer un Web plus sécurisé pour les consommateurs, Target s'engage à fournir des expériences personnalisées lors de la réunion et à dépasser les attentes en matière de confidentialité des visiteurs.
