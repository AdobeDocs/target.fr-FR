---
keywords: aem;experience manager;adobe experience manager;intégrer;intégration;fragments d’expérience;fragments de contenu
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] fragments d’expérience et de contenu dans les activités  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ?
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
source-git-commit: f39ec80d9804fff2c65fce98ca2be5400d99aad0
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 40%

---

# AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] - Aperçu

Utilisez [!UICONTROL Experience Fragments] (XF) et [!UICONTROL Content Fragments] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation et la personnalisation.

L’utilisation de [!UICONTROL Experience Fragments] et de [!UICONTROL Content Fragments] créés dans les activités [!DNL AEM] dans [!DNL Target] vous permet de combiner la facilité d’utilisation et la puissance de [!DNL AEM] avec de puissantes fonctionnalités d’intelligence artificielle (IA) et d’apprentissage automatique (ML) dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience pour chaque appareil à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches de machine learning basées sur des règles et sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne.

[!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] représentent un énorme pas en avant pour lier les créateurs et gestionnaires de contenu/d’expérience aux professionnels de l’optimisation et de la personnalisation qui dirigent les résultats commerciaux en utilisant [!DNL Target].

## Considérations

Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] dans [!DNL Target] :
* Ces fonctionnalités nécessitent que vous soyez client ou cliente [!DNL Adobe Experience Manager] (AEM). Veillez à respecter les exigences de chaque type de fragment : [fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [fragment de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
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
* Vous pouvez utiliser [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement.

## Quelle est la différence entre [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ?

[!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] peuvent sembler similaires à la surface, mais chaque type de fragment joue des rôles clés dans différents cas d’utilisation.

Pour plus d’informations sur la manière dont [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] sont similaires, différents, et sur le moment et la manière d’utiliser chacun d’eux, voir [Comprendre [!UICONTROL Content Fragments] et [!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=fr){target=_blank} dans le [guide des vidéos et tutoriels AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=fr){target=_blank}.
