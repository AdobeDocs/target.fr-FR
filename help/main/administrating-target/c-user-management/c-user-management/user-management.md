---
keywords: ajout utilisateur;gérer utilisateur;autorisations utilisateur
description: Découvrez comment utiliser  [!DNL Adobe Admin Console]  pour gérer les utilisateurs et utilisatrices, leurs autorisations et leurs droits dans  [!DNL Adobe Target Standard].
title: Comment ajouter des utilisateurs et utilisatrices et gérer des autorisations pour un compte  [!DNL Target Standard]  ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 484971ab0fcd07205935c0fef3ea1484f40c3e96
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 63%

---

# Utilisateurs et utilisatrices

Ajoutez des utilisateurs et utilisatrices et gérez leurs autorisations dans [!DNL Adobe Admin Console] pour un compte [!DNL Target Standard].

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Properties] et [!UICONTROL Permissions] est disponible dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>
>Vous pouvez déterminer si votre entreprise dispose d’une licence [!UICONTROL Standard] ou [!UICONTROL Premium] en cliquant sur le lien [!UICONTROL Administration] dans la partie supérieure de l’interface utilisateur de [!DNL Target].
>
>* **[!DNL Target][!UICONTROL Standard] clients** : si vous voyez l’onglet [!UICONTROL Users] ([!UICONTROL Administration > Users]) (et non l’onglet **[!UICONTROL Properties]**), votre entreprise dispose d’une licence [!DNL Target] [!UICONTROL Standard]. [!DNL Target] clients [!UICONTROL Standard] doivent suivre les instructions de cet article pour ajouter des utilisateurs et attribuer des autorisations dans le [!DNL Adobe Admin Console].
>
>* Clients **[!DNL Target]Premium** : si vous voyez l’onglet [!UICONTROL Users] et l’onglet [!UICONTROL Properties] ([!UICONTROL Administration > Properties]), votre entreprise dispose d’une licence [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>Pour plus d’informations sur la gestion des utilisateurs et des autorisations, consultez la page [Gestion des produits et des profils](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html) dans le *Guide d’utilisation d’entreprise et d’équipes*.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Grâce à ces identifiants, les membres des équipes [!DNL Adobe] pourront vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Les nouveaux utilisateurs ne seront pas répertoriés sur la page [!UICONTROL Users] tant qu’ils ne se seront pas connectés à l’aide de leur compte [!DNL Adobe Experience Cloud], puis à [!DNL Target].

Par défaut, tous les utilisateurs [!DNL Target] commencent avec des autorisations [!UICONTROL Observer].

Les utilisateurs administrateurs sont répertoriés dans la liste des [!UICONTROL Users]. Pour faire changer votre niveau d’accès, contactez l’un des administrateurs système.

## Afficher des informations sur les utilisateurs et les utilisatrices dans [!DNL Target]

Vous pouvez afficher la liste des personnes actuelles dans l’interface utilisateur [!DNL Target], y compris leurs rôles par espace de travail et leurs adresses e-mail.

Pour afficher la page [!UICONTROL Users], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser l’[!UICONTROL Adobe Admin Console] , comme expliqué ci-dessous.

## Accéder à [!DNL Adobe Admin Console] {#access}

Pour les tâches effectuées dans [!DNL Adobe Admin Console], accédez à la console en procédant comme suit :

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   Ou

   Rendez-vous à l’adresse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) et connectez-vous à l’aide de votre Adobe ID si ce n’est pas déjà fait.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs entreprises, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’entreprise appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans l’Admin Console ](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE) cliquez sur **[!UICONTROL Users]** > **[!UICONTROL Users]** pour créer des utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs et d’utilisatrices (développeurs, développeuses, analystes, responsables du marketing, directeurs, directrices) et leur attribuer des droits d’accès à l’échelle de plusieurs produits et espaces de travail [!DNL Adobe]. Il est aussi facile d’affecter tous les droits d’accès de différents produits [!DNL Adobe] à une nouvelle personne membre d’équipe qu’à un groupe de personnes spécifique.

1. [Dans l’Admin Console ](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Users]** > **[!UICONTROL User Groups]** pour créer des groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Par exemple, un utilisateur approbateur [!UICONTROL Standard] ne peut pas changer un observateur en approbateur s’il ne dispose pas des droits d’administrateur [!DNL Experience Cloud].

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique depuis [!DNL Experience Cloud] et doivent confirmer leur adresse e-mail avant que leurs comptes ne soient enregistrés.

>[!NOTE]
>
>Pour afficher les activités dans [!DNL Target], les utilisateurs doivent être directement affectés à un espace de travail avec au moins le rôle [!UICONTROL Observer]. L’affectation par le biais de groupes d’utilisateurs est insuffisante. Il est généralement recommandé d’accorder aux utilisateurs l’accès à l’espace de travail par défaut.

1. [Dans l’Admin Console ](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Products]**, puis sélectionnez le nom du produit souhaité.

1. Cliquez sur l’espace de travail souhaité (par exemple, Espace de travail par défaut).

   L’onglet [!UICONTROL Users] affiche tous les utilisateurs dans cet espace de travail.

1. Sélectionnez le rôle d’autorisations souhaité ([!UICONTROL Approver], [!UICONTROL Editor], [!UICONTROL Observer] ou [!UICONTROL Publisher]) à l’aide de la liste déroulante pour chaque utilisateur de la colonne [!UICONTROL Product Role] .

   | Rôle | Description |
   |--- |--- |
   | [!UICONTROL Approver] | Peut créer, modifier et activer ou arrêter les activités. |
   | [!UICONTROL Editor] | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | [!UICONTROL Observer] | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | [!UICONTROL Publisher] | Similaire au rôle [!UICONTROL Observer] (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle [!UICONTROL Publisher] dispose de l’autorisation supplémentaire d’activer les activités. |

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
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Setup]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations de la vidéo suivante sont généralement correctes. Toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/3421731?captions=fre_fr)
