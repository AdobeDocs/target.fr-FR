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
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 2 octobre 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Plate-forme cible

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Node.js SDK version 1.0<br>(9 octobre 2019) | Le SDK de Target Node.js vous permet de déployer Target côté serveur.<br>Ce SDK Node.js vous permet d’intégrer facilement Target à d’autres solutions Experience Cloud, telles qu’Adobe Experience Cloud Identity Service, Adobe Analytics et Adobe Audience Manager.<br>Le SDK Node.js présente les meilleures pratiques et élimine les complexités lors de l’intégration avec Adobe Target via notre API de diffusion afin que vos équipes d’ingénieurs puissent se concentrer sur la logique métier. Les caractéristiques suivantes sont remarquables :<ul><li>Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache.</li><li>Prise en charge de l’optimisation des performances lorsque vous disposez d’une intégration hybride de Target sur vos pages Web et côté serveur. Nous introduisons un paramètre appelé `serverState` qui sera renseigné par les expériences récupérées côté serveur afin qu’at.js 2.2 ne lance plus un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement des pages.</li><li> Prise en charge de la récupération des activités créées par le compositeur d’expérience visuelle via le SDK Node.js, rendu possible par la nouvelle API de diffusion.</li><li>Ouvrez le fichier source afin que vos développeurs puissent contribuer au SDK Node.js.</li></ul>Pour plus d’informations, voir [Notes de mise à jour - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)de Target Node.js. |
| API<br>de livraison (9 octobre 2019) | Un point de fin API de remise entièrement nouveau (/v1/delivery) sera disponible en production. Les principales fonctionnalités sont les suivantes :<ul><li>Un point de fin pour récupérer des expériences pour une ou plusieurs mbox.</li><li>Récupérez les activités créées par le compositeur d’expérience visuelle via l’API.</li><li>Prise en charge d’un objet entièrement nouveau appelé Vues, qui est utilisé pour les applications monopage (SPA) et les applications mobiles.</li></ul>Pour plus d’informations, voir [Notes de mise à jour - API côté serveur Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md). |
| at.js version 2.2<br><br>et at.js version 1.8<br>(Dates à déterminer) | Ces versions d’at.js fournissent :<ul><li>Amélioration des performances lors de l’utilisation du service d’ID d’expérience (ECID) v4.4 et at.js 2.2 ou at.js 1.8 sur vos pages Web.</li><li>Auparavant, l’ECID effectuait deux appels de blocage avant qu’at.js puisse récupérer des expériences. Cela a été réduit à un seul appel, ce qui améliore considérablement les performances.</li></ul> Pour tirer parti de ces améliorations de performances, effectuez une mise à niveau vers at.js 2.2 ou at.js 1.8 avec la bibliothèque ECID v4.4. |


## Target Standard/Premium 19.10.1 (22 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![badge](/help/assets/premium.png) Premium Recommandations basées sur l’utilisateur | Recommande les éléments en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur. Ces éléments sont généralement appelés "Recommandé pour vous".<br>Ce critère vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs de retour. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur. Elle est mise à jour en cours de session et devient plus personnalisée lorsque le visiteur navigue sur votre site. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
