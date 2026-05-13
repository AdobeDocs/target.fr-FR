---
keywords: aem;experience manager;adobe experience manager;intégrer;intégration;fragments d’expérience;fragments de contenu
description: Découvrez comment utiliser les  [!DNL Adobe Experience Manager] fragments d’expérience et de contenu dans les activités  [!DNL Adobe Target] .
title: Comment utiliser  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ?
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
TQID: https://experienceleague.adobe.com/OlgveSjoE0rh1orFsbEZVCSbjd3TKEk8fdBbbXtLxhA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e6ff21d3-dec6-4298-8590-7c749fffaf78id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 43%

---

# Présentation d’AEM [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments]

Utilisez les [!UICONTROL Experience Fragments] (XF) et [!UICONTROL Content Fragments] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans les activités [!DNL Target] pour faciliter l’optimisation et la personnalisation.

L’utilisation des [!UICONTROL Experience Fragments] et des [!UICONTROL Content Fragments] créés dans [!DNL AEM] dans les activités [!DNL Target] permet d’associer la facilité d’utilisation et la puissance des [!DNL AEM] à de puissantes fonctionnalités d’intelligence artificielle (AI) et de machine learning (ML) dans [!DNL Target] de tester et de personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience pour chaque appareil à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches de machine learning basées sur des règles et sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne.

[!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] représentent une énorme avancée permettant de relier les créateurs et les gestionnaires de contenu et d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

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

   * [[!UICONTROL Multivariate Test] (VMT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Vous pouvez utiliser des [!UICONTROL Experience Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).
* Vous pouvez utiliser des [!UICONTROL Content Fragments] dans des activités [!DNL Target] à l’aide du [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement.

## Quelle est la différence entre [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] ?

[!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] et [!UICONTROL Content Fragments] peuvent sembler similaires à première vue, mais chaque type joue des rôles clés dans différents cas d’utilisation.

Pour plus d’informations sur les similitudes et les différences entre les [!UICONTROL Experience Fragments] et les [!UICONTROL Content Fragments], ainsi que pour savoir quand et comment utiliser chacun d’eux, consultez [Présentation des [!UICONTROL Content Fragments] et des [!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=fr){target=_blank} dans le guide des vidéos et tutoriels d’[AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=fr){target=_blank}.
