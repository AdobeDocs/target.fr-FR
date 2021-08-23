---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser AEM fragments d’expérience dans les activités Adobe [!DNL Target] . Combinez la facilité d’utilisation et la puissance de l’AEM avec de puissantes fonctionnalités d’IA et d’ML dans  [!DNL Target].
title: Comment utiliser les fragments d’expérience Adobe Experience Manager (AEM) ?
feature: Offres et expériences
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: c9c335c241727c4eff1d27f52853e32b8d18b6a5
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 30%

---

# Fragments d’expérience AEM

Informations sur l’utilisation des fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Cette fonctionnalité requiert que vous soyez un client [!DNL Adobe Experience Manager] ([!DNL AEM]). Pour plus d’informations, reportez-vous à [Conditions](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.

## Aperçu {#section_95A91830530F493B81C5C9CDB9B783EA}

L’utilisation de fragments d’expérience créés dans [!DNL AEM] dans les activités [!DNL Target] vous permet de combiner la facilité d’utilisation et la puissance de [!DNL AEM] avec de puissantes fonctionnalités d’intelligence automatisée (AI) et d’apprentissage automatique dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches d’apprentissage automatique basées sur des règles et basées sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne. Avec [!DNL Target], vous pouvez facilement configurer et exécuter les activités [Test A/B](/help/c-activities/t-test-ab/test-ab.md) et [Multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) pour déterminer les meilleures offres, contenus et expériences.

Les fragments d’expérience représentent une énorme avancée permettant de relier les créateurs et les gestionnaires de contenu et d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Conditions {#section_AE6F0971E1574B3AA324003599B96E5A}

Les privilèges d’accès doivent vous avoir été attribués pour la fonctionnalité de fragments d’expérience dans [!DNL Target]. De plus, vous devez utiliser [!DNL AEM] 6.3 avec le Service Pack approprié ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager] 6.4 (ou version ultérieure).
* [!DNL Adobe Experience Manager] 6.3 SP2 (ou version ultérieure).
* [!DNL Adobe Target Standard] ou  [!DNL Adobe Target Premium] .
* Contactez [l’assistance clientèle d’Adobe Target](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour activer l’intégration et vous fournir des détails d’authentification.

## Création et configuration de fragments d’expérience dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser des fragments d’expérience [!DNL AEM] dans [!DNL Target], procédez comme suit :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **Adobe I/O** :  [Intégration à Adobe Target à l’aide de l’Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html)  dans le  _guide d’_ administration des utilisateurs.
* **[!DNL AEM]6.3** :  [Accès à Adobe Analytics et Adobe ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) Target dans la documentation  _Adobe Experience Manager 6.3_ .
* **[!DNL AEM]6.4** :  [Accès à Adobe Analytics et Adobe ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) Target dans la documentation d’ _Adobe Experience Manager 6.4_ .
* **[!DNL AEM]6.5** :  [Accès à Adobe Analytics et Adobe ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en) Target dans la documentation  *Adobe Experience Manager 6.5* .

### Étape 2 : créer le fragment d’expérience

Les fragments d’expérience sont créés dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **[!DNL AEM]6.3** :  [Fragments d’expérience ](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) dans la documentation d’ *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4** :  [Fragments d’expérience ](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) dans la documentation d’ *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5** :  [Fragments d’expérience ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) dans la documentation d’ *Adobe Experience Manager 6.5* .

### Étape 3 : Configurez [!DNL AEM] pour partager le fragment d’expérience avec [!DNL Target]

1. Dans [!DNL AEM], sélectionnez le fragment d’expérience souhaité ou son dossier, puis cliquez sur **[!UICONTROL Propriétés]**.
2. Cliquez sur l’onglet **[!UICONTROL Services Cloud]** puis, dans la liste déroulante **[!UICONTROL Configuration du service cloud]**, sélectionnez **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >L’étape précédente suppose qu’une personne de votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

### Étape 4 : publiez le fragment d’expérience et exportez-le dans [!DNL Target]

Selon votre version de [!DNL AEM], consultez les liens suivants pour obtenir des instructions étape par étape :

* **[!DNL AEM]6.3** :  [Exportation d’un fragment d’expérience vers ](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) Target dans la documentation  *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4** :  [Exportation d’un fragment d’expérience vers ](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) Target dans la documentation  *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5** :  [Exportation d’un fragment d’expérience vers ](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) Target dans la documentation  *Adobe Experience Manager 6.5* .

## Utilisation de fragments d’expérience dans des activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le fragment d’expérience s’affiche sur la page [!UICONTROL Offres] de [!DNL Target].

>[!NOTE]
>
>[!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans un délai de dix minutes, mais cette période doit être raccourcie à l’avenir.

>[!IMPORTANT]
>
>Le fragment d’expérience est actuellement importé dans [!DNL Target] en tant qu’offre HTML. Notez que la version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].

Vous pouvez placer le pointeur de la souris sur un fragment d’expérience dans la liste, puis cliquer sur l’icône [!UICONTROL Afficher] ![Icône d’affichage](assets/icon_info.png) pour afficher des informations supplémentaires sur le fragment d’expérience, notamment son URL de diffusion d’offres publiques et son chemin d’accès [!DNL AEM].

Vous pouvez utiliser des fragments d’expérience dans des activités [!DNL Target] à l’aide du [compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou du [compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Pour utiliser pleinement la fonctionnalité [!DNL Target] AI et ML, vous pouvez sélectionner [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) lors de la création d’un test A/B.

**Pour utiliser des fragments d’expérience à l’aide du compositeur d’expérience visuelle :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience visuelle](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez l’option souhaitée pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   * [!UICONTROL Insérer avant]
   * [!UICONTROL Insérer après]
   * [!UICONTROL Permutation avec le fragment d’expérience]

   La liste [!UICONTROL Fragment d’expérience][!DNL AEM] répertorie tout le contenu créé dans qui est désormais disponible en mode natif dans [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![](assets/experience_fragment_list.png)

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Terminé]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Test multivarié (MVT) :** [création d’un test multivarié](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations :** [création d’une activité de recommandations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F).

**Pour utiliser des fragments d’expérience à l’aide du compositeur d’expérience d’après les formulaires :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement sur la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Modifier le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   ![](assets/experience_fragment_list.png)

   La liste [!UICONTROL Fragment d’expérience][!DNL AEM] répertorie tout le contenu créé dans qui est désormais disponible en mode natif dans [!DNL Target].

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Considérations {#considerations}

* [!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans un délai de dix minutes, mais cette période doit être raccourcie à l’avenir.
* Le fragment d’expérience est actuellement importé dans [!DNL Target] en tant qu’offre HTML. Notez que la version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].
* Vous pouvez importer des offres JSON sous forme de fragments d’expérience dans [!DNL Target]. Cependant, ces offres sont importées sous forme d’offres HTML. Les offres JSON (fragments d’expérience) ne sont actuellement pas entièrement prises en charge dans l’interface utilisateur [!DNL Target].
* Vous ne pouvez pas créer de fragments d’expérience à l’aide des E/S d’Adobe. Vous devez créer des fragments d’expérience à l’aide d’AEM, comme expliqué ci-dessus.

## Vidéo de formation : Utilisation de fragments d’expérience AEM avec Adobe Target ![Badge du tutoriel](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

La vidéo suivante montre comment configurer et utiliser des fragments d’expérience :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction [!DNL AEM] de lien profond discutée à 4:54 a été supprimée.

Pour plus d’informations, voir [Utilisation de fragments d’expérience avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) sur la page *Vidéos et Tutorials AEM Sites* .
