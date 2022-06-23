---
keywords: Mise en oeuvre;at.js sans JavaScript;adbox;redirecteur;mbox
description: Découvrez comment mettre en oeuvre Adobe [!DNL Target] dans les scénarios autres que JavaScript, comme l’utilisation d’une adbox ou d’un redirecteur.
title: Comment mettre en oeuvre [!DNL Target] pour Email ?
feature: Implement Email
role: Developer
exl-id: 3287cf3d-3ed4-471f-aa06-25bb12e23ead
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 78%

---

# Messagerie électronique : implémentation de Target

Informations sur la mise en œuvre de Target dans des scénarios sans JavaScript tels qu’AdBox ou Redirecteur.

Vous pouvez effectuer le suivi des visites sur vos annonces ainsi que de tout autre contenu hors site. Vous pouvez également identifier le même utilisateur, que ce soit sur votre site ou en dehors de celui-ci, et lui garantir une expérience web cohérente. Avec une seule URL, l’AdBox permet de réaliser des tests sans utiliser de code JavaScript ou [!DNL at.js].

Une adbox est utile pour les sites qui n’ont pas [!DNL at.js], comme les affiliés. Si votre activité nécessite du contenu publicitaire dynamique (vous devez, par exemple, afficher un produit dans l’annonce qui a été abandonné dans le panier), vous ne pouvez pas utiliser une AdBox.

Les annonces AdBox et le redirecteur peuvent être utilisés avec n’importe quel type d’activité. Le tableau suivant compare le redirecteur et adbox, et indique dans quels cas les utiliser :

|  | Objectif | Conditions d’utilisation | Structure de l’URL | Type d’offre | Contenu de l’offre |
|--- |--- |--- |--- |--- |--- |
| AdBox | Renvoie différentes images à l’annonce | Permet de modifier le contenu d’une annonce | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | Offre de redirection | URL d’une image |
| Redirecteur | Redirige un visiteur vers une autre page Web | Permet de modifier la page d’entrée d’une annonce | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | Offre de redirection | URL d’une page |

## Bonnes pratiques relatives à la sécurité {#security}

Notez qu’avec Redirecteur, vous pouvez être exposé à un risque de vulnérabilité de redirection ouverte. Pour éviter l’utilisation non autorisée de liens de redirection par des tiers, nous vous recommandons d’utiliser des &quot;hôtes autorisés&quot; pour placer sur la liste autorisée les domaines d’URL de redirection par défaut. Target utilise des hôtes pour placer sur la liste autorisée les domaines vers lesquels vous souhaitez autoriser les redirections. Pour plus d’informations, consultez [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à Target](/help/main/administrating-target/hosts.md#allowlist) dans *Hôtes*.

## Contraintes {#section_38F559DCF1324271926608BCD4AB1227}

* Absence de délai d’expiration côté client, contrairement aux mbox standard. Si Target est complètement hors service, aucun contenu n’est présenté aux visiteurs de l’annonce, pas même le contenu par défaut.
* Les cookies tiers sont utilisés pour effectuer le suivi des visites. Si les PCId sont différents, le profil tiers du visiteur est par défaut fusionné avec tout profil propriétaire existant.
* Pour utiliser des cookies propriétaires sur l’AdBox proprement dite, vous devez transmettre la session mBox dans l’URL. Pour cela, contactez le représentant du compte.
* Pour utiliser des cookies propriétaires afin d’effectuer le suivi des clics publicitaires, vous devez transmettre la session mbox dans l’URL. Pour cela, contactez le représentant du compte.
* Pour utiliser plusieurs AdBox sur la même page, vous devez transmettre la session mbox dans l’URL. Pour cela, contactez le représentant du compte. Une AdBox et un lien Redirecteur peuvent coexister sur la même page (car le redirecteur se situe, en réalité, sur une deuxième page).
