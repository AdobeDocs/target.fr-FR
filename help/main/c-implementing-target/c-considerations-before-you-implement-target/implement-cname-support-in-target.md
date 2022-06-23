---
keywords: service à la clientèle;cname;programme de certificat;nom canonique;cookies;certificat;amc;certificat géré adobe;digicert;validation du contrôle de domaine;dcv
description: Utilisation de [!DNL Adobe] Le service à la clientèle doit mettre en oeuvre la prise en charge de CNAME (nom canonique) dans [!DNL Adobe Target] pour gérer les problèmes de blocage des publicités.
title: Comment utiliser CNAME dans Target ?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 1%

---

# CNAME et [!DNL Target]

Instructions pour l’utilisation de [!DNL Adobe] Le service à la clientèle doit mettre en oeuvre la prise en charge de CNAME (nom canonique) dans [!DNL Adobe Target]. Utilisez CNAME pour gérer les problèmes de blocage des publicités ou les stratégies de cookies liées à ITP (Intelligent Tracking Prevention). Avec CNAME, les appels sont effectués vers un domaine détenu par le client plutôt qu’un domaine détenu par [!DNL Adobe].

## Demande de la prise en charge CNAME dans [!DNL Target]

1. Déterminez la liste des noms d’hôtes dont vous avez besoin pour votre certificat SSL (voir la FAQ ci-dessous).

1. Pour chaque nom d’hôte, créez un enregistrement CNAME dans votre DNS en pointant vers votre [!DNL Target] hostname `clientcode.tt.omtrdc.net`.

   Par exemple, si votre code client est &quot;client&quot; et que votre nom d’hôte proposé est `target.example.com`, votre enregistrement CNAME DNS ressemble à ceci :

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]L’autorité de certification de Google, DigiCert, ne peut pas émettre de certificat tant que cette étape n’est pas terminée. Par conséquent, [!DNL Adobe] ne peut pas répondre à votre demande d’implémentation CNAME tant que cette étape n’est pas terminée.

1. [Remplissez ce formulaire.](/help/main/assets/FPC_Request_Form.xlsx) et l’inclure lorsque vous [ouvrir une [!DNL Adobe] Demande d’assistance clientèle concernant la prise en charge CNAME](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] client code:
   * Noms d’hôte de certificat SSL (exemple : `target.example.com target.example.org`) :
   * Acheteur de certificat SSL ([!DNL Adobe] est vivement recommandé, voir FAQ) : Adobe/client
   * Si le client achète le certificat, également appelé &quot;Apportez votre propre certificat&quot; (BYOC), renseignez les détails supplémentaires suivants :
      * Organisation des certificats (exemple : Exemple Entreprise Inc) :
      * Entité organisationnelle du certificat (facultatif, exemple : Marketing) :
      * Pays du certificat (exemple : US) :
      * État/région du certificat (exemple : Californie) :
      * Ville du certificat (exemple : San Jose) :

1. If [!DNL Adobe] achète le certificat, [!DNL Adobe] fonctionne avec DigiCert pour acheter et déployer votre certificat sur [!DNL Adobe]les serveurs de production de .

   Si le client achète le certificat (BYOC), [!DNL Adobe] Le service à la clientèle vous envoie la demande de signature de certificat (CSR). Utilisez la demande de signature de certificat lors de l’achat du certificat par l’intermédiaire de votre autorité de certification de votre choix. Une fois le certificat émis, envoyez une copie du certificat et de tous les certificats intermédiaires à [!DNL Adobe] Assistance clientèle pour le déploiement.

   [!DNL Adobe] Le service à la clientèle vous avertit lorsque votre mise en oeuvre est prête.

1. Mettez à jour le `serverDomain` ([documentation](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)) au nouveau nom d’hôte CNAME et défini. `overrideMboxEdgeServer` to `false` ([documentation](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)) dans votre configuration at.js.

## Questions fréquentes 

Les informations suivantes répondent aux questions fréquentes sur la demande et l’implémentation de la prise en charge CNAME dans [!DNL Target]:

### Puis-je fournir mon propre certificat (Bring Your own Certificate ou BYOC) ?

Vous pouvez fournir votre propre certificat. Cependant, [!DNL Adobe] ne recommande pas cette pratique. La gestion du cycle de vie du certificat SSL est plus facile pour les deux [!DNL Adobe] et vous si [!DNL Adobe] achète et contrôle le certificat. Les certificats SSL doivent être renouvelés chaque année. Par conséquent, [!DNL Adobe] Le service à la clientèle doit vous contacter chaque année pour obtenir un nouveau certificat en temps voulu. Certains clients peuvent avoir des difficultés à produire un certificat renouvelé dans les délais impartis. Votre [!DNL Target] l’implémentation est mise en danger lorsque le certificat expire, car les navigateurs refusent les connexions.

>[!IMPORTANT]
>
>Si vous demandez une [!DNL Target] implémentation CNAME avec votre propre certificat, vous êtes responsable de fournir des certificats renouvelés à [!DNL Adobe] Assistance clientèle chaque année. Autorisation de l’expiration de votre certificat CNAME avant [!DNL Adobe] peut déployer un certificat renouvelé, ce qui entraîne une interruption de votre [!DNL Target] implémentation.

### Combien de temps avant l’expiration de mon nouveau certificat SSL ?

