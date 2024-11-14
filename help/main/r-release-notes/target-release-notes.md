---
keywords: notes de mise à jour;versions;mises à jour;version ultérieure;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d823e9993ff17f1970dc1deac996928781c7e79d
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 27%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : vendredi 14 novembre 2024**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Adobe Experience Platform Web SDK] `__view__` optimisation de la portée (22 octobre 2024)

Entre le 22 juillet 2024 et le 15 août 2024, l’équipe [!DNL Target] a optimisé la portée de `__view__`, ce qui améliore la précision des rapports d’impression d’activité, de visites et de visiteurs. Cette optimisation a pour but de capturer automatiquement les données de rapport pour les propositions générées automatiquement et doit être transparente pour la plupart des comptes.

Cette optimisation sera activée pour tous les nouveaux clients [!DNL Adobe Experience Platform Web SDK]. Toutefois, les clients qui ont migré depuis at.js et n’ont pas suivi les étapes de mise en oeuvre ci-dessous ont désactivé l’optimisation. Nous recommandons vivement à ces clients de passer en revue leurs mises en oeuvre d’ici le 3 février 2025. À compter de cette date, nous activerons l’optimisation pour tous les clients. L’échec de la révision et de l’ajustement des mises en oeuvre d’ici là peut avoir un impact sur les rapports, comme mentionné ci-dessous. Contactez [!DNL Adobe Customer Care] si vous devez confirmer si votre implémentation est affectée ou si vous avez besoin de plus de temps pour ajuster votre implémentation.

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
