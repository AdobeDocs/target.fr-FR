---
keywords: implémentation ; implémentation ; configuration ; configuration ; paramètre de page
description: Récupérez des données dans la Cible à l’aide des paramètres de page.
title: Comment puis-je obtenir des données dans la Cible à l’aide des paramètres de page ?
feature: Mise en œuvre
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: d9cfdf397fb4f4d9d1f5632b4fec828edd95444e
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 45%

---

# Paramètres de page

Les paramètres de page (également appelés &quot;paramètres de mbox&quot;) sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas stockées dans le profil du visiteur pour une utilisation ultérieure.

Les paramètres de page sont utiles pour envoyer des données de page à la Cible qui n’ont pas besoin d’être stockées avec le profil visiteur pour un futur ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique.

## Format

Les paramètres de page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne. Les noms et les valeurs de paramètre sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

### Exemples

* `page=productPage`

* `categoryId=homeLoans`

## Exemples d’utilisation

* **Pages** de produits : Envoyez des informations sur le produit spécifique consulté (cette méthode correspond au fonctionnement de Recommendations).
* **Détails** de la commande : Envoyer l’ID de commande, orderTotal, etc., pour la collecte de commandes
* **Affinité catégorielle** : envoyez les informations de consultation de catégorie à Target afin de développer la connaissance de l’affinité de l’utilisateur pour des catégories de site particulières.
* **Données tierces** : envoyez des informations provenant de sources de données tierces, telles que les fournisseurs de ciblage météo, les fournisseurs de données de compte (par exemple, DemandBase), les fournisseurs de données démographiques (par exemple, Experian), etc.

## Avantages de la méthode

Les données sont envoyées à la Cible en temps réel et peuvent être utilisées sur le même appel serveur pour les données sur lesquelles elles sont envoyées.

## Avertissements

* Nécessite une mise à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).
* Si les données doivent être utilisées pour le ciblage lors d’un appel de page/serveur suivant, elles doivent être traduites en script de profil.
* Les caractères contenus dans les chaînes de requête doivent obligatoirement respecter les [standards de l’Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Outre les caractères mentionnés sur le site IETF, la Cible autorise les caractères suivants dans les chaînes de requête :

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   Le reste doit être encodé en URL. La norme spécifie le format suivant ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), comme illustré ci-dessous :

   ![](assets/ietf1.png)

   Ou la liste complète, pour plus de simplicité :

   ![](assets/ietf2.png)

## Exemples de code

targetPageParamsAll (ajoute les paramètres à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (ajoute les paramètres à la mbox globale sur la page) :

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Paramètres dans le code mboxCreate :

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## Liens vers les informations pertinentes

Recommandations : [implémentation selon le type de page](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmation de commande : [suivi des conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Affinité catégorielle : [affinité catégorielle](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
