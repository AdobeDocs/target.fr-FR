---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
keywords: notes de mise à jour
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
seo-title: Notes de mise à jour d’Adobe Target (préliminaires)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3b21fede9df1ef61da194fac55ffb862c037258a

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 31 juillet 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Annonces

**31 juillet 2019**

[!UICONTROL Les autorisations d'entreprise] permettent [!DNL Target] aux clients d'utiliser une seule organisation, mais la divisent en espaces de travail pour différentes équipes ou différents processus. La fonction [!UICONTROL Autorisations] d'entreprise facilite la mise à l'échelle efficace des programmes d'optimisation entre équipes. Bien que cette fonctionnalité soit disponible dans [!DNL Target] l'interface utilisateur, les API d'administration lacaient la prise en charge correspondante jusqu'à [!DNL Target] la version de février 2019. Adobe a mis à jour les API d'administration afin que vous puissiez utiliser le compte d'intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, bien qu'auparavant, les API d'administration étaient limitées à l'espace de travail par défaut, la mise à jour de février 2019 autorisait l'accès à tous les espaces de travail avec [!UICONTROL accès aux approbateurs] .

Avec la prochaine version [!DNL Target] de septembre 2019, [!UICONTROL les permissions] d'entreprise offrent aux clients les commandes d'accès suivantes :

* Vous pouvez choisir les espaces de travail auxquels l'intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l'intégration d'Adobe I/S : [!UICONTROL Approbateur], [!UICONTROL Éditeur]ou [!UICONTROL Observateur].

**Action requise**: Les clients qui exploitent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et création de rapports) sur tous les espaces de travail doivent accorder à leur intégration d'E/S existante Adobe l'accès à tous les espaces de travail avec le rôle souhaité. Avant la version de septembre, toutes les intégrations utilisées à l'aide [!UICONTROL d'un] accès Approbateur, quel que soit le rôle sélectionné dans [!UICONTROL la liste déroulante Rôle] du produit. Avec la prochaine version, vous pouvez désormais sélectionner un rôle.

Cette action doit être effectuée pendant le mois **d'août 2019**. Après la sortie [!DNL Target] de la version de septembre 2019, les commandes d'accès activeront et vous constaterez l'accès à l'espace de travail par défaut, si c'est comme vous le souhaitez actuellement. Il n'existe aucune conséquence négative pour la définition des rôles d'intégration à l'avance.

Pour obtenir des instructions pas à pas et plus d'informations, voir [Octroi d'intégrations d'E/S Adobe aux espaces de travail et attribution de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.1 (24 septembre 2019)

Cette version de maintenance comprend les améliorations suivantes :

* Plusieurs correctifs de sécurité, notamment une mise à jour de sécurité de l'éditeur de texte enrichi (RTE) dans le compositeur d'expérience visuelle. (TGT-35383)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
