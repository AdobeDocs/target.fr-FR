---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de [!DNL Adobe Target].
keywords: notes de mise à jour
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de [!DNL Adobe Target].
seo-title: Notes de mise à jour d’Adobe Target (préliminaires)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d675c6875c8474ba490956ea395076eef5b9e58f

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 24 septembre 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Annonces

**31 juillet 2019**

[!UICONTROL Enterprise Permissions] permet aux clients [!DNL Target] d’utiliser une seule organisation, mais de la diviser en espaces de travail pour différentes équipes ou processus. La fonction [!UICONTROL Enterprise Permissions] facilite la mise à l’échelle efficace des programmes d’optimisation entre les équipes. Bien que cette fonctionnalité soit disponible dans l’ [!DNL Target] interface utilisateur, les API d’administration n’étaient pas prises en charge jusqu’à la version de [!DNL Target] février 2019. Adobe a mis à jour les API Admin afin que vous puissiez utiliser le compte d’intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, alors que les API d’administration étaient limitées à l’espace de travail par défaut, la mise à jour de février 2019 accordait l’accès à tous les espaces de travail avec l’accès [!UICONTROL Approbateur] .

Avec la prochaine version de [!DNL Target] septembre 2019, les autorisations [!UICONTROL d’] entreprise fourniront aux clients les contrôles d’accès suivants :

* Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l’intégration des E/S Adobe : [!UICONTROL Approbateur], [!UICONTROL éditeur]ou [!UICONTROL observateur].

**Action requise**: Les clients qui utilisent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et rapports) dans tous les espaces de travail doivent accorder à l’intégration d’E/S Adobe existante l’accès à tous les espaces de travail ayant le rôle souhaité. Avant la version de septembre, toutes les intégrations fonctionnaient à l’aide de l’accès [!UICONTROL approbateur] , quel que soit le rôle sélectionné dans la liste déroulante Rôle [!UICONTROL du] produit. Avec la prochaine version, vous pouvez désormais sélectionner le rôle souhaité.

Cette action doit être effectuée au cours du mois d’ **août 2019**. Après la version de [!DNL Target] septembre 2019, les contrôles d’accès s’activent et vous obtiendrez l’accès à l’espace de travail par défaut uniquement si c’est ainsi que vous êtes actuellement configuré. Il n’y a aucune conséquence négative à la configuration préalable des rôles d’intégration.

Pour obtenir des instructions détaillées et plus d’informations, voir [Octroi d’un accès aux espaces de travail aux intégrations d’E/S Adobe et attribution de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 septembre 2019)

Cette version de maintenance comprend les améliorations suivantes :

* Plusieurs correctifs de sécurité, notamment une mise à jour de sécurité de l’éditeur de texte enrichi (RTE) dans le compositeur d’expérience visuelle (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 septembre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![Autorisations d’entreprise Premium badge](/help/assets/premium.png) | Avec la version de septembre 2019 de Target, Enterprise Permissions fournit aux clients les contrôles d’accès suivants :<UL><li>Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.</li><li>Vous pouvez appliquer un rôle à l’intégration des E/S Adobe : Approbateur, éditeur ou observateur.</li></ul>Pour obtenir des instructions détaillées et plus d’informations, voir [Octroi d’un accès aux espaces de travail aux intégrations d’E/S Adobe et attribution de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
