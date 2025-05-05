---
keywords: ajouter un utilisateur;projet;groupe d’utilisateurs;propriétés;espace de travail;gérer la propriété;propriété;at_property;rôles;autorisations
description: Découvrez comment ajouter des utilisateurs à Adobe Target ; créer des espaces de travail, des groupes d’utilisateurs et des propriétés ; mettre à jour votre mise en oeuvre ; et spécifier des rôles et des autorisations.
title: Comment configurer les autorisations d’Enterprise ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 54%

---

# Configuration des autorisations d’Enterprise

Informations sur les tâches requises pour ajouter des utilisateurs à votre implémentation [!DNL Target] ; création d’espaces de travail, de groupes d’utilisateurs et de propriétés ; mise à jour de votre implémentation [!DNL Target] afin d’inclure le paramètre `at_property` ; et spécification des rôles et des autorisations.

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
| 5 : Mettez à jour votre mise en oeuvre pour inclure le paramètre `at_property` | [!DNL Target] Interface utilisateur, fonctions at.js ou balises dans [!DNL Adobe Experience Platform] |
| 6. Spécification des rôles et autorisations | [!DNL Adobe Admin Console for Enterprise] |

Pour les tâches effectuées dans [!DNL Adobe Admin Console for Enterprise], accédez à la console en procédant comme suit :

