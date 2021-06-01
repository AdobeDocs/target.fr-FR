---
keywords: service à la clientèle;cname;programme de certificat;nom canonique;cookies;certificat;amc;certificat géré adobe;digicert;validation du contrôle de domaine;dcv
description: Contactez le service à la clientèle d’Adobe pour mettre en oeuvre la prise en charge CNAME (nom canonique) dans Adobe [!DNL Target] afin de gérer les problèmes de blocage des publicités ou les stratégies de cookies liées à ITP.
title: Comment utiliser CNAME dans Target ?
feature: Confidentialité et sécurité
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 0327f4450ad7b764b01091a106e3dfd3160ffbaf
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 2%

---

# CNAME et Adobe Target

Instructions pour travailler avec [!DNL Adobe] le service à la clientèle pour mettre en oeuvre la prise en charge du CNAME (nom canonique) dans [!DNL Adobe Target]. Utilisez CNAME pour gérer les problèmes de blocage des publicités ou les stratégies de cookies liées à ITP (Intelligent Tracking Prevention). Avec CNAME, les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par [!DNL Adobe].

## Demande de la prise en charge du CNAME dans Target

1. Déterminez la liste des noms d’hôtes dont vous avez besoin pour votre certificat SSL (voir la FAQ ci-dessous).

1. Pour chaque nom d’hôte, créez un enregistrement CNAME dans votre DNS pointant vers votre nom d’hôte [!DNL Target] habituel `clientcode.tt.omtrdc.net`.

   Par exemple, si votre code client est &quot;client&quot; et que votre nom d’hôte proposé est `target.example.com`, votre enregistrement CNAME DNS ressemble à :

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >L’autorité de certification de l’Adobe, DigiCert, ne peut pas émettre de certificat tant que cette étape n’est pas terminée. Par conséquent, [!DNL Adobe] ne peut pas répondre à votre demande d’implémentation CNAME tant que cette étape n’est pas terminée.

1. [Remplissez ce ](/help/assets/FPC_Request_Form.xlsx) formulaire et incluez-le lorsque vous  [ouvrez un ticket Adobe ClientCare demandant la prise en charge du CNAME](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) :

   * Adobe [!DNL Target] code client :
   * Noms d’hôte de certificat SSL (exemple : `target.example.com target.example.org`) :
   * Acheteur de certificat SSL (l’Adobe est vivement recommandé, voir FAQ) : Adobe/client
   * Si le client achète le certificat, également appelé &quot;Apportez votre propre certificat&quot; (BYOC), renseignez les détails supplémentaires suivants :
      * Organisation des certificats (exemple : Exemple Entreprise Inc) :
      * Entité organisationnelle du certificat (facultatif, exemple : Marketing) :
      * Pays du certificat (exemple : US) :
      * État/région du certificat (exemple : Californie) :
      * Ville du certificat (exemple : San Jose) :

1. Si [!DNL Adobe] achète le certificat, [!DNL Adobe] fonctionne avec DigiCert pour acheter et déployer le certificat sur les serveurs de production d’Adobe.

   Si le client achète le certificat (BYOC), [!DNL Adobe] le service à la clientèle vous envoie la demande de signature de certificat (CSR). Utilisez la demande de signature de certificat lors de l’achat du certificat par l’intermédiaire de votre autorité de certification de votre choix. Une fois le certificat émis, envoyez une copie du certificat et de tous les certificats intermédiaires à [!DNL Adobe] l’assistance clientèle pour le déploiement.

   [!DNL Adobe] Le service à la clientèle vous avertit lorsque votre mise en oeuvre est prête.

1. Mettez à jour `serverDomain` vers le nouveau CNAME dans at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquentes sur la demande et l’implémentation de la prise en charge CNAME dans [!DNL Target] :

### Puis-je fournir mon propre certificat (Bring Your own Certificate ou BYOC) ?

Vous pouvez fournir votre propre certificat. Cependant, [!DNL Adobe] ne recommande pas cette pratique. La gestion du cycle de vie du certificat SSL est plus facile pour [!DNL Adobe] et vous si [!DNL Adobe] achète et contrôle le certificat. Les certificats SSL doivent être renouvelés chaque année. Par conséquent, [!DNL Adobe] le service à la clientèle doit vous contacter chaque année pour obtenir un nouveau certificat en temps opportun. Certains clients peuvent avoir des difficultés à produire un certificat renouvelé dans les délais impartis. Votre mise en oeuvre de [!DNL Target] est mise en danger lorsque le certificat expire car les navigateurs refusent les connexions.

>[!IMPORTANT]
>
>Si vous demandez une mise en oeuvre CNAME [!DNL Target] bring your own certificate, vous êtes responsable de fournir des certificats renouvelés au service à la clientèle [!DNL Adobe] chaque année. Le fait d’autoriser votre certificat CNAME à expirer avant [!DNL Adobe] peut déployer un certificat renouvelé entraîne une interruption de votre mise en oeuvre [!DNL Target] spécifique.

### Combien de temps avant l’expiration de mon nouveau certificat SSL ?

