---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments d’expérience;fragments;XF
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] [!UICONTROL Fragments d’expérience] in [!DNL Adobe Target] activités.
title: Comment utiliser [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragments d’expérience]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 32%

---

# AEM [!UICONTROL Fragments d’expérience]

Utilisation [!UICONTROL Fragments d’expérience] (XF) créés dans [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target] activités pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Fragments d’expérience] in [!DNL Target]:
> 
>* Cette fonctionnalité requiert que vous soyez un [!DNL Adobe Experience Manager] (AEM) client. Pour plus d’informations, voir [Conditions](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
>* Cette fonctionnalité est disponible pour les types d’activité suivants : [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique], [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage d’expérience] (XT). Cette fonctionnalité n’est pas disponible dans [!UICONTROL Test multivarié] (MVT) et [!UICONTROL Recommendations] activités.
>
>* Vous pouvez utiliser [!UICONTROL Fragments d’expérience] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).


Pour en savoir plus sur AEM [!UICONTROL Fragments d’expérience] et des fragments de contenu, voir [AEM [!UICONTROL Fragments d’expérience] et Fragments de contenu - Aperçu](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Les [!UICONTROL Fragments d’expérience] fonctionnalité dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou version ultérieure). Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Compte [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium].

[!DNL Adobe Experience Manager] Les versions 6.3 et 6.4 ont atteint la fin de vie et ne sont plus prises en charge (à l’exception des clients qui ont acheté une assistance étendue).

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Création et configuration [!UICONTROL Fragments d’expérience] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour utiliser [!DNL AEM] [!UICONTROL Fragments d’expérience] in [!DNL Target], vous devez effectuer les étapes suivantes :

### Étape 1 : Intégrer [!DNL AEM] à [!DNL Target]

Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service**: [Intégration à Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} dans le *Experience Manager as a Cloud Service* guide.
* **Adobe I/O** : documentation sur l’[Intégration à Adobe Target à l’aide d’Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=fr){target=_blank} dans le *Guide de l’utilisateur d’administration*.
* **[!DNL AEM] 6.5** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Sélection d’Adobe Analytics et Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 2 : Création du fragment d’expérience

[!UICONTROL Fragments d’expérience] sont créées dans [!DNL AEM]. Pour obtenir plus d’informations, voir :

