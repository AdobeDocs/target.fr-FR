---
description: Informations sur l’utilisation des fragments d’expérience créés dans Adobe Experience Manager (AEM) dans des activités Target pour faciliter l’optimisation ou la personnalisation.
keywords: expérience;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
seo-description: Informations sur l’utilisation des fragments d’expérience créés dans Adobe Experience Manager (AEM) dans des activités Target pour faciliter l’optimisation ou la personnalisation.
seo-title: Fragments d’expérience AEM
solution: Target
title: Fragments d’expérience AEM
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 4c8a36f9210a36a658064bd286d6f3c2398da3e4

---


# Fragments d’expérience AEM{#aem-experience-fragments}

Informations sur l’utilisation des fragments d’expérience créés dans Adobe Experience Manager (AEM) dans des activités Target pour faciliter l’optimisation ou la personnalisation.

## Fragments d’expérience AEM {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

Informations sur l’utilisation des fragments d’expérience créés dans Adobe Experience Manager (AEM) dans des activités Target pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Cette fonction nécessite que vous soyez client d’Adobe Experience Manager (AEM). Pour plus d’informations, reportez-vous à [Conditions](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.

## Aperçu {#section_95A91830530F493B81C5C9CDB9B783EA}

L’utilisation des fragments d’expérience créés dans AEM dans les activités Target permet d’associer la facilité d’utilisation et la puissance d’AEM à de puissantes fonctionnalités d’intelligence artificielle (AI) et d’apprentissage automatique (ML) dans Target permettant de tester et de personnaliser des expériences à grande échelle.

AEM rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. AEM permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil : AEM ajuste automatiquement chaque expérience en utilisant votre contenu.

Target permet de diffuser des expériences personnalisées à grande échelle en combinant des approches d’apprentissage automatique basées sur des règles et basées sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne.  Avec Target, vous pouvez facilement configurer et exécuter des activités A/B et multivariées (MVT) afin de déterminer les meilleurs contenus, offres et expériences.

Les fragments d’expérience représentent une énorme avancée permettant de relier les créateurs et les gestionnaires de contenu et d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant Target.

## Conditions {#section_AE6F0971E1574B3AA324003599B96E5A}

Les privilèges d’accès doivent vous avoir été attribués pour la fonctionnalité de fragments d’expérience dans Target. En outre, vous devez utiliser AEM 6.3 avec le Service Pack approprié ou AEM 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* Adobe Experience Manager 6.4 (ou version ultérieure).
* Adobe Experience Manager 6.3 SP2 (ou version ultérieure).
* Compte Adobe Target Standard ou Adobe Target Premium.
* Contactez l’assistance clientèle d’Adobe Target pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Création et configuration de fragments d’expérience dans AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser les fragments d’expérience AEM dans Target, procédez comme suit :

### Étape 1 : intégrer AEM à Target

Pour obtenir plus d’informations, voir :

* **AEM 6.3 :**[Sélection d’Adobe Analytics et Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) dans la documentation d’_Adobe Experience Manager 6.3_.
* **AEM 6.4 :**[Sélection d’Adobe Analytics et Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) dans la documentation d’_Adobe Experience Manager 6.4_.
* **AEM 6.5 :**[Exclusion dans Adobe Analytics et Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html)

### Étape 2 : créer le fragment d’expérience

Les fragments d’expérience sont créés dans AEM. Pour obtenir plus d’informations, voir :

* **AEM 6.3 :**[Fragments d’expérience](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) dans la documentation d’*Adobe Experience Manager 6.3*.
* **AEM 6.4 :**[Fragments d’expérience](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) dans la documentation d’*Adobe Experience Manager 6.4*.
* **AEM 6.5 :**[Fragments d'expérience](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html)

### Étape 3 : configurer AEM pour partager le fragment d’expérience avec Target

1. Dans AEM, sélectionnez le fragment d’expérience souhaité ou son dossier, puis cliquez sur [!UICONTROL Propriétés].
2. Cliquez sur l’onglet [!UICONTROL Services Cloud] puis, dans la liste déroulante [!UICONTROL Configuration du service cloud], sélectionnez [!UICONTROL Adobe Target].

   >[!NOTE]
   >
   >L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration Adobe Target.

3. Cliquez sur [!UICONTROL Enregistrer et fermer].

### Étape 4 : publiez le fragment d’expérience et exportez-le dans Target

**AEM 6.3 :**

1. Dans AEM, sélectionnez le fragment d’expérience souhaité, cliquez sur l’onglet [!UICONTROL Publier], puis sur le bouton [!UICONTROL Publier].
2. Dans AEM, sélectionnez le fragment d’expérience souhaité, cliquez sur [!UICONTROL Exporter vers Adobe Target], puis sur [!UICONTROL OK].

   ![](assets/experience_fragment_export_to_target.png)

**AEM 6.4 :**

1. Dans AEM, sélectionnez le fragment d’expérience souhaité, cliquez sur [!UICONTROL Exporter vers Adobe Target].

   ![](assets/experience_fragment_export_to_target.png)

2. Dans la boîte de dialogue qui s’affiche, sélectionnez [!UICONTROL Publier] pour publier tous les actifs dans le fragment d’expérience dans [!DNL Target].

## Using Experience Fragments in Target Activities {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le fragment d’expérience s’affiche sur la page [!UICONTROL Offres] de Target.

>[!NOTE]
>
>Target recherche actuellement des fragments d’expérience à importer toutes les dix minutes. Le fragment d’expérience importé devrait être disponible dans Target dans les dix minutes qui suivent, mais cette période devrait être réduite à l’avenir.

>[!IMPORTANT]
>
>Le fragment d’expérience est actuellement importé dans Target en tant qu’offre HTML. Il est à noter que la version « maîtresse » du fragment d’expérience demeure dans AEM. Vous ne pouvez pas modifier le fragment d’expérience dans Target.

Vous pouvez passer le pointeur de la souris par-dessus un fragment d’expérience dans la liste, puis cliquer sur l’icône Vue (![](assets/icon_info.png)

) pour voir des informations supplémentaires sur le fragment d’expérience, notamment son URL de diffusion d’offre publique, son chemin d’accès AEM et un lien profond pour ouvrir le fragment d’expérience dans AEM.

Vous pouvez utiliser des fragments d’expérience dans des activités Target avec le compositeur d’expérience visuelle (VEC) ou le compositeur d’expérience d’après les formulaires.

>[!NOTE]
>
>Pour utiliser pleinement la fonctionnalité AI et ML de Target, vous pouvez sélectionner [Affectation automatique](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Personnalisation automatisée](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) lors de la création d’un test A/B.

**Pour utiliser des fragments d’expérience avec le compositeur d’expérience visuelle (VEC) :**

1. Dans Target, lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience visuelle (VEC)](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu AEM, puis sélectionnez **[!UICONTROL Permuter avec le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans AEM qui est désormais disponible en mode natif dans Target.

   ![](assets/experience_fragment_list.png)

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
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

1. Dans Target, lors de la création ou de la modification d’une expérience dans le [compositeur d’expérience d’après les formulaires](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement de la page où vous souhaitez insérer du contenu AEM, puis sélectionnez **[!UICONTROL Modifier le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   ![](assets/experience_fragment_list.png)

   La liste [!UICONTROL Fragment d’expérience] répertorie tout le contenu créé dans AEM qui est désormais disponible en mode natif dans Target.

1. Sélectionnez le fragment d’expérience souhaité, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Vidéo de formation : utilisation des fragments d’expérience AEM avec Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

La vidéo suivante indique comment configurer et utiliser les fragments d’expérience : [Utilisation des fragments d’expérience AEM avec Adobe Target](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html).
