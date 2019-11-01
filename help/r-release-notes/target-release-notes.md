---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des prochaines versions d’Adobe Target.
keywords: notes de mise à jour;versions;mises à jour;future version;améliorations;nouvelles fonctionnalités;correctifs
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
seo-title: Notes de version préliminaire d’Adobe Target
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 31 octobre 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Plate-forme Target (31 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| SDK Java | Le [!DNL Target] SDK Java vous permet de déployer [!DNL Target] côté serveur. Ce SDK Java vous permet de vous intégrer facilement [!DNL Target] à d’autres [!DNL Adobe Experience Cloud] solutions, telles que [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]et [!DNL Adobe Audience Manager].<br>Le SDK Java introduit les meilleures pratiques et élimine les complexités lors de l’intégration avec [!DNL Target] via notre API de diffusion afin que vos équipes d’ingénieurs puissent se concentrer sur la logique métier. Les caractéristiques suivantes sont remarquables :<ul><li>Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache.</li><li>Prise en charge de l’optimisation des performances lorsque vous disposez d’une intégration hybride de [!DNL Target] sur vos pages Web et côté serveur. Nous introduisons un paramètre appelé `serverState` qui est renseigné par les expériences récupérées côté serveur, de sorte qu’at.js 2.2 ne lance plus d’appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement des pages.</li><li>Prise en charge de la récupération des activités créées par le compositeur d’expérience visuelle via le SDK Java, rendu possible par la nouvelle API de diffusion.</li><li>Open Source afin que vos développeurs puissent contribuer au SDK [Java](https://github.com/adobe/target-java-sdk)Target.</li></ul>Pour plus d’informations, voir [Notes de mise à jour - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)Java Target.<br>En savoir plus sur le SDK Java Target sur le blog technique d’Adobe - Optimisation côté [serveur avec le nouveau SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)Java Target. |

## Target Standard/Premium 19.10.2 (31 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![Badge](/help/assets/premium.png) Premium Utilisation d’attributs à plusieurs valeurs | Vous pouvez parfois utiliser un champ à plusieurs valeurs. Prenons les exemples suivants :<ul><li>Vous proposez des films aux utilisateurs. Un film donné a plusieurs acteurs.</li><li>Vous vendez des billets pour des concerts. Un utilisateur donné possède plusieurs groupes favoris.</li><li>Vous vendez des vêtements. Une chemise est disponible en plusieurs tailles.</li></ul>Pour gérer les recommandations dans ces scénarios, vous pouvez transmettre des données à plusieurs valeurs à Target Recommendations et utiliser des opérateurs spéciaux à plusieurs valeurs. |

## Target Standard/Premium 20.1.1

La version 20.1.1 de Target Standard/Premium sera publiée en janvier 2020. La date exacte, les fonctionnalités et les améliorations seront annoncées ici.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
