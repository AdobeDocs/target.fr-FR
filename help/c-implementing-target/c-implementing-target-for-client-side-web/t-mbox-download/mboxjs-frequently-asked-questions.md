---
keywords: mbox.js faq;mbox.js frequently asked questions;document.write;tt.omtrdc.net;parser blocking
description: Réponses aux questions fréquentes sur mbox.js.
title: Questions fréquentes sur mbox.js
feature: null
subtopic: Getting Started
uuid: af3105ab-87d9-4dbf-a380-b72788928958
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 98%

---


# Questions fréquentes sur mbox.js{#mbox-js-frequently-asked-questions}

Réponses aux questions fréquentes sur mbox.js.

## Quel est l’impact de mbox.js sur les délais de chargement des pages ?{#section_90B3B94FE0BF4B369577FCB97B67F089}

Pour plus d’informations, voir [Avantages d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits).

## Pourquoi un avertissement de blocage d’analyseur s’affiche-t-il dans Google Chrome quand j’utilise mbox.js et document.write ?{#section_355A3A5BF02F42EEB8271C96EF41590A}

Ce message de console apparaît parfois dans Chrome lorsque vous utilisez la fonction `document.write` dans le fichier mbox.js. C’est un message d’avertissement qui ne devrait avoir aucune incidence sur la configuration de votre activité.

Pour éviter qu’il ne s’affiche, [migrez votre mise en œuvre Target vers la bibliothèque JavaScript at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA), qui n’utilise pas la fonction `document.write`. L’utilisation de la bibliothèque at.js présente de nombreux avantages par rapport à mbox.js. Pour plus d’informations, voir [Questions fréquentes d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## Pourquoi mes mbox ne se déclenchent-elles pas sur mes pages web ?{#section_4BA5DA424B734324AAB51E4588FA50F5}

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines, sauf si vous personnalisez le paramètre `cookieDomain` à l’aide de targetGlobalSettings(). Pour plus d’informations, voir [Utilisation d’instances basées sur Cloud avec Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## À quoi correspond le domaine tt.omtrdc.net auquel les appels au serveur Target sont adressés ?{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] est le nom de domaine du réseau EDGE d’Adobe utilisé pour recevoir tous les appels au serveur pour Target.

## Pourquoi at.js et mbox.js n’utilisent-ils pas les indicateurs de cookie HttpOnly et Secure ?{#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly ne peut être défini que via un code côté serveur. Les cookies Target, tels que mbox, étant créés et enregistrés via le code JavaScript, Target ne peut pas utiliser l’indicateur de cookie HttpOnly.

Secure ne peut être défini que via JavaScript lorsque la page a été chargée via HTTPS. Si la page se charge initialement via HTTP, JavaScript ne peut pas définir cet indicateur. En outre, si l’indicateur Secure est utilisé, le cookie sera disponible uniquement sur les pages HTTPS.

Pour vous assurer que Target peut assurer un suivi correct des utilisateurs, et parce que les cookies sont générés côté client, Target n’utilise aucun de ces indicateurs.
