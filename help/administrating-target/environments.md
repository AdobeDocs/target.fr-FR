---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: Organisez vos sites et vos environnements de préproduction pour une gestion aisée et des rapports séparés à Adobe Target.
title: Environnements
feature: hosts and environments
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 65%

---


# Environnements

Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.

Les hôtes sont regroupés dans des environnements afin d’en faciliter la gestion. Par exemple, dix hôtes peuvent être groupés dans deux ou trois environnements. Les environnements prédéfinis sont [!UICONTROL Production], [!UICONTROL Évaluation] et [!UICONTROL Développement]. Si vous le souhaitez, vous pouvez ajouter de nouveaux environnements et renommer vos environnements.

Un environnement, l’environnement par défaut, est prénommé [!UICONTROL Production]. Il n’est pas possible de supprimer cet environnement, même si vous le renommez. [!DNL Target] considère que c’est là que vous diffuserez les activités et tests finaux et approuvés.

Lorsqu&#39;une demande [!DNL Target] est reçue de nouveaux sites Web ou domaines, ces nouveaux domaines apparaissent toujours dans l&#39;environnement [!UICONTROL Production]. Les paramètres de l&#39;environnement [!UICONTROL Production] ne peuvent pas être modifiés, de sorte que les sites inconnus ou nouveaux sont assurés de n&#39;afficher que le contenu principal et prêt. Grâce à la gestion des hôtes, vous pouvez facilement garantir la qualité des nouvelles activités et du nouveau contenu dans vos environnements de test et de développement, avant d’activer les activités.

Pour gérer les environnements, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Environnements]**.

![Environnements liste](/help/administrating-target/assets/environments.png)

## Ajouter un environnement {#section_32097D0993724DF3A202D164D3F18674}

1. Dans la liste [!UICONTROL Environnements], cliquez sur **[!UICONTROL Ajouter l&#39;Environnement]**.
1. Attribuez un nom explicite à l’environnement.
1. Spécifiez le mode actif souhaité pour l’environnement : [!UICONTROL Activités actives] ou [!UICONTROL Activités actives et inactives].
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Définir l’environnement par défaut pour le rapports {#section_4F8539B07C0C45E886E8525C344D5FB0}

Vous pouvez sélectionner l’environnement à utiliser par défaut pour tous les rapports d’activités.

Si vous utilisez [!UICONTROL Production] comme serveur par défaut, tous les hôtes inconnus sont automatiquement ajoutés ici et les données des rapports à partir de là sont incluses dans la vue de rapports par défaut. La création d’un environnement « propre » garantit que seuls vos sites/domaines principaux sont inclus.

Procédez comme suit pour définir l’environnement par défaut pour la création de rapports :

1. Dans la liste [!UICONTROL Environnements], cliquez sur l’icône Etoile

>[!NOTE]
>
>Les utilisateurs [!DNL Recommendations] doivent reconstruire leur base de données de comportement et leur base de données de produits si les hôtes changent de groupes d’hôtes.

## Modification du nom d’un environnement {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Dans la liste [!UICONTROL Environnement], cliquez sur l&#39;icône **[!UICONTROL Modifier]**.
1. Modifiez le nom de l’environnement.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Supprimer un environnement {#section_737F8869612047868D03FC755B1223D3}

Vous pouvez supprimer un environnement lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Environnement], cliquez sur l&#39;icône **[!UICONTROL Supprimer]**.
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>Vous ne pouvez pas supprimer l&#39;environnement [!UICONTROL Production], mais vous pouvez le renommer.

## Recommandations : filtrer les collections et exclusions par environnement (groupe d’hôtes)

![Badge Premium](/help/assets/premium.png)

Vous pouvez prévisualiser le contenu des collections et des exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>
>Les activités Recommendations sont disponibles dans le cadre de la solution Premium [!DNL Target]. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.

Un environnement peut être utilisé pour séparer les éléments disponibles dans votre catalogue pour différentes utilisations. Par exemple, vous pouvez utiliser des groupes d’hôtes pour les environnements [!UICONTROL Développement] et [!UICONTROL Production], différentes marques ou des zones géographiques différentes. Par défaut, les résultats d’aperçu dans la recherche de catalogue, les collections et les exclusions sont basés sur le groupe d’hôtes par défaut. (Vous pouvez également sélectionner un autre groupe d’hôtes pour prévisualiser les résultats à l’aide du filtre Environnement.) Par défaut, les éléments nouvellement ajoutés sont disponibles dans tous les groupes d’hôtes, sauf si un identifiant d’environnement est spécifié lors de la création ou de la mise à jour de l’élément. Les recommandations fournies dépendent du groupe d’hôtes spécifié dans la requête.

Si vos produits ne sont pas répertoriés, vérifiez que vous utilisez le groupe d’hôtes approprié. Si, par exemple, vous configurez votre recommandation pour utiliser un environnement d’évaluation et que vous définissez votre groupe d’hôtes sur Évaluation, il se peut que vous deviez recréer vos collections dans l’environnement d’évaluation pour les produits à afficher. Pour voir quels produits sont disponibles dans chaque environnement, utilisez la recherche catalogue pour chaque environnement. Vous pouvez également prévisualiser le contenu des collections et exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>Après avoir modifié l’environnement sélectionné, vous devez cliquer sur Rechercher pour mettre à jour les résultats renvoyés.

Le filtre [!UICONTROL Environnement] est disponible à partir des emplacements suivants dans l’interface utilisateur de la Cible :

* Recherche catalogue ([!UICONTROL Recommandations > Recherche catalogue])
* Boîte de dialogue Créer une collection ([!UICONTROL Recommandations > Collections > Créer nouveau])
* Boîte de dialogue Mettre à jour la collection ([!UICONTROL Recommandations > Collections > Modifier])
* Boîte de dialogue Créer une exclusion ([!UICONTROL Recommandations > Exclusions > Créer nouveau])
* Boîte de dialogue Mettre à jour l’exclusion ([!UICONTROL Recommandations > Exclusions > Modifier])