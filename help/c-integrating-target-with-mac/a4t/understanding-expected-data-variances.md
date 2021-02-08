---
keywords: écarts de données;analytics;différences;écart;a4t;analytics pour target;analytics en tant que source de reporting;incohérences;incohérence
description: Découvrez les écarts de données attendus entre Adobe Target et Analytics lorsque vous n’utilisez pas Analytics pour la Cible (A4T), ce qui élimine complètement la variance de données.
title: Quel est l’écart de données attendu entre Analytics et A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 95%

---


# Écarts de données attendus entre Target et Analytics lors de l’utilisation ou non de A4T{#expected-data-variances-when-not-using-a-t}

Informations sur les écarts de données attendus entre [!DNL Target] et Adobe [!DNL Analytics] lorsque vous *utilisez* ou *non* Analytics en tant que source de reporting (A4T). A4T réduit considérablement les écarts de données.

## Écarts de données attendus lorsqu’A4T est utilisé {#expected-using-a4t}

Avec A4T, les comptes rendus Analytics et Target des performances d’activités utilisent tous deux exclusivement les données Analytics, de sorte qu’il n’y a que peu d’écart entre les solutions dans les rapports d’activités Target. Cependant, dans certaines circonstances, les clients peuvent comparer les données Target à celles d’Analytics indépendamment de l’intégration A4T et, par conséquent, rencontrer les problèmes d’écart décrits ci-dessous.

Voici quelques scénarios dans lesquels vous pouvez rencontrer une variance de données attendue :

* A4T permet qu’un accès Target (haut de la page) se produise, mais empêche qu’un accès Analytics (bas de la page) ne se produise. Par exemple, l’utilisateur charge la page, mais ferme le navigateur avant que l’appel Analytics ne soit déclenché. Dans ce cas, A4T exclut l’accès Target de nos données. La raison en est que le fait d’autoriser les occurrences de Target (encore une fois, haut de la page) à compter comme des occurrences d’Analytics en l’absence d’un appel Analytics réel créerait des incohérences avec l’ensemble de données d’Analytics (inflation du nombre de visiteurs, etc.).

   Si un test de redirection est configuré dans Target pour séparer le trafic 50/50 (ou 25/25/25/25, etc.), le comportement de l’utilisateur risque de ne pas être réparti uniformément. Si une répartition inégale s’affiche, cela signifie simplement qu’un groupe d’utilisateurs n’a pas réussi à exécuter un appel Analytics sur la page d’entrée plus qu’un autre. Cet échec d’exécution de l’appel Analytics d’un groupe entraînait l’exclusion de l’accès Target pour que cet utilisateur soit exclu, créant ainsi une incohérence.

   C’est quelque chose que nous espérons aborder à l’avenir alors que nous travaillons à la technologie A4T sur Adobe Experience Platform. Nos équipes cherchent à gérer les différents événements qui se produisent à des moments différents sur la page.

   >[!NOTE]
   >
   >Un problème connu entraîne un nombre limité de clients utilisant des redirections avec A4T pour afficher un pourcentage plus élevé de taux d’accès désassemblés. Reportez-vous à la section [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

* Supposons que vous créiez une activité d’affectation automatique ouverte à tous les visiteurs d’une page particulière. Comme les activités d’affectation automatique ne prennent pas en charge A4T, toutes les données d’activité sont collectées par [!DNL Target]. Vous pourriez vous attendre à ce que les visiteurs de l’activité dans le rapport [!DNL Target] correspondent aux visiteurs de cette page dans le rapport [!DNL Analytics] sur une même période. Il s’agit d’un scénario dans lequel l’écart décrit ci-dessous est attendu.

   Pour obtenir une liste complète des types d’activité qui prennent en charge A4T, voir [Types d’activité pris en charge](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA).

## Écarts de données attendus lorsqu’A4T *n’est pas utilisé* {#expected-not-using-a4t}

Ainsi, des écarts de 15 à 20 % sont normaux, même avec des jeux de données identiques. Les systèmes qui appliquent des méthodes de comptage différentes peuvent générer des écarts beaucoup plus élevés, jusqu’à 35-50 %, voire même plus.

Bien que les données réelles puissent considérablement varier, les tendances sont généralement cohérentes. Ainsi, les données demeurent valides et utiles tant que les différences et les tendances restent cohérentes. En cas d’incohérence des différences et des tendances, toutefois, il est possible que la configuration soit incorrecte. Dans ce cas, contactez le représentant de votre compte pour obtenir de l’aide.

[!DNL Analytics] applique un système reposant sur les visites et les transactions, tandis que utilise des mesures basées sur les visiteurs. [!DNL Target] En d’autres termes, chaque fois qu’un visiteur ouvre une page, il est compté comme une visite dans [!DNL Analytics], tandis que [!DNL Target] ne comptabilise la visite que si toutes les conditions configurées dans l’activité sont remplies.

Les rapports dans [!DNL Target] affichent les performances en fonction de la mbox de conversion sélectionnée lors de la définition de l’activité. Toutefois, les données de cette mbox de conversion ne sont pas envoyées à [!DNL Analytics], qui possède ses propres variables de conversion, définies par votre implémentation de balisage [!DNL Analytics]. Dans les cas où vous pourriez vous attendre à des données identiques (par exemple, si la page de confirmation de commande d’un détaillant contient à la fois une mbox de conversion et un événement d’achat [!DNL Analytics]), il est possible que les données diffèrent en raison de l’emplacement de ces balises. En général, les tendances dans deux rapports de produit doivent être semblables.

Les écarts de données attendus peuvent résulter de variations techniques et commerciales.

### Exemples d’écarts techniques  {#section_C3B50ED2E2F9416FAC91437CF1A87369}

Les situations suivantes peuvent provoquer des écarts de données en fonction de différences techniques :

* [!DNL Target]Les visiteurs de doivent autoriser les cookies et JavaScript.
* Les cookies propriétaires et tiers sont traités différemment. Par conséquent, les données issues de ces types de cookies diffèrent
* Emplacement relatif des balises sur les pages et « fuites » dues aux visiteurs qui quittent la page avant qu’elle ne soit complètement chargée.
* Prise en compte des fuseaux horaires.
* Différences de comptage des périphériques.

### Exemples d’écarts commerciaux  {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

Les situations suivantes peuvent provoquer des écarts de données en fonction de différences commerciales :

* Différences entre les mesures des visiteurs et des visites.
* Le ciblage des activités exclut certains visiteurs.
* Une seule mbox peut figurer sur plusieurs pages et compter les visiteurs sur chacune de ces pages.
* Les priorités des activités peuvent inclure certains visiteurs et en exclure d’autres sur une page.
* Les visiteurs ayant effectué une conversion peuvent être recomptés lorsqu’ils entrent à nouveau dans l’activité.
* [!DNL Analytics] compte toutes les conversions pour toutes les visites et tous les visiteurs, tandis que [!DNL Target] comptabilise uniquement les conversions des visites et visiteurs inclus dans l’activité.