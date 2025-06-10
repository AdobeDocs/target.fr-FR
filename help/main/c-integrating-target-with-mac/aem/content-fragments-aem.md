---
keywords: experience;json;aem;adobe experience manager;exporter vers adobe target;fragments de contenu;fragments;CF;cf,découplé;personnalisation;expérimentation
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] dans les  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager]  (AEM) [!UICONTROL Content Fragments] ?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 15%

---

# [!UICONTROL Content Fragments] AEM

Utilisez les [!UICONTROL Content Fragments] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter la personnalisation et l’expérimentation découplées.

## Considérations

Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL Content Fragments] AEM dans [!DNL Target] :

* Cette fonctionnalité est réservée aux clientes et clients [!DNL Adobe Experience Manager as a Cloud Service]. Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Multivariate Test] (VMT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser des [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* consommer des [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

Pour en savoir plus sur AEM [!UICONTROL Content Fragments] et [!UICONTROL Experience Fragments], consultez [Présentation d’AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments]](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Vous devez utiliser [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr){target=_blank}. Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Configuration et utilisation de [!UICONTROL Content Fragments] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour exporter des [!UICONTROL Content Fragments] afin de les utiliser dans des activités [!DNL Target], vous devez effectuer quelques étapes préliminaires dans AEM. Pour plus d’informations, consultez [Exportation de fragments de contenu vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=fr){target=_blank} dans la *documentation Experience Manager as a Cloud Service*.

Pour plus d’informations sur la conception, la création, l’organisation et la publication de [!UICONTROL Content Fragments], consultez [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=fr){target=_blank} et [Utilisation de fragments de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=fr){target=_blank} dans la [documentation d’Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=fr){target=_blank}.

## Utilisation de [!UICONTROL Content Fragments] dans les activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le [!UICONTROL Content Fragment] s’affiche sur la page [!UICONTROL Offers] dans [!DNL Target].

[!DNL Target] recherche actuellement des [!UICONTROL Content Fragments] à importer toutes les dix minutes. Les [!UICONTROL Content Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.

Le [!UICONTROL Content Fragment] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL Content Fragment] « principale » reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Content Fragment] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL HTML XFs], [!UICONTROL JSON XFs] et [!UICONTROL Content Fragments] pour vous aider à distinguer les différents types d’offres exportés vers [!DNL Target].

![Filtrer par types de fragments de contenu : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez placer le pointeur de la souris sur un [!UICONTROL Experience Fragment] de la liste, puis cliquer sur l’icône [!UICONTROL View] ![icône Infos](/help/main/assets/icons/InfoOutline.svg) pour afficher des informations supplémentaires sur le [!UICONTROL Content Fragment], notamment ses informations de [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] et dernières modifications. Cliquez sur [!UICONTROL [!UICONTROL View Full Details]] pour afficher les activités qui font référence à cette offre.

Vous pouvez utiliser des [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser des [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). Les [!UICONTROL Content Fragments] sont exportées au format JSON dans [!DNL Target] et ne peuvent pas être utilisées dans les activités créées à l’aide du compositeur d’expérience visuelle.

>[!TIP]
>
>Utilisez l’intelligence artificielle, le machine learning et les recommandations avec [!UICONTROL Content Fragments] :
>
>* Pour tirer pleinement parti de la fonctionnalité d’IA dédiée aux [!DNL Target] et de ML de , sélectionnez [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité de [!UICONTROL A/B Test].
>
>* [!UICONTROL Content Fragments] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Toutefois, pour utiliser des [!UICONTROL Content Fragments] pour les recommandations, vous pouvez créer une activité de [!UICONTROL A/B Test] (y compris [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) ou une activité de [!UICONTROL Experience Targeting] (XT) et [inclure des recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour consommer des [!UICONTROL Content Fragments] à l’aide de l’[!UICONTROL Form-based Experience Composer] :**

1. En [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer [!DNL AEM] contenu, puis sélectionnez **[!UICONTROL Change Content Fragment]** pour afficher la liste [!UICONTROL Choose a Content Fragment].

   ![image content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La liste [!UICONTROL Content Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez la [!UICONTROL Content Fragment] souhaitée, puis cliquez sur **[!UICONTROL Save]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement des [!UICONTROL Content Fragments] à importer toutes les dix minutes. Les [!UICONTROL Content Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
* Le [!UICONTROL Content Fragment] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL Content Fragment] « principale » reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Content Fragment] dans [!DNL Target].
* Vous ne pouvez pas créer de [!UICONTROL Content Fragments] à l’aide de [!DNL Adobe I/O]. Créez des [!UICONTROL Content Fragments] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL Content Fragment] dans AEM, le [!UICONTROL Content Fragment] doit être publié et exporté vers [!DNL Target] de nouveau afin que [!DNL Target] puissiez utiliser les dernières modifications.
