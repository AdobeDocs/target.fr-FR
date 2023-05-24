---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] [!UICONTROL fragments d’expérience] dans les activités  [!DNL Adobe Target] .
title: Comment utiliser les [!UICONTROL fragments d’expérience]  [!DNL Adobe Experience Manager] (AEM) ?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 7c81362a82ca6692bb8c183b8e8fc50c6329e2e8
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 100%

---

# [!UICONTROL Fragments d’expérience] AEM

Utilisez les [!UICONTROL fragments dexpérience] (XF) créés dans [!DNL Adobe Experience Manager] (AEM), au sein des activités [!DNL Target] pour faciliter l’optimisation et la personnalisation.

## Considérations

Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL fragments d’expérience] AEM dans [!DNL Target] :

* Cette fonctionnalité nécessite que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Pour plus d’informations, voir [Conditions préalables](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Ciblage d’expérience] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test multivarié] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser des [!UICONTROL fragments d’expérience] dans des activités [!DNL Target] avec le [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

Pour en savoir plus sur les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] d’AEM, consultez la [présentation sur les [!UICONTROL fragments d’expérience] et les fragments de contenu d’AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Les privilèges d’accès doivent vous avoir été attribués pour la fonctionnalité [!UICONTROL Fragments d’expérience] dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Compte [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium]

[!DNL Adobe Experience Manager] versions 6.3 et 6.4 ont atteint leur fin de vie et ne sont plus prises en charge (sauf pour les clients et clientes qui ont acheté une assistance étendue).

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Créer et configurer des [!UICONTROL fragments d’expérience] dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser les [!UICONTROL fragments d’expérience] [!DNL AEM] dans [!DNL Target], procédez comme suit :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [Intégration à Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **Adobe I/O** : documentation sur l’[Intégration à Adobe Target à l’aide d’Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=fr){target=_blank} dans le *Guide de l’utilisateur d’administration*.
* **[!DNL AEM] 6.5** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 2 : créer le fragment d’expérience

Les [!UICONTROL fragments d’expérience] sont créés dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service** : [[!UICONTROL fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **[!DNL AEM] 6.5** : [[!UICONTROL fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [[!UICONTROL fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 3 : configurer [!DNL AEM] pour partager le [!UICONTROL fragment d’expérience] avec [!DNL Target]

1. Dans [!DNL AEM], sélectionnez le [!UICONTROL fragment d’expérience] souhaité ou son dossier, puis cliquez sur **[!UICONTROL Propriétés]**.
2. Cliquez sur l’onglet **[!UICONTROL Services Cloud]** puis, dans la liste déroulante **[!UICONTROL Configuration du service cloud]**, sélectionnez **[!UICONTROL Adobe Target]**.

   L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

### Étape 4 : publier le [!UICONTROL fragment d’expérience] et l’exporter dans [!DNL Target]

Selon votre version d’[!DNL AEM], consultez les liens suivants pour obtenir des instructions détaillées :

* **AEM as a Cloud Service** : [exporter des [!UICONTROL fragments d’expérience] vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=fr){target=_blank} dans le guide *Experience Manager as a Cloud Service*.
* **[!DNL AEM] 6.5** : [exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

## Utiliser des [!UICONTROL fragments d’expérience] dans des activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Une fois les tâches précédentes effectuées, le [!UICONTROL fragment d’expérience] s’affiche sur la page [!UICONTROL Offres] de [!DNL Target].

[!DNL Target] recherche actuellement des [!UICONTROL fragments d’expérience] à importer toutes les dix minutes. Le [!UICONTROL fragment d’expérience] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.

Le [!UICONTROL fragment d’expérience] est importé dans [!DNL Target] en tant qu’offre HTML ou JSON. La version « principale » du [!UICONTROL fragment d’expérience] demeure dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment d’expérience] dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL Fragment d’expérience HTML] et [!UICONTROL Fragment d’expérience JSON], pour vous aider à distinguer les types de [!UICONTROL fragments d’expérience] exportés vers [!DNL Target].

![Filtrer par types de fragments d’expérience : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez placer le pointeur de la souris sur un [!UICONTROL fragment d’expérience] de la liste, puis cliquer sur l’icône [!UICONTROL Affichage] ![icône Infos](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur le [!UICONTROL fragment d’expérience], y compris le [!UICONTROL Nom], le [!UICONTROL Type], l’[!UICONTROL Identifiant de l’offre], le [!UICONTROL Chemin de l’offre], ainsi que des informations sur les dernières modifications. Cliquez sur l’onglet [!UICONTROL Utilisation de l’offre] pour voir les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Vous pouvez utiliser des [!UICONTROL fragments d’expérience] dans des activités [!DNL Target] avec le [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Utilisez l’intelligence artificielle, le machine learning et les Recommendations avec les [!UICONTROL fragments d’expérience] :
>
>* Pour utiliser pleinement la fonctionnalité d’IA et de ML de [!DNL Target], vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’une activité.
>
>* Les [!UICONTROL fragments d’expérience] ne sont pas pris en charge dans les activités [!DNL Recommendations]. Toutefois, pour utiliser les [!UICONTROL fragments d’expérience] pour les recommandations, vous pouvez créer une activité de [!UICONTROL test A/B] (incluant l’[!UICONTROL Affectation automatique] et le [!UICONTROL Ciblage automatique]), ou encore une activité [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Pour utiliser des [!UICONTROL fragments d’expérience] avec le compositeur d’expérience visuelle (VEC) :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience visuelle](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez l’option souhaitée pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   * [!UICONTROL Insérer avant]
   * [!UICONTROL Insérer après]
   * [!UICONTROL Permutation avec le fragment d’expérience]

   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Sélectionnez le [!UICONTROL fragment d’expérience] souhaité, puis cliquez sur **[!UICONTROL Terminé]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommandations dans une activité de test A/B ou de ciblage d’expérience :** [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md)

   Les [!UICONTROL fragments d’expérience] exportés en tant que JSON dans [!DNL Target] ne peuvent pas être utilisés dans les activités créées à l’aide du Compositeur d’expérience visuelle. Seuls les [!UICONTROL fragments d’expérience] HTML sont pris en charge dans les activités basées sur VEC. Si vous souhaitez utiliser les [!UICONTROL fragments d’expérience] JSON, utilisez-les dans les activités créées à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

**Pour utiliser des [!UICONTROL fragments d’expérience] avec le [!UICONTROL Compositeur d’expérience d’après les formulaires], procédez comme suit :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Modifier le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans [!DNL AEM] qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le [!UICONTROL fragment d’expérience] souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Informations supplémentaires

* [!DNL Target] recherche actuellement des [!UICONTROL fragments d’expérience] à importer toutes les dix minutes. Le [!UICONTROL fragment d’expérience] importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
* Le [!UICONTROL fragment d’expérience] est importé dans [!DNL Target] en tant qu’offre HTML ou JSON. La version « principale » du [!UICONTROL fragment d’expérience] demeure dans [!DNL AEM]. Vous ne pouvez pas modifier le [!UICONTROL fragment d’expérience] dans [!DNL Target].
* Vous ne pouvez pas créer de [!UICONTROL fragments d’expérience] avec [!DNL Adobe I/O]. Vous devez créer des [!UICONTROL fragments d’expérience] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL fragment d’expérience] dans AEM, le [!UICONTROL fragment d’expérience] doit être publié et exporté vers [!DNL Target] de nouveau, pour que [!DNL Target] puisse utiliser les dernières modifications.

## Supprimer les bibliothèques clientes et les HTML superflus des [!UICONTROL fragments d’expérience] exportés vers [!UICONTROL Target]

Lors de l’utilisation d’offres de [!UICONTROL fragments d’expérience] avec [!DNL Target] sur une page fournie par AEM, la page ciblée contient déjà toutes les bibliothèques clientes nécessaires. Notez également que les éléments HTML superflus dans l’offre ne sont pas non plus nécessaires.

Parfois, des pages HTML entières encapsulent le [!UICONTROL fragment d’expérience] et entraînent des problèmes. Assurez-vous que le [!UICONTROL fragment d’expérience] est une petite portion d’HTML et non une page HTML complète avec des en-têtes HTML, HEAD, BODY, etc.

Pour plus d’informations, voir l’article de blog suivant : [AEM 6.5 : supprimer les bibliothèques clientes des [!UICONTROL fragments d’expérience] exportés vers Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vidéo de formation : utiliser les [!UICONTROL fragments d’expérience] AEM avec [!DNL Adobe Target]

La vidéo suivante vous indique comment configurer et utiliser des [!UICONTROL fragments d’expérience] :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction de lien profond [!DNL AEM] évoquée à 4:54 a été supprimée.

Pour plus d’informations, consultez la section [Utiliser des [!UICONTROL fragments d’expérience] avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=fr) sur la page *Vidéos et tutoriels AEM Sites*.
