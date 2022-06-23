---
keywords: implémenter;implémentation;configuration;configurer;paramètres de page
description: Obtenir des données dans [!DNL Target] à l’aide des paramètres de page.
title: Comment obtenir des données dans [!DNL Target] Utilisation des paramètres de page ?
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 44%

---

# Paramètres de page

Les paramètres de page (également appelés &quot;paramètres de mbox&quot;) sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas stockées dans le profil du visiteur pour une utilisation ultérieure.

Les paramètres de page sont utiles pour envoyer à Target des données de page qui n’ont pas besoin d’être stockées avec le profil du visiteur pour une utilisation ultérieure dans le cadre du ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique.

## Format

Les paramètres de page sont transmis à Target via un appel au serveur sous la forme d’une paire nom/valeur de chaîne. Les noms et les valeurs de paramètre sont personnalisables (cependant, certains noms sont réservés à des utilisations spécifiques).

### Exemples

* `page=productPage`

* `categoryId=homeLoans`

## Exemples de cas d’utilisation

* **Pages de produit**: Envoyez des informations sur le produit spécifique consulté (cette méthode est la manière dont Recommendations fonctionne).
* **Détails de la commande**: Envoyez l’identifiant de commande, orderTotal, etc., pour la collecte de commande.
* **Affinité catégorielle** : envoyez les informations de consultation de catégorie à Target afin de développer la connaissance de l’affinité de l’utilisateur pour des catégories de site particulières.
* **Données tierces** : envoyez des informations provenant de sources de données tierces, telles que les fournisseurs de ciblage météo, les fournisseurs de données de compte (par exemple, DemandBase), les fournisseurs de données démographiques (par exemple, Experian), etc.

## Avantages de la méthode

Les données sont envoyées à Target en temps réel et peuvent être utilisées sur le même appel serveur que les données sur lesquelles elles arrivent.

## Avertissements

* Nécessite une mise à jour du code de page (directement ou par l’intermédiaire d’un système de gestion des balises).
* Si les données doivent être utilisées pour le ciblage lors d’un appel de page/serveur ultérieur, elles doivent être traduites en script de profil.
* Les caractères contenus dans les chaînes de requête doivent obligatoirement respecter les [standards de l’Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Outre les caractères mentionnés sur le site de l’IETF, Target autorise les caractères suivants dans les chaînes de requête :

   ```< > # % " { } | \ ^ [ ] ` ```

   Le reste doit être encodé en URL. La norme spécifie le format suivant ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), comme illustré ci-dessous :

   ![](assets/ietf1.png)

   Ou la liste complète, pour plus de simplicité :

   ![](assets/ietf2.png)

## Exemples de code

targetPageParamsAll (ajoute les paramètres à tous les appels de mbox sur la page) :

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (ajoute les paramètres à la mbox globale sur la page) :

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

## Liens vers les informations pertinentes

Recommandations : [implémentation selon le type de page](https://developer.adobe.com/target/implement/recommendations/)

Confirmation de commande : [suivi des conversions](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

Affinité catégorielle : [affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
