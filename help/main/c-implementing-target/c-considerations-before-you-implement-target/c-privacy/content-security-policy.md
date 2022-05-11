---
keywords: politique de sécurité du contenu;csp;at.js;liste blanch;liste autorisée;scintillement;prémasque;prémasqué;prémasquant
description: Découvrez les directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu) que vous devez ajouter lors de l’utilisation d’Adobe Target.
title: Comment  [!DNL Target]  gère-t-il les politiques de sécurité du contenu (CSP) ?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 29%

---

# Directives relatives aux politiques de sécurité du contenu (CSP)

Si vous utilisez une [politique de sécurité du contenu](https://fr.wikipedia.org/wiki/Content_Security_Policy) (CSP) pour l’implémentation de votre [!DNL Adobe Target], vous devez ajouter les directives relatives aux CSP suivantes lors de l’utilisation de [at.js 2.1 ou version ultérieure](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) :

* `connect-src` avec `*.tt.omtrdc.net` placé sur la liste autorisée. Nécessaire pour autoriser la requête réseau à [!DNL Target] edge.
* `style-src unsafe-inline`. Obligatoire pour le prémasquage et le contrôle du scintillement.
* `script-src unsafe-inline`.  Obligatoire pour autoriser l’exécution de JavaScript qui peut faire partie d’une offre HTML.

## Questions fréquentes

Consultez les questions fréquentes suivantes au sujet des stratégies de sécurité :

### Les stratégies CORS (Cross Origin Resource Sharing) et les stratégies inter-domaines de Flash présentent-elles des problèmes de sécurité ?

La méthode recommandée pour mettre en oeuvre la stratégie CORS consiste à autoriser l’accès aux seules origines approuvées qui le nécessitent via une liste autorisée de domaines approuvés. Il en va de même pour la stratégie inter-domaines de Flash. Certains [!DNL Adobe Target] Les clients s’inquiètent de l’utilisation de caractères génériques pour les domaines dans [!DNL Target]. Si un utilisateur est connecté à une application et qu’il visite un domaine autorisé par la stratégie, tout contenu malveillant exécuté sur ce domaine peut potentiellement récupérer du contenu sensible de l’application et effectuer des actions dans le contexte de sécurité de l’utilisateur connecté. On parle généralement de falsification de requête intersites (CSRF).

Dans un [!DNL Adobe Target] implémentation, cependant, ces stratégies ne doivent pas représenter un problème de sécurité.

&quot;adobe.tt.omtrdc.net&quot; est un domaine détenu par l’Adobe. [!DNL Adobe Target] est un outil de test et de personnalisation. Il est prévu que [!DNL Target] peut recevoir et traiter des requêtes de n’importe où sans nécessiter d’authentification. Ces requêtes contiennent des paires clé/valeur utilisées pour les tests A/B, les recommandations ou la personnalisation du contenu.

[!DNL Adobe] ne stocke pas d’informations d’identification personnelles ni d’autres informations sensibles sur [!DNL Adobe Target] serveurs Edge, vers lesquels pointe &quot;adobe.tt.omtrdc.net&quot;.

Il est prévu que [!DNL Target] sont accessibles depuis n’importe quel domaine via des appels JavaScript. La seule façon d’autoriser cet accès consiste à utiliser &quot;Access-Control-Allow-Origin&quot; avec un caractère générique.
