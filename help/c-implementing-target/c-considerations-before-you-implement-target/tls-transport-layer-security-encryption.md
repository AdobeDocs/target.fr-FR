---
keywords: tls;tls 1.0;transport layer security;chiffrement
description: Informations sur les modifications apportées à la manière dont Adobe et Target utilisent TLS (Transport Layer Security) pour maintenir les normes de sécurité les plus strictes et promouvoir la sécurité des données client.
title: Modifications du chiffrement de TLS (Transport Layer Security)
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Modifications du chiffrement de TLS (Transport Layer Security){#tls-transport-layer-security-encryption-changes}

Informations sur les modifications apportées à la manière dont Adobe et Target utilisent TLS (Transport Layer Security) pour maintenir les normes de sécurité les plus strictes et promouvoir la sécurité des données client.

Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. [!DNL Adobe] a adopté des normes de conformité en matière de sécurité qui exigent la cessation des protocoles plus anciens et impose l’utilisation de TLS 1.2 afin de disposer de la version la plus récente et la plus sécurisée.

>[!NOTE]
>
>Le 20 février 2019, l’infrastructure Adobe Target a été mise à niveau dans les régions EMEA, Japon et Asie-Pacifique afin de ne plus collecter les données d’utilisateurs finaux disposant d’anciens appareils ou de navigateurs Web qui ne prennent pas en charge TLS 1.1 ou une version ultérieure. Cette même mise à niveau est prévue pour la région Amérique du Nord pour **le 1er avril 2019**. La migration vers TLS 1.2 améliore la sécurité. Il est important que vous passiez en revue les détails et que vous planifiiez les changements avec votre équipe informatique pour une transition en douceur.

Cette modification ne devrait pas avoir de répercussions importantes sur les données des clients ou le compte rendu des performances.

## Compositeur d’expérience visuelle (VEC) avec Compositeur d’expérience avancé activé {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

Jusqu’à présent, le [Compositeur d’expérience avancé](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) d’Adobe Target utilisait TLS 1.0 par défaut. À partir de la version 18.4.1 de Target (25 avril 2018), Target passe à TLS 1.2 par défaut.

Adobe fera passer les clients de manière progressive à TLS 1.2. Pour ceux dont les domaines sont déjà conformes à la version 1.2, nous les déplacerons vers TLS 1.2 sans que vous ayez à apporter une modification. La plupart des domaines clients prennent déjà en charge TLS 1.2. Cependant, si votre domaine ne prend pas en charge TLS 1.2, nous garderons ces domaines sur TLS 1.0 avec la même prise en charge (jusque février 2019).

Aucun problème ne devrait se poser pendant cette phase de migration. Si le VEC a arrêté de charger un site qui fonctionnait auparavant, [faites une demande d’aide auprès du service à la clientèle](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) en citant cette migration comme une cause possible.

Si, cependant, vous êtes l’un de ces clients qui sont sur TSL 1.0 sans prendre en charge TLS 1.2, alors vous devez planifier le déplacement de vos domaines/infrastructure vers TLS 1.2. Nous continuerons à prendre en charge le protocole TLS 1.0 jusque février 2019. À compter de février 2019, Target ne prendra plus en charge le protocole TLS 1.0 à utiliser pour le VEC via la fonctionnalité Compositeur d’expérience avancé.

Bien que nous recommandions fortement à tout le monde de travailler avec TLS 1.2 à l’avenir, si vous êtes un nouveau client, mais que vous ne prenez *PAS* en charge TLS 1.2, veuillez contacter l’assistance clientèle pour l’informer que vous devez être sur TLS 1.0 pour le Compositeur d’expérience avancé. Cependant, veuillez prévoir de passer à TLS 1.2, car la prise en charge ne sera plus disponible d’ici février 2019.

## Diffusion des activités {#section_46CA5943E4354B259014C2BF340AECD6}

À compter de février 2019, les serveurs Target ne prendront plus en charge TLS 1.0. Avec cette modification, les serveurs Target n’accepteront plus les demandes d’accès des utilisateurs finaux disposant d’appareils ou de navigateurs web plus anciens qui ne prennent pas en charge TLS 1.1 ou une version supérieure. De ce fait, les appareils et navigateurs plus anciens prenant uniquement en charge TLS 1.0 (ou prenant en charge TLS 1.0 par défaut) ne recevront pas de contenu d’activité d’Adobe Target. Le contenu par défaut du site sera rendu.

Certains des anciens appareils et navigateurs qui seront affectés incluent :

* Android 4.3 et versions antérieures
* Internet Explorer 8-10 sous Windows 7 et versions antérieures
* Internet Explorer 10 sous Windows Phone 8.0
* Safari 6.0.4/OS X 10.8.4 et versions antérieures.

Lorsque vous planifiez ce changement, tenez compte de ce qui suit (notez que l’échéance de février 2019 a une incidence sur tous ces éléments) :

* Vous devez vous assurer que votre site par défaut est prêt à être utilisé avec les appareils et navigateurs conformes.
* Il faut savoir que le nombre de visiteurs dans vos rapports Target peut potentiellement enregistrer une baisse minime du nombre de visiteurs.
* Vous devrez peut-être modifier les audiences créées spécifiquement pour les anciens appareils ou navigateurs de Target qui ne prennent pas en charge TLS 1.0. La diffusion sur ces appareils et navigateurs ne sera plus disponible.

Pour plus de détails sur les navigateurs pris en charge et leurs versions, voir [Navigateurs pris en charge](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## API Adobe Target.{#section_88797FA5434049EC89F908853CC76903}

À compter de février 2019, les API de Target ne prendront plus en charge le chiffrement TLS 1.0. Les clients qui accèdent à l’API doivent vérifier qu’ils ne seront pas affectés.

* Les clients d’API utilisant Java 7 avec des paramètres par défaut devront être modifiés pour prendre en charge TLS 1.2. Pour plus d’informations, voir [Changement de la version par défaut du protocole TLS pour les paramètres du client : de TLS 1.0 à TLS 1.2](https://www.java.com/en/configure_crypto.html) sur le site web de Java.
* Les clients d’API utilisant Java 8 ne devraient pas être affectés, étant donné que TLS 1.2 est la configuration par défaut.
* Les clients API utilisant d’autres structures devront contacter leurs fournisseurs pour plus de détails sur la prise en charge de TLS 1.2.

## Accès aux interfaces de solutions d’Experience Cloud {#section_748870ADE77B4CBEB18518DC784E64E5}

Comme l’interface de Target Standard/Premium nécessite déjà un [navigateur Web moderne](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), nous ne prévoyons aucun problème. Si vous ne parvenez pas à vous connecter à Target, mettez à niveau votre navigateur vers la version la plus récente.

## Comment vérifier quelle version de TLS votre navigateur utilise {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Pour vérifier la version TLS de votre site web en utilisant Firefox (les autres navigateurs suivent des étapes similaires) :

1. Ouvrez le site web concerné dans Firefox.
1. Cliquez sur l’icône **[!UICONTROL Afficher les informations du site]dans la barre d’adresse du navigateur.**

   ![](assets/firefox_more_info.png)

1. Cliquez sur **[!UICONTROL Afficher les détails de la connexion]** &gt; **[!UICONTROL Plus d’informations]**.

   ![](assets/firefox_more_info_2.png)

1. Examinez les informations de version TLS dans l’option Détails techniques :

   ![](assets/firefox_more_info_3.png)

## Comportement attendu des navigateurs prenant en charge TLS 1.0 uniquement {#section_B5DA97A34EF248EB927610A5DA71EF2F}

Cette section décrit le comportement attendu des navigateurs qui prennent uniquement en charge TLS 1.0 lors de l’utilisation d’une implémentation d’at.js ou de mbox.js. À des fins de comparaison, cette section décrit également le comportement attendu des navigateurs qui prennent en charge TLS 1.1 et 1.2.

### Points de terminaison centraux

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | Avec TLS 1.0 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li></ul>Avec TLS 1.1 ou 1.2 activé :<ul><li>Téléchargement du fichier at.js.</li></ul> |
| mbox.js | Avec TLS 1.0 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li></ul>Avec TLS 1.1 ou 1.2 activé :<ul><li>Téléchargement du fichier mbox.js.</li></ul> |

### Points de terminaison périphériques

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | Avec TLS 1.0 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Le contenu par défaut est présenté.</li></ul>Avec TLS 1.1 ou 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |
| mbox.js | Avec TLS 1.0 activé :<ul><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li><li>Le message « Impossible d’établir une connexion sécurisée. » s’affiche. Ce message indique que les paramètres de sécurité TLS du site sont peut-être obsolètes ou risqués.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Le contenu par défaut est présenté.</li></ul>Avec TLS 1.1 ou 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |

### Activité ciblée en fonction de l’audience de la version du navigateur (Internet Explorer, version 6, 7 ou 8)

>[!NOTE]
>
>Les audiences ne fonctionnent plus.

| Implémentation JavaScript pour Target | Détails |
|--- |--- |
| at.js | at.js n’est pas pris en charge par les versions antérieures à Internet Explorer 10. |
| mbox.js | Avec TLS 1.0 activé :<ul><li>Le contenu par défaut est présenté.</li><li>Aucune demande de Target n’est déclenchée.</li><li>Aucune erreur ne s’affiche dans la console.</li><li>Lors de l’utilisation des outils de développement du navigateur, « 200 OK » s’affiche sur l’onglet réseau. Cela indique le succès de la requête.</li></ul>Avec TLS 1.1 ou 1.2 activé :<ul><li>Le contenu des offres est présenté.</li></ul> |