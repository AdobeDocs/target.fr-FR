---
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.
keywords: Notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;mise à jour;mise à jour;mise à jour;amélioration;améliorations;correctifs;correctifs
seo-description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
seo-title: 'Notes de mise à jour de Adobe Target (en cours) '
solution: Target
title: Notes de mise à jour de Target (actualisées)
topic: Recommandations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 0d7d4666b5fc0d27ccdde812ef8f1182400dd3e8

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour pour les API Target, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plateformes sont également incluses, le cas échéant.

Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Target Standard/Premium 19.10.1 (22 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![badge](/help/assets/premium.png) Premium Recommandations<br>basées sur l’utilisateur (24 octobre 2019) | Recommande les éléments en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur. Ces éléments sont généralement appelés "Recommandé pour vous".<br>Ce critère vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs de retour. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur. Elle est mise à jour en cours de session et devient plus personnalisée lorsque le visiteur navigue sur votre site.<br>Pour plus d’informations, voir "Recommandations basées sur l’utilisateur" dans [Critères/Algorithmes](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms). |

### Améliorations, correctifs et modifications

* Lorsque vous vous connectez au [!DNL Adobe Experience Cloud], vous accédez au nouvel en-tête de navigation. Il ressemble beaucoup à la navigation précédente avec la barre noire en haut, mais il apporte les améliorations suivantes :

   * Il est plus facile de passer d’une organisation [!DNL Identity Management System] (IMS) à une autre solution.
   * Amélioration de l’aide aux utilisateurs : Les résultats de la recherche incluent les résultats de la documentation du [!DNL Target] produit, ainsi que des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d'accéder plus facilement à un plus grand nombre de contenus pour vous aider à tirer le meilleur parti [!DNL Target]. Nous avons également ajouté un mécanisme de rétroaction directement dans le menu [!UICONTROL Aide] , ce qui facilite le signalement des problèmes ou le partage de vos idées.

   * Amélioration de la fonctionnalité de rétroaction de Net Promoter Score (NPS), de sorte que le module de l'enquête ne perturbe pas votre flux de travail.
   * Amélioration du flux de connexion. Auparavant, tous les [!DNL Target] clients accédaient à la page d’entrée Target après avoir cliqué sur l’ [!DNL Target] icône dans l’en-tête. Cette page a ensuite permis aux clients de continuer avec [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], comme illustré ci-dessous :

      ![Landing page](/help/r-release-notes/assets/landing.png)

      Nous avons éliminé cette page d'entrée pour tous nos clients. Vous êtes désormais toujours dirigé directement vers la page Liste [!UICONTROL des] activités en cliquant sur l’ [!DNL Target] icône dans la nouvelle barre de navigation de l’en-tête.

      Si vous utilisez [!DNL Recommendations Classic], vous pouvez soit accéder directement à la solution, soit accéder au lien court créé dans l’onglet [!UICONTROL Recommandations] , comme illustré ci-dessous :

      ![Lien profond Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si vous utilisez [!DNL Search&Promote], vous devez accéder directement à l’URL [](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). Le chemin à atteindre [!DNL Search&Promote] de l'intérieur de [!DNL Adobe Target] a été complètement supprimé.

   * Les notifications pour [!DNL Target] ne sont actuellement pas disponibles dans la liste déroulante [!UICONTROL Notifications] de l’en-tête.
   >[!NOTE]
   >
   >Ces fonctionnalités ne seront pas déployées à la fois, ni déployées ensemble pour tous les clients. Nous allons déployer ces fonctionnalités au cours des prochains jours à compter de la version [!DNL Target Standard/Premium] 19.10.1 (22 octobre 2019).
   >
   >Dans le cadre du déploiement de la nouvelle barre de navigation, vous remarquerez également des modifications d’URL. Tous les liens précédemment mis en signet continuent de fonctionner, mais nous vous encourageons à mettre en signet de nouveaux liens pour une ouverture plus rapide.

## at.js versions 2.2 et 1.8 (10 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| at.js version 2.2<br><br>et at.js version 1.8 | Ces versions d’at.js fournissent :<ul><li>Amélioration des performances lors de l’utilisation du service d’ID d’expérience (ECID) v4.4 et at.js 2.2 ou at.js 1.8 sur vos pages Web.</li><li>Auparavant, l’ECID effectuait deux appels de blocage avant qu’at.js puisse récupérer des expériences. Cela a été réduit à un seul appel, ce qui améliore considérablement les performances.</li></ul> Pour tirer parti de ces améliorations de performances, effectuez la mise à niveau vers at.js 2.2 ou at.js 1.8, ainsi que vers ECID Library v4.4.<br>at.js 2.2 :<ul><li>**serverState**: Paramètre disponible dans at.js v2.2+ qui peut être utilisé pour optimiser les performances des pages lorsqu’une intégration hybride de Target est implémentée. L’intégration hybride signifie que vous utilisez at.js v2.2+ côté client et l’API de diffusion ou un SDK Target côté serveur pour diffuser des expériences. `serverState` donne à at.js v2.2+ la possibilité d’appliquer des expériences directement à partir du contenu récupéré côté serveur et renvoyé au client dans le cadre de la page diffusée.<br>Pour plus d’informations, voir "serverState" dans [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |

## Plate-forme Target (9 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Node.js SDK version 1.0 | Le SDK de Target Node.js vous permet de déployer Target côté serveur.<br>Ce SDK Node.js vous permet d’intégrer facilement Target à d’autres solutions Experience Cloud, telles qu’Adobe Experience Cloud Identity Service, Adobe Analytics et Adobe Audience Manager.<br>Le SDK Node.js présente les meilleures pratiques et élimine les complexités lors de l’intégration avec Adobe Target via notre API de diffusion afin que vos équipes d’ingénieurs puissent se concentrer sur la logique métier. Les caractéristiques suivantes sont remarquables :<ul><li>Prise en charge de la prérécupération et des notifications qui vous permettent d’optimiser les performances par le biais de la mise en cache.</li><li>Prise en charge de l’optimisation des performances lorsque vous disposez d’une intégration hybride de Target sur vos pages Web et côté serveur. Nous introduisons un paramètre appelé `serverState` qui sera renseigné par les expériences récupérées côté serveur afin qu’at.js 2.2 ne lance plus un appel serveur supplémentaire pour récupérer les expériences. Cette approche optimise les performances de chargement des pages.</li><li> Prise en charge de la récupération des activités créées par le compositeur d’expérience visuelle via le SDK Node.js, rendu possible par la nouvelle API de diffusion.</li><li>Ouvrez le fichier source afin que vos développeurs puissent contribuer au SDK Node.js.</li></ul><br>Pour plus d’informations, voir [Notes de mise à jour - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)de Target Node.js. |
| API de remise | Un point de fin API de remise entièrement nouveau (/v1/delivery) est disponible en production. Les principales fonctionnalités sont les suivantes :<ul><li>Un point de fin pour récupérer des expériences pour une ou plusieurs mbox.</li><li>Récupérez les activités créées par le compositeur d’expérience visuelle via l’API.</li><li>Prise en charge d’un objet entièrement nouveau appelé Vues, qui est utilisé pour les applications monopage (SPA) et les applications mobiles.</li></ul><br>Pour plus d’informations, voir [Notes de mise à jour - API côté serveur Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md). |

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur d’Adobe Target. |
| [Notes de mise à jour - SDK de Node.js Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js d’Adobe Target. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js d’Adobe Target. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour d’](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