Les certificats émis avant le 1er septembre 2020 sont des certificats de deux ans. Les certificats émis le 1er septembre 2020 ou après cette date sont des certificats d’un an. Vous pouvez en savoir plus sur le passage à des certificats d’un an [ici](https://www.digicert.com/position-on-1-year-certificates).

### Quels noms d’hôtes dois-je choisir ? Combien de noms d’hôtes par domaine dois-je choisir ?

[!DNL Target] Les implémentations CNAME ne nécessitent qu’un seul nom d’hôte par domaine sur le certificat SSL et dans le DNS du client. Adobe recommande un nom d’hôte. Certains clients ont besoin de davantage de noms d’hôtes par domaine à leurs propres fins (test dans l’évaluation, par exemple), qui est pris en charge.

La plupart des clients choisissent un nom d’hôte tel que `target.example.com`. Adobe recommande de suivre cette pratique, mais le choix est finalement le vôtre. Ne demandez pas de nom d’hôte d’un enregistrement DNS existant. Cela provoque un conflit et retarde la résolution de votre demande CNAME [!DNL Target].

### J’ai déjà une implémentation CNAME pour [!DNL Adobe Analytics]. Pouvons-nous utiliser le même certificat ou nom d’hôte ?

Non, [!DNL Target] nécessite un nom d’hôte et un certificat distincts.

### Mon implémentation actuelle de [!DNL Target] est-elle affectée par ITP 2.x ?

Dans un navigateur Safari, accédez au site web sur lequel vous disposez d’une bibliothèque JavaScript [!DNL Target]. Si un cookie [!DNL Target] est défini dans le contexte d’un CNAME, tel que `analytics.company.com`, alors vous n’êtes pas affecté par ITP 2.x.

Les problèmes ITP peuvent être résolus pour [!DNL Target] avec un seul CNAME [!DNL Analytics]. Vous avez besoin d’un CNAME [!DNL Target] distinct uniquement dans les scénarios de blocage des publicités où [!DNL Target] est bloqué.

Pour plus d’informations sur ITP, voir [ITP (Intelligent Tracking Prevention) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) d’Apple.

### À quel type de interruption de service puis-je m’attendre lorsque mon implémentation CNAME est déployée ?

Il n’y a aucune interruption de service lorsque le certificat est déployé (y compris les renouvellements de certificat).

Cependant, après avoir remplacé le nom d’hôte dans votre code d’implémentation [!DNL Target] (`serverDomain` dans at.js) par le nouveau nom d’hôte CNAME (`target.example.com`), les navigateurs Web traitent les visiteurs récurrents comme de nouveaux visiteurs. Les données de profil des visiteurs récurrents sont perdues car le cookie précédent est inaccessible sous l’ancien nom d’hôte (`clientcode.tt.omtrdc.net`). Le cookie précédent est inaccessible en raison des modèles de sécurité du navigateur. Cette interruption se produit uniquement lors de la coupure initiale du nouveau CNAME. Les renouvellements de certificats n’ont pas le même effet, car le nom d’hôte ne change pas.

### Quel type de clé et quel algorithme de signature de certificat sont utilisés pour mon implémentation CNAME ?

Tous les certificats sont RSA SHA-256 et les clés sont RSA 2048 bits, par défaut. Les tailles de clés supérieures à 2 048 bits ne sont actuellement pas prises en charge.

### Comment puis-je vérifier que mon implémentation CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande macOS ou Linux, en utilisant bash et curl 7.49+) :

1. Collez cette fonction bash dans votre terminal :

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Collez la commande suivante (en remplaçant `target.example.com` par votre nom d’hôte) :

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si l’implémentation est prête, la sortie s’affiche comme ci-dessous. La partie importante est que toutes les lignes incluent `CN=target.example.com`, qui correspond au nom d’hôte souhaité. Si des lignes contiennent `CN=*.tt.omtrdc.net`, l’implémentation n’est **pas** prête.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Validez votre nouveau CNAME DNS avec une autre requête curl, qui doit également afficher `CN=target.example.com` :

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si cette commande échoue mais que la commande `validateEdgeFpsslSni` ci-dessus réussit, attendez que vos mises à jour DNS se propagent complètement. Les enregistrements DNS ont une [TTL (durée de vie)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) associée qui détermine le délai d’expiration du cache pour les réponses DNS de ces enregistrements. Par conséquent, vous devrez peut-être attendre au moins aussi longtemps que vos TTL. Vous pouvez utiliser la commande `dig target.example.com` ou [la boîte à outils G Suite](https://toolbox.googleapps.com/apps/dig/#CNAME) pour rechercher vos TTL spécifiques.

### Comment utiliser un lien d’exclusion avec CNAME

Si vous utilisez CNAME, le lien d’exclusion doit contenir le paramètre &quot;client=`clientcode`, par exemple :
`https://my.cname.domain/optout?client=clientcode`.

Remplacez `clientcode` par votre code client, puis ajoutez le texte ou l’image à lier à l’[URL d’exclusion](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Limites connues

* Le mode AQ n’est pas attractif lorsque vous utilisez CNAME et at.js 1.x, car il est basé sur un cookie tiers. La solution consiste à ajouter les paramètres d’aperçu à chaque URL à laquelle vous accédez. Le mode AQ est attractif lorsque vous disposez de CNAME et at.js 2.x.
* Actuellement, le paramètre `overrideMboxEdgeServer` ne fonctionne pas correctement avec CNAME lors de l’utilisation de versions d’at.js antérieures à at.js 1.8.2 et at.js 2.3.1. Si vous utilisez une ancienne version d’at.js, ce paramètre doit être défini sur `false` afin d’éviter les demandes en échec. Vous pouvez également envisager de [mettre à jour at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) vers une version plus récente et prise en charge.
* Lors de l’utilisation de CNAME, il est plus probable que la taille de l’en-tête de cookie pour les appels [!DNL Target] augmente. [!DNL Adobe] recommande de conserver la taille du cookie en dessous de 8 Ko.
