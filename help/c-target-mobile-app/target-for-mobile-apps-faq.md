---
description: Questions fréquentes sur Adobe Target pour les applications mobiles.
keywords: application mobile ; questions fréquentes ; faq ; application mobile cible
seo-description: Questions fréquentes sur Adobe Target pour les applications mobiles.
seo-title: Questions fréquentes sur Adobe Target pour les applications mobiles
title: FAQ sur Adobe Target pour les applications mobiles
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# FAQ sur les applications mobiles

Liste des questions fréquentes sur [!DNL Target] les applications mobiles.

## Dois-je utiliser [!DNL Adobe Experience Platform Launch] pour déployer le SDK ou déployer le SDK sans utiliser [!DNL Launch]?

Le SDK est disponible sur [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Si vous n'utilisez pas [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Le compositeur d'expérience visuelle pour les applications mobiles peut-il être utilisé avec la prise en charge native de React pour le SDK Adobe Experience Platform v 5 ?

Le [compositeur d'expérience visuelle pour les applications](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) mobiles natives ne prend actuellement pas en charge l'application native React. Vous devez utiliser le compositeur d'expérience [d'après les formulaires](/help/c-experiences/form-experience-composer.md).

## L'intégration du kit Mobile SDK autorise-t-elle le déploiement de nouvelles fonctionnalités mobiles ? Puis-je activer et désactiver l'indicateur de fonction sans que de nouveaux déploiements de code soient déployés ?

Oui, vous pouvez utiliser notre SDK mobile pour déployer les fonctionnalités progressivement.

## Pour une logique plus complexe, dois-je développer directement dans l'application plutôt que d'utiliser le compositeur d'expérience visuelle mobile ? Dans ce cas, quelle langue de développement dois-je utiliser ?

Actuellement, le compositeur d'expérience visuelle prend en charge les cas d'utilisation courants, tels que la modification de l'image, du texte, de la couleur, etc. Pour des cas d'utilisation plus avancés, comme la personnalisation de la disposition de l'application, vous devez insérer [!DNL Target] la demande/emplacement (mbox) dans le code et utiliser le compositeur d'expérience [d'après les formulaires](/help/c-experiences/form-experience-composer.md) pour concevoir les expériences et affecter le trafic. Notre SDK mobile prend en charge Java, Objective C et Swift. Il dépend des préférences et des ressources de votre équipe pour choisir la langue.

## Quels SDK sont disponibles aujourd'hui ?

Les SDK Adobe Experience Platform Mobile prennent actuellement en charge ios, Android et React. Pour plus d'informations, reportez-vous au [guide Adobe Experience Cloud Platform Mobile sdks](https://aep-sdks.gitbook.io/docs/).

## Quelle est la fréquence de la fonctionnalité basée sur l'emplacement en termes de vérification sur la latitude et la longitude ?

Pour [plus d'informations, consultez la documentation](https://placesdocs.com/places-services-by-adobe-documentation/) d'Adobe Places.

## Quelles sont les classes natives qui prennent en charge les « Vues » des dispositifs portables ? Prend-il en charge toute classe dérivée nsobject (ou tout objet Android) ou simplement nsviewcontroller et activités ?

Pour plus d'informations, consultez la documentation Android pour la manière [manuelle de déclarer des vues](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## Ai-je besoin d'at. js pour que les SDK Adobe Experience Platform Mobile fonctionnent ?

Non, vous n'avez pas besoin d'at. js pour utiliser les kits SDK mobiles. at. js est la bibliothèque [!DNL Target] JavaScript pour les sites Web. Les SDK Adobe Experience Platform Mobile concernent les applications mobiles.

## Target Mobile est-il une fonctionnalité du SKU d'Adobe Target Premium uniquement ?

Pour les clients Adobe Target Standard, vous pouvez utiliser nos kits SDK mobiles pour les activités de test A/B et de ciblage d'expérience uniquement. Si vous souhaitez utiliser des fonctionnalités de recommandations ou d'AI dans l'application mobile, vous devez posséder une licence [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## Puis-je exploiter les audiences d'Adobe Audience Manager (AAM) dans le compositeur d'expérience visuelle pour les applications mobiles ?

Oui, les SDK Adobe Experience Platform Mobile sont créés pour [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)et Target. Vos audiences dans Audience Manager sont partagées avec [!DNL Target].

## Existe-t-il une intégration d'applications mobiles entre Adobe Experience Manager (AEM) et Target Mobile activités ?

Il se trouve sur notre plan, mais il n'y a pas encore de chronologie. Actuellement, vous pouvez partager des fragments [d'expérience JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) d'AEM vers Target et les utiliser ensuite dans une activité d'application mobile.

## Puis-je ajouter d'autres images à l'aide du compositeur d'expérience visuelle ou changer uniquement les images existantes ?

Vous pouvez actuellement changer les images existantes.
