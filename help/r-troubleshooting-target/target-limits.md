---
keywords: character limit;mbox parameters;batch delivery api;profile parameters;limits;built in profiles;maximum;limit;constraint;character;best practice;orderid;orderTotal;mbox3rdPartyID;category;categoryID
description: Informations sur les limitations de caractères et autres limitations (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et d’autres éléments dans Adobe Target.
title: Limites
topic: Standard
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
translation-type: tm+mt
source-git-commit: fa7e418cdbd3a9a7e853111c23eb80bdb411ee58

---


# Limites{#limits}

Informations sur les limitations de caractères et autres limitations (taille des offres, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et d’autres éléments dans Adobe Target.

>[!NOTE]
>
>Les limites indiquées ci-dessous doivent être considérées comme des limites « difficiles à utiliser », sauf indication contraire « recommandées ».
>
>Lorsque les limites désignées comme étant « recommandées » sont ciblées ou dépassées, les performances peuvent ralentir. La lenteur du chargement de l’interface peut également être due à une activité très complexe (une activité comprenant de nombreuses audiences, cibles et expériences, par exemple).
>
>Les activités particulièrement complexes doivent être examinées par les conseillers d’Adobe et testées dans un environnement limité avant d’être mises en production.

## Activités

**Limite recommandée** : 10 000 activités en cours.

**Limite** recommandée : 10 000 activités actives enregistrées (et non terminées).

## Noms d’activité

**Limite** : 250 caractères.

## Noms d’audience

**Limite** : 255 caractères.

## Audiences

**Limite** : 50 audiences par mbox, mesure ou expérience.

## Paramètre categoryId

**Limite** : 128 caractères.

## Noms d’attributs du client

**Limite** : 128 caractères.

## ID d’alias d’attribut du client

**Limite** : 50 caractères.

## Attributs d’entité personnalisés

**Limite** : La longueur maximale dépend de la langue.

* 15 000 caractères (une seule valeur, deux et deux langues)
* 500 valeurs, 100 caractères par valeur (à plusieurs valeurs)

La longueur maximale des attributs personnalisés d’entité à valeur unique est de 15 000 caractères (pour les langues codées UTF-8 à un et deux octets, telles que l’anglais et les autres langues en alphabet latin) ou de 10 000 caractères (pour les langues codées UTF-8 à trois octets, telles que le chinois, le japonais et le coréen).

Les attributs personnalisés d’entité à plusieurs valeurs ne peuvent pas contenir plus de 500 valeurs. Chaque valeur individuelle est limitée à 100 caractères. Le nombre total de caractères pour toutes les valeurs doit se conformer aux limites de la longueur maximale des attributs personnalisés d’entité à une valeur unique (voir ci-dessus).

## entityID parameters

**Limite** : 1 000 caractères.

## excludedIds {#excludedid}

**Limite** : 5 Ko pour les requêtes POST. 2 083 caractères moins la longueur de l’URL pour les requêtes GET.

Pour les requêtes GET, bien que la limite de l’arrière-plan soit de 5 Ko, en raison du fait que Microsoft Internet Explorer limite l’URL à 2 083 caractères, la limite réaliste est de 2 083 caractères, moins la longueur actuelle de l’URL.

## Noms d’expériences

**Limite** : 50 caractères.

## Expériences par activité

**Limite** : 2 000 expériences par ciblage d’expérience (XT), test A/B, test multivarié (MVT) et activité de ciblage automatique.

30 000 expériences par activité d’Automated Personalization (AP).

## Valeur d’attribut de profil interne à mbox

**Limite** : 256 caractères.

Les valeurs plus longues sont tronquées.

## Profils internes à mbox dans une requête de mbox

**Limite** : 50 profils.

Tous les profils suivants sont ignorés.

## Noms des profils internes à mbox

**Limite** : 128 caractères.

## mbox names

**Limite** : 250 caractères.

## Paramètres mbox

**Limite** : Les limites suivantes s’appliquent aux paramètres mbox :

Pour les appels de mbox standard :
* Paramètres mbox : 500 paramètres par mbox.
* Paramètres de profil : 500 paramètres de profil par mbox.
* Autres paramètres (URL, URL de référence, etc.): 50 par mbox pour chaque autre type de paramètre.

Ces limites sont appliquées à moins que la requête ne soit abrégée en raison des restrictions du navigateur Web.

Si vous utilisez l’API de remise par lot, la limite est de 50 mbox par requête de lot.

Si vous utilisez l’[API de livraison par lots](https://developers.adobetarget.com/api/#server-side-batch-delivery) dans le SDK Mobile Services, la limite de 50 paramètres de mbox, 50 paramètres de profil et 50 pour les autres types de paramètres sont les limites de l’API elle-même. Il est impossible d’envoyer une requête contenant plus que ces nombres à l’aide de l’API de livraison par lots. Si une requête contient plus de ces limites, l’API renvoie le message d’erreur suivant :

&quot;Le nombre de mboxParameters ne peut pas dépasser 50.&quot;

Limites définies pour les points de fin :

Mbox par lot v2 :
* Paramètres de mbox 100
* longueur max. du nom du paramètre mbox 128
* La valeur du paramètre mbox ne peut pas être nulle.
* valeur du paramètre mbox 5000
* paramètres de profil 50
* nom du paramètre de profil longueur max. 128
* la valeur du paramètre de profil ne peut pas être nulle
* longueur maximale du paramètre de profil 256

Point de terminaison de l’API de remise
* paramètres de mbox 50
* longueur max. du nom du paramètre mbox 128
* La valeur du paramètre mbox ne peut pas être nulle.
* valeur du paramètre mbox 5000
* paramètres de profil 50
* nom du paramètre de profil longueur max. 128
* la valeur du paramètre de profil ne peut pas être nulle
* longueur maximale du paramètre de profil 256

## URLs de requête mbox

**Limite** : 2 083 caractères.

Cette limite est due aux restrictions de longueur de l’URL Microsoft Internet Explorer.

## Paramètre mbox3rdPartyId

**Limite** : 60 caractères.

## Noms d’offre

**Limite** : 250 caractères.

## Taille de l’offre

**Limite** : Les limites de taille suivantes s’appliquent aux offres :

* 256 Ko pour les offres HTML.
* 64 Ko pour les offres visuelles de l’interface utilisateur.
* 512 Ko à partir de l’API.

Si vous utilisez une mbox globale, la limite se rapporte à l’ensemble du contenu renvoyé pour la page. Le fait de limiter la taille de l’offre optimise les temps de chargement des pages. Si la limite est dépassée, le message suivant s’affiche :

« Contenu pour l’expérience trop volumineux pour être diffusé. Modifiez l’expérience afin d’affecter moins de code de page. »

## Offres

**Limite recommandée** : 50 000 offres totales.

## Paramètre orderId

**Limite recommandée** : 120 caractères.

## Paramètre orderTotal

**Limite recommandée** : 120 caractères.

## Paramètre productPurchasedId

**Limite** : 47 caractères par valeur séparée par une virgule.

Tout ce qui est plus long est tronqué par le système.

## Scripts de profil

**Limite recommandée des scripts** de profil actifs : 300

**Limite recommandée du nombre total de scripts de profil par compte**: 2 000

**Recommandations pour limiter la complexité** des scripts de profil : Les scripts de profil peuvent exécuter un nombre limité d’instructions. Pour plus d’informations, voir [Meilleures pratiques](/help/c-target/c-visitor-profile/profile-parameters.md#best) dans les attributs *de* profil.

## Propriétés

**Limite recommandée** : 5 000 propriétés.

## Audiences/segments créant des rapports

**Limite** : 50 audiences/segments créant des rapports par activité.

## Audiences/compte réutilisables

**Limite recommandée** : 75 audiences.

Les temporisations JavaScript surviennent dans l’interface s’il y en a trop.

## Zone d’entrée Profil de script dans l’interface utilisateur de Target

**Limite recommandée** : 2 000 caractères.

Dépend de la taille de la chaîne codée, qui peut être beaucoup plus longue que la chaîne brute. Si la chaîne est trop longue, elle échoue avant de parvenir à Adobe Target.

## Noms des profils de script

**Limite** : 50 caractères.

## Valeurs de profil de script

**Limite** : 2 048 caractères.

Pour des raisons de performances, nous recommandons une valeur renvoyée qui ne dépasse pas 256 caractères.

Pour une valeur renvoyée par une chaîne, si la taille de la valeur renvoyée dépasse 2 048 caractères, le script est désactivé par le système.

Pour une valeur renvoyée par un tableau, si la taille des valeurs concaténées du tableau dépasse 2 048 caractères, le script est désactivé par le système.

## Mesures de succès

**Limite** : 200 par activité.

## Conditions de cible

**Limite recommandée** : 1 000 valeurs.

Ceci se rapporte au nombre de valeurs séparées par une ligne dans la zone de texte de ciblage ; par exemple, le fait d’entrer 1 000 codes postaux dans une cible de code postal.

## Règles de ciblage

**Limite** recommandée : 2 500 caractères par valeur de règle de ciblage.

**Limite recommandée** : 30 000 valeurs uniques par audience dans les règles de ciblage.

**Limite recommandée** : 100 000 valeurs de règle de ciblage uniques par activité.

