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
source-git-commit: 0d7d4666b5fc0d27ccdde812ef8f1182400dd3e8

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 17 octobre 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

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

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
