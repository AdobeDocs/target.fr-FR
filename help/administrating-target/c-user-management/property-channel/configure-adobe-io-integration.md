---
description: Informations sur l'octroi d'intégrations d'E/S Adobe à tous les espaces de travail avec le rôle souhaité.
keywords: intégration ; rôles ; permissions utilisateur ; console d'administration
seo-description: Informations sur l'octroi d'intégrations d'E/S existantes d'Adobe à tous les espaces de travail avec le rôle souhaité dans Adobe Target
seo-title: Accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et affecter des rôles dans Adobe Target
solution: Target
subtopic: Prise en main
title: Accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et attribuer des rôles
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) accorde aux intégrations d'E/S Adobe l'accès aux espaces de travail et leur affectation

[!UICONTROL Les permissions d'entreprise] permettent [!DNL Target] aux clients d'utiliser une seule organisation, mais la divisent en espaces de travail pour leurs différents processus ou équipes.

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

La fonction [!UICONTROL Autorisations] d'entreprise facilite la mise à l'échelle efficace des programmes d'optimisation entre équipes. Bien que la fonctionnalité soit disponible dans [!DNL Target] l'interface utilisateur, les API Admin ne sont pas associées à la prise en charge correspondante jusqu'à la fin de 2019. Dans la version [!DNL Target] de février 2019, Adobe a mis à jour les API d'administration afin que vous puissiez utiliser le compte d'intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, bien qu'auparavant, les API Admin étaient limitées à l'espace de travail par défaut, la mise à jour de février 2019 autorisait l'accès à tous les espaces de travail avec [!UICONTROL accès approbateur] .

Avec la version [!DNL Target] de septembre 2019, [!DNL Target][!UICONTROL les permissions d'entreprise] offrent aux clients les commandes d'accès suivantes :

* Vous pouvez choisir les espaces de travail auxquels l'intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l'intégration d'Adobe I/S : [!UICONTROL Approbateur], [!UICONTROL Éditeur]ou [!UICONTROL Observateur].

Cette mise à jour prend en charge les cas d'utilisation suivants :

* Accordez à l'intégration d'E/S Adobe l'accès à tous les espaces de travail avec le rôle [!UICONTROL d'observateur] à des fins de création de rapports, sans droits de création ou de modification des ressources.
* Octroyez à l'intégration d'E/S Adobe l'accès permettant de sélectionner les espaces de travail avec le rôle approprié afin d'autoriser une équipe centrale à apporter des modifications basées sur l'API dans quelques espaces de travail seulement.
* Laissez chaque équipe propriétaire de son espace de travail disposer de sa propre intégration chaque fois que l'équipe est prête à explorer les API et à choisir le rôle en question.
* Combinez l'un des scénarios ci-dessus.

**Action requise**: Les clients qui exploitent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et création de rapports) sur tous les espaces de travail doivent accorder à leur intégration d'E/S existante Adobe l'accès à tous les espaces de travail avec le rôle souhaité selon leur cas d'utilisation. Pour ce faire, sélectionnez chaque [!DNL Target][!UICONTROL profil du produit] dans [!DNL Adobe Admin Console] l'onglet [!UICONTROL Intégration] et ajoutez-y les intégration. Avant la version de septembre, toutes les intégrations utilisées à l'aide [!UICONTROL d'un] accès Approbateur, quel que soit le choix choisi dans la [!UICONTROL liste déroulante Rôle] du produit. Vous pouvez désormais choisir un rôle.

>[!NOTE]
>
>Si cette action n'est pas effectuée, après la version [!DNL Target] de septembre 2019, les commandes d'accès activeront et vous constaterez l'accès à l'espace de travail par défaut uniquement si c'est le mode de configuration. Il n'existe pas de réaction négative à la définition des intégrations à l'avance. Plus vous apportez cette modification, meilleure est la meilleure. Selon le nombre d'espaces de travail de votre organisation, ce processus ne prend que quelques clics pour ajouter une intégration existante dans les espaces de travail avec le rôle souhaité.

**Pour accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et affecter des rôles :**

1. Ouvrez la console **[d'administration Adobe](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Choix du produit dans la console d'administration Adobe](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Sélectionnez l'espace de travail (profil du produit).

   ![Sélectionner le profil du produit](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Onglet Intégrations](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditionnel) Pour ajouter une nouvelle intégration, cliquez sur **[!UICONTROL Ajouter une intégration]**, sélectionnez l'intégration souhaitée, puis cliquez **[!UICONTROL sur Enregistrer]**.

1. Dans la liste **[!UICONTROL déroulante Rôle]** du produit, sélectionnez le rôle de votre choix pour cet espace de travail :

   * [!UICONTROL Approbateur]
   * [!UICONTROL Éditeur]
   * [!UICONTROL Observateur]
   ![Choisir un rôle de profil du produit](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
