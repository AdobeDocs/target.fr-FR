---
title: SDK
description: Découvrez l’architecture de SDK dans Flags et les extensions AEP Web SDK et AEP Mobile SDK disponibles.
hide: true
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 1%

---

# SDK {#sdks}

Flags fournit des SDK pour intégrer des indicateurs de fonctionnalité dans vos applications. Les indicateurs sont déployés via AEP Web SDK et AEP Mobile SDK.

## Architecture de SDK {#architecture}

Tous les SDK Flags partagent la même architecture principale :

* **Initialisation** — Le SDK est configuré au démarrage et s&#39;enregistre auprès du service Flags.
* **Récupération de fonctionnalités** — Le SDK récupère les données d&#39;indicateur de fonctionnalité et évalue les indicateurs localement.
* **Mise en cache** — Le SDK met en cache les données d&#39;indicateur de fonctionnalité et les actualise selon un intervalle d&#39;interrogation configurable.
* **Gestion des erreurs** — Si le service n’est pas disponible, le SDK continue à diffuser les évaluations d’indicateur de fonctionnalité à partir du cache local.

## SDK disponibles {#available-sdks}

### AEP Web SDK {#web-sdk}

L’extension Flags pour le web s’intègre à Adobe Experience Platform Web SDK.

>[!NOTE]
>
>La prise en charge de Web SDK sera bientôt disponible. Contactez votre représentant Adobe pour obtenir des conseils sur l’accès anticipé.

### Extension Android {#android-extension}

L’extension Flags pour Android s’intègre à Adobe Experience Platform Mobile SDK.

Consultez le [guide d’intégration de l’extension ](../sdk-releases/android/android-extension-integration-guide.md) pour obtenir des instructions de configuration.

### Extension iOS {#ios-extension}

L’extension Flags pour iOS s’intègre à Adobe Experience Platform Mobile SDK.

Consultez le [guide d’intégration de l’extension ](../sdk-releases/ios/ios-extension-integration-guide.md) pour obtenir des instructions de configuration.

## Voir également {#see-also}

* [Guide d’intégration de l’extension Android](../sdk-releases/android/android-extension-integration-guide.md)
* [Guide d’intégration de l’extension iOS](../sdk-releases/ios/ios-extension-integration-guide.md)
* [Guide d’intégration de l’extension web](../sdk-releases/web/web-extension-integration-guide.md)

<!-- -->
