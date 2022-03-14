---
keywords: stratégie de sécurité du contenu;csp;at.js;liste autorisée;liste autorisée;scintillement;pré-masquage;pré-masquage;prémasquage
description: Découvrez les directives CSP (Content Security Policy) que vous devez ajouter lors de l’utilisation d’Adobe Target.
title: Comment [!DNL Target] Gérer les stratégies de sécurité du contenu (CSP) ?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# Directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu)

Si vous utilisez [Stratégie de sécurité du contenu](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour votre [!DNL Adobe Target] implémentation, vous devez ajouter les directives CSP suivantes lors de l’utilisation de [at.js 2.1 ou version ultérieure](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` avec `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la requête réseau à la variable [!DNL Target] edge.
* `style-src unsafe-inline`. Requis pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Requis pour autoriser l’exécution JavaScript qui peut faire partie d’une offre de HTML.
