---
keywords: limite de caractères;paramètres mbox;api de diffusion par lots;paramètres de profil;limites;profils intégrés;maximum;limite;contrainte;caractère;bonne pratique;orderid;orderTotal;mbox3rdPartyID;catégorie;categoryID;dépannage
description: Affichez une liste des limites de caractères et d’autres limites qui affectent les activités et autres éléments dans [!DNL Adobe Target].
title: Quelles sont les différentes limites de caractère, de taille et autres en  [!DNL Adobe Target] ?
feature: Troubleshooting
mini-toc-levels: 3
exl-id: b318ab16-1382-4f3a-8764-064adf384d6b
source-git-commit: 09874362863144992c69d4b79a935c9d9a769dc1
workflow-type: tm+mt
source-wordcount: '1734'
ht-degree: 74%

---

# Limites

Limites de caractères et autres limites (taille de l’offre, audiences, profils, valeurs, paramètres, etc.) qui affectent les activités et autres éléments dans les [!DNL Adobe Target].

>[!NOTE]
>
>Les limites indiquées ci-dessous doivent être considérées comme des limites « difficiles à utiliser », sauf indication contraire « recommandées ».
>
>Lorsque les limites désignées comme étant « recommandées » sont ciblées ou dépassées, les performances peuvent ralentir. La lenteur du chargement de l’interface peut également être due à une activité très complexe (une activité comprenant de nombreuses audiences, cibles et expériences, par exemple).
>
>Les activités particulièrement complexes doivent être examinées par les conseillers d’[!DNL Adobe] et testées dans un environnement limité avant d’être mises en production.

## Activités

### Noms d’activité

* **Limite** : 250 caractères.

### Nombre d’activités par compte

* **Limite recommandée** : 10 000 activités actives en cours.

* **Limite recommandée** : 10 000 activités actives enregistrées (et non terminées).

## Appels d’API Target

* **Limite** : 50 appels par minute pour les API Admin, Reporting et de mise à jour de profil en masse. Cette limite ne s’applique pas aux API Delivery et de mise à jour de profil unique.

  Si vous effectuez plus de 50 appels d’API par minute, [!DNL Target] renvoie un message d’erreur indiquant « état HTTP 503 ».

## Audiences

### Noms d’audience

* **Limite** : 255 caractères.

### Audiences, réutilisables par compte

* **Limite recommandée** : 20 000 audiences.

### Nombre d’audiences par mbox, mesure ou expérience

* **Limite** : 50 audiences

## Paramètre categoryId

* **Limite** : 256 caractères.

## Diffusion de contenu {#content-delivery}

* **Limite** : 100 requêtes de diffusion de contenu [!DNL Target] simultanées par session utilisateur.

  Si un client dépasse les 100 requêtes de diffusion de contenu [!DNL Target] simultanées pour une session utilisateur donnée, toutes les requêtes suivantes sont bloquées pour cette session utilisateur. Deux requêtes ou plus sont considérées comme simultanées si elles sont toutes envoyées au serveur [!DNL Target] avant que la réponse ne soit reçue pour l’une d’elles. [!DNL Target] traite les requêtes simultanées d’une même session de manière séquentielle.

   * **Comportement d’erreur** :

      * API de diffusion et mbox par lots v2 :
         * Code d’erreur : HTTP 420 Too Many Requests
         * Message d’erreur : « Trop de requêtes avec le même ID de session »

      * API mbox héritée :
         * Contenu par défaut avec le commentaire « Trop de requêtes avec le même ID de session »

      * at.js:
         * Contenu par défaut affiché

* **Limite** : 50 mbox par demande de mbox par lot de diffusion de contenu [!DNL Target].

  Si la demande de mbox de diffusion par lots de contenu est supérieure à 50 mbox par [!DNL Target], un code d’erreur de réponse `HTTP 400` avec un message d’erreur `size must be between 0 and 50`.

  Les requêtes de mbox par lots sont traitées de manière séquentielle, ce qui augmente le temps de réponse global à chaque itération. Plus il y a de mbox sur la requête par lots, plus la latence de réponse attendue est importante et donc le risque de dépassement de délai est élevé. Si le rendu de l’expérience est bloqué sur ces requêtes par lots à latence élevée, la latence peut entraîner une dégradation de l’expérience utilisateur, car les utilisateurs et utilisatrices attendent que les expériences s’affichent.

