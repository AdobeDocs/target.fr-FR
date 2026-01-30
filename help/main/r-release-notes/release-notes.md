---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f06882e99ba67f4c1fb13656b218744f8c0428e1
workflow-type: tm+mt
source-wordcount: '1862'
ht-degree: 14%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.1.2 (samedi 30 janvier 2026)

**Tableau de bord Adobe Target Insights**

Adobe Target comprend désormais un nouveau tableau de bord d’informations qui fournit une vue d’ensemble de la manière dont votre organisation utilise Target pour l’expérimentation et la personnalisation. Le tableau de bord affiche les mesures clés telles que les activités actives, les activités actives et modifiées, les activités terminées, les activités publiées et les activités de test A/B. Utilisez le sélecteur de période pour explorer les tendances sur différentes périodes, y compris une vue récapitulative pour 2025. Ce tableau de bord reste disponible en tant que moyen continu de suivre l’adoption et l’activité au fil du temps.

Voir [Tableau de bord Adobe Target Insights](/help/main/c-activities/insights-dashboard.md)

## [!DNL Target Standard/Premium] 26.1.1 (lundi 18 janvier 2026)

**Activités**

+++Afficher les détails

* **Impossible de copier l’activité - entrée utilisateur non valide.** Le problème en raison duquel les utilisateurs voient une erreur « entrée utilisateur non valide » inutile lors de la copie d’une activité a été corrigé. Auparavant, lorsqu’une activité était dupliquée, les affectations de propriétés spécifiques à l’espace de travail n’étaient pas conservées, ce qui entraînait le rejet par le serveur principal de la demande d’enregistrement, car l’activité ABctivity requiert au moins une propriété appartenant à un espace de travail autre que la propriété par défaut. Cette incohérence a déclenché une erreur générique dans l’interface utilisateur, laissant les utilisateurs sans assistance. Le correctif garantit que les affectations d’espace de travail sont correctement conservées pendant les opérations de copie, ce qui permet aux utilisateurs d’enregistrer l’activité copiée sans modification et d’éviter les erreurs de validation trompeuses. (TGT-54282)
* **Activer la colonne de l’espace de travail dans l’offre de l’éditeur web.** Cette mise à jour résout la confusion des clients causée par les offres du [!UICONTROL Default Workspace] apparaissant dans d’autres espaces de travail de l’éditeur web. Bien que ce comportement fonctionne comme prévu, les offres [!UICONTROL Default Workspace] sont intentionnellement visibles dans tous les espaces de travail, les clients ont signalé que l’interface utilisateur n’a pas clarifié l’origine de l’espace de travail, en particulier lors de la création d’activités dans un espace de travail autre que celui par défaut, tel que « Approbateurs ». Pour plus de clarté, la colonne [!UICONTROL Workspace] a été activée dans la liste des offres de l’éditeur web, ce qui permet aux utilisateurs et aux utilisatrices de distinguer facilement l’espace de travail auquel chaque offre appartient et d’éviter toute interprétation erronée des offres supplémentaires affichées. (TGT-54138)
* **Les liens avec target=« _blank » s’ouvrent dans un nouvel onglet.** Ce correctif résout un problème où les sites web créés contenant des liens avec ~target=« _blank »~ s’ouvraient dans un nouvel onglet du navigateur lorsque l’utilisateur cliquait sur celui-ci en mode [!UICONTROL Browse], ce qui perturbait l’expérience d’aperçu dans l’éditeur. Ce comportement s’est produit, car les attributs de lien natifs de la page créée n’étaient pas interceptés par le JavaScript injecté par l’extension, contrairement à l’interface utilisateur héritée où les éléments d’ancrage étaient transformés et leurs cibles remplacées pour conserver la navigation dans l’éditeur. La mise à jour garantit que les liens utilisant ~target=« _blank »~ sont désormais correctement gérés dans l’éditeur web afin qu’ils n’ouvrent plus d’onglets externes lors de la création. (TGT-54134)
* **Désélectionnez l’avertissement Propriété .** Cette mise à jour introduit un avertissement visuel pour informer clairement les utilisateurs et utilisatrices lorsqu’ils ou elles désélectionnent une propriété détectée automatiquement dans l’éditeur d’activité. Auparavant, la suppression d’une propriété détectée automatiquement n’indiquait pas que la propriété serait supprimée définitivement, ce qui pouvait entraîner une perte accidentelle de la configuration de ciblage. Le correctif ajoute une icône d’avertissement, cohérente avec le comportement dans l’interface utilisateur héritée, pour informer les utilisateurs que la désélection de la propriété la supprime de l’activité. (TGT-54121)
* **[!UICONTROL Workspaces]liste déroulante est limitée à 20 dans la section [!UICONTROL Users].** Ce correctif résout un problème en raison duquel la liste déroulante [!UICONTROL Workspaces] de la section [!UICONTROL Administration] > [!UICONTROL Users] n’affichait que 20 espaces de travail, même lorsqu’un utilisateur ou une utilisatrice avait accès à de nombreux autres espaces de travail. L’appel GraphQL sous-jacent pour `licenseGroups` était également limité à 20 résultats, ce qui entraînait l’affichage d’une liste incomplète dans l’interface utilisateur malgré l’accès de l’utilisateur à davantage d’espaces de travail dans l’organisation. La mise à jour supprime cette limite stricte. L’ensemble complet des espaces de travail disponibles est donc maintenant renvoyé et affiché correctement. (TGT-53820)
* **Correction d’un problème en raison duquel la boîte de dialogue modale des offres n’affichait pas la colonne de l’espace de travail.** Correction d’un problème en raison duquel la boîte de dialogue modale des offres n’affichait pas la colonne de l’espace de travail dans l’interface utilisateur mise à jour. Cela a semé la confusion chez les clients, car les offres de l’[!UICONTROL Default Workspace] sont apparues avec les offres de l’espace de travail sélectionné sans aucune indication de leur origine. La colonne Workspace est désormais activée afin que les clients puissent identifier clairement à quel espace de travail chaque offre appartient. (TGT-52320)

