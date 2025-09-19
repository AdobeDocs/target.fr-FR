---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 14%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe]fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

+++Afficher les détails
L’équipe [!DNL Target] propose une fonctionnalité temporaire qui vous permet de basculer entre l’interface utilisateur de [!DNL Target] mise à jour et la version héritée à l’aide d’un bouton bascule. Cette option n’est disponible que pendant la phase finale du déploiement de l’interface utilisateur.

![Basculement de la version de l’interface utilisateur de Target](/help/main/r-release-notes/assets/toggle.png)

Une fois le déploiement terminé, le bouton (bascule) est supprimé et tous les utilisateurs passent définitivement à l’interface utilisateur mise à jour. [!DNL Adobe] recommande de planifier l’avenir, car cette fonctionnalité sera bientôt supprimée.

#### Chronologie de l’obsolescence

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, l’équipe [!DNL Target] a ajusté le calendrier d’abandon :

* **17 juin 2025** : toutes les organisations IMS ont été activées pour l’interface utilisateur [!DNL Target] mise à jour, pour des utilisateurs spécifiques ou à l’échelle de l’organisation, afin de commencer à tester la nouvelle expérience.

* **30 juin 2025** : l’[updated [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md) est devenue l’expérience par défaut pour toutes les organisations IMS qui ont activé le bouton (bascule) de version de l’interface utilisateur.

   * Les clients qui consultent actuellement l’interface utilisateur héritée, par défaut, voient désormais l’interface utilisateur mise à jour lors de la connexion.
   * Le bouton (bascule) de version de l’interface utilisateur reste disponible jusqu’à la fin juillet, ce qui permet aux utilisateurs et utilisatrices de revenir en arrière si nécessaire.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recommande vivement d’utiliser l’interface utilisateur de [!DNL Target] mise à jour. Revenez à l’interface utilisateur héritée uniquement si un problème de blocage se produit, en raison des [limitations du comportement du bouton (bascule)](#limitations).

* **du 15 au 30 juillet 2025** : le bouton (bascule) de version de l’interface utilisateur sera désactivé définitivement par phases. Les organisations IMS affectées ne peuvent plus revenir à l’interface utilisateur héritée.

   * Les exceptions sont examinées au cas par cas.
   * Les délais d’abandon du bouton (bascule) ne sont accordés que brièvement (quelques jours) pendant que les problèmes de blocage sont résolus.

Contactez l’[Assistance clientèle d’Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) si vous avez des inquiétudes ou si vous prévoyez des problèmes au cours de cette transition.

#### Limites du comportement du bouton (bascule) de l’interface utilisateur {#limitations}

Les informations suivantes décrivent les limites que vous devez connaître lorsque vous choisissez d’utiliser le bouton (bascule) de version :

* **Visibilité des nouvelles activités** : les activités créées dans l’interface utilisateur mise à jour ne seront pas visibles si vous revenez à l’interface utilisateur héritée.
* **Modification d’activités existantes** : les modifications apportées à des activités existantes (créées à l’origine dans l’interface utilisateur héritée) lors de l’utilisation de l’interface utilisateur mise à jour sont publiées sur votre site web. Toutefois, ces mises à jour ne sont pas visibles dans l’interface utilisateur héritée si vous revenez en arrière ; seules les dernières mises à jour effectuées à partir de l’interface utilisateur héritée y apparaissent.
* **Cohérence des détails de l’activité** : les modifications les plus récentes, quelle que soit l’interface utilisateur que vous utilisez, sont répercutées sur votre site web actif. Cependant, l’interface utilisateur héritée n’affiche que les dernières modifications apportées à partir de cette version. Cette situation peut prêter à confusion si les activités modifiées dans l’interface utilisateur mise à jour ont un aspect différent de celui de l’interface utilisateur héritée.

#### Plus de ressources pour en savoir plus sur l’interface utilisateur mise à jour

* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le nouveau [!UICONTROL Visual Experience Composer] (VEC), y compris les modifications de navigation, les emplacements de fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.
* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour [!UICONTROL Activities], [!UICONTROL Recommendations] et le [!UICONTROL Visual Experience Composer] (VEC).
* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour le [!UICONTROL Offers Library].
* [Présentation de l [!DNL Target] interface utilisateur ](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.
* [[!UICONTROL Visual Experience Composer] modifications ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.
* [[!UICONTROL Visual Experience Composer] options ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.

+++

## Mises à jour des flux de données (19 septembre 2025)

L’identifiant du flux de données et la combinaison de sandbox doivent être uniques pour les connexions de destination [!DNL Adobe Target].

Mise à jour de la logique de validation pour [!DNL Target] connexions de destination afin d’imposer que la combinaison de l’identifiant du flux de données et du nom du sandbox doit être unique au sein d’une organisation IMS. Cela signifie :

* La même paire identifiant de flux de données + nom de sandbox ne peut pas être réutilisée sur plusieurs connexions de destination [!DNL Target].
* Un même identifiant de flux de données peut être utilisé pour différentes connexions uniquement si elles sont configurées dans différents sandbox.
* Cette règle s’applique à toutes les sélections de flux de données, y compris lorsque l’option « Aucun » est sélectionnée.

Cette mise à jour garantit une configuration cohérente et empêche les conflits entre les environnements multi-sandbox. Pour plus d’informations, voir [Connexion Adobe Target](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} dans le guide *Destinations Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 septembre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Experience Fragments]**

+++Afficher les détails
* **Amélioration de l’attribution des utilisateurs pour les offres [!UICONTROL AEM Experience Fragment].** Correction d’un problème dans le VEC en raison duquel le champ « [!UICONTROL Last updated] » pour les offres de [!UICONTROL AEM Experience Fragment] (XF) affichait incorrectement un ID de code au lieu du nom d’utilisateur. Cette incohérence s’est produite lors de la sélection des offres dans l’interface utilisateur mise à jour, créant une incohérence avec les offres de l’interface utilisateur et d’HTML héritées, qui affichaient correctement le nom du dernier éditeur. Ce correctif garantit une attribution utilisateur cohérente entre les types d’offres, ce qui améliore la transparence et l’alignement sur le comportement attendu. (TGT-52880 et TGT-52898)

+++

**Offer Decisioning**

+++Afficher les détails
* **L’erreur de décision d’offre a été résolue pour les offres ODE.** Correction d’un problème où les offres du moteur de décision d’offre (ODE) injectées par [!DNL Target] renvoyaient une erreur 400 en raison de métadonnées de format manquantes. Le message d’erreur indiquait que le type MIME était nul, ce qui empêchait le traitement réussi des décisions d’offre. Ce correctif garantit la gestion appropriée des métadonnées de l’offre, la restauration de la fonctionnalité pour la diffusion de contenu personnalisé et la possibilité d’exécuter sans interruption les campagnes marketing. (TGT-53635)
* **Le problème de rendu des offres ODS a été résolu.** Correction d’un problème en raison duquel les offres [!DNL Offer Decision Service] (ODS) créées via [!DNL Adobe Journey Optimizer] (AJO) n’étaient pas rendues lorsque les activités étaient créées à l’aide du VEC dans l’interface utilisateur mise à jour. La même configuration fonctionnait correctement dans l’interface utilisateur héritée, ce qui entraînait une confusion et bloquait l’exécution de la campagne. Ce correctif garantit la cohérence de la diffusion des offres dans les deux versions de l’interface utilisateur et restaure le comportement attendu pour la personnalisation pilotée par AJO.

+++

**Rapports**

+++Afficher les détails
* **Option de téléchargement restaurée dans la section Rapports de l’interface utilisateur de présentation des rapports mise à jour.** Correction d’un problème dans la nouvelle interface utilisateur de l’aperçu en raison duquel le bouton [!UICONTROL Download] était absent de la section Rapports, ce qui empêchait les utilisateurs d’exporter les scores d’importance des attributs. Cette mise à jour restaure l’intégralité des fonctionnalités d’exportation, permettant un accès rationalisé aux données téléchargeables pour l’analyse et le reporting. (TGT-53222)
* **[!UICONTROL Download full CSV report]bouton restauré dans la vue [!UICONTROL Important attributes].** Correction d’un problème dans l’interface utilisateur de création d’activités mise à jour où le bouton [!UICONTROL Download full CSV report] était absent de la section [!UICONTROL Important Attributes] de la vue Rapports. Ce correctif restaure l’accès aux informations téléchargeables, garantissant ainsi des fonctionnalités cohérentes dans les interfaces utilisateur mises à jour et héritées. (TGT-53238)
* **Résolution des problèmes d’interface utilisateur affectant les rapports [!UICONTROL Auto Target] dans l’interface utilisateur de présentation mise à jour.** Correction de plusieurs problèmes d’interface utilisateur dans l’interface de présentation mise à jour qui affectaient les rapports d’activité [!UICONTROL Auto Target]. Ces correctifs incluent :

   * Mesures d’effet élévateur et de confiance manquantes dans les rapports de synthèse
   * Indicateur de couleur incorrect pour la case à cocher « modèles créés »
   * Rapport graphique non fonctionnel malgré la variance des données dans [!DNL Analytics]
   * Lien de téléchargement manquant pour les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes]
   * Affichage du rapport de [!UICONTROL Automated Segments] endommagé

  Ces correctifs restaurent le comportement de création de rapports attendu et améliorent la visibilité sur les performances [!UICONTROL Auto Target] dans l’interface utilisateur mise à jour. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Afficher les détails
* **Validation du formulaire corrigée pour les conditions de présence des paramètres dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de « [!UICONTROL Custom mbox parameter value is present] » ou « [!UICONTROL Parameter is present] » nécessitait incorrectement que les clients saisissent une valeur. Ce comportement était en conflit avec la logique prévue, qui vérifie simplement l’existence d’un paramètre quelle que soit sa valeur. Le correctif aligne la validation du formulaire sur le comportement attendu, ce qui permet une configuration plus fluide des activités et une adoption complète de l’interface utilisateur mise à jour. (TGT-53638)
* **Correction de la logique de formulaire pour les règles de présence de paramètres dans la diffusion de page. »** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de règles de diffusion de page telles que « [!UICONTROL Parameter is present] », « [!UICONTROL Parameter is not present] », « [!UICONTROL Parameter value is present] » ou « [!UICONTROL Parameter value is not present] » obligeait incorrectement les utilisateurs à saisir une valeur de paramètre supplémentaire. Ce comportement était incompatible avec l’interface utilisateur héritée et contredisait la logique prévue de détection de la présence de paramètres sans spécifier de valeur. Ce correctif restaure le comportement attendu de configuration des règles, rationalisant la configuration des activités et améliorant la convivialité. (TGT-53640)
* **Amélioration de la logique de validation pour le créateur de règles à plusieurs pages dans l’interface utilisateur mise à jour.** a résolu plusieurs problèmes de validation dans le créateur de règles multi-pages dans l’interface utilisateur mise à jour. Ces correctifs incluent :

   * Empêcher la création de règles lorsque le paramètre mbox est vide
   * Affichage des messages d’erreur appropriés pour les états de règle non valides
   * Correction de la logique de validation pour les opérateurs unaires et basés sur des paramètres qui ne nécessitent pas de valeurs d’opérande
   * Activation des règles de fragment de hachage avec des opérateurs unaires en restaurant la fonctionnalité d’enregistrement

  Ces mises à jour garantissent une configuration des règles précise et améliorent la convivialité sur plusieurs scénarios de diffusion de pages complexes. (TGT-53722)
* **Problème de changement de nom de l’emplacement résolu dans les activités A/B et MVT.** Correction d’un bug dans l’interface utilisateur mise à jour en raison duquel le changement de nom d’un emplacement dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] (MVT) ne persistait pas après la navigation entre la liste d’emplacements, le ciblage et le retour. Cette mise à jour garantit que les modifications du nom de l’emplacement sont enregistrées et répercutées de manière cohérente tout au long du workflow d’activité. (TGT-52367)
* **Persistance du nom de l’emplacement corrigée pour les activités MVT et AP dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les noms d’emplacement modifiés dans les activités [!UICONTROL Multivariate Test] (MVT) et [!UICONTROL Automated Personalization] (AP) n’étaient pas enregistrés correctement. Après avoir renommé un emplacement, la navigation entre les onglets, tels que [!UICONTROL Targeting] et [!UICONTROL Experiences], a fait revenir les noms à leur état précédent. Ce correctif garantit la cohérence des noms d’emplacement entre les onglets et améliore la fiabilité lors de la configuration des activités. (TGT-52927)
* **Correction de l’étiquetage de l’emplacement dans le panneau Gérer les expériences pour les activités MVT.** Résolution d’un problème dans l’interface utilisateur mise à jour où le panneau [!UICONTROL Manage Experiences] dans les activités [!UICONTROL Multivariate Test] (MVT) affichait une numérotation d’emplacement incohérente. Ce correctif garantit que les libellés d’emplacement sont séquentiels et correctement alignés sur les modifications définies par l’utilisateur, ce qui améliore la clarté et la convivialité lors de la configuration de l’expérience. (TGT-52929)

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

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