* **Limite** : taille de corps HTTP POST de 60 Mo pour les requêtes de diffusion de contenu [!DNL Target].

  Si la taille du corps HTTP POST d’une requête de diffusion de contenu [!DNL Target] dépasse 60 Mo, un code d’erreur de réponse `HTTP 413 Request Entity Too Large`.

* **Limite recommandée** : 50 notifications par demande de lot de diffusion [!DNL Target].

  Dépasser 50 notifications par demande de lot de diffusion [!DNL Target] entraîne probablement une latence de réponse et des délais accrus.

  Les demandes de notification par lots sont traitées de manière séquentielle, ce qui augmente le temps de réponse global à chaque itération. Plus il y a de notifications sur la requête par lots, plus la latence de réponse attendue est élevée, et donc le risque de dépassement de délai. Une latence supplémentaire sur les requêtes de notification par lots peut être acceptable pour certains clients. Toutefois, gardez à l’esprit que les dépassements de délai et toute reprise ultérieure peuvent entraîner une latence encore plus importante.

## Attributs du client

### Noms d’attributs du client

* **Limite** : 250 caractères par le biais du flux ou de l’API.

### ID d’alias d’attribut du client

* **Limite** : 50 caractères.

### Attributs du client, chargement

* **Taille maximale du fichier pour chaque chargement à l’aide de la méthode HTTP** : 100 Mo.
* **Taille maximale du fichier pour chaque chargement à l’aide de la méthode FTP** : 4 Go.
* **Nombre d’attributs autorisés à s’abonner** : 5 pour [!DNL Target Standard] et 200 pour [!DNL Target Premium].

## Entités

### Nombre d’entités

* Le nombre maximum d’entités qu’il est possible de référencer dans une conception, que ce soit par le biais de boucles ou d’un codage en dur, est de 99.
* La limite recommandée pour bénéficier de performances optimales consiste à conserver le catalogue à moins d’un million d’articles par environnement et à moins de dix millions d’articles dans tous les environnements.
* La limite maximale est de dix millions d’articles par environnement et de 100 millions d’articles dans tous les environnements. Si vous avez entre un et dix millions d’éléments par environnement, cela aura une incidence sur les performances de l’interface utilisateur [!UICONTROL Catalog Search]. Toutefois, [!DNL Target Recommendations] continue de générer et de fournir des recommandations.

### Attributs d’entité personnalisés

* **Attributs d’entités personnalisés** : 100.

* **Limite de caractères** : la longueur maximale de caractères dépend de la langue.

   * 15 000 caractères (une seule valeur, deux et deux langues)
   * 500 valeurs, 100 caractères par valeur (à plusieurs valeurs)

  La longueur maximale des attributs personnalisés d’entité à valeur unique est de 15 000 caractères (pour les langues codées UTF-8 à un et deux octets, telles que l’anglais et les autres langues en alphabet latin) ou de 10 000 caractères (pour les langues codées UTF-8 à trois octets, telles que le chinois, le japonais et le coréen).

  Les attributs personnalisés d’entité à plusieurs valeurs ne peuvent pas contenir plus de 500 valeurs. Chaque valeur individuelle est limitée à 100 caractères. Le nombre total de caractères pour toutes les valeurs doit se conformer aux limites de la longueur maximale des attributs personnalisés d’entité à une valeur unique (voir ci-dessus).

### entity.id

* **Limite pour les implémentations qui nécessitent la capture d’informations d’achat** : 50 caractères.

  Cette limite est appliquée, car le paramètre mbox `productPurchasedId` capture le paramètre entity.ids, ce qui limite le nombre de caractères à 50.

* **Limite pour les implémentations qui nécessitent uniquement des algorithmes basés sur les vues** : 1 000 caractères.

  Les algorithmes basés sur les vues incluent les vues/vues, les plus consultés, récemment consultés, etc.

## excludedIds {#excludedid}

