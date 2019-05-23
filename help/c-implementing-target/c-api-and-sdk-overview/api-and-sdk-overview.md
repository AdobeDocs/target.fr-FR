---
description: Informations sur les API de diffusion côté serveur Target, les API de recommandation et le SDK NodeJS.
keywords: côté serveur;api;sdk;nodejs;node js;api de recommandations
seo-description: Informations sur les API de diffusion côté serveur Target, les API de recommandation et le SDK NodeJS.
seo-title: Côté serveur implémentation de Target
solution: Target
title: Côté serveur implémentation de Target
topic: Recommandations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 845fdba274a5aef740ffd4787d36e62bd769942a

---


# Côté serveur : implémentation de Target{#server-side-implement-target}

Informations concernant les API de remise côté serveur Target, les API de remise en lots côté serveur, les API NodeJS, les API de recommandations Target et les API Target Classic (ignorées).

La section suivante répertorie les différentes API et le SDK NodeJS et fournit des informations supplémentaires :

## API de diffusion côté serveur

Lien : [API de diffusion côté serveur](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

Adobe Target permet à votre application d’effectuer des appels mbox depuis n’importe quel navigateur ou périphérique mobile ou même un autre serveur. L’API de diffusion côté serveur est spécialement conçue pour intégrer Adobe Target avec n’importe quelle plateforme côté serveur qui effectue des appels HTTP/HTTPS.

Vous pouvez utiliser l’API pour intégrer votre application personnalisée à Target. Ceci est particulièrement utile pour les organisations qui souhaitent diffuser un ciblage à un périphérique IoT non basé sur un navigateur, tel qu’une TV connectée, un kiosque ou un écran numérique en magasin.

Ce terminal peut renvoyer des offres pour les mboxes ordinaires uniquement. Vous pouvez également récupérer du contenu pour une seule mbox uniquement.

Cette API met en œuvre les fonctions mbox existantes dans un mode RESTful.

Cette API ne traite pas les cookies ni les appels de redirection.

## API de diffusion par lots côté serveur

Lien : [API de remise par lot côté serveur](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

L’API de diffusion par lots permet à votre application de demander du contenu pour plusieurs mboxes dans un seul appel. Elle dispose également d’un mode de prérécupération qui permet aux clients tels que les applications mobiles, les serveurs, etc., de récupérer du contenu pour plusieurs mboxes dans une requête, de placer ce contenu en cache localement et par la suite de notifier Target lorsque l’utilisateur visite ces mboxes.

Ce terminal peut renvoyer des offres pour les mboxes ordinaires uniquement. Parce que vous pouvez récupérer du contenu pour plusieurs mboxes, en termes de performances, il est plus sensé d’utiliser l’API mbox par lots. Cela permet d’éviter d’exécuter plusieurs requêtes HTTP, ce qui peut être onéreux.

## SDK NodeJS

Lien : [SDK nodejs](https://www.npmjs.com/package/@adobe/target-node-client)

En termes de SDK, nous ne disposons actuellement que d’un SDK, le SDK NodeJS.

Le SDK NodeJS est une couche fine autour du module HTTP/HTTPS central NodeJS. Dans les coulisses, les API du SDK NodeJS utilisent les mêmes API de diffusion côté serveur.

Le mappage est le suivant :

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## API de recommandation Target

Lien : [API de recommandations Target](https://developers.adobetarget.com/api/recommendations)

Les API de recommandations vous permettent d’interagir par programmation avec les serveurs de recommandation de Target. Ces API peuvent être intégrées à une plage de piles d’applications pour exécuter des fonctions que vous exécuteriez normalement via l’interface utilisateur.

## API classiques Target

L’interface utilisateur et les API classiques Target ont été déclassées. Pour plus d’informations sur le passage aux API modernes de Target Classic, voir [Transition des API héritées de Target vers Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2).

>[!NOTE]
>Les API de création (dans lesquels vous créez des activités, des offres, des audiences, etc.) ne prennent pas en charge le partage de ressources inter-origines (CORS).

## Différences entre les API de diffusion côté serveur et le SDK NodeJS {#section_10336B7934F54CE98E35907A4748A4A4}

De nombreux clients ne distinguent pas les différences entre les API de diffusion côté serveur et le SDK NodeJS. Ceci est particulièrement vrai lorsqu’il s’agit de performances.

Les questions fréquentes suivantes devraient vous aider à choisir entre les deux :

**Quand utiliser les API côté serveur « brutes » et quand utiliser le SDK NodeJS ?**

Dans l’idéal si vous utilisez NodeJS comme technologie d’arrière-plan, le SDK NodeJS est un choix naturel. Le SDK gère beaucoup de détails, tels que les cookies, les en-têtes, la charge utile, etc. Vous pouvez ainsi vous concentrer sur le point central de votre application.

**Devrais-je obtenir de meilleures performances en utilisant le SDK NodeJS ?**

Malheureusement, nous n’avons aucun chiffre sur les performances. Toutefois, en règle générale, le SDK NodeJS devrait fournir de bonnes performances, grâce à l’architecture orientée événements du SDK NodeJS. Soyez conscient que la plupart du temps est consacré au serveur principal. Le SDK NodeJS effectue très peu de traitement. Le SDK est essentiellement chargé de grouper une requête Target et d’analyser une réponse Target.
