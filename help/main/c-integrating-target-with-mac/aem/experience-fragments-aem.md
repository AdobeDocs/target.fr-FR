---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] dans les  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager]  (AEM) [!UICONTROL Experience Fragments] ?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 31%

---

# [!UICONTROL Experience Fragments] AEM

Utilisez les [!UICONTROL Experience Fragments] (XF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation et la personnalisation.

## Considérations

Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL Experience Fragments] AEM dans [!DNL Target] :

* Cette fonctionnalité nécessite que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Multivariate Test] (VMT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser des [!UICONTROL Experience Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

Pour en savoir plus sur AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments], consultez [Présentation des [!UICONTROL Experience Fragments] AEM et des fragments de contenu](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Les privilèges d’accès doivent vous avoir été attribués pour la fonctionnalité [!UICONTROL Experience Fragments] dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Compte [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium]

[!DNL Adobe Experience Manager] versions 6.3 et 6.4 ont atteint leur fin de vie et ne sont plus prises en charge (sauf pour les clients et clientes qui ont acheté une assistance étendue).

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Création et configuration de [!UICONTROL Experience Fragments] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser [!DNL AEM] [!UICONTROL Experience Fragments] dans [!DNL Target], procédez comme suit :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [Intégration à Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **Adobe Developer** : [Intégration à Adobe Target à l’aide d’Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank} dans la documentation du *Guide d’utilisation d’administration*.
* **[!DNL AEM] 6.5** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 2 : créer le fragment d’expérience

Les [!UICONTROL Experience Fragments] sont créées dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation de *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation de *Adobe Experience Manager 6.4*.

### Étape 3 : configurer [!DNL AEM] pour partager le [!UICONTROL Experience Fragment] avec [!DNL Target]

1. Dans [!DNL AEM], sélectionnez le [!UICONTROL Experience Fragment] souhaité ou son dossier, puis cliquez sur **[!UICONTROL Properties]**.
2. Cliquez sur l’onglet **[!UICONTROL Cloud Services]** puis, dans la liste déroulante **[!UICONTROL Cloud Service Configuration]** , sélectionnez **[!UICONTROL Adobe Target]**.

   L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Save & Close]**.

### Étape 4 : publiez le [!UICONTROL Experience Fragment] et exportez-le dans [!DNL Target]

Selon votre version d’[!DNL AEM], consultez les liens suivants pour obtenir des instructions détaillées :

* **AEM as a Cloud Service** : [Exportation de [!UICONTROL Experience Fragments] vers Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **[!DNL AEM] 6.5** : [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

## Utilisation de [!UICONTROL Experience Fragments] dans les activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le [!UICONTROL Experience Fragment] s’affiche sur la page [!UICONTROL Offers] dans [!DNL Target].

[!DNL Target] recherche actuellement des [!UICONTROL Experience Fragments] à importer toutes les dix minutes. Les [!UICONTROL Experience Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.

Le [!UICONTROL Experience Fragment] est importé dans [!DNL Target] en tant qu’offre HTML ou JSON. La version [!UICONTROL Experience Fragment] « principale » reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Experience Fragment] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL HTML XFs] et [!UICONTROL JSON XFs] pour vous aider à distinguer les types de [!UICONTROL Experience Fragment] exportés vers [!DNL Target].

![Filtrer par types de fragments d’expérience : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez placer le pointeur de la souris sur un [!UICONTROL Experience Fragment] de la liste, puis cliquer sur l’icône [!UICONTROL View] ![icône Infos](/help/main/assets/icons/InfoOutline.svg) pour afficher des informations supplémentaires sur le [!UICONTROL Experience Fragment], notamment ses informations de [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] et dernières modifications. Cliquez sur [!UICONTROL [!UICONTROL View Full Details]] pour afficher les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Vous pouvez utiliser des [!UICONTROL Experience Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Utilisez l’intelligence artificielle, le machine learning et les recommandations avec [!UICONTROL Experience Fragments] :
>
>* Pour utiliser pleinement la fonctionnalité d’IA et de ML de [!DNL Target], vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité.
>
>* [!UICONTROL Experience Fragments] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Toutefois, pour utiliser des [!UICONTROL Experience Fragments] pour les recommandations, vous pouvez créer une activité de [!UICONTROL A/B Test] (y compris [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) ou une activité de [!UICONTROL Experience Targeting] (XT) et [inclure des recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour consommer des [!UICONTROL Experience Fragments] à l’aide du VEC :**

1. En [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience visuelle](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer [!DNL AEM] contenu, puis cliquez sur **[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]** pour afficher la boîte de dialogue [!UICONTROL Experience Fragment].

   La boîte de dialogue [!UICONTROL Experience Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Replace Content] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Sélectionnez la [!UICONTROL Experience Fragment] souhaitée, puis cliquez sur **[!UICONTROL Add]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommandations dans une activité de test A/B ou de ciblage d’expérience :** [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md)

   Les [!UICONTROL Experience Fragments] exportées au format JSON dans [!DNL Target] ne peuvent pas être utilisées dans les activités créées à l’aide du compositeur d’expérience visuelle (VEC) ; seules les [!UICONTROL Experience Fragments] HTML sont prises en charge dans les activités basées sur VEC. Si vous souhaitez utiliser des [!UICONTROL Experience Fragments] JSON, utilisez-les dans les activités créées à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

**Pour consommer des [!UICONTROL Experience Fragments] à l’aide de l’[!UICONTROL Form-based Experience Composer] :**

1. En [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement de la page où vous souhaitez insérer [!DNL AEM] contenu, cliquez sur l’icône **[!UICONTROL More Details]** ( ![icône Plus de détails](/help/main/assets/icons/MoreSmall.svg) ), puis sélectionnez **[!UICONTROL Change Experience Fragment]** pour afficher la boîte de dialogue [!UICONTROL Change Experience Fragment].

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   La boîte de dialogue [!UICONTROL Experience Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez la [!UICONTROL Experience Fragment] souhaitée, puis cliquez sur **[!UICONTROL Add]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement des [!UICONTROL Experience Fragments] à importer toutes les dix minutes. Les [!UICONTROL Experience Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
* Le [!UICONTROL Experience Fragment] est importé dans [!DNL Target] en tant qu’offre HTML ou JSON. La version [!UICONTROL Experience Fragment] « principale » reste en [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Experience Fragment] dans [!DNL Target].
* Vous ne pouvez pas créer de [!UICONTROL Experience Fragments] à l’aide de [!DNL Adobe Developer]. Créez des [!UICONTROL Experience Fragments] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL Experience Fragment] dans AEM, le [!UICONTROL Experience Fragment] doit être publié et exporté vers [!DNL Target] de nouveau afin que [!DNL Target] puissiez utiliser les dernières modifications.

## Suppression des bibliothèques clientes et des HTML superflues de [!UICONTROL Experience Fragments] exportées vers [!UICONTROL Target]

Lors de l’utilisation d’offres [!UICONTROL Experience Fragment] avec [!DNL Target] sur une page fournie par AEM, la page ciblée contient déjà les bibliothèques clientes nécessaires. Notez également que les éléments HTML superflus dans l’offre ne sont pas non plus nécessaires.

Parfois, des pages HTML entières encapsulent le [!UICONTROL Experience Fragment] et entraînent des problèmes. Assurez-vous que le [!UICONTROL Experience Fragment] est un petit morceau d’HTML et non une page HTML complète avec HTML, HEAD, BODY, etc.

Pour plus d’informations, consultez l’article de blog suivant : [AEM 6.5 : suppression des bibliothèques clientes de [!UICONTROL Experience Fragments] exportées vers Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vidéo de formation : Utilisation d’AEM [!UICONTROL Experience Fragments] avec [!DNL Adobe Target]

La vidéo suivante vous explique comment configurer et utiliser [!UICONTROL Experience Fragments] :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction de lien profond [!DNL AEM] décrite à la section 4:54 a été supprimée.

Pour plus d’informations, reportez-vous à la section [Utilisation de [!UICONTROL Experience Fragments] avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=fr) sur la page *Vidéos et tutoriels AEM Sites*.
