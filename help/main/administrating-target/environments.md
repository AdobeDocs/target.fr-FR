---
keywords: environnement;dépannage;bonnes pratiques;ubox;redirections;redirection;liste blanche;liste bloquée;
description: Découvrez comment utiliser les environnements dans Adobe  [!DNL Target]  organiser vos sites et vos environnements de pré-production pour une gestion facile et des rapports séparés.
title: Que sont les environnements et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
TQID: https://experienceleague.adobe.com/ve3zhtylLWwRv890FaptsA9shmINkioM6-Yrq-nmmm0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2: id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 709
ht-degree: 46%

---

# Environnements

Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.

Les hôtes sont regroupés dans des environnements afin d’en faciliter la gestion. Par exemple, dix hôtes peuvent être groupés dans deux ou trois environnements. Les environnements prédéfinis comprennent [!UICONTROL Production], [!UICONTROL Évaluation] et [!UICONTROL Développement]. Si vous le souhaitez, vous pouvez ajouter de nouveaux environnements et renommer vos environnements.

Un environnement, l’environnement par défaut, est prénommé [!UICONTROL Production]. Il n’est pas possible de supprimer cet environnement, même si vous le renommez. [!DNL Target] considère que c’est là que vous diffuserez les activités et tests finaux et approuvés.

Lorsqu’une requête [!DNL Target] est reçue de nouveaux sites web ou domaines, ces nouveaux domaines apparaissent toujours dans l’environnement [!UICONTROL de production]. Les paramètres de l’environnement [!UICONTROL de production] ne peuvent pas être modifiés. Par conséquent, les sites inconnus ou nouveaux ne pourront afficher que le contenu actif et prêt. Grâce à la gestion des hôtes, vous pouvez facilement garantir la qualité des nouvelles activités et du nouveau contenu dans vos environnements de test et de développement, avant d’activer les activités.

{{permissions-update}}

Pour gérer les environnements, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Environnements]**.

## Ajout d’un environnement {#section_32097D0993724DF3A202D164D3F18674}

1. Dans la liste [!UICONTROL  Environnements ], cliquez sur **[!UICONTROL Ajouter un environnement]**.
1. Attribuez un nom explicite à l’environnement.
1. Spécifiez le mode actif souhaité pour l’environnement : [!UICONTROL Activités actives] ou [!UICONTROL Activités actives et inactives].

   Si vous spécifiez [!UICONTROL Activités actives et inactives], les hôtes de cet environnement affichent également les activités inactives.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Définir l’environnement par défaut pour le reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

Vous pouvez sélectionner l’environnement à utiliser par défaut pour tous les rapports d’activités.

Si vous utilisez [!UICONTROL Production] par défaut, tous les hôtes inconnus sont automatiquement ajoutés ici et les données des rapports qui en proviennent sont incluses dans la vue de rapport par défaut. La création d’un environnement « propre » garantit que seuls vos sites/domaines principaux sont inclus.

Procédez comme suit pour définir l’environnement par défaut pour la création de rapports :

1. Dans la liste [!UICONTROL  Environnements ], cliquez sur l’icône en forme d’étoile

>[!NOTE]
>
>Les utilisateurs [!DNL Recommendations] doivent reconstruire leur base de données de comportement et leur base de données de produits si les hôtes changent de groupes d’hôtes.
>
>Si vous spécifiez un environnement [par défaut dans un flux  [!DNL Adobe Experience Platform]  données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}, ce paramètre remplace le paramètre dans [!DNL Target].

## Modification du nom d’un environnement {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Dans la liste [!UICONTROL Environnement], cliquez sur l’icône **[!UICONTROL Modifier]**.
1. Modifiez le nom de l’environnement.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Suppression d’un environnement {#section_737F8869612047868D03FC755B1223D3}

Vous pouvez supprimer un environnement lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Environnement], cliquez sur l’icône **[!UICONTROL Supprimer]**.
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>Vous ne pouvez pas supprimer l’environnement [!UICONTROL de production], mais vous pouvez le renommer.

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."} Recommendations : filtrer les collections et exclusions par environnement (groupe d’hôtes)

Vous pouvez prévisualiser le contenu des collections et des exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

{{premium-note}}

Un environnement peut être utilisé pour séparer les éléments disponibles dans votre catalogue pour différentes utilisations. Par exemple, vous pouvez utiliser des groupes d’hôtes pour les environnements [!UICONTROL Développement] et [!UICONTROL Production], différentes marques ou différentes zones géographiques. Par défaut, les résultats d’aperçu dans la recherche de catalogue, les collections et les exclusions sont basés sur le groupe d’hôtes par défaut. (Vous pouvez également sélectionner un autre groupe d&#39;hôtes pour prévisualiser les résultats à l&#39;aide du filtre Environnement.) Par défaut, les nouveaux éléments ajoutés sont disponibles dans tous les groupes d’hôtes, sauf si un identifiant d’environnement est spécifié lors de la création ou de la mise à jour de l’élément.

>[!NOTE]
>
>Les recommandations diffusées dépendent du groupe d’hôtes ou de l’identifiant d’environnement spécifié dans la requête.


Si vos produits ne sont pas répertoriés, vérifiez que vous utilisez le groupe d’hôtes approprié. Si, par exemple, vous configurez votre recommandation pour utiliser un environnement d’évaluation et que vous définissez votre groupe d’hôtes sur Évaluation, il se peut que vous deviez recréer vos collections dans l’environnement d’évaluation pour les produits à afficher. Pour voir quels produits sont disponibles dans chaque environnement, utilisez la recherche catalogue pour chaque environnement. Vous pouvez également prévisualiser le contenu des collections et exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>Après avoir modifié l’environnement sélectionné, vous devez cliquer sur Rechercher pour mettre à jour les résultats renvoyés.

Le filtre [!UICONTROL Environnement] est disponible aux emplacements suivants dans l’interface utilisateur de Target :

* Recherche catalogue ([!UICONTROL Recommendations > Recherche catalogue])
* Boîte de dialogue Créer une collection ([!UICONTROL Recommendations > Collections > Créer nouvelle])
* Boîte de dialogue Mettre à jour la collection ([!UICONTROL Recommendations > Collections > Modifier])
* Boîte de dialogue Créer une exclusion ([!UICONTROL Recommendations > Exclusions > Créer nouvelle])
* Boîte de dialogue Mettre à jour l’exclusion ([!UICONTROL Recommendations > Exclusions > Modifier])
