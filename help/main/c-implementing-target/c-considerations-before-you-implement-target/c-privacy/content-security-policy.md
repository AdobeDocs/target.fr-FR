---
keywords: politique de sécurité du contenu;csp;at.js;liste blanche;liste autorisée;scintillement;prémasque;prémasqué;prémasquant
description: Découvrez les directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu) que vous devez ajouter lors de l’utilisation d’Adobe Target.
title: Comment  [!DNL Target]  gère-t-il les politiques de sécurité du contenu (CSP) ?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 97%

---

# Directives relatives aux politiques de sécurité du contenu (CSP)

Si vous utilisez une [politique de sécurité du contenu](https://fr.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour l’implémentation de votre [!DNL Adobe Target], vous devez ajouter les directives relatives aux CSP suivantes lors de l’utilisation de [at.js 2.1 ou version ultérieure](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) :

* `connect-src` avec `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la requête réseau à [!DNL Target] edge.
* `style-src unsafe-inline`. Obligatoire pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.

## Questions fréquentes

Consultez les questions fréquentes suivantes au sujet des politiques de sécurité :

### Les politiques CORS (Cross Origin Resource Sharing) et les politiques Flash Cross-domain présentent-elles des problèmes de sécurité ?

La méthode recommandée pour mettre en œuvre la stratégie CORS consiste à autoriser l’accès aux seules origines approuvées qui le nécessitent via une liste autorisée de domaines approuvés. Il en va de même pour la politique Flash Cross-domain. Certains clients [!DNL Adobe Target] s’inquiètent de l’utilisation de caractères génériques pour les domaines dans [!DNL Target]. Si un utilisateur est connecté à une application et qu’il visite un domaine autorisé par la politique, tout contenu malveillant exécuté sur ce domaine peut potentiellement récupérer du contenu sensible dans l’application et effectuer des actions dans le contexte de sécurité de l’utilisateur connecté. On parle généralement d’attaque CSRF (Cross-site request forgery).

Dans une implémentation [!DNL Adobe Target], cependant, ces politiques ne doivent pas représenter un problème de sécurité.

« adobe.tt.omtrdc.net » est un domaine détenu par Adobe. [!DNL Adobe Target] est un outil de test et de personnalisation. Il est prévu que [!DNL Target] puisse recevoir et traiter des requêtes provenant de n’importe où sans nécessiter d’authentification. Ces requêtes contiennent des paires clé/valeur utilisées pour les tests A/B, les recommandations ou la personnalisation du contenu.

[!DNL Adobe] ne stocke pas d’informations d’identification personnelles (PII) ni d’autres informations sensibles sur les serveurs Edge [!DNL Adobe Target], vers lesquels pointe « adobe.tt.omtrdc.net »

Il est prévu que [!DNL Target] soit accessible depuis n’importe quel domaine via des appels JavaScript. La seule façon d’autoriser cet accès consiste à utiliser « Access-Control-Allow-Origin » avec un caractère générique.
