---
keywords: ajouter un utilisateur;projet;groupe d’utilisateurs;propriétés;espace de travail;gérer la propriété;propriété;at_property;rôles;autorisations
description: Découvrez comment ajouter des utilisateurs à Adobe Target ; créer des espaces de travail, des groupes d’utilisateurs et des propriétés ; mettre à jour votre mise en oeuvre ; et spécifier les rôles et les autorisations.
title: Comment configurer les autorisations d’Enterprise ?
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 68%

---

# ![PREMIUM](/help/main/assets/premium.png) Configuration des autorisations d’Entreprise

Informations sur les tâches requises pour ajouter des utilisateurs à vos [!DNL Target] la mise en oeuvre; créer des espaces de travail, des groupes d’utilisateurs et des propriétés ; mettre à jour votre [!DNL Target] pour inclure la variable `at_property` paramètre ; et spécifier les rôles et les autorisations.

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution [Target Premium](/help/main/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

Le tableau suivant répertorie les tâches nécessaires pour créer des propriétés et attribuer des rôles et des autorisations aux utilisateurs : Pour plus d’informations sur chaque tâche, consultez les sections ci-dessous.

| Tâche | Exécutée dans |
|--- |--- |
| 1. Ajout d’utilisateurs (facultatif) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Créer un espace de travail (profil de produit) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Création de groupes d’utilisateurs (facultatif) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Créer des propriétés |  Interface utilisateur [!DNL Target] |
| 5 : Mettez à jour votre mise en oeuvre afin d’inclure la variable `at_property` parameter | [!DNL Target] Interface utilisateur, fonctions at.js ou balises dans [!DNL Adobe Experience Platform] |
| 6. Spécification des rôles et autorisations | [!DNL Adobe Admin Console for Enterprise] |

Pour les tâches effectuées dans la variable [!DNL Adobe Admin Console for Enterprise], accédez à la console en procédant comme suit :

1. Dans Adobe Target, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Propriétés]** > **[!UICONTROL Attribution de propriétés aux espaces de travail]**.

   Ou

   Accédez à [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > connectez-vous à l’aide de votre Adobe ID, si ce n’est pas déjà fait.


1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Étape 1. Ajout d’utilisateurs (facultatif) {#section_A92AF0F921B743FEB9E9033433BD816A}

Lorsque vous commencez à utiliser la nouvelle fonction [!UICONTROL Propriétés], vous devez gérer les utilisateurs exclusivement dans [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont migrés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur l’onglet **[!UICONTROL Utilisateurs]** situé en haut de la page > **[!UICONTROL Ajouter des utilisateurs]** pour créer de nouveaux utilisateurs ou modifier des utilisateurs existants
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Étape 2 : Création d’un espace de travail (profil de produit) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Un espace de travail (profil de produit) permet à une organisation d’affecter un ensemble spécifique d’utilisateurs à un ensemble spécifique de propriétés. Un espace de travail peut être comparé à une suite de rapports dans [!DNL Analytics].

Les entreprises peuvent commencer à tirer parti des fonctionnalités d’autorisations d’Enterprise en créant de nouveaux espaces de travail dans [!DNL Admin Console], attribution [!DNL Target] propriétés de ces espaces de travail et déplacement des utilisateurs de la configuration &quot;Espace de travail par défaut&quot; vers ces espaces de travail plus récents à accès limité.

Les clients peuvent utiliser ces espaces de travail pour séparer l’accès à différentes équipes par région, unité opérationnelle, section de site ou par toute autre méthode de leur choix.

Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent même leur être attribués dans chaque espace de travail.

1. Dans [!DNL Admin Console], cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![espace de travail](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

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

### Obtention de l’identifiant de votre espace de travail {#workspace-id}

Vous devez transmettre l’identifiant de l’espace de travail pour exploiter les autorisations d’Enterprise dans les [API Target](https://developer.adobe.com/target/implement/server-side/){target=_blank}.

1. Dans [Adobe Admin Console](https://adminconsole.adobe.com), cliquez sur l’onglet [!UICONTROL Produits], puis sur le produit dans le menu de gauche pour afficher la liste PLC (espace de travail).
1. Cliquez sur le PLC de votre choix (espace de travail), puis localisez l’identifiant « profils » dans l’URL, comme illustré ci-dessous.

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Étape 3. Création de groupes d’utilisateurs (facultatif) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. Dans Admin Console, cliquez sur l’onglet **[!UICONTROL Utilisateurs]** situé en haut de la page > **[!UICONTROL Groupes d’utilisateurs]** pour créer de nouveaux groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions de la page [Gestion de produits et de configurations](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) du *Guide d’utilisation Enterprise*.

## Étape 4. Créer des propriétés {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Les propriétés sont activées en ajoutant une paire nom/valeur spécifique comme paramètre avec n’importe quel appel (appel Target, appel api, etc.) à Target.

Les propriétés appartiennent à des canaux spécifiques (web, mobile, courrier électronique, API/autre)..

**Conseil** : pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Propriétés]** pour afficher la variable [!UICONTROL Propriétés] liste.
1. Cliquez sur **Créer une propriété**.

   Renseignez les champs suivants :

   * **Nom de la propriété (obligatoire) :** Attribuez un nom explicite à la propriété.
   * **Description** : décrivez la propriété (facultatif).
   * **Canal** : Sélectionnez le canal souhaité pour la propriété : web, application mobile, courrier électronique ou autre/API (un décodeur ou une console PlayStation, par exemple).

1. Cliquez sur **[!UICONTROL Copier]** pour copier le code dans le presse-papiers que vous utiliserez lors de l’exécution des étapes de la section [5 : Mise à jour de votre mise en oeuvre afin d’inclure le paramètre at_property](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Cliquez ensuite sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>Pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

## Étape 5 : Mettez à jour votre mise en oeuvre pour inclure le paramètre at_property {#section_9B17A59807A94712BE642942442EBBC8}

Pour utiliser la variable [!DNL Target] fonctionnalité d’autorisations utilisateur, vous devez ajouter la variable `at_property` à tout appel qui parvient à [!DNL Target] (Appel Target, appel api, etc.).

**Pour obtenir le code de paramètre `at_property`, procédez comme suit :**

1. (Conditionnel) Utilisez le code de mise en œuvre que vous avez généré et enregistré dans le Presse-papiers durant les étapes de la section [4. Création de propriétés](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD), puis passez à l’étape 2.

   OU

   Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Propriétés]** pour afficher la variable [!UICONTROL Propriétés] liste.

   1. Pointez la souris sur la colonne [!UICONTROL Dernière mise à jour] pour connaître la propriété recherchée à afficher, puis cliquez sur l’icône [!UICONTROL Code].

      ![Code de survol de propriété](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Cliquez avec le bouton droit de la souris sur le code de mise en œuvre surligné pour le copier dans le Presse-papiers.

1. Mettez à jour votre [!DNL Target] implémentation avec le code d’implémentation obtenu à l’étape précédente.

   La mise en œuvre [!DNL Target] peut être mise à jour de plusieurs façons. Par exemple, utilisez les méthodes suivantes pour les pages web :

   * **Par le biais d’un &quot;paramètre personnalisé&quot; dans les balises au sein de [!DNL Adobe Experience Platform]:**

      Pour plus d’informations, voir [Ajout de paramètres de mbox](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=en#add-mbox-params) dans le *Présentation des balises* documentation.

   * **Via la fonction targetPageParamsAll() :** Placez le code suivant dans le `<head>` balises, au-dessus de la référence at.js.

      ```javascript
      <script>
       function targetPageParamsAll() {
        return {
         "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
        };
       }
      </script>
      ```

      Pour plus d’informations sur la façon de procéder avec at.js, voir [targetPageParamsAll](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/){target=_blank}.

## Étape 6 : Spécification des rôles et autorisations {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Dans Admin Console, cliquez sur **[!UICONTROL Produits]**, puis sélectionnez le nom du produit souhaité.

   ![Espace de travail](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur le nom du profil souhaité (par exemple, Espace de travail par défaut).

   ![Espace de travail par défaut](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Cliquez sur **[!UICONTROL Utilisateurs]**.

   Cet onglet [!UICONTROL Utilisateurs] de répertorie tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez le rôle d’autorisations souhaité (approbateur, éditeur, observateur ou éditeur) à l’aide de la liste déroulante pour chaque utilisateur du [!UICONTROL Rôle de produit] colonne .

   ![Liste déroulante Rôle du produit](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Rôle | Description |
   |--- |--- |
   | Approbateur | Peut créer, modifier et activer ou arrêter les activités. |
   | Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
   | Observateur | Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
   | Éditeur | Similaire au rôle d’observateur (peut afficher les activités, mais ne peut pas les créer ni les modifier). Cependant, le rôle d’éditeur dispose de l’autorisation supplémentaire d’activer les activités. |

   Pour plus d’informations, voir [Gestion de rôles et d’autorisations de produit dans le portail Admin Console](https://helpx.adobe.com/fr/enterprise/using/manage-permissions-and-roles.html) dans le *Guide d’utilisation d’Enterprise*.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

>[!NOTE]
>
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Configuration]) a été repensée afin d’améliorer les performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur. Les informations contenues dans les vidéos suivantes sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

### Configuration des espaces de travail Adobe Target (6:55) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer des espaces de travail.

* Accès à Adobe Admin Console depuis l’interface Adobe Target (3 manières)
* Configuration d’un espace de travail dans Adobe Admin Console

   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail

* Utilisation des espaces de travail par défaut

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Création de propriétés dans Adobe Target (3:05) ![Badge du tutoriel](/help/main/assets/tutorial.png)

* Comment créer une propriété dans l’interface [!DNL Adobe Target]
* Comment générer un jeton de propriété à inclure dans la mise en œuvre des propriétés
* Familiarisez-vous avec les trois méthodes de mise en œuvre :

   * Web
   * Applications mobiles
   * Courrier électronique, boîtier décodeur ou appels d’API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
