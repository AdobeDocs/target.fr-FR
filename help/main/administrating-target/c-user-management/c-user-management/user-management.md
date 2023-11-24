---
keywords: ajout utilisateur;gérer utilisateur;autorisations utilisateur
description: Découvrez comment utiliser  [!DNL Adobe Admin Console]  pour gérer les utilisateurs et utilisatrices, leurs autorisations et leurs droits dans  [!DNL Adobe Target Standard].
title: Comment ajouter des utilisateurs et utilisatrices et gérer des autorisations pour un compte  [!DNL Target Standard]  ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: ht
source-wordcount: '897'
ht-degree: 100%

---

# Utilisateurs et utilisatrices

Ajoutez des utilisateurs et utilisatrices et gérez leurs autorisations dans [!DNL Adobe Admin Console] pour un compte [!DNL Target Standard].

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL Autorisations] est disponible dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>
>Vous pouvez déterminer si votre organisation dispose d’une licence [!UICONTROL Standard] ou [!UICONTROL Premium] en cliquant sur le lien [!UICONTROL Administration] dans la partie supérieure de l’interface utilisateur de [!DNL Target].
>
>* **[!DNL Target]Clientèle [!UICONTROL Standard]** : si vous voyez l’onglet [!UICONTROL Utilisateurs] ([!UICONTROL Administration > Utilisateurs]) (et non l’onglet **[!UICONTROL Propriétés]**), votre entreprise dispose d’une licence [!DNL Target] [!UICONTROL Standard]. [!DNL Target]Les clientes et clients [!UICONTROL Standard] doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et utilisatrices et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>* Clients **[!DNL Target]Premium** : si les onglets [!UICONTROL Utilisateurs] et [!UICONTROL Propriétés] s’affiche ([!UICONTROL Administration > Propriétés]), votre entreprise dispose d’une licence [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>Pour plus d’informations sur la gestion des utilisateurs et des autorisations, consultez la page [Gestion des produits et des profils](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html) dans le *Guide d’utilisation d’entreprise et d’équipes*.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Grâce à ces identifiants, les membres des équipes [!DNL Adobe] pourront vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Les nouveaux utilisateurs et utilisatrices ne s’afficheront pas sur la page [!UICONTROL Utilisateurs] jusqu’à ce qu’ils se connectent à l’aide de leur compte [!DNL Adobe Experience Cloud], puis à [!DNL Target].

Par défaut, toutes les personnes utilisant [!DNL Target] commencent avec un rôle d’[!UICONTROL observateur].

Les utilisateurs administrateurs sont répertoriés dans la liste des [!UICONTROL Utilisateurs]. Pour faire changer votre niveau d’accès, contactez l’un des administrateurs système.

## Afficher des informations sur les utilisateurs et les utilisatrices dans [!DNL Target]

Vous pouvez afficher la liste des personnes actuelles dans l’interface utilisateur [!DNL Target], y compris leurs rôles par espace de travail et leurs adresses e-mail.

Pour afficher la page [!UICONTROL Utilisateurs], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**.

![Liste des utilisateurs depuis Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser [!UICONTROL Adobe Admin Console], comme expliqué ci-dessous.

## Accéder à [!DNL Adobe Admin Console] {#access}

Pour les tâches effectuées dans [!DNL Adobe Admin Console], accédez à la console en procédant comme suit :

1. À partir de [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** > **[!UICONTROL Gestion des utilisateurs]**.

   Ou

   Rendez-vous à l’adresse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) et connectez-vous à l’aide de votre Adobe ID si ce n’est pas déjà fait.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs entreprises, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’entreprise appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Utilisateurs]** > **[!UICONTROL Utilisateurs]** pour créer des utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs et d’utilisatrices (développeurs, développeuses, analystes, responsables du marketing, directeurs, directrices) et leur attribuer des droits d’accès à l’échelle de plusieurs produits et espaces de travail [!DNL Adobe]. Il est aussi facile d’affecter tous les droits d’accès de différents produits [!DNL Adobe] à une nouvelle personne membre d’équipe qu’à un groupe de personnes spécifique.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Groupes d’utilisateurs]** pour créer des groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Ainsi, une personne approbatrice [!UICONTROL Standard] ne peut pas changer une personne observatrice en personne approbatrice si elle ne dispose pas des droits d’administration dans [!DNL Experience Cloud].

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique depuis [!DNL Experience Cloud] et doivent confirmer leur adresse e-mail avant que leurs comptes ne soient enregistrés.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur l’espace de travail souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   Cet onglet [!UICONTROL Utilisateurs] de répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez un rôle d’autorisations ([!UICONTROL approbateur], [!UICONTROL rédacteur], [!UICONTROL observateur] ou [!UICONTROL éditeur]) dans la liste déroulante, et ce pour chaque utilisateur et utilisatrice de la colonne [!UICONTROL Rôle du produit].

   ![Liste déroulante Rôle du produit](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | [!UICONTROL Approbateur] | Peut créer, modifier et activer ou arrêter les activités. |
   | [!UICONTROL Éditeur] | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | [!UICONTROL Observateur] | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | [!UICONTROL Éditeur] | Similaire au rôle d’[!UICONTROL observateur] (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’[!UICONTROL éditeur] dispose de l’autorisation supplémentaire d’activer les activités. |

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
