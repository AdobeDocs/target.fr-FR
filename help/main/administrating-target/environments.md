---
keywords: environnement;dépannage;bonnes pratiques;boîte de réception;redirections;redirection;liste blanche;liste noire;liste bloquée;liste autorisée
description: Découvrez comment utiliser les environnements dans Adobe [!DNL Target] pour organiser vos sites et environnements de préproduction afin de faciliter la gestion et de créer des rapports séparés.
title: Que sont les environnements et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 516d3969c8a6ed073b9f8d53c842e4d759cee8a2
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 49%

---

# Environnements

Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.

Les hôtes sont regroupés dans des environnements afin d’en faciliter la gestion. Par exemple, dix hôtes peuvent être groupés dans deux ou trois environnements. Les environnements prédéfinis incluent [!UICONTROL Production], [!UICONTROL Staging] et [!UICONTROL Development]. Si vous le souhaitez, vous pouvez ajouter de nouveaux environnements et renommer vos environnements.

Un environnement, l’environnement par défaut, est prénommé [!UICONTROL Production]. Il n’est pas possible de supprimer cet environnement, même si vous le renommez. [!DNL Target] considère que c’est là que vous diffuserez les activités et tests finaux et approuvés.

Lorsqu’une demande [!DNL Target] est reçue de nouveaux sites web ou domaines, ces nouveaux domaines apparaissent toujours dans l’environnement [!UICONTROL Production]. Les paramètres de l’environnement [!UICONTROL Production] ne peuvent pas être modifiés. Par conséquent, les sites nouveaux ou inconnus peuvent voir uniquement le contenu actif et prêt. Grâce à la gestion des hôtes, vous pouvez facilement garantir la qualité des nouvelles activités et du nouveau contenu dans vos environnements de test et de développement, avant d’activer les activités.

Pour gérer les environnements, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Environments]**.

![Liste des environnements](/help/main/administrating-target/assets/environments.png)

## Ajouter un environnement {#section_32097D0993724DF3A202D164D3F18674}

1. Dans la liste [!UICONTROL Environments], cliquez sur **[!UICONTROL Add Environment]**.
1. Attribuez un nom explicite à l’environnement.
1. Spécifiez le mode actif souhaité pour l’environnement : [!UICONTROL Active Activities] ou [!UICONTROL Active and Inactive Activities].

   Si vous spécifiez [!UICONTROL Active and Inactive Activities], les hôtes de cet environnement affichent également les activités inactives.

1. Cliquez sur **[!UICONTROL Save]**.

## Définition de l’environnement par défaut pour la création de rapports {#section_4F8539B07C0C45E886E8525C344D5FB0}

Vous pouvez sélectionner l’environnement à utiliser par défaut pour tous les rapports d’activités.

Si vous utilisez [!UICONTROL Production] comme valeur par défaut, tous les hôtes inconnus sont automatiquement ajoutés à cet emplacement et les données de rapport de cet emplacement sont incluses dans la vue de rapport par défaut. La création d’un environnement « propre » garantit que seuls vos sites/domaines principaux sont inclus.

Procédez comme suit pour définir l’environnement par défaut pour la création de rapports :

1. Dans la liste [!UICONTROL Environments], cliquez sur l’icône Étoile

>[!NOTE]
>
>Les utilisateurs [!DNL Recommendations] doivent reconstruire leur base de données de comportement et leur base de données de produits si les hôtes changent de groupes d’hôtes.
>
>Si vous spécifiez un [environnement par défaut dans un  [!DNL Adobe Experience Platform] arbre de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}, ce paramètre remplace le paramètre dans [!DNL Target].

## Modification du nom d’un environnement {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Dans la liste [!UICONTROL Environment], cliquez sur l&#39;icône **[!UICONTROL Edit]**.
1. Modifiez le nom de l’environnement.
1. Cliquez sur **[!UICONTROL Save]**.

## Supprimer un environnement {#section_737F8869612047868D03FC755B1223D3}

Vous pouvez supprimer un environnement lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Environment], cliquez sur l&#39;icône **[!UICONTROL Delete]**.
1. Cliquez sur **[!UICONTROL Delete]** pour confirmer la suppression.

>[!NOTE]
>
>Vous ne pouvez pas supprimer l’environnement [!UICONTROL Production], mais vous pouvez le renommer.

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."}

Vous pouvez prévisualiser le contenu des collections et des exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

{{premium-note}}

Un environnement peut être utilisé pour séparer les éléments disponibles dans votre catalogue pour différents usages. Par exemple, vous pouvez utiliser des groupes d’hôtes pour les environnements [!UICONTROL Development] et [!UICONTROL Production], différentes marques ou différentes zones géographiques. Par défaut, les résultats d’aperçu dans la recherche de catalogue, les collections et les exclusions sont basés sur le groupe d’hôtes par défaut. (Vous pouvez également sélectionner un autre groupe d’hôtes pour prévisualiser les résultats à l’aide du filtre Environnement.) Par défaut, les éléments nouvellement ajoutés sont disponibles dans tous les groupes d’hôtes, sauf si un ID d’environnement est spécifié lors de la création ou de la mise à jour de l’élément.

>[!NOTE]
>
>Les recommandations diffusées dépendent du groupe d’hôtes ou de l’identifiant d’environnement spécifié dans la requête.


Si vos produits ne sont pas répertoriés, vérifiez que vous utilisez le groupe d’hôtes approprié. Si, par exemple, vous configurez votre recommandation pour utiliser un environnement d’évaluation et que vous définissez votre groupe d’hôtes sur Évaluation, il se peut que vous deviez recréer vos collections dans l’environnement d’évaluation pour les produits à afficher. Pour voir quels produits sont disponibles dans chaque environnement, utilisez la recherche catalogue pour chaque environnement. Vous pouvez également prévisualiser le contenu des collections et exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>Après avoir modifié l’environnement sélectionné, vous devez cliquer sur Rechercher pour mettre à jour les résultats renvoyés.

Le filtre [!UICONTROL Environment] est disponible à partir des emplacements suivants dans l’interface utilisateur de Target :

* Recherche catalogue ([!UICONTROL Recommendations > Catalog Search])
* Boîte de dialogue Créer une collection ([!UICONTROL Recommendations > Collections > Create New])
* Boîte de dialogue Mettre à jour la collection ([!UICONTROL Recommendations > Collections > Edit])
* Boîte de dialogue Créer une exclusion ([!UICONTROL Recommendations > Exclusions > Create New])
* Boîte de dialogue Mettre à jour l’exclusion ([!UICONTROL Recommendations > Exclusions > Edit])
