---
keywords: navigateurs;conditions préalables;prérequis;internet explorer;chrome;firefox;safari;android;surface
description: Découvrez quels navigateurs Internet l’Adobe [!DNL Target] prend en charge pour son interface et pour la diffusion de contenu.
title: Quels sont les navigateurs pris en charge par  [!DNL Target] ?
feature: Mise en œuvre
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 47%

---

# Navigateurs pris en charge

L’application [!DNL Adobe Target] et la diffusion de contenu ont été testées sur un large éventail de navigateurs et de périphériques.

Pour plus d’informations importantes sur TLS, voir [Modifications du chiffrement de TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Interface Standard/Premium {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

L’interface [!DNL Target] prend en charge les navigateurs et périphériques suivants :

| Type de périphérique | Version du navigateur |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (dernière version, dernière version moins 1)</li><li>Mozilla Firefox (dernière version, dernière version moins 1)</li></ul> |
| Mac | <ul><li>Firefox (dernière version, dernière version moins 1)</li><li>Chrome (dernière version, dernière version moins 1)</li></ul> |

## Diffusion de contenu {#section_1045A946056441268D40025529918D3D}

La diffusion de contenu a été testée sur les navigateurs et les périphériques suivants :

| Type de périphérique | Version du navigateur |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 et 10. Testé en mode d’émulation.<br>**Remarque** : La diffusion de contenu sur IE 9 n’est plus prise en charge avec at.js 1.3.0 (et versions ultérieures). La diffusion de contenu sur IE 10, 11 et toutes les versions antérieures n’est plus prise en charge avec at.js 2.5.0 (et versions ultérieures).</li><li>Internet Explorer 11 <br>**Remarque** : La diffusion de contenu sur IE 10, 11 et toutes les versions antérieures n’est plus prise en charge avec at.js 2.5.0 (et versions ultérieures).</li><li>Microsoft Edge</li><li>Chrome (dernière version, dernière version moins 1)</li><li>Firefox (dernière version, dernière version moins 1)</li></ul> |
| Mac | <ul><li>Apple Safari (dernière version)<br>**Remarque** : Pour plus d’informations sur la manière dont Safari gère les cookies propriétaires et tiers, voir [Cookie Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (dernière version, dernière version moins 1)</li><li>Chrome (dernière version, dernière version moins 1)</li></ul> |
| Mobile/Tablette | <ul><li>Apple iOS (dernière version)</li><li>Appareils et tablettes Android (Android 4 et versions ultérieures)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Notez les points suivants :

* Pour les [!DNL at.js]implémentations,[!DNL Target], le contenu par défaut s’affiche dans les versions antérieures d’Internet Explorer, ainsi que dans certaines versions antérieures des navigateurs mentionnés ci-dessus.
* Internet Explorer traite tous les éléments inconnus (tels que les éléments personnalisés) comme un même type d’élément. Par conséquent, la diffusion ne fonctionne pas avec les éléments personnalisés.
* [!DNL Target] affiche le contenu par défaut dans les navigateurs non répertoriés ci-dessus, ainsi que dans les navigateurs en [mode Quirks](https://en.wikipedia.org/wiki/Quirks_mode). at.js nécessite un doctype qui présente le contenu en mode standard, tel que : `<!DOCTYPE html>`
* L’infrastructure de diffusion d’Adobe est sécurisée afin de NE PAS prendre en charge les appareils et navigateurs TLS 1.0 après le 12 septembre 2018. Veuillez consulter la section [Modifications du chiffrement de TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) pour comprendre l’impact global de cette modification.
