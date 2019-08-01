---
description: Informations sur l'octroi d'intégrations d'E/S Adobe à tous les espaces de travail avec le rôle souhaité.
keywords: intégration ; rôles ; permissions utilisateur ; console d'administration
seo-description: Informations sur l'octroi d'intégrations d'E/S existantes d'Adobe à tous les espaces de travail avec le rôle souhaité dans Adobe Target
seo-title: Accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et affecter des rôles dans Adobe Target
solution: Target
subtopic: Prise en main
title: Accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et attribuer des rôles
translation-type: tm+mt
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

---


# ![PREMIUM](/help/assets/premium.png) accorde aux intégrations d'E/S Adobe l'accès aux espaces de travail et leur affectation

[!UICONTROL Les permissions d'entreprise] permettent [!DNL Target] aux clients d'utiliser une seule organisation, mais la divisent en espaces de travail pour leurs différents processus ou équipes.

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* Vous pouvez choisir les espaces de travail auxquels l'intégration peut être appliquée.
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Cette mise à jour prend en charge les cas d'utilisation suivants :

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Octroyez à l'intégration d'E/S Adobe l'accès permettant de sélectionner les espaces de travail avec le rôle approprié afin d'autoriser une équipe centrale à apporter des modifications basées sur l'API dans quelques espaces de travail seulement.
* Laissez chaque équipe propriétaire de son espace de travail disposer de sa propre intégration chaque fois que l'équipe est prête à explorer les API et à choisir le rôle en question.
* Combinez l'un des scénarios ci-dessus.

**Action requise**: Les clients qui exploitent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et création de rapports) sur tous les espaces de travail doivent accorder à leur intégration d'E/S existante Adobe l'accès à tous les espaces de travail avec le rôle souhaité selon leur cas d'utilisation. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. Vous pouvez désormais choisir un rôle.

This action should be performed during the month of **August 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. Il n'existe pas de réaction négative à la définition des intégrations à l'avance. Plus vous apportez cette modification, meilleure est la meilleure. La configuration de ce paramètre est limitée, selon le nombre d'espaces de travail de votre entreprise. Ce processus ne prend que quelques clics pour ajouter une intégration existante dans les espaces de travail avec le rôle souhaité.

**Pour accorder aux intégrations d'E/S Adobe l'accès aux espaces de travail et affecter des rôles :**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Choix du produit dans la console d'administration Adobe](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Sélectionnez l'espace de travail (profil du produit).

   ![Sélectionner le profil du produit](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Onglet Intégrations](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click **[!UICONTROL Add Integration]**, select the desired integration, then click **[!UICONTROL Save]**.

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   * [!UICONTROL Approbateur]
   * [!UICONTROL Éditeur]
   * [!UICONTROL Observateur]
   ![Choisir un rôle de profil du produit](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
