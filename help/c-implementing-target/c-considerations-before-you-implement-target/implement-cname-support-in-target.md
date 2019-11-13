---
keywords: service client;cname;certificate program;canononname;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Informations sur l’utilisation du service à la clientèle Adobe pour l’implémentation de la prise en charge du CNAME (nom canonique) dans Adobe Target.
title: CNAME et Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 872e2329e7954453b5c8bd4f4885b94f1b02fd1f

---


# CNAME et Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Pour gérer au mieux les problèmes de blocage des publicités ou les stratégies de cookies liées au protocole ITP, un CNAME est utilisé de sorte que les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par Adobe.

## Demande de prise en charge CNAME

Perform the following steps to request CNAME support in [!DNL Target]:

1. L’autorité de certification d’Adobe (DigiCert) doit vérifier qu’Adobe est autorisé à générer des certificats sous votre domaine.

   DigiCert appelle ce processus [Domain Control Validation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) (DCV) et Adobe ne sera pas autorisé à générer un certificat sous votre domaine tant que ce processus n’est pas terminé.

   Le DCV utilise quelques méthodes et vous pouvez effectuer quelques opérations avant d’ouvrir un ticket du service à la clientèle Adobe (étape 3) pour accélérer le processus du DCV :

   * DigiCert commence par tester la méthode de courrier électronique, dans laquelle il envoie des courriers électroniques aux adresses figurant dans les informations WHOIS du domaine, ainsi qu’aux adresses électroniques prédéterminées (admin, administrateur, webmaster, hostmaster et postmaster `@[domain_name]`). See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      Pour accélérer le processus de courrier électronique DCV, DigiCert fournit la recommandation suivante :

      "Vérifiez que votre bureau d’enregistrement/fournisseur WHOIS n’a pas masqué ou supprimé les adresses [de courriel]pertinentes. Si tel est le cas, découvrez s’ils vous offrent un moyen (par exemple, une adresse électronique anonyme, un formulaire Web) de permettre aux autorités [de] certification d’accéder aux données WHOIS de votre domaine."

   * Si la méthode de courrier électronique DCV n’est pas une option pour vous, la méthode suivante est la méthode TXT DNS, dans laquelle vous ajoutez un enregistrement TXT DNS à votre domaine avec une valeur de hachage. Cet enregistrement TXT indique à DigiCert qu’Adobe est autorisé à générer le certificat. Si vous devez utiliser cette méthode, faites savoir au service à la clientèle Adobe lorsque vous ouvrez un ticket (étape 3). Cela permettra d’accélérer le processus du DCV.

1. Créez un enregistrement CNAME sur le DNS de votre domaine pointant vers votre nom d’hôte normal `clientcode.tt.omtrdc.net`. Par exemple, si votre code client est client et que votre nom d’hôte proposé est `target.example.com`, votre enregistrement CNAME DNS doit ressembler à ceci :

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Ouvrez un ticket du service à la clientèle [Adobe demandant la prise en charge](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) CNAME pour vos [!DNL Target] appels.

   Adobe collaborera avec DigiCert pour acheter et déployer votre certificat sur les serveurs de production d’Adobe. DigiCert lancera le processus DCV et le service à la clientèle Adobe vous en informera lorsque votre implémentation sera prête.

1. Une fois les tâches précédentes terminées et le service à la clientèle Adobe vous a informé que l’implémentation était prête, vous devez mettre à jour le fichier `serverDomain` vers le nouveau CNAME dans at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquemment posées sur la demande et la mise en oeuvre du soutien du CNAM dans [!DNL Target]:

### Puis-je fournir mon propre certificat ? Si oui, quel est le processus ?

Oui, vous pouvez fournir votre propre certificat, pour ce faire :

1. Ignorez l’étape 1 ci-dessus, mais suivez les étapes 2 et 3. Lorsque vous ouvrez un ticket du service à la clientèle Adobe (étape 3), faites-leur savoir que vous fournissez votre propre certificat.

   Adobe génère et vous envoie une demande de signature de certificat (CSR).

1. Utilisez le fichier CSR pour acheter le certificat par l’intermédiaire de l’autorité de certification (CA) que vous avez choisie.

1. Envoyez le nouveau certificat public à Adobe. Les représentants d’Adobe déploieront le certificat public sur ses serveurs de production.

1. Exécutez l’étape 4 après que le service à la clientèle Adobe vous a informé que l’implémentation est prête.

### J’ai déjà une implémentation CNAME pour [!DNL Adobe Analytics], pouvons-nous utiliser le même certificat ou nom d’hôte ?

Non, [!DNL Target] requiert un nom d’hôte et un certificat distincts.

### Comment puis-je valider que ma mise en oeuvre CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande MacOs ou Linux, à l’aide de bash et de curl 7.49+) :

1. Commencez par coller cette fonction bash dans votre terminal :

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Collez ensuite cette commande (en remplaçant `target.example.com` par votre nom d’hôte) :

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si l’implémentation est prête, vous devriez voir la sortie comme ci-dessous. L'important est que toutes les lignes s'affichent `CN=target.example.com`, qui correspond à notre nom d'hôte souhaité. Si l’un d’eux s’affiche `CN=*.tt.omtrdc.net`, l’implémentation **n’est pas** prête.

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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Validez votre nouveau CNAME DNS avec une autre requête curl, qui doit également afficher `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si cette commande échoue mais que la `validateEdgeFpsslSni` commande ci-dessus réussit, vous devrez peut-être attendre que vos mises à jour DNS se propagent complètement.
