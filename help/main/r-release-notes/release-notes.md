---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f3090ad7ab1c3d15de496039e76bb5ec0b02886f
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 31%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mise à jour de l’interface utilisateur d’[!UICONTROL Offers Library] (9 janvier 2025)

Pour améliorer l’expérience utilisateur des utilisateurs [!DNL Adobe Target], cette version met à jour l’interface utilisateur [!UICONTROL Offers Library]. En utilisant le dernier système de conception [!DNL Adobe Spectrum], cette mise à jour normalise les modèles de conception incohérents et introduit de nouvelles améliorations, notamment les suivantes :

* **Gestion des offres en masse** : sélectionnez et supprimez ou déplacez plusieurs offres simultanément.

* Mises à niveau de **[!UICONTROL Code Editor]** : actualisation de l’HTML et des éditeurs JSON avec mise en surbrillance de la syntaxe et numérotation des lignes.

* **Cartes d’offres améliorées** : cartes d’informations rapides et détaillées améliorées pour un accès plus facile aux informations.

* **Recherche et filtres persistants** : ajoute des options de recherche et de filtrage persistantes dans la session.

À compter du 9 janvier 2025, tous les clients [!DNL Target] auront accès à la nouvelle interface utilisateur, avec la possibilité de revenir à la version actuelle de l’interface utilisateur si nécessaire.

Pour plus d’informations, consultez [Offres](/help/main/c-experiences/c-manage-content/manage-content.md) et les sous-articles de cette section.

Regardez cette courte vidéo pour découvrir les modifications apportées à cette version :

![Vidéo d’actualisation de l’interface utilisateur des offres](/help/main/r-release-notes/assets/offers-video-v2.gif)

## Optimisation de la portée de la `__view__` [!DNL Adobe Experience Platform Web SDK] (22 octobre 2024)

Entre le 22 juillet 2024 et le 15 août 2024, l’équipe [!DNL Target] a optimisé la portée du `__view__`, améliorant la précision des impressions d’activité, des visites et des rapports des visiteurs. Cette optimisation vise à capturer automatiquement les données de rapport pour les propositions générées automatiquement et doit être transparente pour la plupart des comptes.

Cette optimisation sera activée pour tous les nouveaux clients [!DNL Adobe Experience Platform Web SDK]. Toutefois, l’optimisation est désactivée pour les clients qui ont migré depuis at.js et n’ont pas suivi les étapes d’implémentation ci-dessous. Nous recommandons vivement à ces clients de passer en revue leurs mises en œuvre d’ici le 3 février 2025. Passée cette date, nous activerons l’optimisation pour tous les clients. Si vous ne révisez pas et n’ajustez pas les implémentations d’ici là, les rapports peuvent être affectés, comme mentionné ci-dessous. Contactez [!DNL Adobe Customer Care] si vous devez confirmer si votre implémentation est affectée ou si vous avez besoin de plus de temps pour ajuster votre implémentation.

>[!IMPORTANT]
>
>Si vous ne parvenez pas à terminer l’examen de votre mise en œuvre et à résoudre les problèmes d’ici le 3 février 2025, vous pouvez demander une prolongation unique de six mois. Assurez-vous que votre demande a été soumise au plus tard le 31 janvier 2025. L’Adobe examinera votre demande et prendra une décision à son sujet.

Pour bénéficier de cette optimisation en cas de rendu manuel des propositions, passez en revue votre [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} pour vous assurer que vous envoyez des notifications après avoir effectué manuellement le rendu des expériences ou lors de l’utilisation de la méthode `applyPropositions` (ou de l’action [!DNL Launch] correspondante en tant qu’assistant) pour effectuer le rendu des expériences.

Les scénarios les plus courants lorsque les expériences sont rendues manuellement incluent :

* Utilisation des offres JSON
* Utilisation d’une portée de décision personnalisée dans une activité créée dans le [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* Ne pas utiliser de `renderDecisions: true` lors de la récupération d’une activité créée à l’aide du [!UICONTROL Form-Based Experience Composer] qui utilise la portée `__view__` globale

Si les notifications ne sont pas implémentées comme indiqué dans la section [Rendu de contenu personnalisé](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} du guide *Collecte de données*, les données de rapport peuvent être manquantes dans les rapports [!DNL Target] et [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Dans certains scénarios, vous remarquerez peut-être une répartition incorrecte du trafic, car les données des rapports ne sont pas capturées. Ou, dans d’autres scénarios, signaler le même événement à plusieurs reprises.

Selon votre implémentation, vérifiez l’impact des rapports [!DNL Analytics] et A4T.

Le [!DNL Platform Web SDK] prend en charge deux types d’implémentation pour le rendu des expériences et des personnalisations :

* **Appel unique pour la personnalisation et la mesure.**

  Initialement recommandée, l’approche par appel unique pour le [!DNL Platform Web SDK] devrait être abandonnée au profit de l’approche par appel partagé. Adobe conseille à toutes les nouvelles mises en œuvre d’utiliser la nouvelle approche de l’appel partagé et recommande aux clients existants d’effectuer également la transition vers la méthode d’appel partagé.

  Si vous continuez à utiliser l’approche d’appel unique, vous remarquerez peut-être les modifications inattendues suivantes dans vos rapports [!DNL Analytics] :

   * Baisse des bounces.
   * Les accès A4T et [!UICONTROL Page View] ne sont pas regroupés, ce qui rend difficile l’exécution de certaines répartitions et corrélations de vos rapports A4T à l’aide d’eVars et d’événements [!DNL Analytics].

* **Appels fractionnés (également appelés événements en haut et en bas de page).**

  Ce type d’implémentation est la nouvelle approche d’implémentation [appel fractionné](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recommandée par [!DNL Adobe]. Avec cette approche, la nouvelle optimisation n’a aucune incidence sur les rapports [!DNL Analytics] ou A4T.

Si vous avez des questions, contactez l’Assistance clientèle d’Adobe [](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
