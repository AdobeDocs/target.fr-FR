---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
title: CNAME et Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 8139b9373dab3b699a93036752d982793fbd1158
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 2%

---


# CNAME et Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Pour mieux gérer les problèmes de blocage des publicités ou les stratégies de cookies liées à ITP, un CNAME est utilisé de sorte que les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par Adobe.

## Demande de prise en charge CNAME

Perform the following steps to request CNAME support in [!DNL Target]:

1. L’autorité de certification d’Adobe (DigiCert) doit vérifier qu’Adobe est autorisé à générer des certificats sous votre domaine.

   DigiCert appelle ce processus [Domain Control Validation (DCV)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)et Adobe ne sera pas autorisé à générer un certificat sous votre domaine tant que ce processus n’est pas terminé pour au moins l’une des méthodes DCV suivantes :

   * La méthode DCV la plus rapide est la méthode CNAME DNS, dans laquelle vous ajoutez un enregistrement CNAME DNS (contenant un jeton) à votre domaine qui pointe vers le nom d’hôte DCV de DigiCert (`dcv.digicert.com`). Cet enregistrement CNAME indique à DigiCert qu’Adobe est autorisé à générer le certificat. Le service à la clientèle Adobe vous enverra les instructions avec les enregistrements DNS nécessaires. Exemple :

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >* Ces jetons DCV arrivent à expiration après 30 jours. Le service à la clientèle d’Adobe vous contactera alors pour les mettre à jour. Pour résoudre le plus rapidement possible votre demande CNAME, soyez prêt à effectuer ces modifications DNS sur tous les domaines demandés avant de soumettre votre demande.
         >
         >
      * Si votre domaine comporte des enregistrements [CAA](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)DNS, vous devez ajouter `digicert.com` s’il n’est pas déjà ajouté. Cet enregistrement DNS indique les autorités de certificats autorisées à émettre des certificats pour le domaine. L&#39;enregistrement DNS résultant ressemble à ceci : `example.com. IN CAA 0 issue "digicert.com"`. Vous pouvez utiliser [la boîte à outils](https://toolbox.googleapps.com/apps/dig/#CAA) de la suite G pour déterminer si votre domaine racine contient un enregistrement CAA existant. Vous pouvez en savoir plus sur la façon dont DigiCert gère les enregistrements CAA [ici](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check).


   * DigiCert essaie également la méthode de courrier électronique, dans laquelle il envoie des messages électroniques aux adresses figurant dans les informations WHOIS du domaine et aux adresses électroniques prédéterminées (admin, administrateur, webmaster, hostmaster et postmaster `@[domain_name]`). See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      Pour accélérer le processus de courrier électronique DCV, DigiCert fournit la recommandation suivante :

      &quot;Vérifiez que votre serveur d’inscriptions/fournisseur WHOIS n’a pas masqué ou supprimé les adresses électroniques appropriées. Si tel est le cas, découvrez s’ils vous offrent un moyen (par exemple, une adresse électronique anonyme, un formulaire Web) d’autoriser les autorités de certification à accéder aux données WHOIS de votre domaine.&quot;

1. Créez un enregistrement CNAME sur le DNS de votre domaine pointant vers votre nom d’hôte normal `clientcode.tt.omtrdc.net`. Par exemple, si votre code client est client et que votre nom d’hôte proposé est `target.example.com`personnalisé, votre enregistrement CNAME DNS doit ressembler à ceci :

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Ouvrez un ticket du service à la clientèle [Adobe demandant la prise en charge](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) CNAME pour vos [!DNL Target] appels.

   Adobe collaborera avec DigiCert pour acheter et déployer votre certificat sur les serveurs de production d’Adobe. DigiCert lancera le processus DCV et le service à la clientèle d’Adobe vous en informera lorsque votre mise en oeuvre sera prête.

1. Une fois les tâches précédentes terminées et que le service à la clientèle d’Adobe vous a informé que l’implémentation était prête, vous devez mettre à jour le fichier `serverDomain` vers le nouveau CNAME dans at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquentes sur la demande et l’implémentation de la prise en charge CNAME dans [!DNL Target]:

### Puis-je fournir mon propre certificat (c&#39;est-à-dire apporter votre propre certificat ou COJAN) ? Si oui, quel est le processus ?

Oui, vous pouvez fournir votre propre certificat ; cependant, il n&#39;est pas recommandé. La gestion du cycle de vie des certificats SSL est beaucoup plus facile pour Adobe et vous lorsque vous achetez et contrôlez le certificat. Les certificats SSL doivent être renouvelés chaque année, ce qui signifie que le service à la clientèle d’Adobe doit vous contacter chaque année pour envoyer un nouveau certificat à Adobe en temps opportun. Certains clients peuvent avoir de la difficulté à produire un certificat renouvelé en temps opportun chaque année, ce qui compromet leur [!DNL Target] mise en oeuvre car les navigateurs refuseront les connexions à l’expiration du certificat.

>[!IMPORTANT]
>
>Sachez que si vous demandez une mise en oeuvre CNAME [!DNL Target] avec certificat personnel, vous êtes tenu de fournir chaque année des certificats renouvelés au service à la clientèle d’Adobe. L’expiration de votre certificat CNAME avant qu’Adobe puisse déployer un certificat renouvelé entraîne une panne de votre [!DNL Target] implémentation spécifique.

