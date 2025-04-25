---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 24%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 25.4.5 (25 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui entraînait des incohérences dans les listes d’audience entre la page des paramètres de [!UICONTROL Activity] et la page d’aperçu des [!UICONTROL Reporting]. (TGT-52203)
* Correction d’un problème qui empêchait l’ajout d’une nouvelle page à une activité en raison d’une erreur d’entrée utilisateur non valide. (TGT-52263)
* Correction d’un problème en raison duquel les `OptionLocalIDs` étaient incorrectement incrémentées lorsque l’option restait inchangée. (TGT-52187)
* Correction d’un problème en raison duquel `location` et `OptionLocalIDs` s’incrémentaient incorrectement lorsque l’option restait inchangée. (TGT-52188)
* Correction d’un problème en raison duquel l’emplacement sur la page [!UICONTROL Overview] de l’activité était incorrect. (TGT-52182)
* Correction d’un problème où un avertissement de sélecteur non valide ne s’affichait pas pour un emplacement non valide. (TGT-52110)
* Correction d’un problème en raison duquel les fichiers de création de rapports téléchargés affichaient correctement les données présentes dans l’interface utilisateur de création de rapports. (TGT-52068)
* Correction d’un problème en raison duquel les opérations par lots n’échouaient pas après l’ajout de règles de diffusion de page. (TGT-52097)
* Correction d’un problème en raison duquel [!DNL Target] supprimait tous les paramètres de requête de l’URL du site web. (TGT-52100)
* Correction d’une erreur de console qui empêchait les clients de créer des activités dans l’interface utilisateur de [!DNL Target] héritée et mise à jour. (TGT-52181)
* Correction d’un problème qui empêchait les clients et clientes d’ajouter de nouvelles pages, provoquant une erreur d’entrée utilisateur non valide. (TGT-52258)
* Correction d’un problème en raison duquel les modifications disparaissaient après l’ajout de pages supplémentaires, puis en revenant à l’onglet [!UICONTROL Experiences] . (TGT-52264)
* Correction d’un problème qui empêchait les clients et clientes de modifier l’audience dans une activité [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Correction d’une erreur qui empêchait la modification d’une activité XT en raison d’une règle d’IU non prise en charge. (TGT-52273)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) en raison duquel les chemins de navigation n’étaient pas toujours affichés en bas de l’éditeur, ce qui entraînait des difficultés pour sélectionner précisément les éléments. (TGT-52169)
* Correction d’un problème en raison duquel la liste déroulante [!UICONTROL Audience] n’affichait pas toutes les audiences en raison de la pagination. (TGT-52204)
* Correction d’un problème qui entraînait un message d’entrée utilisateur non valide lors de l’ajout de nouvelles offres dans les activités [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Correction d’un problème en raison duquel [!UICONTROL Analytics for Target] (A4T) était incorrectement sélectionné comme source de création de rapports, même si le client n’avait pas accès à A4T. (TGT-52226)
* Correction d’un problème qui empêchait l’enregistrement d’une activité avec la mesure URL [!UICONTROL View a Page]. (TGT-52260)
* Correction d’un problème qui empêchait les clients de sélectionner des espaces de travail lors de la création d’offres dans une activité. (TGT-52289)
* Correction d’un problème qui empêchait les clients de créer des activités dans tous les espaces de travail. (Tgt-52218)
* Correction d’un problème où les modifications d’une expérience s’affichaient incorrectement lors du passage à une autre expérience. (TGT-52184)
* Correction d’un problème en raison duquel l’offre par défaut s’affichait incorrectement dans l’interface utilisateur de [!DNL Target] lors de l’ouverture de l’activité. (TGT-52198)

## Mise à jour des autorisations Target (22 avril 2025)

Cette future mise à jour améliore le contrôle organisationnel sur les configurations d’instance de [!DNL Target], empêchant les mises à jour accidentelles qui pourraient affecter la diffusion des activités entre différentes équipes de test et de personnalisation.

À compter du 22 avril 2025, seuls les administrateurs [!UICONTROL Product] et [!UICONTROL Solutions] pourront mettre à jour les paramètres des sections [!UICONTROL Administration], quels que soient leurs rôles dans les espaces de travail [!DNL Target]. Les utilisateurs ne disposant pas de cette autorisation auront un accès en lecture seule aux sections [!UICONTROL Administration].

Pour plus d’informations, voir [ Administration de Target ](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (17 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout d’un message d’erreur pour guider les utilisateurs et utilisatrices dans la résolution des options en double dans une activité. (TGT-51927)
* Correction d’un problème en raison duquel les sélecteurs `ClickTrack` n’étaient pas supprimés lors de la suppression de pages ou d’expériences avec des offres de redirection. (TGT-51952)
* Correction d’un problème lié à l’autorisation de sélecteurs de `ClickTrack` vides. [!DNL Target] nécessite désormais que le champ de sélecteur ne soit pas vide. (TGT-52107)
* Correction d’un problème qui autorisait incorrectement les mesures avec des noms en double. Les mesures nécessitent désormais des noms uniques. (TGT-52201)
* Correction d’un problème en raison duquel les définitions d’audience n’étaient pas visibles lors de la modification du ciblage au niveau des offres dans les activités [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Correction d’un problème qui empêchait les clients disposant de droits d’[!UICONTROL Editor] d’enregistrer les activités. (TGT-52227)
* `OptionLocalIDs` n’incrémente plus incorrectement lorsque l’option reste inchangée. (TGT-52139)
* Correction d’un problème qui provoquait un message « `optionLocalIds` non valide » lors de la création d’une activité. (TGT-52154)
* Des écarts ont été corrigés entre les `OptionLocalIDs` définis pour une activité et ceux utilisés pour définir les expériences. (TGT-52215)
* Correction d’un problème qui provoquait un échec de validation lors de la tentative de création d’une activité A/B. (TGT-51923)

## [!DNL Target Standard/Premium] 25.4.3 (11 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’une erreur qui empêchait les clients d’ouvrir le pop-up d’informations sur l’audience pour certaines activités [!UICONTROL Experience Targeting] (XT). (TGT-52049)
* Correction d’un problème en raison duquel le paramètre d’audience revenait à « [!UICONTROL All Visitors] » suite aux modifications apportées au [!UICONTROL Visual Experience Composer] (VEC). (TGT-52132)
* Correction d’un problème où les ajustements d’audience n’étaient pas affichés pour des activités spécifiques (TGT-52057)
* Correction d’un problème qui empêchait les clients d’insérer un [!UICONTROL Experience Fragment] dans l’espace de travail par défaut. (TGT-52073)
* Correction d’un problème en raison duquel une offre affichait « Contenu introuvable » et ne s’affichait pas sur la page [!UICONTROL Offers] pour une activité [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Ajout de la possibilité d’autoriser les audiences en double dans une activité. (TGT-51200)
* Correction d’un problème en raison duquel un nom de mbox incorrect s’affichait sur la page [!UICONTROL Goals & Settings] d’une activité XT après modification. (TGT-52026)
* Correction d’un problème en raison duquel les `defaultContent` s’affichaient dans les options alors qu’elles n’étaient pas dans les `experiences/optionLocations`. (TGT-52036)
* Correction d’un problème pour s’assurer que les chaînes vides ne sont pas converties en valeurs nulles. (TGT-52037)
* Correction d’un problème en raison duquel les clients devaient reconfigurer le [!UICONTROL Optimization Goal] dans [!UICONTROL Reporting Settings] sur la page [!UICONTROL Goals & Settings] après les modifications. (TGT-52071)
* Correction d’un problème en raison duquel une activité sans règles de diffusion de page affichait plusieurs règles sur la page [!UICONTROL Overview]. (TGT-52084)
* Ajout d’un message d’erreur pour les utilisateurs qui tentent d’enregistrer une offre avec des caractères en dehors du plan multilingue de base, tels que des émoticônes. (TGT-52105)
* Correction d’un problème en raison duquel l’ouverture d’une activité déclenchait le message d’erreur : « Cette activité utilise une ou plusieurs audiences supprimées à la source ». (TGT-52120)
* Correction d’un problème en raison duquel les mesures ClickTrack n’étaient pas affichées dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) lors de la modification. (TGT-52152)
* Correction d’un problème en raison duquel une URL avec un paramètre de requête comme emplacement de l’activité n’affichait pas le paramètre de requête sur la page de [!UICONTROL Overview] de l’activité. (TGT-51635)
* Correction d’un problème qui empêchait l’affichage de l’URL d’expérience entière dans [!UICONTROL Browse mode] dans le [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Correction d’un problème en raison duquel la modification d’une activité entraînait l’ajout d’un caractère « / » à la fin de l’URL par la diffusion de la page, la rendant non valide. (TGT-52114)
* Correction d’un problème en raison duquel le lien [!UICONTROL Activity QA] dans le [!UICONTROL Form-Based Experience Composer] était incorrectement redirigé vers la page d’accueil [!DNL Adobe Experience Cloud]. (TGT-52055)
* Correction d’un problème en raison duquel les pages supplémentaires ajoutées à l’activité [!UICONTROL A/B Test] n’étaient pas conservées après l’enregistrement et la réouverture. (TGT-51994)
* Correction d’un problème qui empêchait les clients de supprimer des styles dans la section Style intégré . (TGT-52070)
* Restauration de l’accès aux [cartes de définition d’audience](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) dans la boîte de dialogue [!UICONTROL Activity QA], comme dans l’interface utilisateur héritée. (TGT-52056)
* L’interface utilisateur mise à jour n’a pas enregistré de pages ou d’audiences sans modifications. Si les clients ajoutaient de nouvelles pages ou audiences à une activité mais ne leur apportaient aucune modification, [!DNL Target] ignoraient les audiences non modifiées lors de l’enregistrement. Des notifications ont été ajoutées aux endroits appropriés pour informer les utilisateurs de ce comportement. (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.1 (2 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les audiences d’expérience disparaissaient des activités . (TGT-52003)
* Correction d’un problème qui provoquait des éléments inattendus lors de la diffusion. (TGT-52011)
* Correction d’un problème qui empêchait les clients et clientes d’afficher l’audience dans le graphique de ciblage sur la page [!UICONTROL r] vue et lors de la modification de l’activité. (TGT-52050)
* Correction d’un problème qui empêchait les clients de réorganiser les expériences par ordre de priorité dans les activités [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Correction d’un problème qui provoquait un rendu incorrect lors de l’annulation de modifications de style de texte. (TGT-51876)
* Correction d’un problème en raison duquel, lors de la modification d’une offre de redirection, [!DNL Target] supprime également tous les sélecteurs de [!UICONTROL ClickTrack] associés à cette offre. (TGT-51936)
* Correction d’un problème en raison duquel [!DNL Target] enregistrait incorrectement le sélecteur lors de l’annulation du [!UICONTROL ClickTrack]. (TGT-51937)
* Correction d’un problème qui déclenchait une erreur de nom non valide après l’ouverture et la fermeture du sélecteur de mbox sur la page [!UICONTROL Goals & Settings] sans apporter de modifications. (TGT-51983)
* Correction d’un problème qui bloquait la modification des offres ad hoc créées dans l’interface utilisateur de [!DNL Target] héritée. (TGT-51984)
* Correction d’un problème qui bloquait les activités de modification comportant des offres ad hoc contenant du code personnalisé. (TGT-51995)
* Correction d’un problème en raison duquel les règles d’exclusion s’affichaient en tant que règles d’inclusion lors de la modification des définitions d’audience combinées. (TGT-51999)
* Correction d’un problème qui empêchait l’affichage correct du code personnalisé lors de l’édition de l’expérience. (TGT-52005)
* Correction d’un problème qui rendait l’option [!UICONTROL Insert Before] indisponible pour insérer du contenu avant la barre de navigation. (TGT-52031)
* Correction d’un problème qui empêchait la mise en surbrillance correcte de l’expérience par défaut dans les rapports. (TGT-51716)
* Correction d’un problème qui déclenchait un message `default message [Invalid optionLocalIds: xx]]` lors de la création d’une activité. (TGT-52038)

## at.js version 2.11.8 (31 mars 2025)

* Résolution d’une vulnérabilité identifiée par CodeQL dans la validation du suffixe de chaîne pour empêcher les cas Edge lors des opérations de redimensionnement et de déplacement. (TNT-51516)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes De Mise À Jour De Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
