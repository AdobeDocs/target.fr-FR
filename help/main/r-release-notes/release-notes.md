---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b1ead7317debadafcb42469894cdb7b6ba337110
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 39%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Adobe Experience Platform Web SDK] `__view__` optimisation de la portée (22 octobre 2024)

Entre le 22 juillet 2024 et le 15 août 2024, l’équipe [!DNL Target] a optimisé la portée de `__view__`, ce qui améliore la précision des rapports d’impression d’activité, de visites et de visiteurs. Cette optimisation a pour but de capturer automatiquement les données de rapport pour les propositions générées automatiquement et doit être transparente pour la plupart des comptes.

Cette optimisation sera activée pour tous les nouveaux clients [!DNL Adobe Experience Platform Web SDK]. Toutefois, les clients qui ont migré depuis at.js et n’ont pas suivi les étapes de mise en oeuvre ci-dessous ont désactivé l’optimisation. Nous recommandons vivement à ces clients de passer en revue leurs mises en oeuvre d’ici le 3 février 2025. À compter de cette date, nous activerons l’optimisation pour tous les clients. L’échec de la révision et de l’ajustement des mises en oeuvre d’ici là peut avoir un impact sur les rapports, comme mentionné ci-dessous. Contactez [!DNL Adobe Client Care] si vous devez confirmer si votre implémentation est affectée ou si vous avez besoin de plus de temps pour ajuster votre implémentation.

Pour bénéficier de cette optimisation en cas de rendu manuel des propositions, passez en revue votre [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} pour vous assurer que vous envoyez des notifications après avoir effectué un rendu manuel des expériences ou lorsque vous utilisez la méthode `applyPropositions` (ou l’action [!DNL Launch] correspondante en tant qu’assistance) pour effectuer le rendu des expériences.

Les scénarios les plus courants lorsque des expériences sont générées manuellement sont les suivants :

* Utilisation des offres JSON
* Utilisation d’une portée de décision personnalisée dans une activité créée dans le [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* Ne pas utiliser `renderDecisions: true` lors de la récupération d’une activité créée à l’aide de [!UICONTROL Form-Based Experience Composer] qui utilise la portée globale `__view__`

Si les notifications ne sont pas implémentées comme indiqué dans le guide [Render personalized content](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} dans la *collecte de données*, il se peut que les données de rapport soient manquantes dans [!DNL Target] et dans les [rapports Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Dans certains scénarios, il se peut que vous remarquiez un partage de trafic incorrect, car les données de rapport ne sont pas capturées. Ou, dans d’autres scénarios, signaler le même événement à plusieurs reprises.

Selon votre mise en oeuvre, recherchez les impacts des rapports [!DNL Analytics] et A4T.

[!DNL Platform Web SDK] prend en charge deux types d’implémentation pour le rendu des expériences et des personnalisations :

* **Appel unique pour la personnalisation et la mesure.**

  Initialement recommandé, l’approche d’appel unique pour [!DNL Platform Web SDK] est planifiée pour être abandonnée au profit de l’approche d’appel partagé. Adobe conseille à toutes les nouvelles implémentations d’utiliser la nouvelle approche d’appel partagé et recommande que les clients existants passent également à la méthode d’appel partagé.

  Si vous continuez à utiliser l’approche d’appel unique, vous remarquerez peut-être les modifications inattendues suivantes dans vos rapports [!DNL Analytics] :

   * Rebonds en creux.
   * Les accès A4T et [!UICONTROL Page View] ne sont pas assemblés, ce qui complique l’exécution de certaines ventilations et corrélations de vos rapports A4T à l’aide d’eVars et d’événements [!DNL Analytics].

* **Scinder les appels (également appelés événements de haut et de bas de page).**

  Ce type d’implémentation est la nouvelle [méthode d’implémentation d’appel partagé](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recommandée par [!DNL Adobe]. Avec cette approche, la nouvelle optimisation n’a aucune incidence sur les rapports [!DNL Analytics] ou A4T.

Si vous avez des questions, contactez l&#39;[Assistance clientèle Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

## at.js version 2.11.6 (29 septembre 2024)

* Correction d’un problème qui empêchait [!DNL Target] de fonctionner correctement avec les offres de redirection dans le [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Form-Based Experience Composer].

Pour plus d’informations sur les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank} dans le *Guide du développeur d’Adobe Target*.

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
