---
keywords: stratégie de sécurité du contenu ; csp ; at.js ; liste autorisée ; liste autorisée ; scintillement ; pré-masquage ; prémasquage ; prémasquage
description: Découvrez les directives CSP (Content Security Policy) que vous devez ajouter lors de l’utilisation d’Adobe Target.
title: Comment  [!DNL Target] gère-t-il les stratégies de sécurité de contenu (CSP) ?
feature: Confidentialité et sécurité
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 5%

---

# Directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu)

Si vous utilisez [la stratégie de sécurité de contenu](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour votre mise en oeuvre [!DNL Adobe Target], vous devez ajouter les directives CSP suivantes lorsque vous utilisez [at.js 2.1 ou version ultérieure](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) :

* `connect-src` avec  `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la demande réseau à l&#39;arête [!DNL Target].
* `style-src unsafe-inline`. Requis pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.
