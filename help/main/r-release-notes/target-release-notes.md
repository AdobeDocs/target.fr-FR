---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fe370f57978ace161ca2ba2b9f6b11ae8f9b4cfa
workflow-type: tm+mt
source-wordcount: '1538'
ht-degree: 13%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : mardi 3 mars 2025**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.3.1 (3 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Une audience combinée peut inclure des sous-groupes, chacun contenant plusieurs audiences. Cette version a corrigé un problème qui empêchait l’affichage des audiences de sous-groupe dans la boîte de dialogue [!UICONTROL Rules]. (TGT-51813)
* Correction d’un problème où certaines audiences d’expérience étaient remplacées par des [!UICONTROL All Visitors] lors de l’ouverture d’anciennes activités. (TGT-51812)
* Correction d’un problème qui empêchait la modification des activités avec des audiences d’activité uniquement. (TGT-51807)
* Correction d’un problème qui empêchait la modification des modifications d’en-tête de page dans l’interface utilisateur [!DNL Target] mise à jour. (TGT-51797)
* Correction d’une erreur « null » qui se produisait lors de la duplication d’une expérience, de la suppression d’une autre expérience, puis de la tentative d’enregistrement de l’activité. (TGT-51796)
* Correction d’un problème qui empêchait l’affichage des règles d’exclusion d’audience dans le panneau d’informations de l’audience lors de l’étape [!UICONTROL Targeting] de la création d’activités. (TGT-51579)
* Mise à jour des messages d&#39;erreur en coréen. (TGT-51701 et TGT-51699)

## [!DNL Target Standard/Premium] 25.2.3 (26 février 2025)

Cette version comprend les mises à jour suivantes :

* Correction d’un problème qui empêchait les mises à jour des activités après [!DNL Target] version 25.2.1 pour certaines activités. (TGT-51781)
* Correction d’un problème où toutes les modifications d’audience dans l’état étaient supprimées lors de l’annulation du processus de création d’activités (en sélectionnant [!UICONTROL Cancel] au lieu de [!UICONTROL Add Audience]). (TGT-51769 et TGT-51770)
* Correction d’un problème en raison duquel le chargement du [!UICONTROL Visual Experience Composer] (VEC) échouait pour certaines activités, en particulier lorsque du code personnalisé était utilisé.  En raison d’un problème, le VEC affichait un écran vide ou l’interface utilisateur de [!DNL Target] revenait à son ancienne version. (TGT-51758)
* Correction d’un problème où les modifications étaient ignorées après la modification de la diffusion de page pour les audiences. (TGT-51756)
* Correction d’un problème où toutes les audiences non métriques (audiences de page et d’expérience) étaient supprimées des activités lors de la modification d’un type de mesure sur la page [!UICONTROL Goals & Settings]. (TGT-51753)
* Correction d’un problème en raison duquel un clic sur [!UICONTROL Cancel] lors de la modification d’une activité faisait naviguer l’interface utilisateur de Target vers la [!UICONTROL Activities List] plutôt que vers la page [!UICONTROL Activity Details]. (TGT-51731)
* Correction d’un problème qui empêchait les clients et clientes de télécharger des rapports via l’option [!UICONTROL Export Reports to CSV]. (TGT-51708)
* Correction d’un problème dans le compositeur d’expérience d’après les formulaires en raison duquel [!DNL Target Standard] clients s’affichaient incorrectement comme utilisant [!UICONTROL Properties], une fonctionnalité [!DNL Target Premium]. (TGT-51678)
* Correction d’un problème qui empêchait l’affichage des attributs [!DNL Adobe Experience Platform] lors de la création de nouvelles offres. (TGT-51665)
* Déplacement de tous les filtres actifs pour [!DNL Recommendations] inventaire vers la recherche rapide, en alignant l’interface utilisateur avec [!UICONTROL Catalog Search] au lieu du rail de [!UICONTROL Filter]. (TGT-50723)

## at.js version 2.11.7 (26 février 2025)

Cette version comprend la mise à jour suivante :

* Correction de la journalisation de la télémétrie lorsque `localStorage` n’est pas disponible. La télémétrie provoquait un problème pour certains clients qui avaient `localStorage` désactivés dans leurs navigateurs.

Pour plus d’informations à ce sujet et sur les versions précédentes d’at.js, voir [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

## [!DNL Target Standard/Premium] 25.2.1 (17 février 2025)

Cette version comprend les mises à jour suivantes :

* Mise à jour de l’interface utilisateur d’[!UICONTROL Activities]
* Mise à jour de l’interface utilisateur d’[!DNL Recommendations]

### Mise à jour de l’interface utilisateur d’[!UICONTROL Activities]

Alors que les efforts de modernisation de l’interface utilisateur de [!DNL Adobe Target] se poursuivent, nous sommes heureux d’annoncer la disponibilité générale de l’interface utilisateur de [!UICONTROL Activities] mise à jour.

>[!NOTE]
>
>À compter du 17 février, les clients auront progressivement accès à la nouvelle interface utilisateur de [!UICONTROL Activities]. Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape consiste à mettre à niveau le groupe initial de clients [!DNL Target] vers la nouvelle interface utilisateur de [!UICONTROL Activities]. Les étapes suivantes mettront à niveau les clients restants.

En fonction du dernier système de conception [!DNL Adobe Spectrum], la mise à jour normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :

* [Redéfinition des rapports](/help/main/administrating-target/reporting.md) pour une meilleure compréhension des résultats des activités.
* [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md) page, obtenant maintenant les informations du [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} pour des informations en temps réel.
* [Vues Liste personnalisables](/help/main/c-activities/activities.md) pour une meilleure flexibilité en fonction des besoins des différentes équipes.
* [Amélioration des écrans d’informations rapides et détaillées](/help/main/c-activities/activities.md) pour un accès plus facile aux informations.
* [Options de recherche et de filtrage persistantes dans la session](/help/main/c-activities/activities.md).
* [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) entièrement [reconstruit) avec prise en charge des dernières mises à jour de sécurité des fournisseurs de navigateur et une interface utilisateur moderne.

  Pour plus d’informations sur les différences entre le VEC mis à jour et la version précédente, voir :

   * [Modifications du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
   * [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Mise à jour [!DNL Chrome] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) prise en charge de Manifest V3 pour une sécurité accrue et une meilleure prise en charge des cookies propriétaires.

![Actualisation des activités](/help/main/r-release-notes/assets/activities-refresh.png)

### Mise à jour de l’interface utilisateur d’[!DNL Recommendations]

Alors que les efforts de modernisation de l’interface utilisateur de [!DNL Adobe Target] se poursuivent, nous sommes heureux d’annoncer la disponibilité générale de l’interface utilisateur de [!DNL Recommendations] mise à jour.

>[!NOTE]
>
>À compter du 17 février, les clients auront progressivement accès à la nouvelle interface utilisateur de [!UICONTROL Recommendations]. Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape consiste à mettre à niveau le groupe initial de clients [!DNL Target] vers la nouvelle interface utilisateur de [!UICONTROL Activities]. Les étapes suivantes mettront à niveau les clients restants.

En fonction du dernier système de conception [!DNL Adobe Spectrum], la mise à jour normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :

* La [recherche catalogue de produits](/help/main/c-recommendations/c-products/catalog-search.md) comprend désormais une base de données mise à jour permettant une synchronisation en temps réel des produits.
* [!UICONTROL Recommendations] objets ([!UICONTROL Criteria], [!UICONTROL Designs], [!UICONTROL Collections] et [!UICONTROL Exclusions]) [créés via l’API sont désormais disponibles dans l’interface utilisateur](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* Les [paramètres Recommendations](/help/main/administrating-target/recommendations-settings.md) ont été consolidés dans la section [!UICONTROL Administration].
* Vues Liste personnalisables pour une meilleure flexibilité en fonction des besoins des différentes équipes.
* Actualisation des éditeurs de code HTML et JSON avec [mise en surbrillance de la syntaxe et numérotation des lignes](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Amélioration des fenêtres d’informations rapides et détaillées pour un accès plus facile aux informations.
* Options de recherche et de filtrage persistantes dans la session.

![Actualisation de l’interface utilisateur de Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

## [!DNL Target Standard/Premium] 25.1.1 (vendredi 9 janvier 2025)

Cette version comprend les mises à jour suivantes :

### Mise à jour de l’interface utilisateur d’[!UICONTROL Offers Library]

Pour améliorer l’expérience utilisateur des utilisateurs [!DNL Adobe Target], cette version met à jour l’interface utilisateur [!UICONTROL Offers Library].

>[!NOTE]
>
>Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape a mis à niveau le groupe initial de clients Target vers la nouvelle interface utilisateur d’offres. Les étapes suivantes mettront à niveau les clients restants.

En utilisant le dernier système de conception [!DNL Adobe Spectrum], cette mise à jour normalise les modèles de conception incohérents et introduit de nouvelles améliorations, notamment les suivantes :

* **Gestion des offres en masse** : sélectionnez et supprimez ou déplacez plusieurs offres simultanément.

* Mises à niveau de la **[!UICONTROL Code Editor]** : actualisation des éditeurs HTML et JSON avec mise en surbrillance de la syntaxe et numérotation des lignes.

* **Cartes d’offres améliorées** : cartes d’informations rapides et détaillées améliorées pour un accès plus facile aux informations.

* **Recherche et filtres persistants** : ajoute des options de recherche et de filtrage persistantes dans la session.

Pour plus d’informations, consultez [Offres](/help/main/c-experiences/c-manage-content/manage-content.md) et les sous-articles de cette section.

Regardez cette courte vidéo pour découvrir les modifications apportées à cette version :

![Vidéo d’actualisation de l’interface utilisateur des offres](/help/main/r-release-notes/assets/offers-video-v2.gif)

## Optimisation de la portée de la `__view__` [!DNL Adobe Experience Platform Web SDK] (22 octobre 2024)

Entre le 22 juillet 2024 et le 15 août 2024, l’équipe [!DNL Target] a optimisé la portée du `__view__`, améliorant la précision des impressions d’activité, des visites et des rapports des visiteurs. Cette optimisation vise à capturer automatiquement les données de rapport pour les propositions générées automatiquement et doit être transparente pour la plupart des comptes.

Cette optimisation sera activée pour tous les nouveaux clients [!DNL Adobe Experience Platform Web SDK]. Toutefois, l’optimisation est désactivée pour les clients qui ont migré depuis at.js et n’ont pas suivi les étapes d’implémentation ci-dessous. Nous recommandons vivement à ces clients de passer en revue leurs mises en œuvre d’ici le 3 février 2025. Passée cette date, nous activerons l’optimisation pour tous les clients. Si vous ne révisez pas et n’ajustez pas les implémentations d’ici là, les rapports peuvent être affectés, comme mentionné ci-dessous. Contactez [!DNL Adobe Customer Care] si vous devez confirmer si votre implémentation est affectée ou si vous avez besoin de plus de temps pour ajuster votre implémentation.

>[!IMPORTANT]
>
>Si vous ne parvenez pas à terminer l’examen de votre mise en œuvre et à résoudre les problèmes d’ici le 3 février 2025, vous pouvez demander une prolongation unique de six mois. Assurez-vous que votre demande a été soumise au plus tard le 31 janvier 2025. Adobe examinera votre demande et prendra une décision à ce sujet.

Pour bénéficier de cette optimisation en cas de rendu manuel des propositions, passez en revue votre [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} pour vous assurer que vous envoyez des notifications après avoir effectué manuellement le rendu des expériences ou lors de l’utilisation de la méthode `applyPropositions` (ou de l’action [!DNL Launch] correspondante en tant qu’assistant) pour effectuer le rendu des expériences.

Les scénarios les plus courants lorsque les expériences sont rendues manuellement incluent :

* Utilisation des offres JSON
* Utilisation d’une portée de décision personnalisée dans une activité créée dans le [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* Ne pas utiliser de `renderDecisions: true` lors de la récupération d’une activité créée à l’aide du [!UICONTROL Form-Based Experience Composer] qui utilise la portée `__view__` globale

Si les notifications ne sont pas implémentées comme indiqué dans la section [Rendu de contenu personnalisé](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} du guide *Collecte de données*, les données de rapport peuvent être manquantes dans les rapports [!DNL Target] et [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Dans certains scénarios, vous remarquerez peut-être une répartition incorrecte du trafic, car les données des rapports ne sont pas capturées. Ou, dans d’autres scénarios, signaler le même événement à plusieurs reprises.

Selon votre implémentation, vérifiez l’impact des rapports [!DNL Analytics] et A4T.

Le [!DNL Platform Web SDK] prend en charge deux types d’implémentation pour le rendu des expériences et des personnalisations :

* **Appel unique pour la personnalisation et la mesure.**

  Initialement recommandée, l’approche par appel unique pour le [!DNL Platform Web SDK] devrait être abandonnée au profit de l’approche par appel partagé. Adobe conseille à toutes les nouvelles mises en œuvre d’utiliser la nouvelle approche d’appel partagé et recommande aux clients existants d’adopter également la méthode d’appel partagé.

  Si vous continuez à utiliser l’approche d’appel unique, vous remarquerez peut-être les modifications inattendues suivantes dans vos rapports [!DNL Analytics] :

   * Baisse des bounces.
   * Les accès A4T et [!UICONTROL Page View] ne sont pas regroupés, ce qui rend difficile l’exécution de certaines répartitions et corrélations de vos rapports A4T à l’aide d’eVars et d’événements [!DNL Analytics].

* **Appels fractionnés (également appelés événements en haut et en bas de page).**

  Ce type d’implémentation est la nouvelle approche d’implémentation [appel fractionné](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recommandée par [!DNL Adobe]. Avec cette approche, la nouvelle optimisation n’a aucune incidence sur les rapports [!DNL Analytics] ou A4T.

Si vous avez des questions, contactez l’[Assistance clientèle Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
