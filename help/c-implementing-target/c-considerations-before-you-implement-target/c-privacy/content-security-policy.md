---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Informations relatives aux directives CSP (Content Security Policy) que vous devez ajouter lors de l’utilisation d’Adobe Target at.js 2.1 ou version ultérieure.
title: Stratégies de sécurité de contenu (CSP)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 5%

---


# Directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu)

Si vous utilisez [la stratégie](https://en.wikipedia.org/wiki/Content_Security_Policy) de sécurité de contenu (CSP) pour votre implémentation de Cible, vous devez ajouter les directives CSP suivantes lors de l’utilisation d’ [at.js 2.1 ou version ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` avec `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la demande réseau à la [!DNL Target] périphérie.
* `style-src unsafe-inline`. Requis pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.
