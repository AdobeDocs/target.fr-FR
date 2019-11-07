---
keywords: stratégie de sécurité du contenu;csp;at.js;liste blanche;scintillement;pre-hide;pre-hide;prehide;prehide
description: Informations sur les directives CSP (Content Security Policy) que vous devez ajouter lors de l’utilisation d’Adobe Target at.js 2.1 ou version ultérieure.
title: Stratégies de sécurité de contenu (CSP)
subtopic: Prise en main
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Directives CSP (Content Security Policy)

Si vous utilisez [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour votre implémentation Target, vous devez ajouter les directives CSP suivantes lors de l’utilisation d’ [at.js 2.1 ou version ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` avec `*.tt.omtrdc.net` liste blanche. Nécessaire pour autoriser la requête réseau à [!DNL Target] l'extrémité.
* `style-src unsafe-inline`. Requis pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.
