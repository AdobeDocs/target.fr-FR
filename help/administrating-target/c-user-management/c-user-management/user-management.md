---
description: Vous pouvez ajouter des utilisateurs et gérer leurs autorisations dans Adobe Admin Console.
keywords: ajout utilisateur, gérer utilisateur, autorisations utilisateur
seo-description: Vous pouvez ajouter des utilisateurs et gérer leurs autorisations dans Adobe Admin Console.
seo-title: Utilisateurs
solution: Target
subtopic: Prise en main
title: Utilisateurs
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Utilisateurs{#users}

Vous pouvez ajouter des utilisateurs et gérer leurs autorisations dans Adobe Admin Console.

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL autorisations] est disponible dans le cadre de la solution [!DNL Target] Premium. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>Vous pouvez déterminer si votre organisation dispose d’une licence Standard ou Premium en cliquant sur le lien [!UICONTROL Configuration] dans la partie supérieure de l’interface utilisateur de [!DNL Target].
>
>**Clients[!DNL Target]Standard** : si l’onglet [!UICONTROL Utilisateurs] s’affiche ([!UICONTROL Configuration &gt; Utilisateurs]), votre organisation dispose d’une licence standard [!DNL Target]. Les clients [!DNL Target Standard doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>**Clients[!DNL Target] Premium** : si l’onglet [!UICONTROL Propriétés] s’affiche ([!UICONTROL Configuration &gt; Propriétés]), votre organisation dispose d’une licence Premium [!DNL Target]. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].

Seuls les administrateurs système peuvent ajouter des utilisateurs et gérer leurs autorisations. Le rôle d’administrateur du système est attribué au niveau d’[!DNL Experience Cloud]. Les rôles [!DNL Experience Cloud] diffèrent des rôles gérés dans chaque solution.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Grâce à ces identifiants, les membres des équipes Adobe pourront vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Le nouvel utilisateur apparaîtra sur la page [!UICONTROL Utilisateurs] uniquement lorsqu’il se sera connecté à l’aide de son compte Adobe Experience Cloud et aura accédé à [!DNL Target Standard/Premium] en cliquant sur la carte [!DNL Target].

Par défaut, tous les utilisateurs de [!DNL Target] commencent avec un rôle d’observateur.

Les administrateurs système sont répertoriés dans la liste des utilisateurs. Pour faire changer votre niveau d’accès, contactez l’un de ces administrateurs système.

## Accès à Adobe Admin Console {#access}

Pour les tâches effectuées dans Adobe Admin Console, accédez à la console en procédant comme suit :

1. Rendez-vous à l’adresse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) &gt; connectez-vous à l’aide de votre Adobe ID si ce n’est pas déjà fait.

   OU

   Si vous êtes déjà connecté à Experience Cloud, rendez-vous à l’adresse [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), puis cliquez sur l’icône [!UICONTROL Applis] dans la barre de navigation en haut de l’écran, cliquez sur **[!UICONTROL Administration]** sur le côté droit.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Gestion des utilisateurs]** &gt; **[!UICONTROL Utilisateurs]** pour créer des utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. [Dans Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Gestion des utilisateurs]** &gt; **[!UICONTROL Groupes d’utilisateurs]** pour créer des groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécification des rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Ainsi, un utilisateur approbateur de Standard ne peut pas changer un observateur en approbateur s’il ne dispose pas des droits d’administrateur dans Experience Cloud.

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique depuis Experience Cloud et doivent confirmer leur adresse électronique avant que leur compte ne soit enregistré.

1. [Dans Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Cliquez sur le nom de la configuration souhaitée.
1. Cliquez sur **[!UICONTROL Utilisateurs]**.

   Cet onglet [!UICONTROL Utilisateurs de ]répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. Sélectionnez dans la liste déroulante un rôle d’autorisations (approbateur, éditeur ou observateur) pour chaque utilisateur de la colonne [!UICONTROL Rôle du produit].

   | Rôle | Description |
   |--- |--- |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |

Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Vidéo de formation : Configuration des espaces de travail Target (How to Configure Target Workspaces)

Objectifs de la formation :

* Accès à Adobe Admin Console depuis l’interface Adobe Target (trois manières)
* Configuration d’un espace de travail dans Adobe Admin Console
   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail
* Utilisation des espaces de travail par défaut

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=fre_fr)
