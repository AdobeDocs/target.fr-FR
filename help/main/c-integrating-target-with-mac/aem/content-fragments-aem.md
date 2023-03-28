---
keywords: expérience;json;aem;adobe experience manager;exportation vers adobe target;fragments de contenu;fragments;CF;cf
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] [!UICONTROL Fragments de contenu] in [!DNL Adobe Target] activités.
title: Comment utiliser [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragments de contenu]?
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="What are Target Beta release features?"
feature: Integrations
source-git-commit: cbbaea46460b298cbff5015fcf60c37a8aff7751
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 4%

---

# AEM [!UICONTROL Fragments de contenu]

Utilisation [!UICONTROL Fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target] activités pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Cette fonctionnalité devrait être commercialisée le 6 avril 2023.


>[!NOTE]
>
>Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Fragments de contenu] in [!DNL Target]:
> 
>* Cette fonctionnalité requiert que vous soyez un [!DNL Adobe Experience Manager] (AEM) client. Pour plus d’informations, voir [Conditions](#section_AE6F0971E1574B3AA324003599B96E5A) ci-dessous.
>
>* Cette fonctionnalité est disponible pour les types d’activité suivants : [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique], [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage d’expérience] (XT). Cette fonctionnalité n’est pas disponible dans [!UICONTROL Test multivarié] (MVT) et [!UICONTROL Recommendations] activités.
>
>* Vous pouvez utiliser [!UICONTROL Fragments de contenu] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. Vous ne pouvez pas utiliser [!UICONTROL Fragments de contenu] en utilisant la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC).


Pour en savoir plus sur AEM [!UICONTROL Fragments de contenu] et [!UICONTROL Fragments d’expérience], voir [AEM [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] aperçu](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Conditions {#requirements}

Les [!UICONTROL Fragments de contenu] fonctionnalité dans [!DNL Target]. En outre, vous devez utiliser [!DNL AEM] as a Cloud Service. Votre gestionnaire de compte peut vous aider à vous assurer que vous répondez aux exigences requises pour utiliser cette fonction :

Contactez l’[Assistance clientèle d’Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’elle autorise l’intégration et vous fournisse les détails d’authentification.

## Configuration et utilisation [!UICONTROL Fragments de contenu] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Pour exporter [!UICONTROL Fragments de contenu] pour utiliser dans [!DNL Target] , vous devez effectuer quelques étapes préliminaires dans AEM. Pour plus d’informations, voir [Exportation de fragments de contenu vers Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} dans le *Documentation as a Cloud Service du Experience Manager*. Notez que ce lien sera disponible le jour de la publication (6 avril 2023)

Pour plus d’informations sur la conception, la création, l’organisation et la publication [!UICONTROL Fragments de contenu], voir [[!UICONTROL Fragments de contenu]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## Utilisation [!UICONTROL Fragments de contenu] in [!DNL Target] activités {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Après avoir effectué les tâches précédentes, la variable [!UICONTROL Fragment de contenu] s’affiche sur la [!UICONTROL Offres] page [!DNL Target].

[!DNL Target] recherche actuellement [!UICONTROL Fragments de contenu] pour importer toutes les dix minutes. Le fichier importé [!UICONTROL Fragment de contenu] devrait être disponible dans [!DNL Target] dans un délai de dix minutes, mais ce délai devrait être raccourci.

Le [!UICONTROL Fragment de contenu] est importé dans [!DNL Target] comme offre JSON. Cela [!UICONTROL Fragment de contenu] La version &quot;Principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier la variable [!UICONTROL Fragment de contenu] in [!DNL Target].

Vous pouvez filtrer et rechercher par [!UICONTROL Fichier XF HTML], [!UICONTROL Fichier XF JSON], et [!UICONTROL Fragments de contenu] pour vous aider à distinguer les différents types d’offres exportés vers [!DNL Target].

![Filtrage par types de fragments de contenu : HTML ou JSON dans l’interface utilisateur de Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Vous pouvez survoler une [!UICONTROL Fragment de contenu] dans la liste, puis cliquez sur le bouton [!UICONTROL Affichage] icon ![Icône Infos](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) pour afficher des informations supplémentaires sur la variable [!UICONTROL Fragment de contenu], y compris son [!UICONTROL Chemin AEM] et [!UICONTROL AEM lien profond]. Cliquez sur le bouton [!UICONTROL Utilisation de l’offre] pour voir les activités qui font référence à cette offre.

![Fenêtre contextuelle d’informations sur les fragments de contenu](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Vous pouvez utiliser [!UICONTROL Fragments de contenu] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement. You *cannot* consume [!UICONTROL Fragments de contenu] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Fragments de contenu] sont exportées sous la forme JSON dans [!DNL Target] et ne peuvent pas être utilisés dans les activités créées à l’aide du compositeur d’expérience visuelle.

>[!TIP]
>
>Utilisation de l’intelligence artificielle, de l’apprentissage automatique et des recommandations avec [!UICONTROL Fragments de contenu]:
>
>* Pour utiliser pleinement la variable [!DNL Target] Fonctionnalités AI et ML, vous pouvez sélectionner [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) lors de la création d’un test A/B.
>
>* [!UICONTROL Fragments de contenu] ne sont pas pris en charge dans [!DNL Recommendations] activités. Toutefois, pour utiliser [!UICONTROL Fragments de contenu] pour les recommandations, vous pouvez créer une [!UICONTROL Test A/B] (y compris [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]) ou un [!UICONTROL Ciblage d’expérience] (XT) et [inclure des recommandations en tant qu’offre ;](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Pour consommer [!UICONTROL Fragments de contenu] en utilisant la variable [!UICONTROL Compositeur d’expérience d’après les formulaires]:**

1. Dans [!DNL Target], lors de la création ou de la modification d’une expérience dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), sélectionnez l’emplacement de la page à insérer. [!DNL AEM] contenu, puis sélectionnez **[!UICONTROL Modifier le fragment de contenu]** pour afficher la variable [!UICONTROL Choisir un fragment de contenu] liste.

   ![image content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   Le [!UICONTROL Fragment de contenu] affiche le contenu créé dans [!DNL AEM] qui est désormais disponible en natif depuis l’ [!DNL Target].

1. Sélectionnez la [!UICONTROL Fragment de contenu], puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Terminez la configuration de l’activité.

## Considérations {#considerations}

* [!DNL Target] recherche actuellement [!UICONTROL Fragments de contenu] pour importer toutes les dix minutes. Le fichier importé [!UICONTROL Fragment de contenu] devrait être disponible dans [!DNL Target] dans un délai de dix minutes, mais ce délai devrait être raccourci.
* Le [!UICONTROL Fragment de contenu] est importé dans [!DNL Target] comme offre JSON. Le [!UICONTROL Fragment de contenu] La version &quot;Principale&quot; reste dans [!DNL AEM]. Vous ne pouvez pas modifier la variable [!UICONTROL Fragment de contenu] in [!DNL Target].
* Vous ne pouvez pas créer [!UICONTROL Fragments de contenu] using [!DNL Adobe I/O]. Créer [!UICONTROL Fragments de contenu] à l’aide d’AEM, comme expliqué ci-dessus.
* Si vous mettez à jour votre [!UICONTROL Fragment de contenu] dans AEM, la variable [!UICONTROL Fragment de contenu] doit être publié et exporté vers [!DNL Target] de nouveau [!DNL Target] Vous pouvez utiliser les dernières modifications.