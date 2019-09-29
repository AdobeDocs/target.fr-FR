---
description: Questions fréquentes sur Adobe Target pour les applications mobiles.
keywords: application mobile;questions fréquentes;faq;cibler l’application mobile
seo-description: Questions fréquentes sur Adobe Target pour les applications mobiles.
seo-title: Questions fréquentes sur Adobe Target pour les applications mobiles
title: FAQ sur Adobe Target pour les applications mobiles
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# FAQ sur Target pour les applications mobiles

Liste des questions fréquentes sur [!DNL Target] les applications mobiles.

## Dois-je utiliser [!DNL Adobe Experience Platform Launch] pour déployer le SDK ou puis-je le déployer sans l’utiliser [!DNL Launch]?

Le SDK est disponible sur le git [d’](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)Adobe Marketing Cloud. Si vous n’utilisez pas [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), vous devez gérer votre propre fichier de paramètres et le gérer dans votre application.

## Le compositeur d’expérience visuelle (VEC) pour les applications mobiles peut-il être utilisé avec la prise en charge native de React pour le SDK Adobe Experience Platform v5 ?

Le [compositeur d’expérience visuelle pour les applications](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) mobiles natives ne prend actuellement pas en charge l’application native React. Vous devez utiliser le compositeur d’expérience d’après les [formulaires](/help/c-experiences/form-experience-composer.md).

## L’intégration du kit SDK mobile permet-elle le déploiement de nouvelles fonctionnalités mobiles ? Puis-je activer et désactiver l’indicateur de fonctionnalité sans nouveaux déploiements de code ?

Oui, vous pouvez utiliser notre SDK mobile pour déployer progressivement des fonctionnalités.

## Pour une logique plus complexe, dois-je développer directement dans l’application au lieu d’utiliser le compositeur d’expérience visuelle mobile ? Si oui, quel langage de développement devrais-je utiliser ?

Actuellement, le compositeur d’expérience visuelle prend en charge les cas d’utilisation courants tels que la modification de l’image, du texte, de la couleur, etc. Pour des cas d’utilisation plus avancés, comme la personnalisation de la mise en page de l’application, vous devez insérer la [!DNL Target] requête/emplacement (mbox) dans le code et utiliser le compositeur d’expérience d’après les [formulaires](/help/c-experiences/form-experience-composer.md) pour concevoir les expériences et allouer le trafic. Notre SDK mobile prend en charge Java, Objective C et Swift. Cela dépend des préférences et des ressources de votre équipe pour choisir la langue.

## Quels sont les SDK disponibles aujourd’hui ?

Les SDK mobiles Adobe Experience Platform prennent actuellement en charge iOS, Android et React. Pour plus d’informations, reportez-vous au guide [des kits SDK mobiles](https://aep-sdks.gitbook.io/docs/)Adobe Experience Cloud Platform.

## Quelle est la fréquence de la fonction de localisation, en termes de vérification de la latitude et de la longitude?

Pour plus d’informations, consultez la documentation [d’](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places.

## Quelles sont les classes natives prises en charge par les "vues" mobiles ? Prennent-ils en charge une classe dérivée NSObject (ou un objet Android) ou simplement NSViewController et les activités ?

Pour plus d’informations, consultez la documentation Android pour savoir comment déclarer [manuellement les vues](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## Ai-je besoin d’at.js pour que les SDK mobiles d’Adobe Experience Platform fonctionnent ?

Non, vous n’avez pas besoin d’at.js pour utiliser les kits SDK mobiles. at.js est la bibliothèque [!DNL Target] JavaScript pour les sites Web. Les SDK mobiles d’Adobe Experience Platform sont destinés aux applications mobiles.

## Target Mobile est-il une fonctionnalité du SKU du produit Adobe Target Premium uniquement ?

Pour les clients d’Adobe Target Standard, vous pouvez uniquement utiliser nos SDK mobiles pour les activités A/B Test et de ciblage d’expérience (XT). Si vous souhaitez utiliser les fonctionnalités de Recommendations ou d’IA dans l’application mobile, vous avez besoin d’une licence [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## Puis-je exploiter les audiences d’Adobe Audience Manager (AAM) dans le compositeur d’expérience visuelle pour applications mobiles ?

Oui, les SDK mobiles Adobe Experience Platform sont conçus pour [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)et Target. Vos audiences dans Audience Manager sont partagées avec [!DNL Target].

## Existe-t-il une intégration d’applications mobiles entre Adobe Experience Manager (AEM) et les activités mobiles Target ?

C'est sur notre feuille de route, mais il n'y a pas encore de calendrier. Actuellement, vous pouvez partager des fragments [d’](/help/c-experiences/c-manage-content/aem-experience-fragments.md) expérience JSON d’AEM vers Target et il est possible de les utiliser dans une activité d’application mobile.

## Puis-je ajouter d’autres images à l’aide du compositeur d’expérience visuelle ou uniquement modifier des images existantes ?

Vous ne pouvez actuellement modifier que les images existantes.
