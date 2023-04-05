---
keywords: aem;experience manager;adobe experience manager;intégrer;intégration;fragments d’expérience;fragments de contenu
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] fragments d’expérience et de contenu dans les activités  [!DNL Adobe Target] .
title: Comment utiliser les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu]  [!DNL Adobe Experience Manager]  (AEM) ?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---

# Présentation des [!UICONTROL fragments d’expérience] et [!UICONTROL fragments de contenu] AEM

Utilisez les [!UICONTROL fragments d’expérience] (XF) et les [!UICONTROL fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] AEM dans [!DNL Target] :
> 
>* Ces fonctionnalités nécessitent que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Veillez à respecter les exigences de chaque type de fragment : [fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [fragment de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* Ces fonctionnalités sont disponibles pour les types d’activité suivants : [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique], [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage d’expérience] (XT). Cette fonctionnalité n’est pas disponible dans les activités de [!UICONTROL test multivarié] (MVT) et de [!UICONTROL recommandations].
>* Vous pouvez utiliser des [!UICONTROL fragments d’expérience] dans des activités [!DNL Target] avec le [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).
>
>* Vous pouvez utiliser les [!UICONTROL fragments de contenu] dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement.


L’utilisation des [!UICONTROL fragments d’expérience] et des [!UICONTROL fragments de contenu] créés dans [!DNL AEM] dans les activités [!DNL Target] permet d’associer la facilité d’utilisation et la puissance d’[!DNL AEM] à de puissantes fonctionnalités d’intelligence artificielle (AI) et de machine learning (ML) dans [!DNL Target], afin de tester et de personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience pour chaque appareil à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches de machine learning basées sur des règles et sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne. Avec [!DNL Target], vous pouvez facilement configurer et exécuter des activités de [tests A/B](/help/main/c-activities/t-test-ab/test-ab.md) et [tests multivariés](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) afin de déterminer les meilleurs contenus, offres et expériences.

Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] présentent une énorme avancée permettant de relier les créateurs/créatrices et gestionnaires de contenu et d’expérience aux professionnels et professionnelles de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Quelle est la différence entre [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] ?

[!DNL Adobe Experience Manager] [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] peuvent sembler similaires à première vue, mais chaque type joue des rôles clés dans différents cas d’utilisation.

Pour plus d’informations sur les similitudes et les différences des [!UICONTROL fragments de contenu] et [!UICONTROL fragments d’expérience], ou encore pour savoir quand et comment utiliser chacun d’eux, voir [Comprendre les [!UICONTROL fragments de contenu] et les [!UICONTROL fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=fr){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=fr){target=_blank}.