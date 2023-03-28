---
keywords: aem;experience manager;adobe experience manager;intégrer;intégration;fragments d’expérience;fragments de contenu
description: Découvrez comment utiliser [!DNL Adobe Experience Manager] fragments d’expérience et de contenu dans [!DNL Adobe Target] activités.
title: Comment utiliser [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 14%

---

# AEM [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] aperçu

Utilisation [!UICONTROL Fragments d’expérience] (XF) et [!UICONTROL Fragments de contenu] (CF) créés dans [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target] activités pour faciliter l’optimisation ou la personnalisation.

>[!NOTE]
>
>Tenez compte des points suivants lorsque vous utilisez AEM [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] in [!DNL Target]:
> 
>* Ces fonctionnalités nécessitent que vous soyez un [!DNL Adobe Experience Manager] (AEM) client. Veillez à respecter les exigences de chaque type de fragment : [Fragment d’expérience](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [Fragment de contenu](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* Ces fonctionnalités sont disponibles pour les types d’activité suivants : [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique], [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage d’expérience] (XT). Cette fonctionnalité n’est pas disponible dans [!UICONTROL Test multivarié] (MVT) et [!UICONTROL Recommendations] activités.
>* Vous pouvez utiliser [!UICONTROL Fragments d’expérience] in [!DNL Target] activités utilisant la variable [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).
>
>* Vous pouvez utiliser [!UICONTROL Fragments de contenu] dans le [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) uniquement.


Utilisation [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] créé dans [!DNL AEM] in [!DNL Target] Les activités permettent de combiner la facilité d’utilisation et la puissance de [!DNL AEM] avec de puissantes fonctionnalités d’intelligence artificielle (IA) et d’apprentissage automatique (ML) dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle.

[!DNL AEM] rassemble tous vos contenus et ressources dans un emplacement central pour alimenter votre stratégie de personnalisation. [!DNL AEM] permet de créer facilement du contenu pour les ordinateurs de bureau, les tablettes et les appareils mobiles dans un emplacement sans avoir à écrire de code. Il n’est pas nécessaire de créer des pages pour chaque appareil. [!DNL AEM] ajuste automatiquement chaque expérience pour chaque appareil à l’aide de votre contenu.

[!DNL Target] permet de diffuser des expériences personnalisées à grande échelle en combinant des approches d’apprentissage automatique basées sur des règles et basées sur l’intelligence artificielle qui intègrent des variables comportementales, contextuelles et hors ligne. Avec [!DNL Target], vous pouvez facilement configurer et exécuter [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) et [Multivariate](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) pour déterminer les meilleures offres, contenus et expériences.

[!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] représente un énorme pas en avant pour lier les créateurs et les gestionnaires de contenu/d’expérience aux professionnels de l’optimisation et de la personnalisation qui génèrent les résultats commerciaux en utilisant [!DNL Target].

## Quelle est la différence entre [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu]?

[!DNL Adobe Experience Manager] [!UICONTROL Fragments d’expérience] et [!UICONTROL Fragments de contenu] peut sembler similaire à la surface, mais chaque type de fragment joue des rôles clés dans différents cas d’utilisation.

Pour plus d’informations sur la manière dont [!UICONTROL Fragments de contenu] et [!UICONTROL Fragments d’expérience] sont similaires, différents, et quand et comment utiliser chaque affichage [Comprendre [!UICONTROL Fragments de contenu] et [!UICONTROL Fragments d’expérience]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html){target=_blank}.