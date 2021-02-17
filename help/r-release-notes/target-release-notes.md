---
keywords: notes de mise à jour ; versions ; mises à jour ; versions futures ; améliorations ; nouvelles fonctionnalités ; correctifs ; mises à jour ; pré-version
description: Découvrez les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version d’Adobe Target, y compris les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
translation-type: tm+mt
source-git-commit: 3e4b05553100efff697beec0824108f28d80ccb2
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 25%

---


# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 17 février 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (9 et 10 mars 2021)

Cette version de maintenance comprend les améliorations, correctifs et modifications suivants.

Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

* Augmentation de la taille d’offre autorisée :

   | Type | Limite précédente | Nouvelle limite |
   | --- | --- | --- |
   | HTML | 256 Ko | 1024 Ko |
   | Offres visuelles de l’interface utilisateur de Cible | 64 Ko | 1 024 Ko pour chaque expérience |
   | Via l’API | 512 Ko | 1024 Ko |

* Correction d’un problème en raison duquel la dépendance actuelle ne s’affichait pas lorsque les clients cliquaient sur [!UICONTROL Modifier la dépendance] sur une page [!UICONTROL Objectifs et paramètres] d’une activité. (TGT-39340)
* Correction d’un problème lors de l’actualisation de la [!UICONTROL bibliothèque d’Audiences] d’un espace de travail. Avant l’actualisation, les audiences de l’espace de travail actuellement sélectionné s’affichaient. Après l’actualisation, l’[!UICONTROL espace de travail par défaut] et ses audiences s’affichaient. L’espace de travail actuel et ses audiences persistent après l’actualisation. (TGT-38871)
* Correction d’un problème lors de la copie d’une activité [!UICONTROL Recommendations] et de la modification ultérieure de l’activité d’origine en modifiant sa séquence de critères. La modification de la séquence de critères dans l’activité d’origine a également été incorrectement appliquée à l’activité copiée. (TGT-39155)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
