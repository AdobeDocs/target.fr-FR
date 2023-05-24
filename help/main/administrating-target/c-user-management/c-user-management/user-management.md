---
keywords: ajout utilisateur;gérer utilisateur;autorisations utilisateur
description: Découvrez comment utiliser Adobe Admin Console pour gérer les utilisateurs, leurs autorisations et leurs droits dans Adobe Target.
title: Comment ajouter des utilisateurs et gérer les autorisations ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 4251832a5983ea8950e54d52df5d27bf395894e0
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 100%

---

# Utilisateurs

Ajoutez des utilisateurs et gérez leurs autorisations dans [!DNL Adobe Admin Console].

>[!NOTE]
>
>La fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL autorisations] est disponible dans le cadre de la solution [!DNL Target] Premium. Elle n’est pas disponible dans [!DNL Target] Standard sans une licence [!DNL Target] Premium.
>Vous pouvez déterminer si votre entreprise dispose d’une licence Standard ou Premium en cliquant sur le lien [!UICONTROL Administration] dans la partie supérieure de l’interface utilisateur de [!DNL Target].
>
>* **[!DNL Target]Clients standard** : si vous voyez l’onglet [!UICONTROL Utilisateurs] ([!UICONTROL Administration > Utilisateurs]) (et non l’onglet **[!UICONTROL Propriétés]**), votre entreprise dispose d’une licence [!DNL Target] Standard. Les clients [!DNL Target] Standard doivent suivre les instructions de cette rubrique pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>* Clients **[!DNL Target]Premium** : si les onglets [!UICONTROL Utilisateurs] et [!UICONTROL Propriétés] s’affiche ([!UICONTROL Administration > Propriétés]), votre entreprise dispose d’une licence [!DNL Target] Premium. Les clients [!DNL Target] Premium doivent suivre les instructions données dans [Autorisations des utilisateurs de société](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) et dans [Configurer les autorisations de société](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) pour ajouter des utilisateurs et attribuer des autorisations dans [!DNL Adobe Admin Console].
>
>Pour plus d’informations sur la gestion des utilisateurs et des autorisations, consultez la page [Gestion des produits et des profils](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html) dans le *Guide d’utilisation d’entreprise et d’équipes*.

Lorsque vous commencerez à utiliser [!DNL Adobe Target], vous constaterez que des identifiants (se terminant par Adobe.com) sont pré-renseignés dans votre compte [!DNL Adobe Experience Cloud]. Grâce à ces identifiants, les membres des équipes [!DNL Adobe] pourront vous aider à gérer votre nouveau compte et à utiliser [!DNL Adobe Target], si besoin est. Pour obtenir de l’aide, contactez vos équipes Adobe de la manière habituelle.

Le nouvel utilisateur apparaîtra sur la page [!UICONTROL Utilisateurs] uniquement lorsqu’il se sera connecté à l’aide de son compte [!DNL Adobe Experience Cloud] et aura accédé à [!DNL Target Standard/Premium].

Par défaut, tous les utilisateurs de [!DNL Target] commencent avec un rôle d’observateur.

Les utilisateurs administrateurs sont répertoriés dans la liste des [!UICONTROL Utilisateurs]. Pour faire changer votre niveau d’accès, contactez l’un des administrateurs système.

## Affichage des informations sur les utilisateurs dans Target

Vous pouvez afficher une liste de vos utilisateurs actuels dans votre environnement Target, y compris leurs rôles par espace de travail et leurs adresses électroniques directement depuis Target.

Pour afficher la page Utilisateurs, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**.

![Liste des utilisateurs depuis Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Pour gérer un utilisateur existant ou ajouter de nouveaux utilisateurs, vous devez utiliser [!UICONTROL Adobe Admin Console], comme expliqué ci-dessous.

## Accès à Adobe Admin Console {#access}

Pour les tâches effectuées dans Adobe Admin Console, accédez à la console en procédant comme suit :

1. À partir de [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** > **[!UICONTROL Gestion des utilisateurs]**.

   Ou

   Rendez-vous à l’adresse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) et connectez-vous à l’aide de votre Adobe ID si ce n’est pas déjà fait.

1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs entreprises, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’entreprise appropriée.

## Ajout d’utilisateurs {#add-users}

L’ensemble de la gestion d’utilisateur doit être effectué dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Utilisateurs]** > **[!UICONTROL Utilisateurs]** pour créer des utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Création de groupes d’utilisateurs {#user-groups}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Groupes d’utilisateurs]** pour créer des groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Spécifier les rôles et autorisations {#roles-permissions}

Seuls les administrateurs système peuvent définir des rôles utilisateur dans [!DNL Target]. Ainsi, un utilisateur approbateur de Standard ne peut pas changer un observateur en approbateur s’il ne dispose pas des droits d’administrateur dans [!DNL Experience Cloud].

Les administrateurs système doivent ajouter des utilisateurs au système. Ceux-ci ne sont pas automatiquement ajoutés. Ils sont invités par courrier électronique depuis [!DNL Experience Cloud] et doivent confirmer leur adresse e-mail avant que leurs comptes ne soient enregistrés.

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Onglet Produits](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur l’espace de travail souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   Cet onglet [!UICONTROL Utilisateurs] de répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez dans la liste déroulante un rôle d’autorisations (approbateur, éditeur ou observateur) pour chaque utilisateur de la colonne [!UICONTROL Rôle du produit].

   ![Liste déroulante Rôle du produit](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Similaire au rôle d’observateur (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’éditeur dispose de l’autorisation supplémentaire d’activer les activités. |

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
