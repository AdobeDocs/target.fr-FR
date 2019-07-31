---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
keywords: notes de mise à jour
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
seo-title: Notes de mise à jour d'Adobe Target (bêta)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 48cb808283c9b2858e1bd041feb3fe8228253d6a

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 31 juillet 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, les fonctionnalités et d'autres informations peuvent être modifiées sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Annonces

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. Cela facilite la mise à l'échelle efficace de leur programme d'optimisation dans les équipes. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* Vous pouvez choisir les espaces de travail auxquels l'intégration peut être appliquée.
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Cette mise à jour prend en charge les cas d'utilisation suivants :

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Octroyez à l'intégration d'E/S Adobe l'accès permettant de sélectionner les espaces de travail avec le rôle approprié afin d'autoriser une équipe centrale à apporter des modifications basées sur l'API dans quelques espaces de travail seulement.
* Chaque équipe propriétaire de son espace de travail décide de disposer de sa propre intégration chaque fois que l'équipe est prête à explorer les API et à choisir le rôle en question.
* Combinez l'un des scénarios ci-dessus.

**Action requise**: Les clients qui exploitent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et création de rapports) sur tous les espaces de travail doivent accorder à leur intégration d'E/S existante Adobe l'accès à tous les espaces de travail avec le rôle souhaité selon leur cas d'utilisation. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. Vous pouvez désormais choisir un rôle.

This action *must* be performed before September 4, 2019 to not face any disruption on your end. Si cette action n'est pas effectuée, après le [! Version de septembre de DNL Target, les commandes d'accès activent et vous constaterez que vous accéderez à l'espace de travail par défaut si c'est comme vous le souhaitez actuellement. Il n'existe pas de réaction négative à la définition d'intégrations ultérieures à l'avance conformément aux directives ci-dessus. Plus vous apportez cette modification, meilleure est la meilleure. La configuration de ce paramètre est limitée, selon le nombre d'espaces de travail de votre entreprise. Ce processus ne prend que quelques clics pour ajouter une intégration existante dans les espaces de travail avec le rôle souhaité.

## Target Standard/Premium 19.8.1 (20 août 2019) {#tgt-19-8-1}

Cette version de maintenance comprend les améliorations suivantes :

* Plusieurs correctifs de sécurité, notamment une mise à jour de sécurité de l'éditeur de texte enrichi (RTE) dans le compositeur d'expérience visuelle. (TGT-35383)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
