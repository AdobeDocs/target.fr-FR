---
keywords: service client ; cname ; programme de certificats ; nom canonique ; cookies ; certificat ; amc ; certificat géré adobe ; digicert ; validation du contrôle de domaine ; dcv
description: Travailler avec l’Adobe Client Care pour mettre en oeuvre la prise en charge de CNAME (Canonical Name) dans l’Adobe [!DNL Target] pour gérer les problèmes de blocage des annonces.
title: Comment utiliser CNAME dans Target ?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: e51c7805939e8bf32d7f358036c9070931580187
workflow-type: tm+mt
source-wordcount: '1165'
ht-degree: 1%

---

# CNAME et cible

Instructions pour l’utilisation [!DNL Adobe] Le service à la clientèle doit mettre en oeuvre la prise en charge de CNAME (Nom Canonique) dans [!DNL Adobe Target]. Utilisez CNAME pour gérer les problèmes de blocage et de blocage ou les stratégies de cookies liées à ITP (Intelligent Tracking Prevention). Avec CNAME, les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par [!DNL Adobe].

## Demander la prise en charge de CNAME dans Target

1. Déterminez la liste des noms d’hôte dont vous avez besoin pour votre certificat SSL (voir la FAQ ci-dessous).

1. Pour chaque nom d’hôte, créez un enregistrement CNAME dans votre DNS pointant vers votre nom d’hôte standard [!DNL Target] nom d&#39;hôte `clientcode.tt.omtrdc.net`.

   Par exemple, si votre code client est &quot;client client&quot; et que votre nom d’hôte proposé est `target.example.com`, votre enregistrement CNAME DNS ressemble à :

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >L’autorité de certification de l’Adobe, DigiCert, ne peut pas émettre de certificat tant que cette étape n’est pas terminée. Par conséquent, [!DNL Adobe] ne peut pas répondre à votre demande d&#39;implémentation CNAME tant que cette étape n&#39;est pas terminée.

1. [Remplissage de ce formulaire](/help/assets/FPC_Request_Form.xlsx) et l’inclure lorsque vous [ouvrir un ticket de service à la clientèle Adobe demandant la prise en charge de CNAME](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target] code client :
   * Noms d&#39;hôte de certificat SSL (exemple : `target.example.com target.example.org`) :
   * Acheteur de certificat SSL (Adobe fortement recommandé, voir FAQ) : Adobe/client
   * Si le client achète le certificat, également connu sous le nom de &quot;Bring Your Own Certificate&quot; (BYOC), renseignez les informations supplémentaires suivantes :
      * Organisation de certificats (exemple : Exemple de société Inc) :
      * Unité organisationnelle du certificat (facultatif, exemple : Marketing) :
      * Pays du certificat (exemple : États-Unis) :
      * État/région du certificat (exemple : Californie) :
      * Ville du certificat (exemple : San Jose) :

1. Si [!DNL Adobe] achète le certificat, [!DNL Adobe] travaille avec DigiCert pour acheter et déployer votre certificat sur les serveurs de production d’Adobe.

   Si le client achète le certificat (BYOC), [!DNL Adobe] Le service clientèle vous envoie la demande de signature de certificat (CSR). Utilisez le fichier CSR lors de l’achat du certificat par l’intermédiaire de votre autorité de certification de choix. Une fois le certificat délivré, envoyer une copie du certificat et de tout certificat intermédiaire à [!DNL Adobe] Assistance clientèle pour le déploiement.

   [!DNL Adobe] Le service clientèle vous avertit lorsque votre mise en oeuvre est prête.

