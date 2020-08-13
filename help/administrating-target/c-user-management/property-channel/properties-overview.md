---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: Informations sur les tâches requises pour ajouter des utilisateurs à votre mise en œuvre d’Adobe Target ; création d’espaces de travail, de groupes d’utilisateurs et de propriétés ; mise à jour de votre mise en œuvre Target afin d’inclure le paramètre at_property ; spécification des rôles et des autorisations.
title: Configuration des autorisations d’Enterprise
feature: user management
subtopic: Getting Started
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 69%

---


# ![PREMIUM](/help/assets/premium.png) Configuration des autorisations d’Entreprise{#configure-enterprise-permissions}

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

Le tableau suivant répertorie les tâches nécessaires pour créer des propriétés et attribuer des rôles et des autorisations aux utilisateurs : Pour plus d’informations sur chaque tâche, consultez les sections ci-dessous.

| Tâche | Exécutée dans |
|--- |--- |
| 1. Ajout d’utilisateurs (facultatif) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Création d’un espace de travail (profil produit) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Création de groupes d’utilisateurs (facultatif) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Création de propriétés | [!DNL Target] L’nterface utilisateur |
| 5. Mise à jour de l’implémentation afin d’inclure le paramètre `at_property` | [!DNL Target] interface utilisateur, fonctions at.js, [!DNL Adobe Launch] ou [!DNL Dynamic Tag Management] |
| 6. Spécification des rôles et autorisations | [!DNL Adobe Admin Console for Enterprise] |

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. Dans Adobe Target, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Propriétés]** > **[!UICONTROL Attribuer des propriétés aux espaces de travail]**.

   OU

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Étape 1. Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

Lorsque vous commencez à utiliser la nouvelle fonction [!UICONTROL Propriétés], vous devez gérer les utilisateurs exclusivement dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont migrés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur l’onglet **[!UICONTROL Utilisateurs]** situé en haut de la page > **[!UICONTROL Ajouter des utilisateurs]** pour créer de nouveaux utilisateurs ou modifier des utilisateurs existants
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Étape 2 : Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Un espace de travail (profil de produits) permet à une organisation d’affecter un ensemble spécifique d’utilisateurs à un ensemble spécifique de propriétés. Un espace de travail peut être comparé à une suite de rapports dans [!DNL Analytics].

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the &quot;Default Workspace&quot; configuration to these newer, limited-access workspaces.

Les clients peuvent utiliser ces espaces de travail pour séparer l’accès à différentes équipes par région, unité opérationnelle, section de site ou par toute autre méthode de leur choix.

Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent même leur être attribués dans chaque espace de travail.