+++

**Propriétés**

+++Afficher les détails

* **La modification de l’activité ne doit pas ajouter de propriété détectée automatiquement si elle a déjà été supprimée.** Ce correctif résout un problème en raison duquel la modification d’une activité réintroduisait automatiquement une propriété détectée automatiquement et supprimée par l’utilisateur. Lors de la réouverture d’une activité pour modification, le système a restauré de manière incorrecte la propriété supprimée, ce qui a entraîné un comportement incohérent et une confusion dans le [!UICONTROL Properties List]. La mise à jour garantit qu’une fois qu’une propriété détectée automatiquement est supprimée, elle reste supprimée lors de toutes les modifications ultérieures et ne réapparaît pas, sauf si l’utilisateur la rajoute explicitement. (TGT-54182)
* **N’ajoutez pas de propriétés détectées automatiquement si elles sont déjà supprimées.** Ce correctif garantit qu’une fois qu’un utilisateur supprime manuellement une propriété détectée automatiquement d’une activité, le système ne la réintroduit plus lors d’une navigation ultérieure dans l’éditeur d’activités. Auparavant, si l’utilisateur désélectionnait une propriété détectée automatiquement, passait à l’étape [!UICONTROL Targeting], puis revenait à [!UICONTROL Experiences], l’éditeur renseignait à nouveau la propriété supprimée en fonction de la liste détectée automatiquement stockée dans la tranche d’état de l’éditeur d’activité. La logique mise à jour compare désormais les propriétés détectées automatiquement aux propriétés actuelles de la tranche ~ActivityState~ et empêche de rajouter toute propriété détectée automatiquement que l’utilisateur a déjà supprimée. Cela se traduit par un comportement cohérent entre les étapes et respecte l’intention de l’utilisateur. (TGT-54181)
* **Ajout de texte détecté automatiquement dans la liste des propriétés.** Cette amélioration met à jour le [!UICONTROL Properties List] pour étiqueter clairement toute propriété automatiquement détectée par le système. Lorsqu’une propriété détectée automatiquement est également présente dans le [!UICONTROL Properties List] visible par l’utilisateur, elle affiche désormais le texte « (Détecté automatiquement) » en regard de son nom, à l’aide de la valeur stockée à l’état ~ActivityEditorSlice~. Cela reflète le comportement de l’interface utilisateur héritée et permet aux utilisateurs de faire facilement la distinction entre les propriétés sélectionnées manuellement et les propriétés identifiées automatiquement. (TGT-54120)
* **Ajoutez des [!UICONTROL Properties] détectées automatiquement à l’état .** Cette mise à jour permet de s’assurer que l’état ~ActivityEditorSlice.ExperienceEditor~ conserve de manière cohérente une liste à jour de tous les identifiants de propriété détectés automatiquement transmis de l’éditeur web à l’onglet [!UICONTROL Experiences] d’activité. Chaque fois que l’utilisateur accède à l’onglet [!UICONTROL Experiences] , toutes les propriétés nouvellement détectées sont actualisées, tout en empêchant les doublons, ce qui garantit un suivi précis et un comportement fiable en aval. (TGT-54119)

+++

**Recommandations**

+++Afficher les détails

* **[!UICONTROL Environment]liste déroulante n’affiche que 100 résultats.** Ce correctif corrige une limitation en raison de laquelle les clients disposant de plus de 100 environnements ne pouvaient afficher que les 100 premières entrées de la liste déroulante [!UICONTROL Environment] dans [!UICONTROL Recommendations]. La requête GraphQL sous-jacente (~getEnvironmentsV2~) a été paginée avec une taille de page codée en dur de 100, ce qui fait que l’interface utilisateur n’affiche qu’une liste partielle même si d’autres pages étaient disponibles. Pour les clients qui disposent de plus de 100 environnements, ce problème entraînait des options manquantes et une expérience de sélection incomplète. La mise à jour augmente la limite afin que tous les environnements soient renvoyés et affichés, assurant ainsi une visibilité complète quel que soit le nombre d’environnements. (TGT-53903)

