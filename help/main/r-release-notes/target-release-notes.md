---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la version à venir ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dd8c0f3781625985f53aeb3b659fb4498a3e10e8
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 37%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 11 avril 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.3.1 (version échelonnée, date à déterminer)

Cette version contient les modifications et améliorations suivantes :

* Correction d’un problème en raison duquel les modifications apportées aux scripts de profil revenaient au script original non modifié après l’édition, l’activation et la désactivation du script. Le script de profil reste à l’état modifié. (TGT-43249)
* Correction d’un problème qui provoquait le message d’erreur suivant dans la variable [!DNL Target] Interface utilisateur lors du déplacement d’une audience utilisée dans une activité avec l’état &quot;version préliminaire&quot; : &quot;Nous ne pouvons pas terminer votre demande. Veuillez contacter le service à la clientèle Adobe si le problème persiste.&quot; (TGT-43212)
* Correction d’un problème en raison duquel la variable [!UICONTROL Inclure] et [!UICONTROL Exclure] options à désactiver pour les audiences combinées lors de la modification d’une activité. (TGT-43422)
* Correction d’un problème qui empêchait certains clients d’afficher la liste des audiences disponibles lors de la modification d’une activité. (TGT-43404)
* Correction d’un problème qui empêchait certains clients de supprimer une adresse IP du[!UICONTROL IP à exclure de [!DNL Target] données de reporting]&quot; list in [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Correction d’un problème qui empêchait l’utilisation de nombres négatifs dans le critère d’audience qui vérifiaient que toute variable était &quot;supérieure ou égale à&quot;, &quot;supérieure ou égale à&quot;, &quot;inférieure à&quot; ou &quot;inférieure ou égale à&quot;. (TGT-43367)
* Correction d’un problème qui empêchait les clients d’afficher la variable [!UICONTROL Détails de l’audience] lors de la création d’audiences combinées. (TGT-43303)
* Correction d’un problème en raison duquel la variable [!DNL Target] Interface utilisateur ou nouvelle [!UICONTROL Audiences] pour que certains clients expirent prématurément. (TGT-42590 et TGT-43273)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
