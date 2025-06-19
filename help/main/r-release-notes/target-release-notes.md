---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 29%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 19 juin 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.3 (samedi 20 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout de l’option [!UICONTROL Rearrange] à l’interface utilisateur du [!UICONTROL Visual Experience Composer] mis à jour pour s’aligner sur les fonctionnalités disponibles dans l’ancien compositeur d’expérience visuelle. (TGT-46957)
* Correction d’un problème en raison duquel la copie d’une activité d’un espace de travail à un autre déclenchait des erreurs telles que « ne doit pas être nul » ou « Un problème est survenu ». (TGT-52474)
* Correction d’un problème en raison duquel les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes] n’étaient pas générés pour certaines activités. (TNT-52904)
* Correction d’un problème dans le VEC mis à jour en raison duquel la gestion de contenu par défaut dans les activités [!UICONTROL Automated Personalization] (AP) ne correspondait pas à l’interface utilisateur héritée. Le système ajoute désormais automatiquement un `optionGroup` par défaut nommé « Contenu par défaut » avec des `optionGroupLocalId = 0` lorsqu’aucun groupe n’est explicitement ajouté. Ce groupe comprend l’option par défaut (par exemple, `optionLocalId: 0`). Si le contenu par défaut est supprimé, le groupe d&#39;options correspondant est également supprimé. (TGT-52651)
* Correction d’un problème dans les activités [!UICONTROL Multivariate Test] (MVT) où la réutilisation d’un `experienceLocalId` d’expériences supprimées précédemment était incorrectement interdite. (TNT-52672)
* Correction d’un problème en raison duquel les URL des emplacements d’activité n’affichaient pas les paramètres de requête en raison de caractères non valides, tels que des barres obliques (/). (TNT52845)
* Amélioration du message d’erreur de validation pour les mises à jour d’activité [!DNL A/B Test] via l’API principale. Lorsque des noms d’emplacement en double sont présents, le message indique désormais clairement : « Les noms en double ne sont pas autorisés » pour `locations.selectors`. (TGT-52589)
* Correction d’une erreur qui se produisait lors de la mise à jour d’une activité Live [!UICONTROL Recommendations] en raison d’une propriété non reconnue dans la payload de la requête. Le système gère désormais correctement le fichier JSON « non valide ». Erreur « Nom de propriété non reconnu ». (TNT52723)
* Correction d’une erreur de validation du serveur principal qui provoquait une erreur « 400 Bad Request » lors de l’enregistrement d’une activité [!UICONTROL Recommendations]. (TNT-52716)
* Correction d’un problème dans l’[!UICONTROL Form-Based Experience Composer] en raison duquel le survol d’une mbox avec des caractères spéciaux dans la liste déroulante [!UICONTROL Location] entraînait le vide de l’éditeur et le déclenchement d’un événement « Échec de l’exécution de querySelector » sur « Élément ». s’affiche. (TGT-52717)
* Amélioration de la précision de l’état du flux avec un nouvel indicateur « PARTIALLY_IMPORTED ». Auparavant, les flux étaient marqués comme « succès » même lorsque toutes les lignes d’un fichier n’étaient pas importées, ce qui était trompeur.
* Correction d’une erreur en raison de laquelle, après la migration vers AP V2, certains appels API à `/admin/rest/ui/v1/campaigns` renvoyaient des erreurs côté client (HTTP 4xx). (TGT-52721)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
