---
keywords: tls;tls 1.0;transport layer security;encryption;tls 1.1;tls 1.2
description: Informations sur les modifications apportées à la manière dont Adobe et Target utilisent TLS (Transport Layer Security) pour maintenir les normes de sécurité les plus strictes et promouvoir la sécurité des données client.
title: Modifications du chiffrement de TLS (Transport Layer Security)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 62%

---


# Modifications du chiffrement de TLS (Transport Layer Security){#tls-transport-layer-security-encryption-changes}

Informations sur les modifications apportées à la façon dont l&#39;Adobe et l&#39;Adobe Target utilisent TLS (Transport Layer Security) pour maintenir les normes de sécurité les plus élevées et promouvoir la sécurité des données des clients.

Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. Adobe a adopté des normes de conformité en matière de sécurité qui exigent la cessation des protocoles plus anciens et impose l’utilisation de TLS 1.2 afin de disposer de la version la plus récente et la plus sécurisée.

>[!IMPORTANT]
>
>Après le 1er mars 2020, Adobe Target ne prendra plus en charge le chiffrement TLS 1.1 pour le compositeur d’expérience visuelle (VEC), le compositeur d’expérience amélioré (CEE), la diffusion d’activité, les API, etc. Veuillez effectuer la mise à niveau vers TLS 1.2 avant le 1er mars 2020 pour éviter tout problème.

Cette modification ne devrait pas avoir de répercussions importantes sur les données des clients ou le compte rendu des performances.

## Compositeur d’expérience visuelle (VEC) avec Compositeur d’expérience avancé activé {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

TLS 1.2 est la valeur par défaut à compter du 1er mars 2020 et TLS 1.1 ne sera plus pris en charge.

Adobe fera passer les clients de manière progressive à TLS 1.2. Pour ceux dont les domaines sont déjà conformes à la version 1.2, nous les déplacerons vers TLS 1.2 sans que vous ayez à apporter une modification. La plupart des domaines de clients prennent déjà en charge TLS 1.2 ; toutefois, si votre domaine ne prend pas en charge TLS 1.2, nous conserverons ces domaines sur TLS 1.1 comme aujourd&#39;hui (jusqu&#39;en mars 2020).

Aucun problème ne devrait se poser pendant cette phase de migration. Si le VEC a arrêté de charger un site qui fonctionnait auparavant, [faites une demande d’aide auprès du service à la clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) en citant cette migration comme une cause possible.

Si, toutefois, vous faites partie de ces clients qui utilisent TSL 1.1 sans prendre en charge TLS 1.2, vous devriez prévoir le déplacement de vos domaines/infrastructures vers TLS 1.2. Nous continuerons à prendre en charge le protocole TLS 1.1 jusqu&#39;au 1er mars 2020. À compter du 1er mars 2020, la Cible ne prendra pas en charge le protocole TLS 1.1 à utiliser pour le compositeur d’expérience amélioré pour le compositeur d’expérience.

Bien que nous recommandions fortement à tout le monde de travailler avec TLS 1.2 à l’avenir, si vous êtes un nouveau client, mais que vous ne prenez *PAS* en charge TLS 1.2, veuillez contacter l’assistance clientèle pour l’informer que vous devez être sur TLS 1.1 pour le Compositeur d’expérience avancé. Cependant, veuillez prévoir de passer à TLS 1.2 car vous ne serez pas non plus pris en charge au-delà du 1er mars 2020.

## Activité diffusion {#section_46CA5943E4354B259014C2BF340AECD6}

À compter du 1er mars 2020, les serveurs de Cible ne prendront plus en charge TLS 1.1. Avec ce changement, les serveurs de Cible n&#39;accepteront plus les demandes des visiteurs dotés d&#39;anciens périphériques ou navigateurs Web qui ne prennent pas en charge TLS 1.2 (ou version ultérieure). De ce fait, les appareils et navigateurs plus anciens prenant uniquement en charge TLS 1.1 (ou prenant en charge TLS 1.1 par défaut) ne recevront pas de contenu d’activité d’Adobe Target. Le contenu par défaut du site sera rendu.

Certains des anciens appareils et navigateurs qui seront affectés incluent :

* Google Chrome (Chrome pour Android) versions 29 et antérieures
* Opera Browser (Opera Mobile) versions 12.17 et antérieures
* Mozilla Firefox (Firefox pour Mobile) versions 26 et antérieures
* Android 4.3 et versions antérieures
* Internet Explorer 8-10 sous Windows 7 et versions antérieures
* Internet Explorer 10 sous Windows Phone 8.0
* Safari 6.0.4/OS X 10.8.4 et versions antérieures.