* **Limite** : 5 Ko pour les requêtes POST. 2 083 caractères moins la longueur de l’URL pour les requêtes GET.

  Pour les requêtes GET, bien que la limite de l’arrière-plan soit de 5 Ko, en raison du fait que Microsoft Internet Explorer limite l’URL à 2 083 caractères, la limite réaliste est de 2 083 caractères, moins la longueur actuelle de l’URL.

## Expériences

### Noms d’expériences

* **Limite** : 50 caractères.

### Expériences par activité

* **Limite** : 2 000 expériences par [!UICONTROL Experience Targeting] (XT), [!UICONTROL A/B Test], [!UICONTROL Multivariate Test] (MVT) et activité [!UICONTROL Auto-Target].

  30 000 expériences par activité d’Automated Personalization (AP).

### Modifications par expérience

* **Limite** : 50 par expérience, quelle que soit lʼactivité.

## mbox

### Valeur d’attribut de profil interne à mbox {#in-mbox}

* **Limite** : 256 caractères.

  Les valeurs de plus de 256 caractères sont tronquées lors de l’utilisation d’at.js 1.*x*. Vous recevez un message d’erreur lors de l’envoi de valeurs de plus de 256 caractères lors de l’utilisation d’at.js 2.*x* ou la [!DNL Adobe Experience Platform Web SDK]. Les valeurs ne sont pas automatiquement tronquées.

### Noms des profils internes à mbox

* **Limite** : 128 caractères.

### mbox names {#mbox-names}

