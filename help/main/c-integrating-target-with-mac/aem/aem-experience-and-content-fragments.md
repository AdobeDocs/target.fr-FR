---
keywords: aem;experience manager;adobe experience manager;intégrer;intégration;fragments d’expérience;fragments de contenu
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] fragments d’expérience et de contenu dans les activités  [!DNL Adobe Target] .
title: Comment utiliser les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu]  [!DNL Adobe Experience Manager] (AEM) ?
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
source-git-commit: f39ec80d9804fff2c65fce98ca2be5400d99aad0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---

# Présentation des [!UICONTROL fragments d’expérience] et [!UICONTROL fragments de contenu] AEM

Les [!UICONTROL fragments d’expérience] (XF) et les [!UICONTROL fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] permettent d’offrir une optimisation et une personnalisation plus poussées.

L’utilisation des [!UICONTROL fragments d’expérience] et des [!UICONTROL fragments de contenu] créés dans [!DNL AEM] dans les activités [!DNL Target] permet d’associer la facilité d’utilisation et la puissance d’[!DNL AEM] à de puissantes fonctionnalités d’intelligence artificielle (AI) et de machine learning (ML) dans [!DNL Target], afin de tester et de personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience pour chaque appareil à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches de machine learning basées sur des règles et sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne.

Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] présentent une énorme avancée permettant de relier les personnes créant et gérant du contenu et des expériences aux personnes professionnelles de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Considérations

Tenez compte des points suivants lorsque vous utilisez les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] AEM dans [!DNL Target] :
* Ces fonctionnalités nécessitent que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Veillez à respecter les exigences de chaque type de fragment : [fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [fragment de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] sont disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Ciblage d’expérience] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Les [!UICONTROL fragments d’expérience] et les [!UICONTROL fragments de contenu] ne sont pas disponibles pour les types d’activité suivants :

   * [[!UICONTROL Test multivarié] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser des [!UICONTROL fragments d’expérience] dans des activités [!DNL Target] avec le [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).
* Vous pouvez utiliser les [!UICONTROL fragments de contenu] dans les activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement.

## Quelle est la différence entre [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] ?

[!DNL Adobe Experience Manager] [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] peuvent sembler similaires à première vue, mais chaque type joue des rôles clés dans différents cas d’utilisation.

Pour plus d’informations sur les similitudes et les différences entre les [!UICONTROL fragments de contenu] et les [!UICONTROL fragments d’expérience], ou encore pour savoir quand et comment utiliser chacun d’eux, consultez la section [Comprendre les [!UICONTROL fragments de contenu] et les [!UICONTROL fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=fr){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=fr){target=_blank}.
