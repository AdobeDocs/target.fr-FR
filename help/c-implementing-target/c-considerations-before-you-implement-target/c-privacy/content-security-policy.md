---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Informations relatives aux directives CSP (Content Security Policy) que vous devez ajouter lors de l’utilisation d’Adobe Target at.js 2.1 ou version ultérieure.
title: Stratégies de sécurité de contenu (CSP)
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 5%

---


# Directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu)

Si vous utilisez [la stratégie de sécurité de contenu](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour votre mise en oeuvre [!DNL Adobe Target], vous devez ajouter les directives CSP suivantes lorsque vous utilisez [at.js 2.1 ou version ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) :

* `connect-src` avec  `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la demande réseau à l&#39;arête [!DNL Target].
* `style-src unsafe-inline`. Requis pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.