À mesure que vous prévoyez ce changement, tenez compte des points suivants (notez que la date limite du 1er mars 2020 touche tous ces éléments) :

* Vous devez vous assurer que votre site par défaut est prêt à être utilisé avec les appareils et navigateurs conformes.
* Il faut savoir que le nombre de visiteurs dans vos rapports Target peut potentiellement enregistrer une baisse minime du nombre de visiteurs.
* Vous devrez peut-être modifier les audiences créées spécifiquement pour cible des périphériques ou navigateurs plus anciens qui ne prennent pas en charge TLS 1.2. La Diffusion à ces périphériques et navigateurs ne fonctionnera plus.

Pour plus de détails sur les navigateurs pris en charge et leurs versions, voir [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## API Adobe Target.{#section_88797FA5434049EC89F908853CC76903}

À compter du 1er mars 2020, les API de Cible ne prendront plus en charge le chiffrement TLS 1.1. Les clients qui accèdent à l’API doivent vérifier qu’ils ne seront pas affectés.

* Les clients d’API utilisant Java 7 avec des paramètres par défaut devront être modifiés pour prendre en charge TLS 1.2. Pour plus d’informations, voir [Changement de la version par défaut du protocole TLS pour les paramètres du client : de TLS 1.0 à TLS 1.2](https://www.java.com/en/configure_crypto.html) sur le site web de Java.
* Les clients d’API utilisant Java 8 ne devraient pas être affectés, étant donné que TLS 1.2 est la configuration par défaut.
* Les clients API utilisant d’autres structures devront contacter leurs fournisseurs pour plus de détails sur la prise en charge de TLS 1.2.

## Accès aux interfaces des solutions Experience Cloud {#section_748870ADE77B4CBEB18518DC784E64E5}

Comme l’interface de Target Standard/Premium nécessite déjà un [navigateur Web moderne](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), nous ne prévoyons aucun problème. Si vous ne parvenez pas à vous connecter à Target, mettez à niveau votre navigateur vers la version la plus récente.

## Comment vérifier quelle version TLS votre navigateur utilise {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Pour vérifier la version TLS de votre site Web à l’aide de Google Chrome, procédez comme suit :

1. Ouvrez le site Web concerné dans Chrome.
1. Dans le menu Chrome (les trois ellipses verticales), cliquez sur Autres outils > Outils de développement.

   ![Chrome Developer Tools](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. Ouvrez l’onglet Sécurité, puis examinez les informations de version TLS sous Connexion :

   ![Détails de la version TLS](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>Ces instructions sont à jour à compter de la publication et peuvent être modifiées. Une recherche rapide sur Internet devrait vous aider si ces instructions changent.  D’autres navigateurs suivent les mêmes étapes.

## Comportement attendu avec les navigateurs prenant en charge les versions TLS inférieures à 1.2 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

Cette section décrit ce à quoi s’attendre avec les navigateurs qui prennent en charge les versions TLS inférieures à 1.2 uniquement lors de l’utilisation d’une implémentation at.js ou mbox.js. À des fins de comparaison, cette section décrit également ce à quoi s&#39;attendre avec les navigateurs qui prennent en charge TLS 1.2.

### Points de terminaison centraux

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | Avec TLS 1.0 ou TLS 1.1 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li></ul>Avec TLS 1.2 activé :<ul><li>Téléchargement du fichier at.js.</li></ul> |
| mbox.js | Avec TLS 1.0 ou TLS 1.1 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li></ul>Avec TLS 1.2 activé :<ul><li>Téléchargement du fichier mbox.js.</li></ul> |

### Points de terminaison Edge

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | Avec TLS 1.0 ou TLS 1.1 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Le contenu par défaut est présenté.</li></ul>Avec TLS 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |
| mbox.js | Avec TLS 1.0 ou TLS 1.1 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Le contenu par défaut est présenté.</li></ul>Avec TLS 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |

### Activité ciblée avec l’audience de la version du navigateur (Internet Explorer, versions 6, 7 ou 8)

>[!NOTE]
>
>Les audiences ne fonctionnent plus.

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | at.js n’est pas pris en charge par les versions antérieures à Internet Explorer 10. |
| mbox.js | Avec TLS 1.0 ou TLS 1.1 activé :<ul><li>Le contenu par défaut est présenté.</li><li>Aucune demande de Target n’est déclenchée.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li></ul>Avec TLS 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |