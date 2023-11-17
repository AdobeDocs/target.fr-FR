---
keywords: ajout utilisateur;gérer utilisateur;autorisations utilisateur
description: Découvrez comment utiliser le [!DNL Adobe Admin Console] pour gérer les utilisateurs et leurs autorisations et droits dans [!DNL Adobe Target Standard].
title: Comment ajouter des utilisateurs et gérer des autorisations pour une [!DNL Target Standard] Compte ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 73%

---

# Utilisateurs

Ajoutez des utilisateurs et gérez leurs autorisations dans le [!DNL Adobe Admin Console] pour un [!DNL Target Standard] compte .

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL Autorisations] est disponible dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>
>Vous pouvez déterminer si votre organisation dispose d’une [!UICONTROL Standard] ou [!UICONTROL Premium] en cliquant sur la [!UICONTROL Administration] en haut de la page [!DNL Target] Interface utilisateur.
>
>* **[!DNL Target] Clients standard** : si vous voyez l’onglet [!UICONTROL Utilisateurs] ([!UICONTROL Administration > Utilisateurs]) (et non l’onglet **[!UICONTROL Propriétés]**), votre entreprise dispose d’une licence [!DNL Target] Standard.  [!DNL Target]Les clients  Standard doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>* Clients **[!DNL Target]Premium** : si les onglets [!UICONTROL Utilisateurs] et [!UICONTROL Propriétés] s’affiche ([!UICONTROL Administration > Propriétés]), votre entreprise dispose d’une licence [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>Pour plus d’informations sur la gestion des utilisateurs et des autorisations, consultez la page [Gestion des produits et des profils](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html) dans le *Guide d’utilisation d’entreprise et d’équipes*.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Grâce à ces identifiants, les membres des équipes [!DNL Adobe] pourront vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Les nouveaux utilisateurs ne seront pas répertoriés dans la [!UICONTROL Utilisateurs] jusqu’à ce qu’ils se connectent à l’aide de leur [!DNL Adobe Experience Cloud] puis connectez-vous à [!DNL Target].

Par défaut, tous les [!DNL Target] les utilisateurs commencent par [!UICONTROL Observateur] autorisations.

Les utilisateurs administrateurs sont répertoriés dans la liste des [!UICONTROL Utilisateurs]. Pour faire changer votre niveau d’accès, contactez l’un des administrateurs système.

## Affichage des informations sur les utilisateurs dans [!DNL Target]

Vous pouvez afficher la liste de vos utilisateurs actuels dans le [!DNL Target] l’interface utilisateur, y compris leurs rôles par espace de travail et leurs adresses électroniques.

Pour afficher la variable [!UICONTROL Utilisateurs] page, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**.

![Liste des utilisateurs depuis Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser [!UICONTROL Adobe Admin Console], comme expliqué ci-dessous.

## Accédez au [!DNL Adobe Admin Console] {#access}

Pour les tâches effectuées dans la variable [!DNL Adobe Admin Console], accédez à la console en procédant comme suit :

1. À partir de [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** > **[!UICONTROL Gestion des utilisateurs]**.

   Ou

   Rendez-vous à l’adresse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) et connectez-vous à l’aide de votre Adobe ID si ce n’est pas déjà fait.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs entreprises, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’entreprise appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Utilisateurs]** > **[!UICONTROL Utilisateurs]** pour créer des utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, marketeurs, directeurs, etc.), puis attribuer des privilèges sur plusieurs [!DNL Adobe] produits et espaces de travail. Attribution à un nouveau membre de l’équipe de tous les privilèges appropriés sur différents [!DNL Adobe] les produits peuvent être aussi faciles à ajouter à un groupe d’utilisateurs spécifique.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Groupes d’utilisateurs]** pour créer des groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Par exemple, un [!UICONTROL Standard] l’utilisateur approbateur ne peut pas changer un observateur en approbateur, sans avoir également [!DNL Experience Cloud] Droits d’administrateur.

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique depuis [!DNL Experience Cloud] et doivent confirmer leur adresse e-mail avant que leurs comptes ne soient enregistrés.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur l’espace de travail souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   Cet onglet [!UICONTROL Utilisateurs] de répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez le rôle d’autorisations souhaité ([!UICONTROL Approbateur], [!UICONTROL Éditeur], [!UICONTROL Observateur] ou [!UICONTROL Éditeur]) en utilisant la liste déroulante pour chaque utilisateur dans la variable [!UICONTROL Rôle de produit] colonne .

   ![Liste déroulante Rôle du produit](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | [!UICONTROL Approbateur] | Peut créer, modifier et activer ou arrêter les activités. |
   | [!UICONTROL Éditeur] | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | [!UICONTROL Observateur] | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | [!UICONTROL Éditeur] | Semblable au [!UICONTROL Observateur] rôle (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’[!UICONTROL éditeur] dispose de l’autorisation supplémentaire d’activer les activités. |

Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/fr/enterprise/using/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Vidéo de formation : configuration d’Adobe Target Workspaces ![Badge du tutoriel](/help/main/assets/tutorial.png)

Objectifs de la formation :

* Accès à Adobe Admin Console depuis l’interface Adobe Target (trois manières)
* Configuration d’un espace de travail dans Adobe Admin Console
   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail
* Utilisation des espaces de travail par défaut

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Configuration]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations de la vidéo suivante sont généralement correctes. Toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
