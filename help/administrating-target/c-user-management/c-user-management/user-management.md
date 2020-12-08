---
keywords: add user;manage user;user permissions
description: Vous pouvez ajouter des utilisateurs à Adobe Target et gérer leurs autorisations dans le Adobe Admin Console.
title: Utilisateurs
feature: user management
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 47%

---


# Utilisateurs{#users}

You can add users and manage their permissions in the [!DNL Adobe Admin Console].

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL autorisations] est disponible dans le cadre de la solution [!DNL Target] Premium. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.
>
>* **[!DNL Target]Clients** standard : Si l’onglet [!UICONTROL Utilisateurs] ([!UICONTROL Administration > Utilisateurs]) (et non l’onglet **[!UICONTROL Propriétés]** ) s’affiche, votre entreprise dispose d’une licence [!DNL Target] Standard. [!DNL Target]Les clients [! Standard doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clients** Premium : Si les onglets [!UICONTROL Utilisateurs] et [!UICONTROL Propriétés] ([!UICONTROL Administration > Propriétés]) s’affichent, votre entreprise dispose d’une licence [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>
Pour plus d’informations sur la gestion des utilisateurs et des autorisations, voir [Gestion des produits et des profils](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) dans le Guide *de l’utilisateur de* l’entreprise et des équipes.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. These IDs are for members of [!DNL Adobe] teams so that they can assist you with your new account and with your use of [!DNL Adobe Target], should you need help. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her [!DNL Adobe Experience Cloud] account and then logs in to [!DNL Target Standard/Premium].

Par défaut, tous les utilisateurs de [!DNL Target] commencent avec un rôle d’observateur.

Admin users are identified in the [!UICONTROL Users] list. Contactez l’un des administrateurs système si vous souhaitez modifier votre niveau d’accès.

## Informations sur l&#39;utilisateur vue depuis la Cible

Vous pouvez vue une liste de vos utilisateurs actuels dans votre environnement de Cible, y compris leurs rôles par espace de travail et leurs adresses électroniques directement depuis la Cible interne.

Pour vue à la page Utilisateurs, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**.

![Liste utilisateur depuis la Cible](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser le [!UICONTROL Adobe Admin Console], comme expliqué ci-dessous.

## Accès à Adobe Admin Console {#access}

Pour les tâches effectuées dans Adobe Admin Console, accédez à la console en procédant comme suit :

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** > Gestion des **** utilisateurs.

   OU

   Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), then sign in using your Adobe ID, if you have not already logged in.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Add users {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans le Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Utilisateurs]** > **[!UICONTROL Utilisateurs]** pour créer de nouveaux utilisateurs ou pour modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Create user groups {#user-groups}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. [Dans le Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Utilisateurs]** > Groupes **[!UICONTROL d’]** utilisateurs pour créer de nouveaux groupes d’utilisateurs ou pour modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. For example, a Standard approver user cannot change an observer to an approver, without also having [!DNL Experience Cloud] Admin rights.

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. They are invited by email from the [!DNL Experience Cloud] and must confirm their email addresses before their accounts are registered.

1. [Dans Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur l’espace de travail de votre choix (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   Cet onglet [!UICONTROL Utilisateurs de ]répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez dans la liste déroulante un rôle d’autorisations (approbateur, éditeur ou observateur) pour chaque utilisateur de la colonne [!UICONTROL Rôle du produit].

   ![Liste déroulante Rôle du produit](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Semblable au rôle d’observateur (peut vue des activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle Editeur dispose des autorisations supplémentaires pour activer les activités. |

Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Training video: How to Configure Target Workspaces ![Tutorial badge](/help/assets/tutorial.png)

Objectifs de la formation :

* Accès à Adobe Admin Console depuis l’interface Adobe Target (trois manières)
* Configuration d’un espace de travail dans Adobe Admin Console
   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail
* Utilisation des espaces de travail par défaut

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] Administration [!UICONTROL (anciennement] Configuration ) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur sur l’ensemble du produit. Les informations de la vidéo suivante sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Les vidéos mises à jour seront bientôt publiées.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
