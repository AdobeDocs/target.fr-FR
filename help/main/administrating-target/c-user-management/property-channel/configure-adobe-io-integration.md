---
keywords: intégration;rôles; autorisations utilisateur;admin console
description: Découvrez comment accorder aux intégrations Adobe I/O existantes l’accès à tous les espaces de travail avec le rôle souhaité dans Adobe Target.
title: Comment accorder à Adobe I/O l’accès aux espaces de travail et affecter des rôles ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 59%

---

# Octroi aux espaces de travail de l’accès aux intégrations Adobe I/O et affectation de rôles

[!UICONTROL Enterprise Permissions] permet à [!DNL Target] clients d’utiliser une seule organisation, mais en la divisant en espaces de travail pour leurs différentes équipes ou workflows.

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/main/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

La fonctionnalité [!UICONTROL Enterprise Permissions] facilite la mise à l’échelle efficace des programmes d’optimisation entre les équipes. Bien que cette fonctionnalité ait été disponible dans l’interface utilisateur de [!DNL Target], les API d’administration n’assuraient pas la prise en charge correspondante jusqu’à début 2019. Dans la version de février 2019 de [!DNL Target], Adobe a mis à jour les API d’administration afin que vous puissiez utiliser le compte d’intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, alors qu’auparavant les API d’administration étaient limitées à l’espace de travail par défaut, la mise à jour de février 2019 a accordé l’accès à tous les espaces de travail avec un accès [!UICONTROL Approver].

Avec la version [!DNL Target] de septembre 2019, [!DNL Target] [!UICONTROL Enterprise Permissions] fournit aux clients les contrôles d’accès suivants :

* Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.
* Vous pouvez attribuer un rôle à l’intégration Adobe I/O : [!UICONTROL Approver], [!UICONTROL Editor] ou [!UICONTROL Observer].

Cette mise à jour prend en charge les cas d’utilisation suivants :

* Accordez à l’intégration Adobe I/O l’accès à tous les espaces de travail dotés du rôle [!UICONTROL Observer] à des fins de création de rapports, sans droits de création ou de modification des ressources.
* Octroyez à l’intégration Adobe I/O l’accès permettant de sélectionner les espaces de travail avec le rôle approprié afin d’autoriser une équipe centrale à apporter des modifications pilotées par API dans quelques espaces de travail seulement.
* Permettez à chaque équipe détenant son espace de travail de disposer de sa propre intégration chaque fois qu’elle est prête à explorer les API et à choisir un rôle en conséquence.
* Combinez les scénarios ci-dessus.

**Action requise** : les clients qui utilisent actuellement les API pour les opérations CRUD sur les ressources (activités, audiences, offres et création de rapports) de tous les espaces de travail doivent accorder l’accès à leur intégration Adobe I/O existante à tous les espaces de travail avec le rôle souhaité. Pour ce faire, sélectionnez chaque [!DNL Target] [!UICONTROL Product Profile] dans le [!DNL Adobe Admin Console] et ajoutez la ou les intégrations dans l’onglet [!UICONTROL Integration] . Avant la version de septembre, toutes les intégrations fonctionnaient avec un accès [!UICONTROL Approver], quel que soit le choix effectué dans la liste déroulante [!UICONTROL Product Role] . Vous pouvez maintenant sélectionner le rôle souhaité.

>[!NOTE]
>
>Si cette action n’est pas effectuée, après la publication de la version de septembre 2019 de [!DNL Target], les contrôles d’accès seront activés et vous constaterez un accès à l’espace de travail par défaut uniquement, si c’est ce que vous souhaitez. La configuration à l’avance des intégrations n’a aucune conséquence négative. Apportez cette modification le plus tôt possible. Selon le nombre d’espaces de travail de votre organisation, ce processus ne prend que quelques clics pour ajouter une intégration existante aux espaces de travail avec le rôle souhaité.

**Pour accorder aux espaces de travail l’accès aux intégrations Adobe I/O et affecter des rôles :**

1. Ouvrez le **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Cliquez sur l’onglet **[!UICONTROL Products]** , puis sélectionnez le nom du produit souhaité.

   ![Sélection du produit dans Adobe Admin Console](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Sélectionnez l’espace de travail souhaité (profil produit).

   ![Sélection du profil produit](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Cliquez sur l’onglet **[!UICONTROL Integrations]** .

   ![Onglet Intégrations](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditionnel) Pour ajouter une nouvelle intégration, cliquez sur **[!UICONTROL Add Integration]**, sélectionnez l’intégration souhaitée, puis cliquez sur **[!UICONTROL Save]**.

1. Dans la liste déroulante **[!UICONTROL Product Role]** , sélectionnez le rôle souhaité pour cet espace de travail :

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Similaire au rôle d’observateur (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’éditeur dispose de l’autorisation supplémentaire d’activer les activités. |
