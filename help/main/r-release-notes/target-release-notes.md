---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la version à venir ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 83a7fb03dcf334cb82eb507d2803e955a655b40a
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 23%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 5er mai 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.5.1 (version échelonnée) ; 10-12 mai 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **10 mai**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **11 mai**: Région Asie-Pacifique (APAC)
* **12 mai**: Région de l&#39;Amérique du Nord

Cette version contient les améliorations et correctifs suivants :

* Correction d’un problème qui provoquait une erreur JavaScript et empêchait certains clients d’accéder aux détails de l’activité pour certains [!UICONTROL Automated Personalization] (AP). (TGT-43526)
* Correction d’un problème qui empêchait certains clients d’ajouter (ou de modifier) une offre spécifique à une activité AP. (TGT-43503)
* Correction d’un problème dans la variable [!DNL Target] Interface utilisateur qui affiche le message d’erreur suivant : &quot;Votre mbox globale peut ne pas être synchronisée. Réessayez de lʼenregistrer ». Ce problème était un problème de l’interface utilisateur et n’avait aucune incidence sur les mises en oeuvre des clients. (TGT-43475)
* Correction d’un problème qui empêchait un client de modifier des perfectionnements et des audiences au niveau de l’expérience pour une activité si les perfectionnements et les audiences étaient créés avant la nouvelle [!UICONTROL Audiences] L’interface utilisateur a été déployée. (TGT-43433)
* Correction d’un problème en raison duquel les clients pouvaient sélectionner des doublons. [!DNL Adobe Audience Manager] (AAM) audiences lors de la modification des audiences pour une activité de rapport. (TGT-43430)
* Correction d’un problème qui empêchait les clients de créer des audiences en double, mais dans différents espaces de travail. (TGT-43423)
* Correction d’un problème qui empêchait les clients de supprimer les emplacements où des offres ad hoc étaient créées dans les activités créées dans la variable [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-43315)
* Correction d’un problème qui empêchait les clients d’accéder aux offres de code après avoir cliqué sur des offres d’image, puis actualisé l’interface utilisateur. (TGT-43566)
* Assurez-vous que la liste des mesures disponibles dans la variable [!DNL Target] Interface utilisateur lors de la création d’activités qui utilisent [!DNL Analytics for Target] (A4T) affiche uniquement les mesures qui ont été collectées par [!DNL Adobe Analytics]. (TGT-43294)
* Correction d’un problème qui provoquait parfois [!UICONTROL Configuration] demandes de page échouées. Par exemple, en modifiant le[!UICONTROL Solution Experience Cloud de création de rapports]&quot; à partir de &quot;[!UICONTROL Analytics]&quot; à &quot;[!UICONTROL Cible]&quot; ou &quot;[!UICONTROL Sélection par activité]&quot;. (TGT-43272)
* Correction d’un problème en raison duquel les modifications apportées aux scripts de profil n’étaient pas mises à jour correctement. (TGT-43249)
* Correction d’un problème qui provoquait l’erreur suivante lors de la tentative de déplacement d’une audience vers un autre espace de travail : &quot;Nous ne pouvons pas terminer votre demande. Contactez le service à la clientèle Adobe si le problème persiste.&quot; (TGT-43212)
* Correction d’une erreur qui provoquait une erreur lors du clonage des modifications de code personnalisé pour les pages d’application d’une seule page (SPA). (TGT-43137)
* Modification de la manière dont la mesure &quot;pages vues&quot; est gérée dans SPA. À la place de l’URL de page qui s’affiche dans la variable [!DNL Target] L’interface utilisateur affiche désormais la &quot;vue&quot;. (TGT-41200)
* Correction d’un problème en raison duquel la promotion d’origine était affectée après la duplication d’une expérience, puis la modification de la promotion. (TGT-41775)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir des produits à [!DNL Target] et autres [!DNL Adobe Experience Cloud] solutions, inscrivez-vous au [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
