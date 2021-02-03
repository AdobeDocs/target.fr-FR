---
keywords: service à la clientèle ; cname ; certificat programme ; nom canonique ; cookies ; certificat ; amc ; certificat géré adobe ; digicert ; validation du contrôle de domaine ; dcv
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
title: CNAME
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 2%

---


# CNAME et Adobe Target

Instructions pour travailler avec le service à la clientèle d’Adobe pour mettre en oeuvre la prise en charge de CNAME (Canonical Name) dans [!DNL Adobe Target]. Pour mieux gérer les problèmes de blocage des publicités ou les stratégies de cookies liées à ITP, un CNAME est utilisé de sorte que les appels sont effectués vers un domaine détenu par le client plutôt que vers un domaine détenu par l’Adobe.

## Demande de prise en charge CNAME

Effectuez les étapes suivantes pour demander la prise en charge de CNAME dans [!DNL Target] :

1. Déterminez la liste des noms d’hôte dont vous avez besoin pour votre certificat SSL (voir FAQ).

1. Pour chaque nom d’hôte, créez un enregistrement CNAME dans votre DNS en pointant vers votre nom d’hôte [!DNL Target] habituel `clientcode.tt.omtrdc.net`.

   Par exemple, si votre code client est &quot;client&quot; et que votre nom d’hôte proposé est `target.example.com`, votre enregistrement CNAME DNS doit ressembler à ceci :

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >L&#39;autorité de certification de l&#39;Adobe, DigiCert, ne peut pas émettre de certificat tant que cette étape n&#39;est pas terminée. Par conséquent, l’Adobe ne peut pas répondre à votre demande d’implémentation CNAME tant que cette étape n’est pas terminée.

