---
keywords: experience;json;aem;adobe experience manager;exporter vers adobe target;fragments de contenu;fragments;CF;cf,découplé;personnalisation;expérimentation
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] [!UICONTROL fragments de contenu] dans les activités  [!DNL Adobe Target] .
title: Comment utiliser les [!UICONTROL fragments de contenu]  [!DNL Adobe Experience Manager] (AEM) ?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: ht
source-wordcount: '701'
ht-degree: 100%

---

# [!UICONTROL Fragments de contenu] AEM

Utilisez les [!UICONTROL fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter la personnalisation et l’expérimentation découplées.

## Considérations

Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL fragments de contenu] d’AEM dans [!DNL Target] :

* Cette fonctionnalité est réservée aux clientes et clients [!DNL Adobe Experience Manager as a Cloud Service]. Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Ciblage d’expérience] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test multivarié] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser les [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser les [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [!UICONTROL Compositeur d’expérience visuelle] (VEC).

Pour en savoir plus sur les [!UICONTROL fragments de contenu] et les [!UICONTROL fragments d’expérience] AEM, voir la [présentation sur les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Vous devez utiliser [[!DNL AEM]  as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr){target=_blank}. Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Configurer et utiliser les [!UICONTROL fragments de contenu] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour exporter les [!UICONTROL fragments de contenu] et les utiliser dans les activités [!DNL Target], vous devez effectuer quelques étapes préliminaires dans AEM. Pour plus d’informations, consultez [Exportation de fragments de contenu vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=fr){target=_blank} dans la *documentation d’Experience Manager as a Cloud Service*.

Pour plus d’informations sur la conception, la création, l’organisation et la publication de [!UICONTROL fragments de contenu], voir [[!UICONTROL Fragments de contenu]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=fr){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=fr){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=fr){target=_blank}.

## Utiliser des [!UICONTROL fragments de contenu] dans des activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Une fois les tâches précédentes effectuées, le [!UICONTROL fragment de contenu] s’affiche sur la page [!UICONTROL Offres] de [!DNL Target].

[!DNL Target] recherche actuellement des [!UICONTROL fragments de contenu] à importer toutes les dix minutes. Le [!UICONTROL fragment de contenu] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette durée devrait être réduite à l’avenir.

Le [!UICONTROL fragment de contenu] est importé dans [!DNL Target] comme offre JSON. La version « principale » du [!UICONTROL fragment de contenu] reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment de contenu] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL fragments d’expérience HTML], [!UICONTROL fragments d’expérience JSON] et [!UICONTROL fragments de contenu], pour vous aider à distinguer les différents types d’offres exportés vers [!DNL Target].

![Filtrer par types de fragments de contenu : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez pointer sur un [!UICONTROL fragment de contenu] dans la liste, puis cliquer sur l’icône [!UICONTROL Affichage] ![Icône Infos](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur le [!UICONTROL fragment de contenu], comme le [!UICONTROL Chemin AEM] et le [!UICONTROL lien profond AEM]. Cliquez sur l’onglet [!UICONTROL Utilisation de l’offre] pour voir les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment de contenu](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Vous pouvez utiliser les [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous *ne pouvez pas* utiliser les [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). Les [!UICONTROL fragments de contenu] sont exportés sous la forme JSON dans [!DNL Target] et ne peuvent pas être utilisés dans les activités créées à l’aide du Compositeur d’expérience visuelle.

>[!TIP]
>
>Utiliser l’intelligence artificielle, le machine learning et les recommandations avec les [!UICONTROL fragments de contenu] :
>
>* Pour tirer pleinement parti de la fonctionnalité d’IA et de ML de [!DNL Target], sélectionnez [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’un [!UICONTROL test A/B].
>
>* Les [!UICONTROL fragments de contenu] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Toutefois, pour utiliser les [!UICONTROL fragments de contenu] pour les recommandations, vous pouvez créer une activité de [!UICONTROL test A/B] (avec [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]) ou une activité [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour utiliser des [!UICONTROL fragments de contenu] avec le [!UICONTROL Compositeur d’expérience d’après les formulaires] :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Modifier le fragment de contenu]** pour afficher la liste [!UICONTROL Choisir un fragment de contenu].

   ![image content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   La liste [!UICONTROL Fragment de contenu] répertorie tout le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le [!UICONTROL fragment de contenu] souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement des [!UICONTROL fragments de contenu] à importer toutes les dix minutes. Le [!UICONTROL fragment de contenu] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette durée devrait être réduite à l’avenir.
* Le [!UICONTROL fragment de contenu] est importé dans [!DNL Target] comme offre JSON. La version « principale » du [!UICONTROL fragment de contenu] reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment de contenu] dans [!DNL Target].
* Vous ne pouvez pas créer de [!UICONTROL fragments de contenu] avec [!DNL Adobe I/O]. Créez des [!UICONTROL fragments de contenu] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL fragment de contenu] dans AEM, le [!UICONTROL fragment de contenu] doit à nouveau être publié et exporté vers [!DNL Target], pour que [!DNL Target] puisse utiliser les dernières modifications.