1. Dans [!DNL Admin Console], cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![espace de travail](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Créez l’espace de travail souhaité (profil produit) :

   * **Accès par défaut** : toutes les activités sont fusionnées dans un seul projet ainsi nommé. Cela n’a aucune incidence sur les clients. Tous les rôles d’utilisateur et les fonctionnalités restent identiques à ce qu’ils étaient avant ce changement.

      Toutes les activités créées dans [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] et [!DNL Target Classic] font elles aussi partie de l’espace de travail « Accès par défaut ». Actuellement, vous ne pouvez pas déplacer les projets de l’accès par défaut vers un autre projet.

   * **Nouveaux espaces de travail (profils produit)** : procédez comme suit pour commencer à profiter de la nouvelle fonctionnalité d’autorisations :

      * Créez de nouveaux espaces de travail dans [!DNL Admin Console for Enterprise].
      * Affectez des propriétés Target aux espaces de travail.

   Utilisez ces espaces de travail pour répartir l’accès entre différentes équipes par région, unité opérationnelle, section du site ou par toute autre méthode de votre choix. Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent leur être attribués dans chaque espace de travail.

1. Suivez les instructions de la page [Gestion de produits et de configurations](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) du *Guide d’utilisation Enterprise*.

>[!NOTE]
>Pour plus d’informations sur la configuration des espaces de travail, consultez la vidéo de formation ci-dessous.

### Obtain your workspace ID {#workspace-id}

Vous devez transmettre l’identifiant de l’espace de travail pour exploiter les autorisations d’Enterprise dans les [API Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. Dans [Adobe Admin Console](https://adminconsole.adobe.com), cliquez sur l’onglet [!UICONTROL Produits], puis sur le produit dans le menu de gauche pour afficher la liste PLC (espace de travail).
1. Cliquez sur le PLC de votre choix (espace de travail), puis localisez l’identifiant « profils » dans l’URL, comme illustré ci-dessous.

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Étape 3. Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. Dans Admin Console, cliquez sur l’onglet **[!UICONTROL Utilisateurs]** situé en haut de la page > **[!UICONTROL Groupes d’utilisateurs]** pour créer de nouveaux groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions de la page [Gestion de produits et de configurations](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) du *Guide d’utilisation Enterprise*.

## Étape 4. Créer des propriétés {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Les propriétés sont activées en ajoutant une paire nom/valeur spécifique en tant que paramètre avec tout appel (appel de Cible, appel api, etc.) à Target.

Les propriétés appartiennent à des canaux spécifiques (web, mobile, courrier électronique, API/autre)..

**Conseil** : pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. Cliquez sur **Créer une propriété**.

   ![Boîte de dialogue Nouvelle propriété](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Renseignez les champs suivants :

   * **Nom de la propriété (obligatoire) :** Attribuez un nom descriptif à la propriété.
   * **Description** : décrivez la propriété (facultatif).
   * **Canal** : Sélectionnez le canal souhaité pour la propriété : web, application mobile, courrier électronique ou autre/API (un décodeur ou une console PlayStation, par exemple).

1. Cliquez sur **[!UICONTROL Copier]** pour copier le code dans le Presse-papiers que vous utiliserez lors de l&#39;exécution des étapes de la section [5 : Mettez à jour votre implémentation pour inclure le paramètre](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)at_property.
1. Cliquez ensuite sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>Pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**Pour obtenir le code de paramètre`at_property`, procédez comme suit :**

1. (Conditionnel) Utilisez le code de mise en œuvre que vous avez généré et enregistré dans le Presse-papiers durant les étapes de la section [4. Création de propriétés](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD), puis passez à l’étape 2.

   OU

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. Pointez la souris sur la colonne [!UICONTROL Dernière mise à jour] pour connaître la propriété recherchée à afficher, puis cliquez sur l’icône [!UICONTROL Code].

      ![Code de survol de propriété](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Cliquez avec le bouton droit de la souris sur le code de mise en œuvre surligné pour le copier dans le Presse-papiers.

      ![Code de propriété](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   La mise en œuvre [!DNL Target] peut être mise à jour de plusieurs façons. Par exemple, utilisez les méthodes suivantes pour les pages web :

   * **Au moyen d’un paramètre global dans la[!DNL Adobe Launch] :**

      For more information, see [Add Global Target Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **Au moyen d’un paramètre global dans la[!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      Pour en savoir plus, voir [Paramètres globaux – Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) dans la *documentation de la Dynamic Tag Management*.

   * **Via la fonction targetPageParams() :** placez le code suivant dans le <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> balises, au-dessus de la référence at.js ou mbox.js.

      ![](assets/property_token_1.png)

      Pour en savoir plus sur la façon de procéder avec at.js, voir [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Au moyen de la fonction mboxCreate() :**

      ![](assets/property_token_3.png)

      Pour en savoir plus sur la façon de procéder avec at.js, voir [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) et [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Dans Admin Console, cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Espace de travail](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur le nom du profil souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Cliquez sur **[!UICONTROL Utilisateurs]**.

   Cet onglet [!UICONTROL Utilisateurs de ]répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![Liste déroulante Rôle du produit](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Semblable au rôle d’observateur (peut vue des activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle Editeur dispose des autorisations supplémentaires pour activer les activités. |

   Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] Administration [!UICONTROL (anciennement] Configuration ) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur sur l’ensemble du produit. Les informations contenues dans les vidéos suivantes sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Les vidéos mises à jour seront bientôt publiées.

### Configuration des espaces de travail de Cible (6:55) - Badge ![du didacticiel](/help/assets/tutorial.png)

Cette vidéo explique comment créer des espaces de travail.

* Accès à Adobe Admin Console depuis l’interface Adobe Target (3 manières)
* Configuration d’un espace de travail dans Adobe Admin Console

   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail

* Utilisation des espaces de travail par défaut

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* Comment créer une propriété dans l’interface [!DNL Adobe Target]
* Comment générer un jeton de propriété à inclure dans la mise en œuvre des propriétés
* Familiarisez-vous avec les trois méthodes de mise en œuvre :

   * Web
   * Applications mobiles
   * Courrier électronique, boîtier décodeur ou appels d’API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