+++

**Rapports**

+++Afficher les détails

* **Correction d’un problème en raison duquel la flèche de [!UICONTROL Reports] n’indiquait pas clairement les colonnes extensibles.** Correction d’un problème où le tableau de reporting n’indiquait pas clairement que les colonnes supplémentaires pouvaient être développées dans l’interface utilisateur mise à jour. Une info-bulle disparaissant a été ajoutée à la flèche [!UICONTROL Reports] près des en-têtes de colonne pour aider les clients à comprendre que d’autres colonnes sont disponibles.

+++

**Vues**

+++Afficher les détails

* **Impossible de supprimer les modifications appliquées aux vues.** Ce correctif résout un problème où les utilisateurs et utilisatrices ne pouvaient pas supprimer les modifications d’une activité à moins que la modification n’ait d’abord été réappliquée à des vues supplémentaires. Lors de la modification d’une activité (par exemple, l’ID d’activité 302467), les tentatives de suppression des modifications n’ont eu aucun effet, empêchant les utilisateurs et utilisatrices de supprimer les modifications indésirables. Cependant, une fois qu’une modification a été réappliquée à l’aide de « Appliquer à d’autres vues » et affectée à un événement `Page Load`, la suppression a soudainement fonctionné comme prévu. (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Afficher les détails

* **[!UICONTROL Experience Fragment]nom a été tronqué dans la nouvelle interface utilisateur du VEC** (TGT-54312)
* **Impossible d’utiliser [!UICONTROL Advanced Settings] pour la mesure [!UICONTROL Revenue].** Ce correctif résout un problème où les utilisateurs et utilisatrices rencontraient une erreur 403 « Accès refusé » lors de la configuration de [!UICONTROL Advanced Settings] pour la mesure [!UICONTROL Revenue] dans [!UICONTROL Goals & Settings]. Le problème s’est produit lors de l’ajout d’une condition de dépendance liée à l’objectif principal ; le serveur principal nécessitait incorrectement le privilège d’éditeur même pour les utilisateurs qui disposaient déjà des autorisations suffisantes pour créer et modifier des activités. Par conséquent, l’enregistrement de l’activité a échoué malgré une configuration valide. La mise à jour corrige la vérification des autorisations afin que les utilisateurs disposant d’un accès approprié puissent ajouter avec succès des dépendances de mesures de chiffre d’affaires sans déclencher d’erreur de ressource interdite. (TGT-54092)
* **Correction d’un problème en raison duquel le bouton Ajouter ne s’appliquait pas aux images sélectionnées.** Correction d’un problème qui empêchait les clients d’ajouter certaines images lors de la sélection ou de la mise à jour d’une image dans le processus de création d’activités. Lorsque les clients recherchaient des ressources spécifiques, par exemple des images renvoyées lors de la recherche d’« ipp », le fait de cliquer sur le bouton [!UICONTROL Add] n’appliquait pas l’image sélectionnée et aucune modification n’était créée. La sélection d’autres images, telles que `Homepage-banner-1-moz.jpg`, a continué à fonctionner comme prévu. Cette mise à jour garantit que toutes les images valides peuvent être appliquées de manière cohérente dans l’interface utilisateur mise à jour. (TGT-53610)
* **Correction d’un problème en raison duquel la suppression d’une condition d’URL réinitialisait la configuration des mesures d’objectif.** Correction d’un problème en raison duquel la suppression d’une condition d’URL unique dans la mesure de [!UICONTROL Goal] entraînait la réinitialisation de l’ensemble de la configuration dans l’interface utilisateur mise à jour. Lorsque les clients et clientes tentent de supprimer une condition d’URL enregistrée sous [!UICONTROL Conversion] > [!UICONTROL Viewed a Page], le type d’objectif passe inopinément à [!UICONTROL Viewed an Mbox] et tous les paramètres précédemment configurés sont supprimés. Cette mise à jour garantit que seule la condition d’URL sélectionnée est supprimée et que tous les paramètres d’objectif restants restent intacts. (TGT-53271)
* **Correction d’un problème en raison duquel la recherche ne parcourait pas les sous-dossiers.** Correction d’un problème en raison duquel la recherche d’offres ne renvoyait pas de résultats de sous-dossiers dans l’interface utilisateur mise à jour. Les clients ne pouvaient trouver une offre que s’ils accédaient manuellement au dossier dans lequel elle était stockée, ce qui rendait le comportement de recherche incompatible avec les fonctionnalités de l’API. La recherche prend désormais en charge la recherche récursive à travers les dossiers afin que les clients puissent localiser les offres sans avoir à ouvrir chaque dossier individuellement. (TGT-51954)

+++

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

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
