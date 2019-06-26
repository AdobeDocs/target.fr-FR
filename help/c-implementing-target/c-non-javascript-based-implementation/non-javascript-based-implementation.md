---
description: Informations sur la mise en œuvre de Target dans des scénarios sans JavaScript tels qu’AdBox ou Redirecteur.
keywords: Mise en œuvre;mbox.js sans JavaScript;adbox;redirecteur;mbox
seo-description: Informations sur la mise en œuvre de Target dans des scénarios sans JavaScript tels qu’AdBox ou Redirecteur.
seo-title: Implémentation d’e-mail par Target
solution: Target
subtopic: Prise en main
title: Implémentation d’e-mail par Target
topic: Standard
uuid: 07abc419-0253-47c6-80b8-0bd0734d2c9d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Messagerie électronique : implémentation de Target{#email-implement-target}

Informations sur la mise en œuvre de Target dans des scénarios sans JavaScript tels qu’AdBox ou Redirecteur.

Vous pouvez effectuer le suivi des visites sur vos annonces ainsi que de tout autre contenu hors site. Vous pouvez également identifier le même utilisateur, que ce soit sur votre site ou en dehors de celui-ci, et lui garantir une expérience web cohérente. Avec une simple URL, l’AdBox permet de réaliser des tests sans faire usage de code JavaScript, d’[!DNL at.js] ou de [!DNL mbox.js].

Une AdBox est utile pour les sites qui ne possèdent pas [!DNL at.js] ou [!DNL mbox.js], tels que les affiliés. Si votre activité nécessite du contenu publicitaire dynamique (vous devez, par exemple, afficher un produit dans l’annonce qui a été abandonné dans le panier), vous ne pouvez pas utiliser une AdBox.

Les annonces AdBox et le redirecteur peuvent être utilisés avec n’importe quel type d’activité. Le tableau suivant compare le redirecteur et adbox, et indique dans quels cas les utiliser :

|  | Objectif | Conditions d’utilisation | Structure de l’URL | Type d’offre | Contenu de l’offre |
|--- |--- |--- |--- |--- |--- |
| AdBox | Renvoie différentes images à l’annonce | Permet de modifier le contenu d’une annonce | `clientcode​.tt.​omtrdc​.net/​m2​/​clientcode/ubox/​image?` | Offre de redirection | URL d’une image |
| Redirecteur | Redirige un visiteur vers une autre page Web | Permet de modifier la page d’entrée d’une annonce | `clientcode​.tt.omtrdc.net/​m2/clientcode​/ubox/page?` | Offre de redirection | URL d’une page |

## Contraintes {#section_38F559DCF1324271926608BCD4AB1227}

* Absence de délai d’expiration côté client, contrairement aux mbox standard. Si Target est complètement hors service, aucun contenu n’est présenté aux visiteurs de l’annonce, pas même le contenu par défaut.
* Les cookies tiers sont utilisés pour effectuer le suivi des visites. Si les PCId sont différents, le profil tiers du visiteur est par défaut fusionné avec tout profil propriétaire existant.
* Pour utiliser des cookies propriétaires sur l’AdBox proprement dite, vous devez transmettre la session mBox dans l’URL. Pour cela, contactez le représentant du compte.
* Pour utiliser des cookies propriétaires afin d’effectuer le suivi des clics publicitaires, vous devez transmettre la session mbox dans l’URL. Pour cela, contactez le représentant du compte.
* Pour utiliser plusieurs AdBox sur la même page, vous devez transmettre la session mbox dans l’URL. Pour cela, contactez le représentant du compte. Une AdBox et un lien Redirecteur peuvent coexister sur la même page (car le redirecteur se situe, en réalité, sur une deuxième page).

