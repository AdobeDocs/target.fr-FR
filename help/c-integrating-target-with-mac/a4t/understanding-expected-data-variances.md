---
description: Informations sur les écarts de données attendus entre Target et Adobe Analytics lorsque vous n’utilisez pas Analytics en tant que source des rapports (A4T), ce qui élimine complètement la variance de données.
keywords: écarts de données;analytics;différences;écart;a4t;analytics pour target;analytics en tant que source de reporting;incohérences;incohérence
seo-description: Informations sur les écarts de données attendus entre Target et Adobe Analytics lorsque vous n’utilisez pas Analytics en tant que source des rapports (A4T), ce qui élimine complètement la variance de données.
seo-title: Écarts de données attendus lorsqu’A4T n’est pas utilisé
solution: Target
title: Écarts de données attendus lorsqu’A4T n’est pas utilisé
topic: Advanced
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Écarts de données attendus entre Target et Analytics lors de l’utilisation ou non de A4T{#expected-data-variances-when-not-using-a-t}

Informations sur les écarts de données attendus entre [!DNL Target] et Adobe [!DNL Analytics] lors *de l&#39;utilisation* et *de la non* utilisation d&#39;Analytics en tant que source de création de rapports (A 4 T). A4T réduit considérablement les écarts de données.

## Variance de données attendue lors de l&#39;utilisation de A 4 T {#expected-using-a4t}

Avec A4T, les comptes rendus Analytics et Target des performances d’activités utilisent tous deux exclusivement les données Analytics, de sorte qu’il n’y a que peu d’écart entre les solutions dans les rapports d’activités Target. Cependant, dans certaines circonstances, les clients peuvent comparer les données Target à celles d’Analytics indépendamment de l’intégration A4T et, par conséquent, rencontrer les problèmes d’écart décrits ci-dessous.

Voici quelques scénarios dans lesquels vous pouvez rencontrer une variance de données attendue :

* A 4 T autorise la possibilité qu&#39;un accès Target (haut de la page) se produise, mais qu&#39;aucun accès Analytics (bas de la page) ne se produise. Par exemple, l&#39;utilisateur charge la page, mais ferme le navigateur avant que l&#39;appel Analytics ne soit déclenché. Dans ce cas, A 4 T exclut l&#39;accès Target de nos données. Cela est dû au fait que la possibilité d&#39;autoriser les accès Target (de nouveau, la partie supérieure de la page) sera comptabilisée comme des accès Analytics en l&#39;absence d&#39;un appel Analytics réel créerait des incohérences avec le jeu de données dans Analytics (augmentation du nombre de visiteurs, etc.).

   Si un test de redirection est configuré dans Target pour séparer le trafic 50/50 (ou 25/25/25/25, etc.), le comportement de l&#39;utilisateur risque de ne pas être réparti uniformément. Si une répartition inégale s&#39;affiche, cela signifie simplement qu&#39;un groupe d&#39;utilisateurs n&#39;a pas réussi à exécuter un appel Analytics sur la page d&#39;entrée plus que l&#39;autre. Cet échec d&#39;exécution de l&#39;appel Analytics d&#39;un groupe entraînait l&#39;exclusion de l&#39;accès Target pour que cet utilisateur soit exclu, créant ainsi une incohérence.

   Nous espérons que nous nous adresserons à A 4 T sur la plate-forme Adobe Experience Platform à l&#39;avenir. Nos équipes cherchent à gérer les différents événements qui se produisent à des moments différents sur la page.

* Supposons que vous créiez une activité d&#39;affectation automatique ouverte à tous les visiteurs d&#39;une page particulière. Comme les activités d’affectation automatique ne prennent pas en charge A4T, toutes les données d’activité sont collectées par [!DNL Target]. Vous pourriez vous attendre à ce que les visiteurs de l’activité dans le rapport [!DNL Target] correspondent aux visiteurs de cette page dans le rapport [!DNL Analytics] sur une même période. Il s’agit d’un scénario dans lequel l’écart décrit ci-dessous est attendu.

   Pour obtenir une liste complète des types d’activité qui prennent en charge A4T, voir [Types d’activité pris en charge](../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA).

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