* **AEM as a Cloud Service**: [[!UICONTROL Fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} dans le *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM] 6.5** : [[!UICONTROL Fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [[!UICONTROL Fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

### Étape 3 : Configurer [!DNL AEM] pour partager le fragment d’expérience avec [!DNL Target]

1. À partir de [!DNL AEM], sélectionnez le fragment d’expérience souhaité ou son dossier, puis cliquez sur **[!UICONTROL Propriétés]**.
2. Cliquez sur l’onglet **[!UICONTROL Services Cloud]** puis, dans la liste déroulante **[!UICONTROL Configuration du service cloud]**, sélectionnez **[!UICONTROL Adobe Target]**.

   L’étape précédente suppose que quelqu’un dans votre organisation a créé la configuration [!DNL Adobe Target].

3. Cliquez sur **[!UICONTROL Enregistrer et fermer]**.

### Étape 4 : Publier le fragment d’expérience et l’exporter dans [!DNL Target]

Selon votre version d’[!DNL AEM], consultez les liens suivants pour obtenir des instructions détaillées :

* **AEM as a Cloud Service**: [Export [!UICONTROL Fragments d’expérience] vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} dans le *Experience Manager as a Cloud Service* guide.
* **[!DNL AEM] 6.5** : [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} dans la documentation d’*Adobe Experience Manager 6.5*.
* **[!DNL AEM] 6.4** : [Exportation d’un fragment d’expérience vers Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=fr){target=_blank} dans la documentation d’*Adobe Experience Manager 6.4*.

## Utilisation [!UICONTROL Fragments d’expérience] in [!DNL Target] activités {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, le fragment d’expérience s’affiche sur la page [!UICONTROL Offres] page [!DNL Target].

[!DNL Target] recherche actuellement [!UICONTROL Fragments d’expérience] pour importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans un délai de dix minutes, mais ce délai devrait être raccourci.

Le fragment d’expérience est importé dans [!DNL Target] en tant qu’offre JSON ou HTML. Cette version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL Fichier XF HTML] et [!UICONTROL Fichier XF JSON] pour vous aider à distinguer les types de fragments d’expérience exportés vers [!DNL Target].

![Filtrage par types de fragments d’expérience : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez placer le pointeur de la souris sur un fragment d’expérience de la liste, puis cliquer sur le bouton [!UICONTROL Affichage] icon ![Icône Infos](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur le fragment d’expérience, y compris son [!UICONTROL Nom], [!UICONTROL Type], [!UICONTROL Identifiant de l’offre], [!UICONTROL Chemin de l’offre]et les informations sur les dernières modifications. Cliquez sur le bouton [!UICONTROL Utilisation de l’offre] pour voir les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur le fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Vous pouvez utiliser [!UICONTROL Fragments d’expérience] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Utilisation de l’intelligence artificielle, de l’apprentissage automatique et des recommandations avec [!UICONTROL Fragments d’expérience]:
>
>* Pour utiliser pleinement la variable [!DNL Target] Fonctionnalités AI et ML, vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’un test A/B.
>
>* [!UICONTROL Fragments d’expérience] ne sont pas pris en charge dans [!DNL Recommendations] activités. Toutefois, pour utiliser [!UICONTROL Fragments d’expérience] pour les recommandations, vous pouvez créer une [!UICONTROL Test A/B] (y compris [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]) ou un [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre ;](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Pour utiliser des fragments d’expérience avec le compositeur d’expérience visuelle (VEC) :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience visuelle](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez l’option souhaitée pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   * [!UICONTROL Insérer avant]
   * [!UICONTROL Insérer après]
   * [!UICONTROL Permutation avec le fragment d’expérience]

   Le [!UICONTROL Fragment d’expérience] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en natif depuis l’ [!DNL Target].

   >[!NOTE]
   >
   >L’option [!UICONTROL Permuter avec le fragment d’expérience] n’est pas disponible pour les images. Si vous voulez utiliser cette option avec une image, cliquez sur l’élément conteneur qui contient l’image souhaitée.

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Sélectionnez le fragment d’expérience de votre choix, puis cliquez sur **[!UICONTROL Terminé]**.
1. Terminez la configuration de l’activité.

   Pour plus d’informations sur la configuration des différents types d’activités, reportez-vous aux rubriques suivantes :

   * **Test A/B :** [création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Affectation automatique :** [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Ciblage automatique :** [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Personnalisation automatisée (AP) :** [Création d’une activité de personnalisation automatisée](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Ciblage d’expérience (XT) :** [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations dans une activité de test A/B ou de ciblage d’expérience :** [Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Fragments d’expérience] exporté en tant que JSON dans [!DNL Target] ne peut pas être utilisé dans les activités créées à l’aide du compositeur d’expérience visuelle ; seul HTML [!UICONTROL Fragments d’expérience] sont prises en charge dans les activités basées sur VEC. Si vous souhaitez utiliser JSON [!UICONTROL Fragments d’expérience], utilisez-les dans les activités créées à l’aide de la fonction [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

**Pour utiliser des fragments d’expérience avec le compositeur d’expérience d’après les formulaires :**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), cliquez sur l’emplacement de la page où vous souhaitez insérer du contenu [!DNL AEM], puis sélectionnez **[!UICONTROL Modifier le fragment d’expérience]** pour afficher la liste [!UICONTROL Choisir un fragment d’expérience].

   ![image experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   Le [!UICONTROL Fragment d’expérience] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en natif depuis l’ [!DNL Target].

1. Sélectionnez le fragment d’expérience de votre choix, puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Considérations {#considerations}

* [!DNL Target] recherche actuellement [!UICONTROL Fragments d’expérience] pour importer toutes les dix minutes. Le fragment d’expérience importé doit être disponible dans [!DNL Target] dans un délai de dix minutes, mais ce délai devrait être raccourci.
* Le fragment d’expérience est importé dans [!DNL Target] en tant qu’offre JSON ou HTML. La version &quot;Principale&quot; du fragment d’expérience reste dans [!DNL AEM]. Vous ne pouvez pas modifier le fragment d’expérience dans [!DNL Target].
* Vous ne pouvez pas créer [!UICONTROL Fragments d’expérience] using [!DNL Adobe I/O]. Créer [!UICONTROL Fragments d’expérience] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre fragment d’expérience dans AEM, celui-ci doit être publié et exporté vers [!DNL Target] de nouveau [!DNL Target] Vous pouvez utiliser les dernières modifications.

## Suppression de bibliothèques clientes et de HTMLS superflus de [!UICONTROL Fragments d’expérience] exporté vers [!UICONTROL Cible]

Lors de l’utilisation d’offres de fragments d’expérience avec [!DNL Target] sur une page fournie par AEM, la page ciblée contient déjà toutes les bibliothèques clientes nécessaires. Notez également que les éléments de HTML superflus dans l’offre ne sont pas non plus nécessaires.

Parfois, des pages de HTML entières encapsulent le fragment d’expérience et entraînent des problèmes. Assurez-vous que le fragment d’expérience est un petit HTML et non une page de HTML complète avec HTML, HEAD, CORPS, etc.

Pour plus d’informations, voir le billet de blog suivant : [AEM 6.5 : Suppression de bibliothèques clientes de [!UICONTROL Fragments d’expérience] exporté vers Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vidéo de formation : Utilisation des AEM [!UICONTROL Fragments d’expérience] avec [!DNL Adobe Target]

La vidéo suivante montre comment configurer et utiliser [!UICONTROL Fragments d’expérience]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>La fonction de lien profond [!DNL AEM] évoquée à 4:54 a été supprimée.

Pour plus d’informations, voir [Utilisation [!UICONTROL Fragments d’expérience] avec Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=fr) sur le *Vidéos et Tutorials AEM Sites* page.