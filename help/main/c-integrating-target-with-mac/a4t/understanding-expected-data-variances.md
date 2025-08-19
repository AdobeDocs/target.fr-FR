---
keywords: écarts de données;analytics;différences;écart;a4t;analytics pour target;analytics en tant que source de reporting;incohérences;incohérence
description: Découvrez les écarts de données attendus entre Adobe et Analytics lorsque vous n [!DNL Target] utilisez pas Analytics for [!DNL Target] (A4T), ce qui élimine complètement les écarts de données.
title: Quelle est la variance des données attendue entre Analytics et A4T ?
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 45%

---

# Écarts de données attendus entre Adobe [!DNL Target] et Adobe Analytics lors de l’utilisation ou de la non-utilisation d’A4T

Informations sur les écarts de données attendus entre [!DNL Target] et Adobe [!DNL Analytics] lorsque vous *utilisez* ou *non* Analytics en tant que source de reporting (A4T). A4T réduit considérablement les écarts de données.

## Variance de données attendue lors de l’utilisation d’A4T {#expected-using-a4t}

Avec A4T, les comptes rendus Analytics et Target des performances d’activités utilisent tous deux exclusivement les données Analytics, de sorte qu’il n’y a que peu d’écart entre les solutions dans les rapports d’activités Target. Cependant, dans certains cas, les clients comparent les données Target aux données Analytics en dehors de la portée de l’intégration A4T et rencontrent donc les problèmes d’écart décrits ci-dessous.

Voici quelques scénarios dans lesquels vous pouvez rencontrer la variance attendue des données :

* A4T permet qu’un accès Target (haut de la page) se produise, mais empêche qu’un accès Analytics (bas de la page) ne se produise. Supposons, par exemple, qu’un visiteur charge la page, mais ferme le navigateur avant le déclenchement de l’appel Analytics. Dans ces cas, A4T exclut l’accès à Target des données. Autoriser les accès à Target (toujours en haut de la page) à compter comme accès Analytics en l’absence d’appel Analytics réel crée des incohérences avec les données définies dans Analytics (inflation des visiteurs, etc.).

  Si un test de redirection est configuré dans Target pour répartir le trafic 50/50 (ou 25/25/25/25, etc.), le comportement de l’utilisateur peut ne pas être divisé de manière égale. Si vous constatez une répartition inégale, cela signifie simplement qu’un groupe d’utilisateurs n’a pas réussi à exécuter un appel Analytics sur la page de destination plus souvent que les autres groupes. Cet échec d’exécution de l’appel Analytics d’un groupe entraînait l’exclusion de l’accès Target pour que cet utilisateur soit exclu, créant ainsi une incohérence.

  Adobe espère résoudre ce problème à l’avenir, car les équipes d’Adobe travaillent sur A4T sur Adobe Experience Platform. Les équipes d’Adobe déterminent comment gérer ces différents événements se produisant à différents moments sur la page.

## Écarts de données attendus lorsqu’A4T *n’est pas utilisé* {#expected-not-using-a4t}

Ainsi, des écarts de 15 à 20 % sont normaux, même avec des jeux de données identiques. Les systèmes qui appliquent des méthodes de comptage différentes peuvent générer des écarts beaucoup plus élevés, jusqu’à 35-50 %, Parfois, les écarts peuvent être encore plus élevés.

Bien que les données réelles puissent considérablement varier, les tendances sont généralement cohérentes. Ainsi, les données demeurent valides et utiles tant que les différences et les tendances restent cohérentes. En cas d’incohérence des différences et des tendances, toutefois, il est possible que la configuration soit incorrecte. Dans ce cas, contactez le représentant de votre compte pour obtenir de l’aide.

[!DNL Analytics] applique un système reposant sur les visites et les transactions, tandis que utilise des mesures basées sur les visiteurs. [!DNL Target] Chaque fois qu’un visiteur ouvre une page, celle-ci est comptabilisée comme une visite dans [!DNL Analytics], mais [!DNL Target] ne la comptabilise pas tant que les conditions définies dans l’activité ne sont pas remplies.

Les rapports dans [!DNL Target] affichent les performances en fonction de la mbox de conversion sélectionnée lors de la définition de l’activité. Toutefois, ces données de mbox de conversion ne sont pas envoyées à [!DNL Analytics], qui possède ses propres variables de conversion, telles que définies par votre implémentation de balisage [!DNL Analytics]. Lorsque vous vous attendez à des données identiques (par exemple, si une commande retailer confirme que la page contient à la fois une mbox de conversion et un événement d’achat [!DNL Analytics]), les données peuvent différer en raison de l’emplacement de ces balises. En général, les tendances des rapports des deux produits sont similaires.

Les écarts de données attendus peuvent résulter de variations techniques et commerciales.

### Exemples d’écarts techniques {#section_C3B50ED2E2F9416FAC91437CF1A87369}

Les situations suivantes peuvent provoquer des écarts de données en fonction de différences techniques :

* [!DNL Target]Les visiteurs de doivent autoriser les cookies et JavaScript.
* Les cookies propriétaires et tiers sont traités différemment. Par conséquent, les données issues de ces types de cookies diffèrent
* Emplacement relatif des balises sur les pages et « fuites » dues aux visiteurs qui quittent la page avant qu’elle ne soit complètement chargée.
* Prise en compte des fuseaux horaires.
* Différences de comptage des périphériques.

### Exemples d’écarts commerciaux {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

Les situations suivantes peuvent provoquer des écarts de données en fonction de différences commerciales :

* Différences entre les mesures des visiteurs et des visites.
* Le ciblage des activités exclut certains visiteurs.
* Une mbox unique sur plusieurs pages, comptant les visiteurs sur chacune de ces pages
* Les priorités des activités peuvent inclure certains visiteurs et en exclure d’autres sur une page
* Les visiteurs qui ont effectué une conversion peuvent être comptabilisés à nouveau lorsqu’ils rejoignent l’activité
* [!DNL Analytics] compte toutes les conversions pour toutes les visites et tous les visiteurs, tandis que [!DNL Target] comptabilise uniquement les conversions des visites et visiteurs inclus dans l’activité.