1. Dans Adobe Target, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**.

   Ou

   Accédez à [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > connectez-vous à l’aide de votre Adobe ID, si vous ne vous êtes pas encore connecté.


1. (Conditionnel) Si vous avez accès à [!DNL Admin Console for Enterprise] pour plusieurs organisations, cliquez sur l’avatar en haut à droite de l’écran ou dans la barre de navigation supérieure, puis sélectionnez l’organisation appropriée.

## Étape 1. Ajout d’utilisateurs (facultatif) {#section_A92AF0F921B743FEB9E9033433BD816A}

Lorsque vous commencez à utiliser la nouvelle fonctionnalité [!UICONTROL Properties], toute gestion des utilisateurs doit être effectuée dans le [!DNL Adobe Admin Console for Enterprise]. Néanmoins, tous les utilisateurs existants de [!DNL Target] sont déplacés de [!DNL Target] vers [!DNL Admin Console for Enterprise].

1. [Dans l’Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), cliquez sur l’onglet **[!UICONTROL Users]** en haut de la page > **[!UICONTROL Add Users]** pour créer de nouveaux utilisateurs ou modifier des utilisateurs existants.
1. Suivez les instructions des articles [Gestion des utilisateurs et des groupes dans Experience Cloud](https://helpx.adobe.com/fr/enterprise/using/users.html) dans le *Guide d’utilisation d’Enterprise*.

## Étape 2 : Création d’un espace de travail (profil de produit) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Un espace de travail (profil de produit) permet à une organisation d’affecter un ensemble spécifique d’utilisateurs à un ensemble spécifique de propriétés. Un espace de travail peut être comparé à une suite de rapports dans [!DNL Analytics].

Les entreprises peuvent commencer à tirer parti de la fonctionnalité des autorisations d’Enterprise en créant de nouveaux espaces de travail dans [!DNL Admin Console], en attribuant des propriétés [!DNL Target] à ces espaces de travail et en déplaçant les utilisateurs de la configuration &quot;Workspace par défaut&quot; vers ces espaces de travail plus récents à accès limité.

Les clients peuvent utiliser ces espaces de travail pour séparer l’accès à différentes équipes par région, unité opérationnelle, section de site ou par toute autre méthode de leur choix.

Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent même leur être attribués dans chaque espace de travail.

1. Dans le [!DNL Admin Console], cliquez sur **[!UICONTROL Products]**, puis sélectionnez le nom du produit souhaité.

   ![espace de travail](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Créez l’espace de travail souhaité (profil produit) :

   * **Accès par défaut** : toutes les activités sont fusionnées dans un seul projet ainsi nommé. Cela n’a aucune incidence sur les clients. Tous les rôles d’utilisateur et les fonctionnalités restent identiques à ce qu’ils étaient avant ce changement.

     Toutes les activités créées dans [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] et [!DNL Target Classic] font elles aussi partie de l’espace de travail « Accès par défaut ». Actuellement, vous ne pouvez pas déplacer les projets de l’accès par défaut vers un autre projet.

   * **Nouveaux espaces de travail (profils produit)** : procédez comme suit pour commencer à profiter de la nouvelle fonctionnalité d’autorisations :

      * Créez de nouveaux espaces de travail dans [!DNL Admin Console for Enterprise].
      * Affectez des propriétés Target aux espaces de travail.

   Utilisez ces espaces de travail pour répartir l’accès entre différentes équipes par région, unité opérationnelle, section du site ou par toute autre méthode de votre choix. Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent leur être attribués dans chaque espace de travail.

1. Suivez les instructions de la page [Gestion de produits et de configurations](https://helpx.adobe.com/fr/enterprise/help/manage-products-and-configurations.html) du *Guide d’utilisation Enterprise*.

>[!NOTE]
>Pour plus d’informations sur la configuration des espaces de travail, consultez la vidéo de formation ci-dessous.

### Obtention de l’identifiant de votre espace de travail {#workspace-id}

Vous devrez transmettre l’ID de l’espace de travail pour utiliser les autorisations d’entreprise dans les [API Target](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=fr){target=_blank}.

1. Dans [Adobe Admin Console](https://adminconsole.adobe.com), cliquez sur l’onglet [!UICONTROL Products], puis sur le produit dans le menu de gauche pour afficher la liste PLC (espace de travail).
1. Cliquez sur le PLC de votre choix (espace de travail), puis localisez l’identifiant « profils » dans l’URL, comme illustré ci-dessous.

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Étape 3. Création de groupes d’utilisateurs (facultatif) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

1. Dans l’Admin Console, cliquez sur l’onglet **[!UICONTROL Users]** en haut de la page > **[!UICONTROL User Groups]** pour créer de nouveaux groupes d’utilisateurs ou modifier des groupes existants.
1. Suivez les instructions de la page [Gestion de produits et de configurations](https://helpx.adobe.com/fr/enterprise/help/manage-products-and-configurations.html) du *Guide d’utilisation Enterprise*.

## Étape 4. Création de propriétés {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

Les propriétés sont activées en ajoutant une paire nom/valeur spécifique comme paramètre avec n’importe quel appel (appel Target, appel api, etc.) à Target.

Les propriétés appartiennent à des canaux spécifiques (web, mobile, courrier électronique et API/autre).

**Conseil** : pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Properties]** pour afficher la liste [!UICONTROL Properties].
1. Cliquez sur **Créer une propriété**.

   Renseignez les champs suivants :

   * **Nom de la propriété (obligatoire) :** Spécifiez un nom descriptif pour la propriété.
   * **Description** : décrivez la propriété (facultatif).
   * **Canal** : Sélectionnez le canal souhaité pour la propriété : web, application mobile, courrier électronique ou autre/API (un décodeur ou une console PlayStation, par exemple).

1. Cliquez sur **[!UICONTROL Copy]** pour copier le code dans le presse-papiers que vous utiliserez lors de l’exécution des étapes de [5 : mettez à jour votre mise en oeuvre afin d’inclure le paramètre at_property](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

>[!NOTE]
>Pour plus d’informations sur la création de propriétés, consultez la vidéo de formation ci-dessous.

## Étape 5 : mise à jour de votre mise en oeuvre afin d’inclure le paramètre at_property {#section_9B17A59807A94712BE642942442EBBC8}

Pour utiliser la fonctionnalité [!DNL Target] d’autorisations d’utilisateur, vous devez ajouter le paramètre `at_property` à tout appel qui parvient à [!DNL Target] (appel Target, appel api, etc.).

**Pour obtenir le code de paramètre `at_property`, procédez comme suit :**

1. (Conditionnel) Utilisez le code de mise en œuvre que vous avez généré et enregistré dans le Presse-papiers durant les étapes de la section [4. Création de propriétés](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD), puis passez à l’étape 2.

   OU

   Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Properties]** pour afficher la liste [!UICONTROL Properties].

   1. Pointez votre souris sur la colonne [!UICONTROL Last Updated] pour connaître la propriété à afficher, puis cliquez sur l’icône [!UICONTROL Code].

      ![Code de survol de propriété](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Cliquez avec le bouton droit de la souris sur le code de mise en œuvre surligné pour le copier dans le Presse-papiers.

1. Mettez à jour votre mise en oeuvre [!DNL Target] avec le code de mise en oeuvre obtenu à l’étape précédente.

   La mise en œuvre [!DNL Target] peut être mise à jour de plusieurs façons. Par exemple, utilisez les méthodes suivantes pour les pages web :

   * **Au moyen d’un &quot;paramètre personnalisé&quot; dans les balises [!DNL Adobe Experience Platform] :**

     Pour plus d’informations, voir [Ajout de paramètres de mbox](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=fr#add-mbox-params) dans la documentation *Présentation des balises*.

   * **Via la fonction targetPageParamsAll() :** Placez le code suivant dans les balises `<head>`, au-dessus de la référence at.js.

     ```javascript
     <script>
      function targetPageParamsAll() {
       return {
        "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
       };
      }
     </script>
     ```

     Pour plus d’informations sur la façon de procéder avec at.js, voir [targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=fr){target=_blank}.

## Étape 6 : spécification des rôles et des autorisations {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. Dans l’Admin Console, cliquez sur **[!UICONTROL Products]**, puis sélectionnez le nom du produit souhaité.

   ![Espace de travail](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Cliquez sur le nom du profil souhaité (par exemple, Workspace par défaut).

   ![Espace de travail par défaut](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Cliquez sur **[!UICONTROL Users]**.

   L’onglet [!UICONTROL Users] affiche tous les utilisateurs dans cet espace de travail.

   ![configuration des utilisateurs](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Sélectionnez le rôle d’autorisations souhaité (approbateur, éditeur, observateur ou éditeur) à l’aide de la liste déroulante pour chaque utilisateur de la colonne [!UICONTROL Product Role].

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
>L’interface utilisateur du menu [!DNL Target] [!UICONTROL Administration] (anciennement [!UICONTROL Setup]) a été repensée afin de fournir de meilleures performances, de réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et d’améliorer l’expérience utilisateur sur l’ensemble du produit. Les informations contenues dans les vidéos suivantes sont généralement correctes ; toutefois, les options peuvent se trouver à des emplacements légèrement différents. Des vidéos mises à jour seront bientôt publiées.

### Comment configurer les espaces de travail Adobe Target (6:55) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer des espaces de travail.

* Accès à Adobe Admin Console depuis l’interface Adobe Target (3 manières)
* Configuration d’un espace de travail dans Adobe Admin Console

   * Ajout d’utilisateurs à des espaces de travail
   * Ajout de propriétés à des espaces de travail

* Utilisation des espaces de travail par défaut

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### Comment créer des propriétés dans Adobe Target (3:05) ![Badge de tutoriel](/help/main/assets/tutorial.png)

* Comment créer une propriété dans l’interface [!DNL Adobe Target]
* Comment générer un jeton de propriété à inclure dans la mise en œuvre des propriétés
* Familiarisez-vous avec les trois méthodes de mise en œuvre :

   * Web
   * Applications mobiles
   * Envoyer un courrier électronique, définir une boîte de réception ou des appels API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
