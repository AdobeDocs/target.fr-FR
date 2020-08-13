---
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
description: L’application Adobe Target et la diffusion de contenu ont été testées sur un large éventail de navigateurs et de périphériques.
title: Navigateurs pris en charge
feature: reference general
subtopic: Getting Started
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 86%

---


# Navigateurs pris en charge{#supported-browsers}

L’application [!DNL Adobe Target] et la diffusion de contenu ont été testées sur un large éventail de navigateurs et de périphériques.

Pour plus d’informations importantes sur TLS, voir [Modifications du chiffrement de TLS (Transport Layer Security)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Interface Standard/Premium {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

The [!DNL Target] interface supports the following browsers and devices:

| Type de périphérique | Version du navigateur |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (dernière version, dernière version moins 1)</li><li>Mozilla Firefox (dernière version, dernière version moins 1)</li></ul> |
| Mac | <ul><li>Firefox (dernière version, dernière version moins 1)</li><li>Chrome (dernière version, dernière version moins 1)</li></ul> |

## Diffusion de contenu {#section_1045A946056441268D40025529918D3D}

La diffusion de contenu a été testée sur les navigateurs et les périphériques suivants :

| Type de périphérique | Version du navigateur |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 et 10. Testé en mode d’émulation.<br>**Remarque :** at.js 1.3.0 (et versions supérieures) ne prend plus en charge la diffusion de contenu sur Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (dernière version, dernière version moins 1)</li><li>Firefox (dernière version, dernière version moins 1)</li></ul> |
| Mac | <ul><li>Apple Safari (dernière version)<br>**Remarque** : pour plus d’informations sur la manière dont Safari traite les cookies propriétaires et les cookies tiers, veuillez consulter la section [Cookie de Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (dernière version, dernière version moins 1)</li><li>Chrome (dernière version, dernière version moins 1)</li></ul> |
| Mobile/Tablette | <ul><li>Apple iOS (dernière version)</li><li>Appareils et tablettes Android (Android 4 et versions ultérieures)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Notez les points suivants :

* Pour les [!DNL at.js]implémentations,[!DNL Target], le contenu par défaut s’affiche dans les versions antérieures d’Internet Explorer, ainsi que dans certaines versions antérieures des navigateurs mentionnés ci-dessus. Pour les [!DNL mbox.js]implémentations,[!DNL Target] tente de présenter le contenu mais peut échouer.
* Internet Explorer traite tous les éléments inconnus (tels que les éléments personnalisés) comme un même type d’élément. Par conséquent, la diffusion ne fonctionne pas avec les éléments personnalisés.
* [!DNL Target] affiche le contenu par défaut dans les navigateurs non répertoriés ci-dessus, ainsi que dans les navigateurs en [mode Quirks](https://en.wikipedia.org/wiki/Quirks_mode). at.js nécessite un doctype qui présente le contenu en mode standard, tel que : `<!DOCTYPE html>`
* L’infrastructure de diffusion d’Adobe est sécurisée afin de NE PAS prendre en charge les appareils et navigateurs TLS 1.0 après le 12 septembre 2018. Veuillez consulter la section [Modifications du chiffrement de TLS (Transport Layer Security)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) pour comprendre l’impact global de cette modification.
