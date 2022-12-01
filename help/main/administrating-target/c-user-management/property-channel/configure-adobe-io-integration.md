---
keywords: intégration;rôles; autorisations utilisateur;admin console
description: Découvrez comment accorder aux intégrations Adobe I/O existantes l’accès à tous les espaces de travail avec le rôle souhaité dans Adobe Target.
title: Comment puis-je accorder l’accès aux Adobes I/O aux espaces de travail et attribuer des rôles ?
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 87%

---

# ![PREMIUM](/help/main/assets/premium.png) Octroi aux espaces de travail de l’accès aux intégrations Adobe I/O et affectation de rôles

Les [!UICONTROL autorisations d’entreprise] permettent aux clients [!DNL Target] d’utiliser une seule organisation qui est divisée en espaces de travail pour les différentes équipes ou les différents workflows. 

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/main/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

La fonctionnalité [!UICONTROL Autorisations d’entreprise] permet de mettre facilement et efficacement à l’échelle les programmes d’optimisation entre les équipes. Bien que cette fonctionnalité ait été disponible dans l’interface utilisateur de [!DNL Target], les API d’administration n’assuraient pas la prise en charge correspondante jusqu’à début 2019. Dans la version de février 2019 de [!DNL Target], Adobe a mis à jour les API d’administration afin que vous puissiez utiliser le compte d’intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, bien qu’auparavant les API d’administration étaient limitées à l’espace de travail par défaut, la mise à jour de février 2019 accordait l’accès à tous les espaces de travail avec l’accès [!UICONTROL Approbateur].

Avec le [!DNL Target] Version de septembre 2019, [!DNL Target] [!UICONTROL Autorisations d’entreprise] fournit aux clients les contrôles d’accès suivants :

* Vous pouvez choisir les espaces de travail auxquels l’intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l’intégration d’Adobe I/O : [!UICONTROL Approbateur], [!UICONTROL Éditeur] ou [!UICONTROL Observateur].

Cette mise à jour prend en charge les cas d’utilisation suivants :

* Octroyez l’accès aux intégrations Adobe I/O à tous les espaces de travail avec le rôle [!UICONTROL Observateur] à des fins de création de rapports, sans droits de création ou de modification des ressources.
* Octroyez à l’intégration Adobe I/O l’accès permettant de sélectionner les espaces de travail avec le rôle approprié afin d’autoriser une équipe centrale à apporter des modifications pilotées par API dans quelques espaces de travail seulement.
* Permettez à chaque équipe détenant son espace de travail de disposer de sa propre intégration chaque fois qu’elle est prête à explorer les API et à choisir un rôle en conséquence.
* Combinez les scénarios ci-dessus.

**Action requise** : les clients qui utilisent actuellement les API pour les opérations CRUD sur les ressources (activités, audiences, offres et création de rapports) de tous les espaces de travail doivent accorder l’accès à leur intégration Adobe I/O existante à tous les espaces de travail avec le rôle souhaité. Pour ce faire, sélectionnez chaque [!DNL Target] [!UICONTROL profil produit] dans [!DNL Adobe Admin Console] l’onglet [!UICONTROL Intégration] et ajoutez-y les intégration. Avant la version du mois de septembre, toutes les intégrations fonctionnaient avec l’accès [!UICONTROL Approbateur], quel que soit le rôle sélectionné dans la liste déroulante [!UICONTROL Rôle produit]. Vous pouvez maintenant sélectionner le rôle souhaité.

>[!NOTE]
>
>Si cette action n’est pas effectuée, après la publication de la version de septembre 2019 de [!DNL Target], les contrôles d’accès seront activés et vous constaterez un accès à l’espace de travail par défaut uniquement, si c’est ce que vous souhaitez. La configuration à l’avance des intégrations n’a aucune conséquence négative. Apportez cette modification le plus tôt possible. Selon le nombre d’espaces de travail de votre entreprise, ce processus ne prend que quelques clics pour ajouter une intégration existante aux espaces de travail avec le rôle souhaité.

**Pour accorder aux espaces de travail l’accès aux intégrations Adobe I/O et affecter des rôles :**

1. Ouvrez le **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Cliquez sur l’onglet **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Sélection du produit dans Adobe Admin Console](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Sélectionnez l’espace de travail souhaité (profil produit).

   ![Sélection du profil produit](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Cliquez sur l’onglet **[!UICONTROL Intégrations]**.

   ![Onglet Intégrations](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditionnel) Pour ajouter une intégration, cliquez sur **[!UICONTROL Ajouter une intégration]**, sélectionnez l’intégration souhaitée, puis cliquez sur **[!UICONTROL Enregistrer]**.

1. Dans la liste déroulante **[!UICONTROL Rôle produit]**, sélectionnez le rôle de votre choix pour cet espace de travail :

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Similaire au rôle d’observateur (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’éditeur dispose de l’autorisation supplémentaire d’activer les activités. |