1. Mettez à jour la `serverDomain` ([documentation](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#serverDomain)) au nouveau nom d’hôte CNAME et définissez `overrideMboxEdgeServer` à `false` ([documentation](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#overridemboxedgeserver)) dans votre configuration at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquemment posées sur la demande et la mise en oeuvre de la prise en charge CNAME dans [!DNL Target]:

### Puis-je fournir mon propre certificat (Apporter votre propre certificat ou COVAN) ?

Vous pouvez fournir votre propre certificat. Cependant, [!DNL Adobe] ne recommande pas cette pratique. La gestion du cycle de vie du certificat SSL est plus facile pour les deux [!DNL Adobe] et si [!DNL Adobe] achète et contrôle le certificat. Les certificats SSL doivent être renouvelés chaque année. Par conséquent, [!DNL Adobe] Le service à la clientèle doit communiquer avec vous chaque année pour obtenir un nouveau certificat en temps opportun. Certains clients peuvent avoir de la difficulté à produire un certificat renouvelé en temps opportun. Votre [!DNL Target] est mise en péril lorsque le certificat expire parce que les navigateurs refusent les connexions.

>[!IMPORTANT]
>
>Si vous demandez un [!DNL Target] implémentation CNAME de votre propre certificat, vous êtes responsable de fournir des certificats renouvelés à [!DNL Adobe] Assistance à la clientèle chaque année. Autoriser l’expiration de votre certificat CNAME avant [!DNL Adobe] peut déployer un certificat renouvelé, ce qui entraîne une interruption pour votre [!DNL Target] mise en oeuvre.

### Combien de temps avant l’expiration de mon nouveau certificat SSL ?

Tous les certificats achetés par Adobe sont valables un an. Voir [Article de DigiCert sur les certificats d&#39;un an](https://www.digicert.com/blog/position-on-1-year-certificates) pour plus d’informations.

### Quels noms d’hôtes dois-je choisir ? Combien de noms d’hôte par domaine dois-je choisir ?

[!DNL Target] Les implémentations CNAME ne nécessitent qu’un seul nom d’hôte par domaine sur le certificat SSL et dans le DNS du client. Adobe recommande un nom d’hôte par domaine. Certains clients ont besoin d’un plus grand nombre de noms d’hôte par domaine pour leurs propres besoins (test dans la phase intermédiaire, par exemple), qui est pris en charge.

La plupart des clients choisissent un nom d’hôte comme `target.example.com`. L&#39;Adobe recommande de suivre cette pratique, mais le choix est finalement le vôtre. Ne demandez pas le nom d&#39;hôte d&#39;un enregistrement DNS existant. Cela entraîne un conflit et retarde la résolution de votre [!DNL Target] Demande CNAME.

### J&#39;ai déjà mis en oeuvre CNAME pour [!DNL Adobe Analytics], puis-je utiliser le même certificat ou le même nom d’hôte ?

Non, [!DNL Target] nécessite un nom d’hôte et un certificat distincts.

### Est-ce que ma mise en oeuvre actuelle de [!DNL Target] impacté par ITP 2.x ?

La version 2.3 d&#39;Apple Intelligent Tracking Prevention (ITP) a introduit sa fonction CNAME Cloaking Mitigation, qui permet de détecter les implémentations Adobe Target CNAME et réduit l&#39;expiration du cookie à sept jours. Actuellement [!DNL Target] n&#39;a pas de solution pour l&#39;atténuation du voilage CNAME de ITP. Pour plus d’informations sur ITP, voir [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).


### Quels types de perturbations de service puis-je attendre lors du déploiement de l&#39;implémentation CNAME ?

Il n’y a aucune interruption de service lorsque le certificat est déployé (y compris les renouvellements de certificat).

Cependant, après avoir modifié le nom d’hôte dans votre [!DNL Target] code de mise en oeuvre (`serverDomain` dans at.js) au nouveau nom d’hôte CNAME (`target.example.com`), les navigateurs Web traitent les visiteurs de retour comme de nouveaux visiteurs. Les données de profil des visiteurs de retour sont perdues car le cookie précédent est inaccessible sous l’ancien nom d’hôte (`clientcode.tt.omtrdc.net`). Le cookie précédent est inaccessible en raison des modèles de sécurité du navigateur. Cette interruption se produit uniquement lors de la coupure initiale du nouveau CNAME. Les renouvellements de certificats n’ont pas le même effet, car le nom d’hôte ne change pas.

### Quel type de clé et quel algorithme de signature de certificat sont utilisés pour ma mise en oeuvre CNAME ?

Tous les certificats sont RSA SHA-256 et les clés sont RSA 2048-bit, par défaut. Les tailles de clés supérieures à 2 048 bits ne sont pas actuellement prises en charge.

### Comment puis-je valider que ma mise en oeuvre CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande macOS ou Linux, en utilisant bash et curl >=7.49) :

1. Copiez et collez cette fonction bash dans votre terminal ou collez-la dans votre fichier de script de démarrage bash (généralement `~/.bash_profile` ou `~/.bashrc`) afin que la fonction soit disponible pour toutes les sessions de terminal :

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. Coller cette commande (remplacement `target.example.com` avec votre nom d&#39;hôte) :

   ```
   adobeTargetCnameValidation target.example.com
   ```

   Si la mise en oeuvre est prête, vous voyez la sortie comme ci-dessous. La partie importante est que toutes les lignes d’état de validation s’affichent. `✅` plutôt que `🚫`. Chacune [!DNL Target] le partage CNAME de bord doit s&#39;afficher `CN=target.example.com`, qui correspond au nom d&#39;hôte principal sur le certificat demandé (les noms d&#39;hôtes SAN supplémentaires sur le certificat ne sont pas imprimés dans cette sortie).

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >Si cette commande de validation échoue sur la validation DNS mais que vous avez déjà effectué les modifications DNS nécessaires, vous devrez peut-être attendre que vos mises à jour DNS soient entièrement propagées. Les enregistrements DNS sont associés à [TTL (durée de vie)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) qui détermine le délai d&#39;expiration du cache pour les réponses DNS de ces enregistrements. Par conséquent, vous devrez peut-être attendre au moins aussi longtemps que vos TTL. Vous pouvez utiliser la `dig target.example.com` ou [Boîte à outils de la suite G](https://toolbox.googleapps.com/apps/dig/#CNAME) pour rechercher vos TTL spécifiques. Pour vérifier la propagation DNS dans le monde entier, voir [whatsmydns.net](https://whatsmydns.net/#CNAME).

### Comment utiliser un lien d’exclusion avec CNAME ?

Si vous utilisez CNAME, le lien d’exclusion doit contenir la mention &quot;client=&quot;`clientcode` par exemple :
`https://my.cname.domain/optout?client=clientcode`.

Remplacer `clientcode` avec votre code client, puis ajoutez le texte ou l’image à lier au fichier [URL de retrait](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Limites connues

* Le mode QA n&#39;est pas collant lorsque vous avez CNAME et at.js 1.x, car il est basé sur un cookie tiers. La solution consiste à ajouter les paramètres d’aperçu à chaque URL à laquelle vous accédez. Le mode QA est autocollant lorsque vous utilisez CNAME et at.js 2.x.
* Lors de l’utilisation de CNAME, il devient plus probable que la taille de l’en-tête de cookie pour [!DNL Target] les appels augmentent. [!DNL Adobe] recommande de conserver la taille du cookie en dessous de 8 Ko.
