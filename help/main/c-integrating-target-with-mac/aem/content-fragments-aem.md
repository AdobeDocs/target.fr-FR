---
keywords: experience;json;aem;adobe experience manager;exporter vers adobe target;fragments de contenu;fragments;CF;cf,découplé;personnalisation;expérimentation
description: Découvrez comment utiliser  [!DNL Adobe Experience Manager] [!UICONTROL &#x200B; fragments de contenu &#x200B;] dans  [!DNL Adobe Target]  activités.
title: Comment utiliser  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL fragments de contenu] ?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 775
ht-degree: 20%

---

# AEM [!UICONTROL fragments de contenu]

Utilisez les [!UICONTROL fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter la personnalisation et l’expérimentation découplées.

## Considérations

Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL fragments de contenu] dans [!DNL Target] :

* Cette fonctionnalité est réservée aux clientes et clients [!DNL Adobe Experience Manager as a Cloud Service]. Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Ciblage d’expérience] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test multivarié] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommandations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser [!UICONTROL fragments de contenu] dans des activités [!DNL Target] à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC).

Pour en savoir plus sur AEM [!UICONTROL Fragments de contenu] et [!UICONTROL Fragments d’expérience], consultez [Présentation d’AEM [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu]](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Vous devez utiliser [[!DNL AEM] &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr){target=_blank}. Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Configuration et utilisation de [!UICONTROL fragments de contenu] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour exporter des [!UICONTROL fragments de contenu] et les utiliser dans des activités [!DNL Target], vous devez effectuer quelques étapes préliminaires dans AEM. Pour plus d’informations, consultez [Exportation de fragments de contenu vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=fr){target=_blank} dans la *documentation Experience Manager as a Cloud Service*.

Pour plus d’informations sur la conception, la création, l’organisation et la publication de [!UICONTROL fragments de contenu], consultez [[!UICONTROL fragments de contenu]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=fr){target=_blank} et [utilisation de fragments de contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=fr){target=_blank} dans la [documentation d’Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=fr){target=_blank}.

## Utilisation de [!UICONTROL fragments de contenu] dans des activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le [!UICONTROL fragment de contenu] s’affiche sur la page [!UICONTROL Offres] dans [!DNL Target].

[!DNL Target] recherche actuellement des [!UICONTROL fragments de contenu] à importer toutes les dix minutes. Le [!UICONTROL fragment de contenu] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.

Le [!UICONTROL &#x200B; fragment de contenu &#x200B;] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL principale] Fragment de contenu, reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment de contenu] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL fragments d’expérience &#x200B;], [!UICONTROL fragments d’expérience JSON] et [!UICONTROL fragments de contenu] pour vous aider à distinguer les différents types d’offres exportés vers [!DNL Target].

![Filtrer par types de fragments de contenu : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez placer le pointeur de la souris sur un [!UICONTROL fragment d’expérience] de la liste, puis cliquer sur l’icône [!UICONTROL Affichage] ![Icône Infos](/help/main/assets/icons/InfoOutline.svg) pour afficher des informations supplémentaires sur le [!UICONTROL fragment de contenu], y compris ses informations [!UICONTROL Nom], [!UICONTROL Type], [!UICONTROL Identifiant de l’offre], [!UICONTROL Chemin de l’offre], ainsi que des informations sur les dernières modifications. Cliquez sur [!UICONTROL [!UICONTROL Afficher tous les détails]] pour afficher les activités qui font référence à cette offre.

Vous pouvez utiliser [!UICONTROL fragments de contenu] dans des activités [!DNL Target] à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). Les [!UICONTROL fragments de contenu] sont exportés au format JSON dans [!DNL Target] et ne peuvent pas être utilisés dans les activités créées à l’aide du compositeur d’expérience visuelle.

>[!TIP]
>
>Utilisez l’intelligence artificielle, le machine learning et les recommandations avec les [!UICONTROL fragments de contenu] :
>
>* Pour utiliser pleinement la fonctionnalité d’IA dédiée aux [!DNL Target] et de ML de , vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité [!UICONTROL Test A/B].
>
>* Les [!UICONTROL fragments de contenu] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Toutefois, pour utiliser [!UICONTROL Fragments de contenu] pour les recommandations, vous pouvez créer une activité [!UICONTROL Test A/B] (y compris [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]) ou une activité [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour utiliser [!UICONTROL Fragments de contenu] avec le [!UICONTROL Compositeur d’expérience d’après les formulaires]:**

1. En [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer [!DNL AEM] contenu, puis sélectionnez **[!UICONTROL Modifier le fragment de contenu]** pour afficher la liste [!UICONTROL Choisir un fragment de contenu].

   ![image content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La liste [!UICONTROL Fragment de contenu] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le [!UICONTROL fragment de contenu] souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement des [!UICONTROL fragments de contenu] à importer toutes les dix minutes. Le [!UICONTROL fragment de contenu] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
* Le [!UICONTROL &#x200B; fragment de contenu &#x200B;] est importé dans [!DNL Target] en tant qu’offre JSON. La version [!UICONTROL principale] Fragment de contenu, reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment de contenu] dans [!DNL Target].
* Vous ne pouvez pas créer de [!UICONTROL fragments de contenu] à l’aide de [!DNL Adobe I/O]. Créez des [!UICONTROL fragments de contenu] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL fragment de contenu] dans AEM, le [!UICONTROL fragment de contenu] doit à nouveau être publié et exporté vers [!DNL Target] afin que [!DNL Target] puissiez utiliser les dernières modifications.
