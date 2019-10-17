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
source-git-commit: 0a9cf0e98f5f833402b96f37df5513325222ad19

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 17 octobre 2019**

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
| at.js version 2.2<br><br>et at.js version 1.8<br>(10 octobre 2019) | Ces versions d’at.js fournissent :<ul><li>Amélioration des performances lors de l’utilisation du service d’ID d’expérience (ECID) v4.4 et at.js 2.2 ou at.js 1.8 sur vos pages Web.</li><li>Auparavant, l’ECID effectuait deux appels de blocage avant qu’at.js puisse récupérer des expériences. Cela a été réduit à un seul appel, ce qui améliore considérablement les performances.</li></ul> Pour tirer parti de ces améliorations de performances, effectuez la mise à niveau vers at.js 2.2 ou at.js 1.8, ainsi que vers ECID Library v4.4.<br>at.js 2.2 :<ul><li>**serverState**: Paramètre disponible dans at.js v2.2+ qui peut être utilisé pour optimiser les performances des pages lorsqu’une intégration hybride de Target est implémentée. L’intégration hybride signifie que vous utilisez at.js v2.2+ côté client et l’API de diffusion ou un SDK Target côté serveur pour diffuser des expériences. `serverState` donne à at.js v2.2+ la possibilité d’appliquer des expériences directement à partir du contenu récupéré côté serveur et renvoyé au client dans le cadre de la page diffusée.<br>Pour plus d’informations, voir "serverState" dans [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |


## Target Standard/Premium 19.10.1 (22 octobre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![badge](/help/assets/premium.png) Premium Recommandations basées sur l’utilisateur | Recommande les éléments en fonction de l’historique de navigation, d’affichage et d’achat de chaque visiteur. Ces éléments sont généralement appelés "Recommandé pour vous".<br>Ce critère vous permet de fournir du contenu et des expériences personnalisés aux nouveaux visiteurs et aux visiteurs de retour. La liste des recommandations est pondérée en fonction de l’activité la plus récente du visiteur. Elle est mise à jour en cours de session et devient plus personnalisée lorsque le visiteur navigue sur votre site. |

### Améliorations, correctifs et modifications

* Modifications apportées au shell unifié Adobe.

   Adobe effectue des mises à jour du shell existant (la barre noire en haut des [!DNL Experience Cloud] solutions) afin d’unifier et d’améliorer votre expérience dans toutes les [!DNL Adobe Experience Cloud] solutions.

   Il n'y a pas de changements dans les processus actuels, et ces changements apparemment simples sont conçus pour vous faciliter la vie de manière modeste mais importante.

   Lorsque vous vous connectez au [!DNL Adobe Experience Cloud]serveur, vous serez dirigé vers le nouveau shell unifié. Il ressemble beaucoup au Shell précédent avec la barre noire en haut, mais il apporte les améliorations suivantes :

   * Il est plus facile de basculer entre les organisations IMS (Identity Management System) ou une autre solution [!EExperience Cloud] .
   * Amélioration de l’aide aux utilisateurs : Les résultats de la recherche incluent les résultats de la documentation du [!DNL Target] produit, ainsi que des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d'accéder plus facilement à un plus grand nombre de contenus pour vous aider à tirer le meilleur parti [!DNL Target]. Nous avons également ajouté un mécanisme de rétroaction dans le menu Aide, ce qui facilite la création de rapports sur les problèmes ou le partage de vos idées.
   * Amélioration de la fonctionnalité NPS (Net Promoter Score). Parfois, certains clients voyaient [!DNL Target] des enquêtes plus fréquemment que prévu. De plus, le mode d'enquête utilisé pour perturber votre flux de travail. Nous avons complètement mis à jour cette fonctionnalité afin qu'elle devienne une petite enquête qui ne soit plus intrusive. De plus, grâce à la nouvelle conception, nous sommes en mesure de mieux contrôler la fréquence de l'enquête.
   * Amélioration du flux de connexion. Auparavant, tous les [!DNL Target] clients se retrouvaient sur la page d’entrée de Target après avoir cliqué sur l’ [!DNL Target] icône du shell. Cette page a ensuite permis aux clients de poursuivre avec [!DNL Target Standard/Premium], [!DNl’URL de Recommendations Classic]ou [!DNL Search&Promote], comme illustré ci-dessous :

      ![Landing page](/help/r-release-notes/assets/landing.png)

      Nous avons éliminé cette page d'entrée pour tous nos clients. Vous êtes désormais toujours dirigé directement vers la page Liste [!UICONTROL des] activités en cliquant sur l’ [!DNL Target] icône .

      Si vous utilisez [!DNL Recommendations Classic], vous pouvez soit accéder directement à la solution, soit accéder au lien court créé dans l’onglet [!UICONTROL Recommandations] , comme illustré ci-dessous :

      ![Lien profond Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si vous utilisez [!DNL Search&Promote], vous devez accéder directement au lien. Le chemin d’accès à Search&amp;Promote depuis l’intérieur de [!DNL Adobe Target] a été complètement supprimé.
   * Les notifications pour [!DNL Target] ne sont actuellement plus visibles dans la liste déroulante [!UICONTROL Notifications] dans Shell.
   >[!NOTE]
   >
   >Ces fonctionnalités ne seront pas déployées à la fois, ni déployées ensemble pour tous les clients. Nous allons déployer ces fonctionnalités au cours des prochains jours à compter de la version [!DNL Target Standard/Premium] 19.10.1 (22 octobre 2019).
   >
   >Dans le cadre du déploiement du nouveau Shell, vous remarquerez également des modifications d’URL. Tous les liens précédemment mis en signet continuent de fonctionner, mais nous vous encourageons à mettre en signet de nouveaux liens pour une ouverture plus rapide.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
