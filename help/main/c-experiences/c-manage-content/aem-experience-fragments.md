---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] fragments d’expérience dans [!DNL Adobe Target] activités.
title: Comment utiliser [!DNL Adobe Experience Manager] (AEM) Fragments d’expérience ?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 8eab87951f860d07f6f05a53f81e94c56e7563c8
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 55%

---

# Fragments d’expérience AEM

Utilisation de fragments d’expérience créés dans [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target] activités pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Cette fonctionnalité requiert que vous soyez un [!DNL Adobe Experience Manager] (AEM) client. Pour plus d’informations, voir [Conditions](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.

Utilisation de fragments d’expérience créés dans [!DNL AEM] in [!DNL Target] activités vous permet de combiner la facilité d’utilisation et la puissance de [!DNL AEM] avec de puissantes fonctionnalités d’intelligence artificielle (IA) et d’apprentissage automatique (ML) dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches d’apprentissage automatique basées sur des règles et basées sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne. Avec [!DNL Target], vous pouvez facilement configurer et exécuter [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) et [Multivariate](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) pour déterminer les meilleures offres, contenus et expériences.

Les fragments d’expérience représentent une énorme avancée permettant de relier les créateurs et les gestionnaires de contenu et d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Conditions {#section_AE6F0971E1574B3AA324003599B96E5A}

Les privilèges d’accès doivent vous avoir été attribués pour la fonctionnalité de fragments d’expérience dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Compte [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium].

>[!NOTE]
>
>[!DNL Adobe Experience Manager] Les versions 6.3 et 6.4 ont atteint la fin de vie et ne sont plus prises en charge (à l’exception des clients qui ont acheté une assistance étendue).

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Création et configuration de fragments d’expérience dans [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser les fragments d’expérience [!DNL AEM] dans [!DNL Target], procédez comme suit :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service**: [Intégration à Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} dans la variable *Experience Manager as a Cloud Service* guide.
* **Adobe I/O**: [Intégration à Adobe Target à l’aide de l’Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=fr){target=_blank} dans la variable *Guide de l’utilisateur pour l’administration* documentation.
* **[!DNL AEM]6,5**: [Souscription à Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=fr){target=_blank} dans la variable *Adobe Experience Manager 6.5* documentation.
* **[!DNL AEM]6.4**: [Souscription à Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr){target=_blank} dans la variable *Adobe Experience Manager 6.4* documentation.

### Étape 2 : créer le fragment d’expérience

Les fragments d’expérience sont créés dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service**: [Fragments d’expérience](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} dans la variable *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6,5**: [Fragments d’expérience](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la variable *Adobe Experience Manager 6.5* documentation.
* **[!DNL AEM]6.4**: [Fragments d’expérience](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la variable *Adobe Experience Manager 6.4* documentation.

### Étape 3 : Configurer [!DNL AEM] pour partager le fragment d’expérience avec [!DNL Target]

1. Dans [!DNL AEM], sélectionnez le fragment d’expérience souhaité ou son dossier, puis cliquez sur **[!UICONTROL Propriétés]**.
2. Cliquez sur l’onglet **[!UICONTROL Services Cloud]** puis, dans la liste déroulante **[!UICONTROL Configuration du service cloud]**, sélectionnez **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

### Étape 4 : publiez le fragment d’expérience et exportez-le dans [!DNL Target]

Selon votre version d’[!DNL AEM], consultez les liens suivants pour obtenir des instructions détaillées :

* **AEM as a Cloud Service**: [Exportation de fragments d’expérience vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} dans la variable *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM]6,5**: [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} dans la variable *Adobe Experience Manager 6.5* documentation.
* **[!DNL AEM]6.4**: [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la variable *Adobe Experience Manager 6.4* documentation.

## Utilisation des fragments d’expérience dans des activités [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le fragment d’expérience s’affiche sur la page [!UICONTROL Offres] de [!DNL Target].

>[!NOTE]
>
>* [!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
>
>* Le fragment d’expérience est importé dans [!DNL Target] comme offre de HTML. Cette version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].


Vous pouvez survoler un fragment d’expérience dans la liste, puis cliquer sur l’icône [!UICONTROL Afficher] ![Icône d’affichage](assets/icon_info.png) pour afficher des informations supplémentaires sur le fragment d’expérience, notamment son URL de diffusion d’offres publiques et son chemin d’accès [!DNL AEM].

Vous pouvez utiliser des fragments d’expérience dans des activités [!DNL Target] avec le [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Pour utiliser pleinement la variable [!DNL Target] Fonctionnalités AI et ML, vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’un test A/B.
>
>Les fragments d’expérience ne sont pas pris en charge dans [!DNL Recommendations] activités. Cependant, pour utiliser des fragments d’expérience pour des recommandations, vous pouvez créer une [!UICONTROL Test A/B] (y compris [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]) ou un [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre ;](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**Pour utiliser des fragments d’expérience à l’aide du VEC :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience visuelle](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez l’option souhaitée pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   * [!UICONTROL Insérer avant]
   * [!UICONTROL Insérer après]
   * [!UICONTROL Permutation avec le fragment d’expérience]

   Le [!UICONTROL Fragment d’expérience] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en natif depuis l’ [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![](assets/experience_fragment_list.png)

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Terminé]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Test multivarié (MVT) :** [création d’un test multivarié](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations :** [création d’une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F).

**Pour utiliser des fragments d’expérience avec le compositeur d’expérience d’après les formulaires :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Modifier le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   ![](assets/experience_fragment_list.png)

   Le [!UICONTROL Fragment d’expérience] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en natif depuis l’ [!DNL Target].

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Considérations {#considerations}

* [!DNL Target] recherche actuellement des fragments d’expérience à importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.
* Le fragment d’expérience est importé dans [!DNL Target] comme offre de HTML. La version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].
* Vous ne pouvez pas créer de fragments d’expérience à l’aide de [!DNL Adobe I/O]. Créez des fragments d’expérience à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre fragment d’expérience dans AEM, celui-ci doit être publié et exporté vers [!DNL Target] de nouveau [!DNL Target] Vous pouvez utiliser les dernières modifications.

## Suppression de bibliothèques clientes des fragments d’expérience exportés vers Target

Lors de l’utilisation d’une offre de fragment d’expérience avec [!DNL Target] sur une page fournie par AEM, la page ciblée contient déjà toutes les bibliothèques clientes nécessaires. En outre, le code HTML superflu dans l’offre XF n’est pas non plus nécessaire.

Pour plus d’informations, voir [billet de blog](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vidéo de formation : Utilisation de fragments d’expérience AEM avec [!DNL Adobe Target]

La vidéo suivante vous indique comment configurer et utiliser des fragments d’expérience :

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction de lien profond [!DNL AEM] évoquée à 4:54 a été supprimée.

Pour plus d’informations, voir [Utilisation de fragments d’expérience avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=fr) sur le *Vidéos et Tutorials AEM Sites* page.