* **Limite** : 250 caractères.

  Par [!DNL Delivery API] (at.js 2.*x*), les intégrations de mbox par lot V2 et [!DNL Adobe Experience Platform Web SDK] (alloy.js), les noms de mbox *peuvent* contenir des caractères alphanumériques (A-Z, a-z, 0-9) et l’un des caractères suivants :

  ```
  - , . _ / = ` : ; & ! @ # $ % ^ & * ( ) _ + | ? ~ [ ] { }
  ```

  Pour at.js 1.Les intégrations *x*, les noms de mbox *ne peuvent pas* contenir l’un des caractères suivants :

  ```
  ' " %22 %27 < > %3C %3E 
  ```

### Paramètres mbox {#mbox-parameters}

* **Limite** : Les limites suivantes s’appliquent aux paramètres mbox :

  Pour les appels mbox standard :

   * Paramètres mbox : 500 paramètres par mbox.
   * Paramètres de profil : 500 paramètres de profil par mbox.
   * Autres paramètres (URL, URL de référence, etc.): 50 par mbox pour chaque autre type de paramètre.

  Ces limites sont appliquées à moins que la requête ne soit abrégée en raison des restrictions du navigateur web.

  Si vous utilisez l’API de diffusion par lots, la limite est de 50 mbox par requête de lot.

  Si vous utilisez l’API de diffusion par lots dans le SDK Mobile Services, la limite de 50 paramètres de mbox, 50 paramètres de profil et 50 pour les autres types de paramètres sont les limites de l’API elle-même. Il est impossible d’envoyer une requête contenant plus que ces nombres à l’aide de l’API de diffusion par lots. Si une requête dépasse ces limites, l’API renvoie le message d’erreur suivant :

  « Le nombre de mboxParameters ne peut pas dépasser 50. »

  Limites définies pour les points d’entrée :

  **mbox par lot v2** :

   * Paramètres mbox : 100
   * Longueur maximale du nom du paramètre mbox : 128
   * La valeur du paramètre mbox ne peut pas être nulle.
   * Valeur du paramètre mbox : 5 000
   * Paramètres de profil : 50
   * Longueur maximale du nom du paramètre de profil : 128
   * La valeur du paramètre de profil ne peut pas être nulle.
   * Longueur maximale de la valeur du paramètre de profil : 5000

  **Point d’entrée de l’API de diffusion** :

   * Paramètres mbox : 100
   * Longueur maximale du nom du paramètre mbox : 128
   * La valeur du paramètre mbox ne peut pas être nulle.
   * Valeur du paramètre mbox : 5 000
   * Paramètres de profil : 50
   * Longueur maximale du nom du paramètre de profil : 128
   * La valeur du paramètre de profil ne peut pas être nulle.
   * Longueur maximale de la valeur du paramètre de profil : 5000

### URL de requête mbox

* **Limite** : 2 083 caractères.

  Cette limite est due aux restrictions de longueur de l’URL Microsoft Internet Explorer.

### Paramètre mbox3rdPartyId

* **Limite** : 256 caractères.

## Offres

### Noms d’offre

* **Limite** : 250 caractères.

### Nombre d’offres

* **Limite** : 150 000 offres totales.

  Les erreurs de synchronisation des activités se produisent si la limite de 150 000 offres est dépassée.

### Taille de l’offre {#offer-size}

Les limites de taille suivantes s’appliquent aux offres :

* 1 024 Ko pour les offres HTML.
* 1 024 Ko (pour chaque expérience) pour les offres visuelles provenant de l’interface utilisateur.
* 1 024 Ko à partir de l’API.

  Si vous utilisez une mbox globale, la limite se rapporte à l’ensemble du contenu renvoyé pour la page. Le fait de limiter la taille de l’offre optimise les temps de chargement des pages. Si la limite est dépassée, le message suivant s’affiche :

  « Contenu pour l’expérience trop volumineux pour être diffusé. Modifiez l’expérience afin d’affecter moins de code de page. »

## Paramètre orderId

* **Limite recommandée** : 120 caractères.

## Paramètre orderTotal

* **Limite recommandée** : 120 caractères.

## Paramètre productPurchasedId

* **Limite** : 50 caractères par valeur séparée par des virgules et 250 caractères au total. Les valeurs individuelles de plus de 50 caractères sont tronquées par le système. Les longueurs totales supérieures à 250 caractères génèrent une erreur 400.

## Scripts de profil

* **Limite recommandée pour les scripts de profil actifs (ceux qui sont activés)** : 300

* **Limite recommandée du nombre total de scripts de profil par compte** : 2 000

* **Recommandations pour limiter la complexité des scripts de profil** : les scripts de profil peuvent exécuter un nombre limité d’instructions. Pour plus d’informations, consultez [Bonnes pratiques](/help/main/c-target/c-visitor-profile/profile-parameters.md#best) dans *Attributs de profil*.

## Propriétés

* **Limite recommandée** : 5 000 propriétés.

## Audiences/segments créant des rapports

* **Limite** : 50 audiences/segments créant des rapports par activité.

## sessionID

L’ID de session peut être n’importe quelle chaîne imprimable, à l’exception d’un espace ou d’un point d’interrogation ( ? ), des accolades ( { } ) ou une barre oblique ( / ). Elle doit comporter entre 1 et 128 caractères.

## Zone d’entrée Profil de script dans l’interface utilisateur de [!DNL Target]

* **Limite recommandée** : 2 000 caractères.

  Dépend de la taille de la chaîne codée, qui peut être beaucoup plus longue que la chaîne brute. Si la chaîne est trop volumineuse, elle échoue avant d’arriver à [!DNL Adobe Target].

## Profils de script

### Noms des profils de script

* **Limite** : 50 caractères.

### Valeurs de profil de script

* **Limite** : 2 048 caractères.

  Pour des raisons de performances, nous recommandons une valeur renvoyée qui ne dépasse pas 256 caractères.

  Pour une valeur renvoyée par une chaîne, si la taille de la valeur renvoyée dépasse 2 048 caractères, le script est désactivé par le système.

  Pour une valeur renvoyée par un tableau, si la taille des valeurs concaténées du tableau dépasse 2 048 caractères, le script est désactivé par le système.

## Mesures de succès

* **Limite** : 200 par activité.

## Ciblage

### Conditions de cible

* **Limite recommandée** : 1 000 valeurs.

  Ceci se rapporte au nombre de valeurs séparées par une ligne dans la zone de texte de ciblage ; par exemple, le fait d’entrer 1 000 codes postaux dans une cible de code postal.

### Règles de ciblage {#targeting-rules}

* **Limite recommandée** : 2 500 caractères par valeur de règle de ciblage.
* **Limite recommandée** : 50 000 valeurs uniques par audience dans les règles de ciblage.
* **Limite recommandée** : 100 000 valeurs de règle de ciblage uniques par activité.