Tous [!DNL Adobe]Les certificats achetés sont valides pendant un an. Voir [Article de DigiCert sur les certificats d&#39;un an](https://www.digicert.com/blog/position-on-1-year-certificates) pour plus d’informations.

### Quels noms d’hôtes dois-je choisir ? Combien de noms d’hôtes par domaine dois-je choisir ?

[!DNL Target] Les implémentations CNAME ne nécessitent qu’un seul nom d’hôte par domaine sur le certificat SSL et dans le DNS du client. [!DNL Adobe] recommande un nom d’hôte par domaine. Certains clients ont besoin de davantage de noms d’hôtes par domaine à leurs propres fins (test dans l’évaluation, par exemple), qui est pris en charge.

La plupart des clients choisissent un nom d’hôte comme `target.example.com`. [!DNL Adobe] recommande de suivre cette pratique, mais le choix est finalement le vôtre. Ne demandez pas de nom d’hôte d’un enregistrement DNS existant. Cela entraîne un conflit et retarde la résolution de votre problème. [!DNL Target] Requête CNAME.

### Je dispose déjà d’une implémentation CNAME pour [!DNL Adobe Analytics], puis-je utiliser le même certificat ou nom d’hôte ?

Non, [!DNL Target] nécessite un nom d’hôte et un certificat distincts.

### Mon implémentation actuelle de [!DNL Target] impacté par ITP 2.x ?

ITP (Intelligent Tracking Prevention) version 2.3 d’Apple a introduit sa fonctionnalité de réduction du cloaking CNAME, qui est capable de détecter [!DNL Adobe Target] Les mises en oeuvre CNAME et réduisent l’expiration du cookie à sept jours. Actuellement [!DNL Target] n’a aucune solution pour la limitation CNAME de cloaking Mitigation ITP. Pour plus d’informations sur ITP, voir [ITP (Intelligent Tracking Prevention) 2.x d’Apple](https://developer.adobe.com/target/before-implement/privacy/apple-itp-2x/).

### À quel type de interruption de service puis-je m’attendre lorsque mon implémentation CNAME est déployée ?

Il n’y a aucune interruption de service lorsque le certificat est déployé (y compris les renouvellements de certificat).

Cependant, après avoir modifié le nom d’hôte dans votre [!DNL Target] code d’implémentation (`serverDomain` dans at.js) au nouveau nom d’hôte CNAME (`target.example.com`), les navigateurs Web traitent les visiteurs récurrents comme de nouveaux visiteurs. Les données de profil des visiteurs récurrents sont perdues car le cookie précédent est inaccessible sous l’ancien nom d’hôte (`clientcode.tt.omtrdc.net`). Le cookie précédent est inaccessible en raison des modèles de sécurité du navigateur. Cette interruption se produit uniquement lors de la coupure initiale du nouveau CNAME. Les renouvellements de certificats n’ont pas le même effet, car le nom d’hôte ne change pas.

### Quel type de clé et quel algorithme de signature de certificat sont utilisés pour mon implémentation CNAME ?

Tous les certificats sont RSA SHA-256 et les clés sont RSA 2048 bits, par défaut. Les tailles de clés supérieures à 2 048 bits ne sont actuellement pas prises en charge.

### Comment puis-je vérifier que mon implémentation CNAME est prête pour le trafic ?

Utilisez l’ensemble de commandes suivant (dans le terminal de ligne de commande macOS ou Linux, à l’aide de bash et curl >=7.49) :

1. Copiez et collez cette fonction bash dans votre terminal ou collez-la dans votre fichier de script de démarrage bash (généralement `~/.bash_profile` ou `~/.bashrc`) afin que la fonction soit disponible dans toutes les sessions de terminal :

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

1. Collez cette commande (en remplaçant `target.example.com` avec votre nom d’hôte) :

   ```
   adobeTargetCnameValidation target.example.com
   ```

   Si l’implémentation est prête, la sortie s’affiche comme ci-dessous. La partie importante est que toutes les lignes d’état de validation affichent `✅` plutôt que `🚫`. Chaque [!DNL Target] Le partage CNAME Edge doit s’afficher `CN=target.example.com`, qui correspond au nom d’hôte Principal sur le certificat demandé (les noms d’hôtes SAN supplémentaires sur le certificat ne sont pas imprimés dans cette sortie).

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
   >Si cette commande de validation échoue lors de la validation DNS, mais que vous avez déjà apporté les modifications DNS nécessaires, vous devrez peut-être attendre que vos mises à jour DNS se propagent complètement. Les enregistrements DNS sont associés à [Durée de vie (TTL)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) qui détermine le délai d’expiration du cache pour les réponses DNS de ces enregistrements. Par conséquent, vous devrez peut-être attendre au moins aussi longtemps que vos TTL. Vous pouvez utiliser la variable `dig target.example.com` ou [Boîte à outils de la suite G](https://toolbox.googleapps.com/apps/dig/#CNAME) pour rechercher vos TTL spécifiques. Pour vérifier la propagation DNS dans le monde, voir [whatsmydns.net](https://whatsmydns.net/#CNAME).

### Comment utiliser un lien d’exclusion avec CNAME ?

Si vous utilisez CNAME, le lien d’exclusion doit contenir &quot;client=`clientcode` par exemple :
`https://my.cname.domain/optout?client=clientcode`.

Remplacer `clientcode` avec votre code client, puis ajoutez le texte ou l’image à lier au [URL d’exclusion](https://developer.adobe.com/target/before-implement/privacy/privacy/).

## Limites connues

* Le mode AQ n’est pas attractif lorsque vous utilisez CNAME et at.js 1.x, car il est basé sur un cookie tiers. La solution consiste à ajouter les paramètres d’aperçu à chaque URL à laquelle vous accédez. Le mode AQ est attractif lorsque vous disposez de CNAME et at.js 2.x.
* Lors de l’utilisation de CNAME, il devient plus probable que la taille de l’en-tête du cookie pour [!DNL Target] les appels augmentent. [!DNL Adobe] recommande de conserver la taille du cookie en dessous de 8 Ko.
