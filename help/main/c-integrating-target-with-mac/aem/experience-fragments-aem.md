---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] dans les activités  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments] ?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 7c81362a82ca6692bb8c183b8e8fc50c6329e2e8
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 36%

---

# AEM [!UICONTROL Experience Fragments]

Utilisez [!UICONTROL Experience Fragments] (XF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation et la personnalisation.

## Considérations

Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Experience Fragments] dans [!DNL Target] :

* Cette fonctionnalité nécessite que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser [!UICONTROL Experience Fragments] dans des activités [!DNL Target] à l’aide du [ compositeur d’expérience visuelle ](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et du [ compositeur d’expérience d’après les formulaires ](/help/main/c-experiences/form-experience-composer.md).

Pour en savoir plus sur AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments], consultez la [présentation d&#39;AEM [!UICONTROL Experience Fragments] et de fragments de contenu ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Vous devez disposer de la fonctionnalité [!UICONTROL Experience Fragments] dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Compte [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium]

[!DNL Adobe Experience Manager] versions 6.3 et 6.4 ont atteint leur fin de vie et ne sont plus prises en charge (sauf pour les clients et clientes qui ont acheté une assistance étendue).

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Création et configuration de [!UICONTROL Experience Fragments] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser [!DNL AEM] [!UICONTROL Experience Fragments] dans [!DNL Target], vous devez effectuer les étapes suivantes :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [Intégration à Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **Adobe I/O** : documentation sur l’[Intégration à Adobe Target à l’aide d’Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=fr){target=_blank} dans le *Guide de l’utilisateur d’administration*.
* **[!DNL AEM] 6.5** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 2 : créer le fragment d’expérience

[!UICONTROL Experience Fragments] sont créés dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=fr){target=_blank} dans le guide *as a Cloud Service Experience Manager*.
* **[!DNL AEM]6.5** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4** : [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation *Adobe Experience Manager 6.4*.

### Étape 3 : configurer [!DNL AEM] pour partager le [!UICONTROL Experience Fragment] avec [!DNL Target]

1. Dans [!DNL AEM], sélectionnez le dossier [!UICONTROL Experience Fragment] ou son dossier, puis cliquez sur **[!UICONTROL Properties]**.
2. Cliquez sur l’onglet **[!UICONTROL Cloud Services]**, puis, dans la liste déroulante **[!UICONTROL Cloud Service Configuration]**, sélectionnez **[!UICONTROL Adobe Target]**.

   L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Save & Close]**.

### Étape 4 : Publish le [!UICONTROL Experience Fragment] et l’exporter dans [!DNL Target]

Selon votre version d’[!DNL AEM], consultez les liens suivants pour obtenir des instructions détaillées :

* **AEM as a Cloud Service** : [ export de [!UICONTROL Experience Fragments] vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **[!DNL AEM] 6.5** : [exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

## Utilisation de [!UICONTROL Experience Fragments] dans les activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le [!UICONTROL Experience Fragment] s’affiche sur la page [!UICONTROL Offers] de [!DNL Target].

[!DNL Target] recherche actuellement [!UICONTROL Experience Fragments] à importer toutes les dix minutes. Les [!UICONTROL Experience Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes, mais cette période devrait être raccourcie à l&#39;avenir.

[!UICONTROL Experience Fragment] est importé dans [!DNL Target] en tant qu’offre d’HTML ou JSON. La version [!UICONTROL Experience Fragment] &quot;principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Experience Fragment] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL HTML XFs] et [!UICONTROL JSON XFs] pour vous aider à distinguer les types [!UICONTROL Experience Fragment] qui sont exportés vers [!DNL Target].

![Filtrer par types de fragments d’expérience : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez survoler un [!UICONTROL Experience Fragment] dans la liste, puis cliquer sur l’icône [!UICONTROL View] ![Icône d’informations](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur le [!UICONTROL Experience Fragment], y compris ses [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] et les informations sur les dernières modifications. Cliquez sur l’onglet [!UICONTROL Offer Usage] pour afficher les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Vous pouvez utiliser [!UICONTROL Experience Fragments] dans des activités [!DNL Target] à l’aide du [ compositeur d’expérience visuelle ](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et du [ compositeur d’expérience d’après les formulaires ](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Utiliser l’intelligence artificielle, l’apprentissage automatique et des recommandations avec [!UICONTROL Experience Fragments] :
>
>* Pour utiliser pleinement la fonctionnalité d’IA et de ML de [!DNL Target], vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité.
>
>* [!UICONTROL Experience Fragments] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Cependant, pour utiliser [!UICONTROL Experience Fragments] pour les recommandations, vous pouvez créer une activité [!UICONTROL A/B Test] (y compris [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) ou une activité [!UICONTROL Experience Targeting] (XT) et [inclure des recommandations en tant qu&#39;offre](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Pour consommer [!UICONTROL Experience Fragments] à l’aide du VEC :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience visuelle](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez l’option souhaitée pour afficher la liste [!UICONTROL Choose an Experience Fragment].

   * [!UICONTROL Insert Before]
   * [!UICONTROL Insert After]
   * [!UICONTROL Swap with Experience Fragment]

   La liste [!UICONTROL Experience Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Swap with Experience Fragment] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Sélectionnez le [!UICONTROL Experience Fragment] de votre choix, puis cliquez sur **[!UICONTROL Done]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommandations dans une activité de test A/B ou de ciblage d’expérience :** [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Experience Fragments] exporté en tant que JSON dans [!DNL Target] ne peut pas être utilisé dans les activités créées à l’aide du VEC ; seul l’HTML [!UICONTROL Experience Fragments] est pris en charge dans les activités basées sur le VEC. Si vous souhaitez utiliser JSON [!UICONTROL Experience Fragments], utilisez-les dans les activités créées à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

**Pour consommer [!UICONTROL Experience Fragments] à l’aide de [!UICONTROL Form-based Experience Composer] :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement sur la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Change Experience Fragment]** pour afficher la liste [!UICONTROL Choose an Experience Fragment].

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   La liste [!UICONTROL Experience Fragment] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le [!UICONTROL Experience Fragment] de votre choix, puis cliquez sur **[!UICONTROL Save]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement [!UICONTROL Experience Fragments] à importer toutes les dix minutes. Les [!UICONTROL Experience Fragment] importés doivent être disponibles dans [!DNL Target] dans les dix minutes, mais cette période devrait être raccourcie à l&#39;avenir.
* [!UICONTROL Experience Fragment] est importé dans [!DNL Target] en tant qu’offre d’HTML ou JSON. La version [!UICONTROL Experience Fragment] &quot;principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL Experience Fragment] dans [!DNL Target].
* Vous ne pouvez pas créer [!UICONTROL Experience Fragments] à l’aide de [!DNL Adobe I/O]. Créez [!UICONTROL Experience Fragments] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL Experience Fragment] dans AEM, le [!UICONTROL Experience Fragment] doit à nouveau être publié et exporté vers [!DNL Target] afin que [!DNL Target] puisse utiliser les dernières modifications.

## Suppression des bibliothèques clientes et des HTMLS superflus de [!UICONTROL Experience Fragments] exportés vers [!UICONTROL Target]

Lors de l’utilisation de [!UICONTROL Experience Fragment] offres avec [!DNL Target] sur une page fournie par AEM, la page ciblée contient déjà toutes les bibliothèques clientes nécessaires. Notez également que les éléments HTML superflus dans l’offre ne sont pas non plus nécessaires.

Parfois, des pages d’HTML entières encapsulent le [!UICONTROL Experience Fragment] et provoquent des problèmes. Assurez-vous que le [!UICONTROL Experience Fragment] est un petit HTML et non une page d’HTML complète avec HTML, HEAD, CORPS, etc.

Pour plus d’informations, voir l’article de blog suivant : [AEM 6.5 : suppression des bibliothèques clientes de [!UICONTROL Experience Fragments] exportées vers Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vidéo de formation : utilisation de AEM [!UICONTROL Experience Fragments] avec [!DNL Adobe Target]

La vidéo suivante montre comment configurer et utiliser [!UICONTROL Experience Fragments] :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction de lien profond [!DNL AEM] évoquée à 4:54 a été supprimée.

Pour plus d’informations, voir [Utilisation de [!UICONTROL Experience Fragments] avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=fr) sur la page *Vidéos et Tutorials AEM Sites* .
