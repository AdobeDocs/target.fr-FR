---
keywords: implémenter;implémentation;configuration;configurer;paramètre de page
description: Obtenir des données dans [!DNL Target] à l’aide des attributs de profil internes à la page.
title: Comment obtenir des données dans [!DNL Target] Utilisation des attributs de profil internes à la page ?
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 57%

---

# Attributs de profil sur la page

Attributs de profil internes à la page dans [!DNL Adobe Target] (également appelées &quot;attributs de profil internes à la mbox&quot;) sont des paires nom/valeur transmises directement par le biais du code de page qui sont stockées dans le profil du visiteur en vue d’une utilisation ultérieure.

Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs.

## Format

Les attributs de profil internes à la page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne précédée du préfixe « profile » .

Les noms et les valeurs d’attribut sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

### Exemples

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## Exemples de cas d’utilisation

* **Informations de connexion** : partagez les données non personnelles avec Target selon la connexion de l’utilisateur. Il peut s’agir de l’état de l’adhésion, de l’historique des commandes, etc.
* **Informations de boutique** : déterminez quelle est la boutique de prédilection de cet utilisateur.
* **Interactions précédentes** : effectuez le suivi des activités précédentes de l’utilisateur sur le site afin d’informer la personnalisation ultérieure.

## Avantages de la méthode

Les données sont envoyées à Target en temps réel et peuvent être utilisées sur le même appel de serveur que celui sur lequel les données entrent.

## Avertissements

Nécessite des mises à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).

Les attributs et valeurs sont visibles dans les appels au serveur, ce qui signifie qu’un visiteur peut les voir. Si vous partagez des informations telles que des plages de crédits ou d’autres informations potentiellement privées, cette méthode peut ne pas être la meilleure approche.

## Exemples de code

targetPageParamsAll (ajoute les attributs à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (ajoute les attributs à la mbox globale sur la page) :

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attributs dans le code mboxCreate :

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## Liens vers les informations pertinentes

[Attributs de profil](/help/main/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Profil du visiteur](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