1. Ignorez l’étape 1 ci-dessus, mais complétez les étapes 2 et 3. Lorsque vous ouvrez un ticket d’assistance clientèle Adobe (étape 3), informez-leur que vous fournissez votre propre certificat.

   Adobe génère et vous envoie une demande de signature de certificat (CSR).

1. Utilisez la demande de signature de certificat pour acheter le certificat par l’intermédiaire de l’autorité de certification (AC) que vous avez choisie.

1. Envoyez le nouveau certificat public à Adobe. Les représentants d’Adobe déploieront le certificat public sur ses serveurs de production.

1. Effectuez l’étape 4 une fois que le service à la clientèle Adobe vous a informé que l’implémentation est prête.

### Combien de temps avant l’expiration de mon nouveau certificat SSL ?

Les certificats délivrés avant le 1er septembre 2020 seront des certificats de deux ans. Les certificats délivrés le 1er septembre 2020 ou après cette date seront des certificats d’un an. Vous pouvez en savoir plus sur le passage à des certificats d&#39;un an [ici](https://www.digicert.com/position-on-1-year-certificates).

### Quels noms d’hôtes dois-je choisir ? Combien d’hôtes par domaine dois-je choisir ?

[!DNL Target] Les implémentations CNAME ne nécessitent qu’un seul nom d’hôte par domaine sur le certificat SSL et dans le DNS du client. C’est donc ce que nous recommandons. Certains clients peuvent avoir besoin de noms d’hôte supplémentaires par domaine pour leurs propres besoins (test dans l’évaluation, par exemple), qui est pris en charge.

La plupart des clients choisissent un nom d’hôte comme `target.example.com`, c’est ce que nous recommandons, mais le choix est finalement le vôtre. Veillez à ne pas demander un nom d’hôte d’un enregistrement DNS existant, car cela provoquerait un conflit et retarderait la résolution de votre demande [!DNL Target] CNAME.

### J’ai déjà une implémentation CNAME pour [!DNL Adobe Analytics], pouvons-nous utiliser le même certificat ou nom d’hôte ?

Non, [!DNL Target] requiert un nom d’hôte et un certificat distincts.

### Est-ce que ma mise en oeuvre actuelle de la Cible est affectée par ITP 2.x ?

Dans un navigateur Safari, accédez à votre site Web sur lequel vous disposez d’une bibliothèque JavaScript Cible. If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Les problèmes ITP peuvent être résolus pour la Cible avec un seul CNAME Analytics. Vous aurez besoin d’un CNAME de Cible distinct uniquement dans le cas de scénarios de blocage des publicités où la Cible est bloquée.

Pour plus d’informations sur ITP, voir [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Adobe/DigiCert peut-il envoyer les courriers électroniques du DCV à une autre adresse électronique `<someone>@example.com`?

Non, DigiCert (ou toute autre autorité de certification) n&#39;autorisera pas uniquement quiconque ayant une adresse électronique sous un domaine à autoriser un certificat SSL sous ce même domaine, à moins que cette adresse électronique ne soit également incluse dans les informations WHOIS du domaine ou dans la liste prédéfinie des adresses (voir ci-dessus). Ainsi, seules les personnes autorisées peuvent approuver le DCV pour un domaine particulier. Si cela n’est pas possible pour vous, nous vous recommandons d’utiliser la méthode DCV CNAME DNS (voir ci-dessus).

### Comment puis-je valider que ma mise en oeuvre CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande MacOs ou Linux, en utilisant bash et curl 7.49+) :

1. Commencez par coller cette fonction bash dans votre terminal :

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Collez ensuite cette commande (en remplaçant `target.example.com` par votre nom d’hôte) :

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si l’implémentation est prête, vous devriez voir la sortie comme ci-dessous. L&#39;important est que toutes les lignes s&#39;affichent `CN=target.example.com`, ce qui correspond à notre nom d&#39;hôte souhaité. Si l’une d’elles s’affiche `CN=*.tt.omtrdc.net`, l’implémentation **n’est pas** prête.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Validez votre nouveau CNAME DNS avec une autre requête d’URL, qui doit également afficher `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si cette commande échoue mais que la `validateEdgeFpsslSni` commande ci-dessus réussit, vous devrez peut-être attendre que vos mises à jour DNS se propagent complètement. Les enregistrements DNS sont associés à une [TTL (durée de vie)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) qui détermine le délai d’expiration du cache pour les réponses DNS de ces enregistrements, de sorte que vous devrez peut-être attendre au moins aussi longtemps que vos TTL. Vous pouvez utiliser la `dig target.example.com` commande ou [](https://toolbox.googleapps.com/apps/dig/#CNAME) la boîte à outils de la suite G pour rechercher vos TTL spécifiques.

## Limites connues

* Le mode AQ n’est pas collant lorsque vous utilisez CNAME et at.js 1.x, car il est basé sur un cookie tiers. La solution consiste à ajouter les paramètres de prévisualisation à chaque URL à laquelle vous accédez. Le mode AQ reste bascule lorsque vous utilisez CNAME et at.js 2.x.
* Actuellement, le `overrideMboxEdgeServer` paramètre ne fonctionne pas correctement avec CNAME. Cette valeur doit être définie `false` de manière à éviter les demandes qui échouent.
