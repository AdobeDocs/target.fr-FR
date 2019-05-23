---
description: Informations sur les limitations de caractères et autres limitations (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et d’autres éléments dans Adobe Target.
keywords: limite de caractères;paramètres mbox;api de remise par lots;paramètres de profil;limites;profils intégrés;maximum;limite;contrainte;caractère;bonne pratique;orderid;orderTotal;mbox3rdPartyID;catégorie;categoryID
seo-description: Informations sur les limitations de caractères et autres limitations (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et d’autres éléments dans Adobe Target.
seo-title: Limites
solution: Target
title: Limites
topic: Standard
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
translation-type: tm+mt
source-git-commit: 5e8edb25f0b0255247c535bcac1d960b6e8acf94

---


# Limites{#limits}

Informations sur les limitations de caractères et autres limitations (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et d’autres éléments dans Adobe Target.

Vous trouverez ci-dessous une liste de limites recommandées. Un ralentissement des performances peut être observé lorsque vous vous approchez ou dépassez ces limites. La lenteur du chargement de l’interface peut également être due à une activité très complexe (une activité comprenant de nombreuses audiences, cibles et expériences, par exemple). 

Les activités particulièrement complexes doivent être examinées par les conseillers d’Adobe et testées dans un environnement limité avant d’être mises en production.

## Noms d&#39;activité

**Limite**: 250 caractères.

## Noms d&#39;audience

**Limite**: 256 caractères.

Les valeurs supérieures à 256 caractères sont tronquées.

## Paramètre categoryId

**Limite**: 250 caractères.

## Noms d&#39;attributs du client

**Limite**: 128 caractères.

## ID d&#39;alias d&#39;attribut du client

**Limite** de 50 caractères.

## Attributs personnalisés d&#39;entité

**Limite**: La longueur maximale dépend de la langue.

* 15 000 caractères (une seule valeur, deux et deux langues)
* 500 valeurs, 100 caractères par valeur (à plusieurs valeurs)

La longueur maximale des attributs personnalisés d&#39;entité à une valeur est de 15 000 caractères (pour les langues codées UTF -8 et les langues codées en UTF -8 comme Anglais et d&#39;autres alphabets alphabétiques Latin) ou de 10 000 caractères (pour les langues codées UTF -8 sur trois octets comme le chinois, le japonais et le coréen).

Les attributs personnalisés d&#39;entité à plusieurs valeurs ne peuvent pas contenir plus de 500 valeurs. Chaque valeur individuelle est limitée à 100 caractères. Le nombre total de caractères pour toutes les valeurs doit se conformer aux limites de la longueur maximale des attributs personnalisés d&#39;entité à une valeur unique (voir ci-dessus).

## Paramètres entityid

**Limite**: 1 000 caractères.

## Excludedids {#excludedid}

**Limite**: 5 Ko pour les requêtes POST. 2 083 caractères moins la longueur de l&#39;URL pour les requêtes GET.

Pour les requêtes GET, bien que la limite de l&#39;arrière-plan soit de 5 Ko, en raison du fait que Microsoft Internet Explorer limite l&#39;URL à 2 083 caractères, la limite réaliste est de 2 083 caractères, moins la longueur actuelle de l&#39;URL.

## Noms d&#39;expériences

**Limite**: 20 caractères.

## Valeur d&#39;attribut de profil interne à la mbox

**Limite**: 256 caractères.

Les valeurs plus longues sont tronquées.

## Profils internes à la mbox dans une requête de mbox

**Limite**: 50 profils.

Tous les profils suivants sont ignorés.

## Noms des profils internes à la mbox

**Limite**: 128 caractères.

## noms de mbox

**Limite**: 250 caractères.

## Paramètres moxb

**Limite**: Les limites suivantes s&#39;appliquent aux paramètres mbox :

* paramètres de mbox : 500 paramètres par mbox.
* Paramètres de profil : 500 paramètres.
* paramètres de profil par mbox:
* Autres paramètres (URL, URL de référence, etc.): 50 par mbox pour chaque autre type de paramètre.

Pour les paramètres qui sont enregistrés dans la base de données Target, les limites ci-dessus concernent les requêtes de mbox standard. Ces limites sont appliquées à moins que la requête ne soit abrégée en raison des restrictions du navigateur Web.

Si vous utilisez l’[API de livraison par lots](https://developers.adobetarget.com/api/#server-side-batch-delivery) dans le SDK Mobile Services, la limite de 50 paramètres de mbox, 50 paramètres de profil et 50 pour les autres types de paramètres sont les limites de l’API elle-même. Il est impossible d’envoyer une requête contenant plus que ces nombres à l’aide de l’API de livraison par lots. Si le contenu d’une requête est supérieur à ces limites, l’API renvoie le message d’erreur suivant : « Le nombre de mboxParameters ne peut pas dépasser 100. »

## URL de requête de mbox

**Limite**: 2 083 caractères.

Cette limite est due aux restrictions de longueur de l&#39;URL Microsoft Internet Explorer.

## Paramètre mbox3rdPartyId

**Limite**: 60 caractères.

## Noms des offres

**Limite**: 250 caractères.

## Taille de l&#39;offre

**Limite**: Les limites de taille suivantes s&#39;appliquent aux offres :

* 256 Ko pour les offres HTML.
* 64 Ko pour les offres visuelles de l’interface utilisateur.
* 512 Ko à partir de l’API.

Si vous utilisez une mbox globale, la limite correspond à l&#39;ensemble du contenu renvoyé pour la page. Le fait de limiter la taille de l’offre optimise les temps de chargement des pages. Si la limite est dépassée, le message suivant s’affiche :

« Contenu pour l’expérience trop volumineux pour être diffusé. Modifiez l’expérience afin d’affecter moins de code de page. »

## Paramètre orderId

**Limite**: 120 caractères.

Limite recommandée.

## Paramètre orderTotal

**Limite**: 120 caractères.

Limite recommandée.

## Paramètre productPurchasedId

**Limite**: 47 caractères par valeurs séparées par des virgules.

Tout ce qui est plus long est tronqué par le système.

## Audiences/compte réutilisables

**Limite**: 75 audiences.

Limite recommandée. Les temporisations JavaScript surviennent dans l’interface s’il y en a trop.

## Zone d&#39;entrée Profil de script dans l&#39;interface utilisateur de Target

**Limite**: 2 000 caractères.

Limite recommandée. Dépend de la taille de la chaîne codée, qui peut être beaucoup plus longue que la chaîne brute. Si la chaîne est trop longue, elle échoue avant de parvenir à Adobe Target.

## Noms des profils de script

**Limite**: 50 caractères.

## Valeurs de profil de script

**Limite**: 2 048 caractères.

Pour des raisons de performances, nous recommandons une valeur renvoyée qui ne dépasse pas 256 caractères.

Pour une valeur renvoyée par une chaîne, si la taille de la valeur renvoyée dépasse 2 048 caractères, le script est désactivé par le système.

Pour une valeur renvoyée par un tableau, si la taille des valeurs concaténées du tableau dépasse 2 048 caractères, le script est désactivé par le système.

## Conditions de ciblage

**Limite**: 1 000 valeurs.

Limite recommandée. Ceci se rapporte au nombre de valeurs séparées par une ligne dans la zone de texte de ciblage ; par exemple, le fait d’entrer 1 000 codes postaux dans une cible de code postal.