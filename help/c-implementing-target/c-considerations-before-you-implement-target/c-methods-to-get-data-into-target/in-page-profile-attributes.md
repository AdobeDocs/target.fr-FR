---
keywords: implémentation ; implémentation ; configuration ; configuration ; paramètre de page
description: Récupérez des données dans  [!DNL Target] à l’aide d’attributs de profil internes à la page.
title: Comment puis-je obtenir des données dans  [!DNL Target] l’utilisation des attributs de Profil de la page ?
feature: Mise en œuvre
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 56%

---

# Attributs de profil sur la page

Les attributs de profil internes à la page dans [!DNL Adobe Target] (également appelés &quot;attributs de profil internes à la mbox&quot;) sont des paires nom/valeur transmises directement par le code de page qui sont stockées dans le profil du visiteur en vue d’une utilisation ultérieure.

Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs.

## Format

Les attributs de profil internes à la page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne précédée du préfixe « profile » .

Les noms et les valeurs d’attribut sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

### Exemples

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## Exemples d’utilisation

* **Informations de connexion** : partagez les données non personnelles avec Target selon la connexion de l’utilisateur. Il peut s’agir de l’état d’adhésion, de l’historique des commandes ou de plusieurs autres données.
* **Informations de boutique** : déterminez quelle est la boutique de prédilection de cet utilisateur.
* **Interactions précédentes** : effectuez le suivi des activités précédentes de l’utilisateur sur le site afin d’informer la personnalisation ultérieure.

## Avantages de la méthode

Les données sont envoyées à la Cible en temps réel et peuvent être utilisées sur le même appel de serveur sur lequel elles sont envoyées.

## Avertissements

Nécessite des mises à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).

Les attributs et valeurs sont visibles dans les appels au serveur, ce qui signifie qu’un visiteur peut les voir. Si vous partagez des informations telles que des plages de crédit ou d&#39;autres informations potentiellement privées, cette méthode peut ne pas être la meilleure approche.

## Exemples de code

targetPageParamsAll (ajoute les attributs à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (ajoute les attributs à la mbox globale sur la page) :

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attributs dans le code mboxCreate :

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## Liens vers les informations pertinentes

[Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Profil du visiteur](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
