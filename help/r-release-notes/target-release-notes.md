---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des prochaines versions d’Adobe Target.
keywords: notes de mise à jour;versions;mises à jour;future version;améliorations;nouvelles fonctionnalités;correctifs
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des versions à venir de DNL Adobe Target.
seo-title: Notes de mise à jour d’Adobe Target (préliminaires)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1d91c46c78c0bcb58607def4cacaff0b761162fa

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

**31 juillet 2019**

Les [!UICONTROL autorisations d’entreprise] permettent aux clients [!DNL Target] d’utiliser une seule organisation qui est divisée en espaces de travail pour les différentes équipes ou les différents workflows. La fonctionnalité [!UICONTROL Autorisations d’entreprise] permet de mettre facilement et efficacement à l’échelle les programmes d’optimisation entre les équipes. Bien que cette fonctionnalité ait été disponible dans l’interface utilisateur de [!DNL Target], les API d’administration n’assuraient pas la prise en charge correspondante jusqu’à la version de février 2019 de [!DNL Target]. Adobe a mis à jour les API d’administration afin que vous puissiez utiliser le compte d’intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, bien qu’auparavant les API d’administration étaient limitées à l’espace de travail par défaut, la mise à jour de février 2019 accordait l’accès à tous les espaces de travail avec l’accès [!UICONTROL Approbateur].

Avec la version de septembre 2019 de [!DNL Target], les [!UICONTROL autorisations d’entreprise] offriront aux clients les contrôles d’accès suivants :

* Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l’intégration d’Adobe I/O : [!UICONTROL approbateur], [!UICONTROL éditeur] ou [!UICONTROL observateur].

**Action requise** : les clients qui utilisent actuellement les API pour les opérations CRUD sur les ressources (activités, audiences, offres et création de rapports) de tous les espaces de travail doivent accorder l’accès existant à leur intégration Adobe I/O à tous les espaces de travail avec le rôle souhaité. Avant la version du mois de septembre, toutes les intégrations fonctionnaient avec l’accès [!UICONTROL Approbateur], quel que soit le rôle sélectionné dans la liste déroulante [!UICONTROL Rôle produit]. Avec la version à venir, vous pourrez maintenant sélectionner un rôle.

Cette action doit être effectuée pendant le mois d’**août 2019**. Après la publication de la version de septembre 2019 de [!DNL Target], les contrôles d’accès seront activés et vous constaterez un accès à l’espace de travail par défaut uniquement, si c’est ce que vous souhaitez. La configuration à l’avance des rôles d’intégration n’a aucune conséquence négative.

Pour obtenir des instructions détaillées et des informations supplémentaires, consultez [Octroi aux espaces de travail de l’accès aux intégrations Adobe I/O et affectation de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 septembre 2019)

Cette version de maintenance comprend l’amélioration suivante :

* Plusieurs correctifs de sécurité, notamment une mise à jour de sécurité de l’éditeur de texte enrichi (RTE) dans le compositeur d’expérience visuelle (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 septembre 2019)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| ![Autorisations d’entreprise Premium badge](/help/assets/premium.png) | Avec la version de septembre 2019 de Target, Enterprise Permissions fournit aux clients les contrôles d’accès suivants :<UL><li>Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.</li><li>Vous pouvez appliquer un rôle à l’intégration d’Adobe I/O : approbateur, éditeur ou observateur.</li></ul>Pour obtenir des instructions détaillées et des informations supplémentaires, consultez [Octroi aux espaces de travail de l’accès aux intégrations Adobe I/O et affectation de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
