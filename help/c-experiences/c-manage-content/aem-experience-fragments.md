---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Informations sur l’utilisation des fragments d’expérience créés dans Adobe Experience Manager (AEM) dans les activités Adobe Target pour faciliter l’optimisation ou la personnalisation.
title: Fragments d’expérience Adobe Experience Manager (AEM) dans Adobe Target
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Fragments d’expérience AEM{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. Pour plus d’informations, reportez-vous à [Conditions](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.

## Aperçu {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in [!DNL Target] activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

AEM rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. AEM permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque périphérique. AEM ajuste automatiquement chaque expérience à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches d’apprentissage automatique basées sur des règles et basées sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne. With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Les fragments d’expérience représentent une énorme avancée permettant de relier les créateurs et les gestionnaires de contenu et d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Conditions {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNl Target]. En outre, vous devez utiliser AEM 6.3 avec le Service Pack approprié ou AEM 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* Adobe Experience Manager 6.4 (ou version ultérieure).
* Adobe Experience Manager 6.3 SP2 (ou version ultérieure).
* Compte Adobe Target Standard ou Adobe Target Premium.
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Création et configuration de fragments d’expérience dans AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in [!DNL Target], you must perform the following steps:

### Étape 1 : intégrer AEM à Target

Pour obtenir plus d’informations, voir :

* **AEM 6.3**: [Ouverture dans Adobe Analytics et Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) dans la documentation _Adobe Experience Manager 6.3_ .
* **AEM 6.4**: [Ouverture dans Adobe Analytics et Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) dans la documentation _Adobe Experience Manager 6.4_ .
* **AEM 6.5**: [Ouverture dans Adobe Analytics et Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) dans la documentation *Adobe Experience Manager 6.5* .

### Étape 2 : créer le fragment d’expérience

Les fragments d’expérience sont créés dans AEM. Pour obtenir plus d’informations, voir :

* **AEM 6.3**: Fragments [d’expérience](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) dans la documentation *Adobe Experience Manager 6.3* .
* **AEM 6.4**: Fragments [d’expérience](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) dans la documentation *Adobe Experience Manager 6.4* .
* **AEM 6.5**: Fragments [d’expérience](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) dans la documentation *Adobe Experience Manager 6.5* .

### Étape 3 : configurer AEM pour partager le fragment d’expérience avec Target

1. Dans AEM, sélectionnez le fragment d’expérience souhaité ou son dossier, puis cliquez sur **[!UICONTROL Propriétés]**.
2. Cliquez sur l’onglet **[!UICONTROL Services Cloud]** puis, dans la liste déroulante **[!UICONTROL Configuration du service cloud]**, sélectionnez **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

### Étape 4 : publiez le fragment d’expérience et exportez-le dans Target

Selon votre version d’AEM, reportez-vous aux liens suivants pour obtenir des instructions étape par étape :

* **AEM 6.3**: [Exportation d’un fragment d’expérience vers Target](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) dans la documentation *Adobe Experience Manager 6.3* .
* **AEM 6.4**: [Exportation d’un fragment d’expérience vers Target](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) dans la documentation *Adobe Experience Manager 6.4* .
* **AEM 6.5**: [Exportation d’un fragment d’expérience vers Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) dans la documentation *Adobe Experience Manager 6.5* .

## Utilisation des fragments d’expérience dans des activités Target {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le fragment d’expérience s’affiche sur la page [!UICONTROL Offres] de Target.

>[!NOTE]
>
>[!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. Il est à noter que la version « maîtresse » du fragment d’expérience demeure dans AEM. Vous ne pouvez pas modifier le fragment d’expérience dans Target.

You can hover over an experience fragment in the list, then click the View icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**Pour utiliser des fragments d’expérience avec le compositeur d’expérience visuelle (VEC) :**

1. In [!DNL Target], while creating or editing an experience in the [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), click the location on the page where you want to insert AEM content, then select the desired option to display the [!UICONTROL Choose an Experience Fragment] list.

   * [!UICONTROL Insérer avant]
   * [!UICONTROL Insérer après]
   * [!UICONTROL Permutation avec le fragment d’expérience]
   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans AEM qui est désormais disponible en mode natif dans [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **Affectation automatique :** [Affectation automatique](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [Ciblage automatique pour les expériences personnalisées](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Test multivarié (MVT) :** [création d’un test multivarié](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations :** [création d’une activité de recommandations](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F).

**Pour utiliser des fragments d’expérience avec le compositeur d’expérience d’après les formulaires :**

1. In [!DNl Target], while creating or editing an experience in the [Form-Based Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), select the location on the page where you want to insert AEM content, then select **[!UICONTROL Change Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   ![](assets/experience_fragment_list.png)

   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans AEM qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Considérations {#considerations}

* [!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. Il est à noter que la version « maîtresse » du fragment d’expérience demeure dans AEM. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].
* Vous pouvez importer des offres JSON sous forme de fragments d’expérience dans [!DNL Target]. Toutefois, ces offres sont importées en tant qu’offres HTML. Les offres JSON (fragments d’expérience) ne sont actuellement pas entièrement prises en charge dans l’ [!DNL Target] interface utilisateur.

## Training video: Using AEM Experience Fragments with Adobe Target {#section_C0EDC54063464F41A182492D2045BC64} ![Tutorial badge](/help/assets/overview.png)

La vidéo suivante vous explique comment configurer et utiliser des fragments d’expérience :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

Pour plus d’informations, voir [Utilisation de fragments d’expérience avec Adobe Target](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) sur la page Vidéos et didacticiels *des sites* AEM.
