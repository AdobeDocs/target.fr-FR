---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5c1dda629a33fc38f51e2e3198a7ea091a369897
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 19%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.11.1 (10 novembre 2025)


**Analytics for Target (A4T)**

+++Afficher les détails
* **[!UICONTROL Goals & Settings]message d’erreur lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL Overview] mise à jour où la section Objectifs affichait l’erreur « Un problème s’est produit. Nous ne pouvons pas traiter votre demande. Veuillez contacter [!DNL Adobe Client Care] si le problème persiste » lorsque [!DNL Adobe Analytics] (A4T) a été sélectionné comme source de création de rapports. Les objectifs s’affichent désormais correctement avec les mesures de [!UICONTROL Adobe Analytics], ce qui garantit une visibilité cohérente entre les sources de création de rapports. (TGT-54021)

+++

**Audiences**

+++Afficher les détails
* **Impossible de sélectionner plusieurs audiences de création de rapports dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les utilisateurs ne pouvaient pas sélectionner simultanément plusieurs audiences de rapports nouvellement créées lors de la modification d’une activité. Plusieurs audiences peuvent désormais être affectées simultanément, ce qui améliore la flexibilité et l’efficacité de la configuration des rapports. (TGT-53253)

+++

**Offres Decisioning**

+++Afficher les détails
* **Impossible de modifier ou de remplacer les offres de prise de décision dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où les offres de prise de décision ne pouvaient pas être modifiées ni remplacées par le biais du panneau [!UICONTROL Modifications] et où les noms d’offre apparaissaient vides. Les offres de prise de décision sont désormais entièrement accessibles et modifiables, ce qui permet de restaurer la parité avec l’interface utilisateur héritée et de s’assurer que les clients peuvent gérer les offres directement dans les activités. (TGT-53884)

+++

**Localisation**

+++Afficher les détails
* **Correction de plusieurs erreurs de localisation dans l’interface utilisateur coréenne et japonaise.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 ET TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++Afficher les détails
* **La promotion par attribut avec correspondance d’attribut d’entité n’a pas pu charger la clé de recommandation après l’enregistrement de l’activité.** Correction d’un problème en raison duquel les promotions de type [!UICONTROL Promotion by Attribute] avec le type de règle [!UICONTROL Entity Attribute Matching] ne chargeaient pas la clé de recommandation lors de la modification après l’enregistrement d’une activité. Le problème est dû au fait que le `customKeyId` n’est pas demandé via GraphQL. Les clés de recommandation se chargent désormais correctement lors des modifications de promotion. (TGT-53117)
* **La recommandation persiste visuellement lors du passage d’ExpB à ExpA.** Correction d’un problème en raison duquel l’insertion d’une recommandation dans l’expérience B, puis le passage à l’expérience A laissait la zone d’offre de recommandation visible. Il s’agissait uniquement d’une incohérence visuelle ; les modifications s’affichent désormais correctement lors du changement d’expérience, garantissant ainsi un comportement précis de l’interface utilisateur. (TGT-53911)
* **La clé de recommandation ne se charge pas pour les [!UICONTROL Promotion by Attribute] avec correspondance de [!UICONTROL Entity Attribute].** Correction d’un problème en raison duquel les promotions de type [!UICONTROL Promotion by Attribute] avec le type de règle [!UICONTROL Entity Attribute Matching] ne chargeaient pas la clé de recommandation lors de la modification après l’enregistrement d’une activité. La clé de recommandation est désormais correctement récupérée via GraphQL, ce qui garantit que les promotions s’affichent et fonctionnent comme prévu. (TGT-53917)
* **La modification des recommandations sur les éléments HTML masqués ne fonctionne pas dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL New Create] et du VEC en raison duquel les activités de recommandation appliquées aux éléments HTML masqués ne pouvaient pas être modifiées. Cette fonctionnalité fonctionne désormais comme prévu, en rétablissant la parité avec l’interface utilisateur héritée et en s’assurant que les recommandations peuvent être modifiées, quelle que soit la visibilité des éléments. (TGT-53953)
* **Impossible de modifier les activités de recommandation sur les éléments HTML masqués dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les activités de recommandation appliquées aux éléments HTML masqués ne pouvaient pas être modifiées. Cette fonctionnalité fonctionne désormais comme prévu, en rétablissant la parité avec l’interface utilisateur héritée et en s’assurant que les recommandations peuvent être modifiées, quelle que soit la visibilité des éléments. (TGT-53951)
* **Le catalogue de recommandations ne contient pas de valeurs d’attribut par intermittence dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL Recommendations] mise à jour en raison duquel les listes de recherche de catalogue échouaient par intermittence à afficher certaines valeurs d’attribut (par exemple, message) même lorsqu’elles étaient présentes dans le flux de produits. Les valeurs d’attribut se chargent désormais de manière cohérente dans les résultats de recherche sans nécessiter de reconfiguration des colonnes, ce qui améliore la fiabilité et l’efficacité de la gestion des catalogues. (TGT-52769)
* **[!UICONTROL Download Recommendations]bouton est manquant pour les activités [!DNL Recommendations] dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur de [!DNL Recommendations] mise à jour en raison duquel le bouton [!UICONTROL Download Recommendations] n’était pas visible pour les activités A/B à l’aide de recommandations. Le bouton s’affiche désormais correctement, ce qui permet aux utilisateurs d’exporter des données de recommandation comme prévu, conformément à la fonctionnalité de l’interface utilisateur héritée. (TGT-53768)
* Bouton **[!UICONTROL Download Recommendation Data]manquant dans l’interface utilisateur de présentation mise à jour.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL Overview] mise à jour en raison duquel le bouton [!UICONTROL Download Recommendation Data] n’était pas visible pour les activités contenant des recommandations. Le bouton s’affiche désormais correctement, ce qui permet aux utilisateurs d’exporter directement les données de recommandations sans avoir à revenir à l’interface utilisateur héritée. (TGT-53772)
* **La modification des critères d’activité entraînait parfois un écran vide dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel cliquer sur [!UICONTROL Edit Criteria in Experiences] entraînait parfois l’affichage d’un écran vide pour certaines activités. L’éditeur de critères se charge désormais de manière fiable dans toutes les activités, ce qui permet aux utilisateurs de modifier sans interruption. (TGT-53961)
* **Impossible de modifier les critères de séquence dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où la tentative de modification de [!UICONTROL Sequence Criteria] entraînait le blocage de la fenêtre contextuelle des critères lors du chargement, puis l’affichage d’un écran vide. L’éditeur de critères se charge désormais correctement, ce qui permet aux utilisateurs et utilisatrices de modifier et de mettre à jour les critères de séquence sans interruption. (TGT-53985)