1. [Remplissez ce ](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) formulaire et incluez-le lorsque vous  [ouvrez un ticket d’Adobe pour le service à la clientèle demandant la prise en charge](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME :

   * Adobe [!DNL Target] code client :
   * Noms d’hôte de certificat SSL (exemple : `target.example.com target.example.org`) :
   * Acheteur de certificat SSL (Adobe fortement recommandé, voir FAQ) : Adobe/client
   * Si le client achète le certificat (également appelé BYOC), veuillez remplir les champs suivants :
      * Organisation des certificats (exemple : Exemple de Société Inc) :
      * Unité organisationnelle du certificat (facultative, exemple : Marketing) :
      * Pays du certificat (exemple : US) :
      * État/région du certificat (exemple : Californie) :
      * Ville de certificat (exemple : San Jose) :

1. Si l’Adobe achète le certificat, l’Adobe collabore avec DigiCert pour acheter et déployer le certificat sur les serveurs de production de l’Adobe.

   Si le client achète le certificat (BYOC), le service à la clientèle d’Adobe vous envoie la demande de signature de certificat (CSR), que vous devrez utiliser lors de l’achat du certificat par l’intermédiaire de votre autorité de certification de choix. Une fois le certificat émis, vous devez renvoyer une copie du certificat et de tous les certificats intermédiaires à l’assistance clientèle d’Adobe pour le déploiement.

   Le service à la clientèle d’Adobe vous avertit lorsque votre mise en oeuvre est prête.

1. Une fois que vous avez terminé les tâches précédentes et que le service à la clientèle de l’Adobe vous a informé que l’implémentation est prête, vous devez mettre à jour `serverDomain` vers le nouveau CNAME dans at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquentes sur la demande et l&#39;implémentation de la prise en charge CNAME dans [!DNL Target] :

### Puis-je fournir mon propre certificat (c&#39;est-à-dire apporter votre propre certificat ou COJAN) ?

Oui, vous pouvez fournir votre propre certificat ; cependant, il n&#39;est pas recommandé. La gestion du cycle de vie du certificat SSL est beaucoup plus facile pour l’Adobe et pour vous lorsque l’Adobe achète et contrôle le certificat. Les certificats SSL doivent être renouvelés chaque année, ce qui signifie que le service à la clientèle de l’Adobe doit vous contacter chaque année pour envoyer à l’Adobe un nouveau certificat en temps opportun. Certains clients peuvent avoir de la difficulté à produire un certificat renouvelé en temps opportun chaque année, ce qui compromet leur mise en oeuvre [!DNL Target] car les navigateurs refuseront les connexions lorsque le certificat expire.

>[!IMPORTANT]
>
>Sachez que si vous demandez une mise en oeuvre [!DNL Target] de CNAME avec certificat personnel, vous devez fournir chaque année des certificats renouvelés au service à la clientèle d’Adobe. Le fait de permettre à votre certificat CNAME d’expirer avant que l’Adobe puisse déployer un certificat renouvelé entraîne une panne de votre implémentation [!DNL Target] spécifique.

### Combien de temps avant l’expiration de mon nouveau certificat SSL ?

Les certificats délivrés avant le 1er septembre 2020 seront des certificats de deux ans. Les certificats délivrés le 1er septembre 2020 ou après cette date seront des certificats d’un an. Vous pouvez en savoir plus sur le passage à des certificats d&#39;un an [ici](https://www.digicert.com/position-on-1-year-certificates).

### Quels noms d’hôtes dois-je choisir ? Combien d’hôtes par domaine dois-je choisir ?

[!DNL Target] Les implémentations CNAME ne nécessitent qu’un seul nom d’hôte par domaine sur le certificat SSL et dans le DNS du client. C’est donc ce que nous recommandons. Certains clients peuvent avoir besoin de noms d’hôte supplémentaires par domaine pour leurs propres besoins (test dans l’évaluation, par exemple), qui est pris en charge.

La plupart des clients choisissent un nom d’hôte tel que `target.example.com`, c’est donc ce que nous recommandons, mais le choix est finalement le vôtre. Veillez à ne pas demander un nom d’hôte d’un enregistrement DNS existant, car cela provoquerait un conflit et retarderait la résolution de votre demande [!DNL Target] CNAME.

### J’ai déjà une implémentation CNAME pour [!DNL Adobe Analytics]. Pouvons-nous utiliser le même certificat ou nom d’hôte ?

Non, [!DNL Target] nécessite un nom d’hôte et un certificat distincts.

### Est-ce que ma mise en oeuvre actuelle de la Cible est affectée par ITP 2.x ?

Dans un navigateur Safari, accédez à votre site Web sur lequel vous disposez d’une bibliothèque JavaScript Cible. Si vous voyez un cookie de Cible défini dans le contexte d’un CNAME, tel que `analytics.company.com`, vous n’êtes pas affecté par ITP 2.x.

Les problèmes ITP peuvent être résolus pour la Cible avec un seul CNAME Analytics. Vous aurez besoin d’un CNAME de Cible distinct uniquement dans le cas de scénarios de blocage des publicités où la Cible est bloquée.

Pour plus d’informations sur la technologie ITP, voir [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Quel type de panne de service puis-je attendre lorsque mon implémentation CNAME est déployée ?

Il n’y a aucune interruption de service lorsque le certificat est déployé (y compris les renouvellements de certificat). Cependant, lorsque vous remplacez le nom d’hôte dans votre code d’implémentation [!DNL Target] (`serverDomain` dans at.js) par le nouveau nom d’hôte CNAME (`target.example.com`), les navigateurs Web traitent les visiteurs de retour comme de nouveaux visiteurs et leurs données de profil sont perdues car le cookie précédent est inaccessible sous l’ancien nom d’hôte (`clientcode.tt.omtrdc.net`) en raison des modèles de sécurité de navigateur. Il s’agit d’une interruption ponctuelle uniquement sur la coupure initiale du nouveau CNAME. Les renouvellements de certificats n’ont pas le même effet puisque le nom d’hôte ne change pas.

### Quel type de clé et quel algorithme de signature de certificat seront utilisés pour mon implémentation CNAME ?

Tous les certificats sont RSA SHA-256 et les clés sont RSA 2048-bit, par défaut. Actuellement, les tailles de clés supérieures à 2 048 bits ne sont pas prises en charge.

### Comment puis-je valider que ma mise en oeuvre CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande MacOs ou Linux, en utilisant bash et curl 7.49+) :

1. Commencez par coller cette fonction bash dans votre terminal :

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Collez ensuite cette commande (en remplaçant `target.example.com` par votre nom d’hôte) :

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si l’implémentation est prête, vous devriez voir la sortie comme ci-dessous. L&#39;important est que toutes les lignes affichent `CN=target.example.com`, qui correspond à notre nom d&#39;hôte souhaité. Si l’un d’eux affiche `CN=*.tt.omtrdc.net`, l’implémentation n’est pas **prête**.

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

1. Validez votre nouveau CNAME DNS avec une autre requête d’URL, qui doit également afficher `CN=target.example.com` :

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si cette commande échoue mais que la commande `validateEdgeFpsslSni` ci-dessus réussit, vous devrez peut-être attendre que vos mises à jour DNS se propagent complètement. Les enregistrements DNS sont associés à une [TTL (durée de vie)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) qui détermine le délai d&#39;expiration du cache pour les réponses DNS de ces enregistrements, de sorte que vous devrez peut-être attendre au moins aussi longtemps que vos TTL. Vous pouvez utiliser la commande `dig target.example.com` ou [la boîte à outils de la suite G](https://toolbox.googleapps.com/apps/dig/#CNAME) pour rechercher vos TTL spécifiques.

## Limites connues

* Le mode AQ n’est pas collant lorsque vous utilisez CNAME et at.js 1.x, car il est basé sur un cookie tiers. La solution consiste à ajouter les paramètres de prévisualisation à chaque URL à laquelle vous accédez. Le mode AQ reste bascule lorsque vous utilisez CNAME et at.js 2.x.
* Actuellement, le paramètre `overrideMboxEdgeServer` ne fonctionne pas correctement avec CNAME lors de l’utilisation des versions d’at.js antérieures à at.js 1.8.2 et at.js 2.3.1. Si vous utilisez une ancienne version d’at.js, il doit être défini sur `false` pour éviter d’échouer aux requêtes. Vous pouvez également envisager de [mettre à jour at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) vers une version plus récente et prise en charge.
* Lors de l’utilisation de CNAME, il est plus probable que la taille de l’en-tête du cookie pour les appels de Cible augmente. Nous vous recommandons de conserver la taille du cookie sous 8 Ko.
