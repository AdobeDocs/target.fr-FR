---
keywords: ajout utilisateur, gérer utilisateur, autorisations utilisateur
description: Découvrez comment utiliser Adobe Admin Console pour gérer les utilisateurs, leurs autorisations et leurs droits dans Adobe Target.
title: Comment ajouter des utilisateurs et gérer les autorisations ?
feature: Administration et configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 48%

---

# Utilisateurs

Ajoutez des utilisateurs et gérez leurs autorisations dans le [!DNL Adobe Admin Console].

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL autorisations] est disponible dans le cadre de la solution [!DNL Target] Premium. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>Vous pouvez déterminer si votre entreprise dispose d’une licence Standard ou Premium en cliquant sur le lien [!UICONTROL Administration] en haut de l’interface utilisateur de [!DNL Target].
>
>* **[!DNL Target]Clients standard** : Si l’onglet   Utilisateur s’affiche ([!UICONTROL Administration > Utilisateurs]) (et non l’onglet  **** Propriétés), votre entreprise dispose d’une licence  [!DNL Target] Standard. [!DNL Target]Les clients [! Standard doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clients Premium** : Si les onglets   Utilisateur et   Propriétés s’affichent ([!UICONTROL Administration > Propriétés]), votre organisation dispose d’une licence  [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>
Pour plus d’informations sur la gestion des utilisateurs et des autorisations, voir [Gestion des produits et des profils](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) dans le *Guide de l’utilisateur Enterprise &amp; Teams*.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Ces identifiants sont destinés aux membres des équipes [!DNL Adobe] afin qu’ils puissent vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Le nouvel utilisateur apparaîtra sur la page [!UICONTROL Utilisateurs] uniquement lorsqu’il se sera connecté à l’aide de son compte [!DNL Adobe Experience Cloud] et aura accédé à [!DNL Target Standard/Premium].

Par défaut, tous les utilisateurs de [!DNL Target] commencent avec un rôle d’observateur.

Les utilisateurs administrateurs sont identifiés dans la liste [!UICONTROL Utilisateurs]. Contactez l’un des administrateurs système si vous souhaitez que votre niveau d’accès soit modifié.

## Affichage des informations sur les utilisateurs dans Target

Vous pouvez afficher une liste de vos utilisateurs actuels dans votre environnement Target, y compris leurs rôles par espace de travail et leurs adresses électroniques directement depuis Target.

Pour afficher la page Utilisateurs, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**.

![Liste des utilisateurs de Target](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser la balise [!UICONTROL Adobe Admin Console], comme expliqué ci-dessous.

## Accès à Adobe Admin Console {#access}

Pour les tâches effectuées dans Adobe Admin Console, accédez à la console en procédant comme suit :

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** > **[!UICONTROL Gestion des utilisateurs]**.

   Ou

   Accédez à [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), puis connectez-vous à l’aide de votre Adobe ID, si vous ne vous êtes pas encore connecté.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans le Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur  **[!UICONTROL Utilisateurs]**  >  **** Utilisateurs pour créer de nouveaux utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. [Dans le Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur  **[!UICONTROL Utilisateurs]**  >  **[!UICONTROL Groupes d’utilisateurs]** pour créer de nouveaux groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Par exemple, un utilisateur approbateur standard ne peut pas changer un observateur en approbateur, sans avoir également les droits [!DNL Experience Cloud] d’administrateur.

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique à partir de [!DNL Experience Cloud] et doivent confirmer leur adresse électronique avant que leur compte ne soit enregistré.

1. [Dans Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur l’espace de travail souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   Cet onglet [!UICONTROL Utilisateurs de ]répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez dans la liste déroulante un rôle d’autorisations (approbateur, éditeur ou observateur) pour chaque utilisateur de la colonne [!UICONTROL Rôle du produit].

   ![Liste déroulante Rôle produit](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Similaire au rôle Observateur (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’éditeur dispose de l’autorisation supplémentaire d’activer les activités. |

Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Vidéo de formation : Configuration des espaces de travail Adobe Target ![Badge du tutoriel](/help/assets/tutorial.png)

Objectifs de la formation :

* Accès à Adobe Admin Console depuis l’interface Adobe Target (trois manières)
* Configuration d’un espace de travail dans Adobe Admin Console
   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail
* Utilisation des espaces de travail par défaut

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Configuration]) a été repensée afin de fournir des performances améliorées, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur sur l’ensemble du produit. Les informations de la vidéo suivante sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