+++

**[!UICONTROL Reports]**

+++Afficher les détails
* Les emplacements **[!UICONTROL Multivariate Test](MVT) et les problèmes de création de rapports graphiques ont empêché la génération de rapports.** Correction d’un problème en raison duquel les activités MVT ne généraient pas de rapports [!UICONTROL Location Contribution] et graphiques dans l’interface utilisateur de Target, affichant l’erreur « Un problème est survenu. Nous ne pouvons pas traiter votre demande. » Les rapports se chargent désormais correctement dans l’interface utilisateur, offrant ainsi une visibilité totale. (TGT-53654)
* **Les rapports MVT ne se chargent pas en raison d’[!UICONTROL Element] erreur de rapport de contribution.** Correction d’un problème en raison duquel le chargement des rapports d’activité MVT échouait dans l’interface utilisateur de Target, affichant l’erreur « Impossible de récupérer le rapport de contribution des éléments ». Les rapports s’affichent désormais correctement, assurant ainsi une visibilité complète des contributions des éléments. (TGT-53691)
* **Exportez les détails de la commande vers un événement CSV pour les activités [!UICONTROL Experience Targeting] (XT).** Correction d’un problème en raison duquel l’option [!UICONTROL Export Order Details to CSV] s’affichait incorrectement pour les activités XT et renvoyait un fichier vide. L’option s’affiche désormais uniquement pour les activités AP, ce qui garantit une fonctionnalité d’exportation précise et empêche toute confusion. (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Afficher les détails
* **[!UICONTROL Delete Modification]problème de bouton empêchait la suppression des modifications d’activité.** Correction d’un problème en raison duquel le bouton [!UICONTROL Delete Modification] de l’interface utilisateur de [!DNL Target] ne fonctionnait pas, empêchant les utilisateurs de supprimer des modifications dans les activités . Le bouton fonctionne désormais comme prévu, ce qui permet de supprimer les modifications de manière fiable et sans délai. (TGT-53728)
* **Les sélecteurs préférés ne sont pas reconnus dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où les sélecteurs préférés, tels que `data-target-component-id`, n’apparaissaient pas dans la liste des sélecteurs CSS dans le VEC. Les utilisateurs peuvent désormais sélectionner de manière fiable les attributs préférés au lieu des noms de classe générés dynamiquement, ce qui garantit un ciblage stable entre les mises à jour de page SPA. (TGT-53908)
* **Incompatibilité d’alignement de l’emplacement des activités entre les pages [!UICONTROL Edit] et [!UICONTROL Overview].** Correction d’un problème en raison duquel la numérotation des emplacements d’activités dans la page [!UICONTROL Overview] ne correspondait pas aux mises à jour effectuées dans la page [!UICONTROL  Edit Experience]. Les emplacements restent désormais cohérents sur les deux vues, ce qui garantit un alignement précis et empêche les positions manquantes ou mal numérotées. (TGT-53960 et TGT-53954)
* **Impossible de revenir au mode [!UICONTROL Design] dans le VEC mis à jour.** Correction d’un problème dans l’interface utilisateur mise à jour du VEC en raison duquel les utilisateurs ne pouvaient pas revenir au mode [!UICONTROL Design] après avoir accédé à une nouvelle page en mode [!UICONTROL Browse]. Le bouton (bascule) [!UICONTROL Design] fonctionne désormais correctement, ce qui permet d’appliquer facilement les modifications sur plusieurs pages. (TGT-53988 et TGT-53993)
* **Paramètre de requête non affiché dans la vue d’ensemble de l’activité.** Correction d’un problème dans l’interface utilisateur mise à jour où les paramètres de requête n’étaient pas affichés dans la page [!UICONTROL Overview] pour les activités, ce qui provoquait des incohérences entre les URL de diffusion de [!UICONTROL Overview] et de page. Les paramètres de requête s’affichent désormais correctement, ce qui garantit que les emplacements des activités sont entièrement représentés et cohérents entre les vues. (TGT-53701)

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
