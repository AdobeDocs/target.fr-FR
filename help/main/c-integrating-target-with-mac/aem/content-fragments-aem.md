---
keywords: experience;json;aem;adobe experience manager;exporter vers adobe target;fragments de contenu;fragments;CF;cf,découplé;personnalisation;expérimentation
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] dans les activités  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments] ?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 21%

---

# AEM [!UICONTROL Content Fragments]

Utilisez [!UICONTROL Content Fragments] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter la personnalisation et l’expérimentation sans interface.

## Considérations

Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Content Fragments] dans [!DNL Target] :

* Cette fonctionnalité est réservée aux clientes et clients [!DNL Adobe Experience Manager as a Cloud Service]. Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* consommer [!UICONTROL Content Fragments] dans les activités [!DNL Target] à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

Pour en savoir plus sur AEM [!UICONTROL Content Fragments] et [!UICONTROL Experience Fragments], consultez [AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] vue d&#39;ensemble](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Vous devez utiliser [[!DNL AEM]  as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr){target=_blank}. Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Configuration et utilisation de [!UICONTROL Content Fragments] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour exporter [!UICONTROL Content Fragments] afin de l&#39;utiliser dans des activités [!DNL Target], vous devez effectuer quelques étapes préliminaires dans AEM. Pour plus d’informations, consultez [Exportation de fragments de contenu vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=fr){target=_blank} dans la *documentation d’Experience Manager as a Cloud Service*.

Pour plus d&#39;informations sur la conception, la création, l&#39;organisation et la publication [!UICONTROL Content Fragments], voir [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=fr){target=_blank} et [Utilisation de fragments de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=fr){target=_blank} dans la [documentation as a Cloud Service Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=fr){target=_blank}}.

## Utilisation de [!UICONTROL Content Fragments] dans les activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le [!UICONTROL Content Fragment] s’affiche sur la page [!UICONTROL Offers] de [!DNL Target].

[!DNL Target] recherche actuellement [!UICONTROL Content Fragments] à importer toutes les dix minutes. Les [!UICONTROL Content Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes, mais cette période devrait être raccourcie à l&#39;avenir.

[!UICONTROL Content Fragment] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL Content Fragment] &quot;principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Content Fragment] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL HTML XFs], [!UICONTROL JSON XFs] et [!UICONTROL Content Fragments] pour vous aider à distinguer les différents types d&#39;offres qui sont exportés vers [!DNL Target].

![Filtrer par types de fragments de contenu : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez survoler un [!UICONTROL Content Fragment] dans la liste, puis cliquer sur l’icône [!UICONTROL View] ![Icône d’informations](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur le [!UICONTROL Content Fragment], y compris ses [!UICONTROL AEM path] et [!UICONTROL AEM deep link]. Cliquez sur l’onglet [!UICONTROL Offer Usage] pour afficher les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment de contenu](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Vous pouvez utiliser [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser [!UICONTROL Content Fragments] dans les activités [!DNL Target] à l’aide du [compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Content Fragments] sont exportés en tant que JSON dans [!DNL Target] et ne peuvent pas être utilisés dans les activités créées à l’aide du VEC.

>[!TIP]
>
>Utiliser l’intelligence artificielle, l’apprentissage automatique et des recommandations avec [!UICONTROL Content Fragments] :
>
>* Pour utiliser pleinement la fonctionnalité [!DNL Target] AI et ML, vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité [!UICONTROL A/B Test].
>
>* [!UICONTROL Content Fragments] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Cependant, pour utiliser [!UICONTROL Content Fragments] pour les recommandations, vous pouvez créer une activité [!UICONTROL A/B Test] (y compris [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) ou une activité [!UICONTROL Experience Targeting] (XT) et [inclure des recommandations en tant qu&#39;offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour consommer [!UICONTROL Content Fragments] à l’aide de [!UICONTROL Form-based Experience Composer] :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement sur la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Change Content Fragment]** pour afficher la liste [!UICONTROL Choose a Content Fragment].

   ![image content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La liste [!UICONTROL Content Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le [!UICONTROL Content Fragment] de votre choix, puis cliquez sur **[!UICONTROL Save]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement [!UICONTROL Content Fragments] à importer toutes les dix minutes. Les [!UICONTROL Content Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes, mais cette période devrait être raccourcie à l&#39;avenir.
* [!UICONTROL Content Fragment] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL Content Fragment] &quot;principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Content Fragment] dans [!DNL Target].
* Vous ne pouvez pas créer [!UICONTROL Content Fragments] à l’aide de [!DNL Adobe I/O]. Créez [!UICONTROL Content Fragments] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL Content Fragment] dans AEM, le [!UICONTROL Content Fragment] doit à nouveau être publié et exporté vers [!DNL Target] afin que [!DNL Target] puisse utiliser les dernières modifications.
