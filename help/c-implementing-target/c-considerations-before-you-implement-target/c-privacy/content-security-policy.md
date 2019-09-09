---
description: Informations sur les directives CSP (Content Security Policy) que vous devez ajouter lors de l'utilisation d'Adobe Target at. js 2.1 ou version ultérieure.
keywords: stratégie de sécurité du contenu ; csp ; at. js ; Liste blanche ; scintillement ; pre-hide ; prémasquage ; prémasquage
seo-description: Informations sur les directives CSP (Content Security Policy) que vous devez ajouter lors de l'utilisation d'Adobe Target at. js 2.1 ou version ultérieure.
seo-title: Stratégies de sécurité du contenu (CSP)
solution: Target
subtopic: Prise en main
title: Directives CSP (Content Security Policy)
topic: Standard
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Directives CSP (Content Security Policy)

Si vous utilisez [la stratégie](https://en.wikipedia.org/wiki/Content_Security_Policy) CSP (Content Security Policy) pour votre implémentation Target, vous devez ajouter les directives CSP suivantes lors de l'utilisation [d'at. js 2.1 ou version ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` avec `*.tt.omtrdc.net` liste blanche. Nécessaire pour autoriser la demande réseau à atteindre [!DNL Target] le bord.
* `style-src unsafe-inline`. Obligatoire pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l'exécution de JavaScript qui peut faire partie d'une offre HTML.
