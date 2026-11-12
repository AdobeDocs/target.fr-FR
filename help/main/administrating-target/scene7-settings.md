---
keywords: scene7;dynamic media classic;gestion des ressources numériques;ressources;dam;bibliothèque de contenu;permuter l’image
description: Connectez Adobe Target à Adobe Dynamic Media Classic (Scene7) afin que les auteurs puissent utiliser les offres d’images et permuter des images provenant de ressources Experience Cloud dans les activités .
landing-page-description: Configurez la configuration de Scene7 dans Administration pour activer les offres d’image, les workflows de gestion des ressources numériques de la bibliothèque de contenu et les actions de permutation d’image dans le VEC et le compositeur d’expérience d’après les formulaires.
short-description: Configurez la configuration de Scene7 dans Administration pour activer les offres d’image, les workflows de gestion des ressources numériques de la bibliothèque de contenu et les actions de permutation d’image dans le VEC et le compositeur d’expérience d’après les formulaires.
title: Comment dois-je procéder pour configurer l’intégration de Dynamic Media Classic (Scene7) ?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: 'https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%
---
# Configuration De Dynamic Media Classic (Scene7)

Utilisez l’onglet **[!UICONTROL Configuration de Scene7]** sous **[!UICONTROL Administration]** pour connecter [!DNL Adobe Target] à [!DNL Adobe Dynamic Media Classic] (anciennement [!DNL Scene7]). L’intégration apporte la gestion des ressources numériques (DAM) dans la [!UICONTROL bibliothèque de contenu] et permet des workflows de permutation d’image dans les activités .

Pour savoir comment cet onglet s’intègre aux autres tâches d’administration, consultez [Comment administrer Target ?](/help/main/administrating-target/administrating-target.md). Pour localiser **[!UICONTROL Administration]** dans l’interface, consultez [Comprendre l’ [!DNL Target] interface utilisateur](/help/main/c-intro/understand-the-target-ui.md).

**Aperçu**

1. [Ce que l’intégration permet](#what-it-enables) : offres d’images, permutation d’images et ressources éligibles.
1. [Compte et informations d’identification](#account-and-credentials) : comptes [!DNL Dynamic Media] existants et types de compte pris en charge.
1. [Instructions d&#39;utilisation](#usage-guidelines) : URL, diffusion et éléments non pris en charge.
1. [Configurer Scene7 dans Target](#configure-scene7) : paramètres de connexion et de région.

{{permissions-update}}

## Ce que l’intégration permet {#what-it-enables}

Lorsque la **[!UICONTROL Configuration de Scene7]** est configurée, les auteurs peuvent utiliser des images chargées dans le dossier de ressources [!DNL Adobe Experience Cloud] dans les activités [!DNL Target]. L’option **[!UICONTROL Permuter l’offre d’image]** apparaît dans le workflow d’activité, y compris dans le [compositeur d’expérience visuelle et le compositeur d’expérience d’après les formulaires](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Pour connaître le comportement de permutation dans le VEC, consultez les [options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

Si ce paramètre n’est pas configuré, l’**[!UICONTROL offre de permutation d’image]** n’est pas disponible lors de la création de l’activité.

L’intégration fournit des ressources qui font partie des activités à partir du dossier de ressources Experience Cloud. Il n’expose **pas** chaque ressource dans [!DNL Dynamic Media Classic] pour une utilisation dans [!DNL Target] activités.

Après la configuration, gérez les offres d’images dans la bibliothèque [!UICONTROL Offres]. Voir [Gérer le contenu](/help/main/c-experiences/c-manage-content/manage-content.md).

## Compte et informations d’identification {#account-and-credentials}

Si vous disposez déjà d’un compte [!DNL Dynamic Media], saisissez ces informations d’identification sur la page **[!UICONTROL Configuration de Scene7]**.

Adobe ne met plus en service de comptes [!DNL Dynamic Media Classic] à utilisation restreinte et gratuits pour les nouveaux [!DNL Target] clients ou utilisateurs. Si votre organisation dispose déjà d’informations d’identification de connexion pour cette intégration, elles continuent à fonctionner. Pour toute question sur le compte, contactez votre représentant [!DNL Adobe].

## Instructions d’utilisation {#usage-guidelines}

Gardez à l’esprit les contraintes suivantes lorsque vous utilisez des images avec cette intégration :

* **Offres d’image, et non URL de stockage.** Les URL de stockage [!DNL Dynamic Media] et les URL de diffusion publiées sont différentes. Ne créez pas d’offres à partir de liens de stockage ; la diffusion échoue. Utilisez plutôt des [offres d’image](/help/main/c-experiences/c-manage-content/manage-content.md) et des workflows de permutation d’image.
* **URL publiques dans le code personnalisé.** Pour référencer une URL d’image publique directement dans une offre ou un code personnalisé, hébergez l’image sur vos propres serveurs web et utilisez cette URL. Vous ne pouvez pas obtenir d&#39;URL publiée pour une image Experience Cloud chargée afin de l&#39;utiliser en dehors des workflows de ciblage [!DNL Target]. Cette utilisation n&#39;est pas autorisée par contrat.
* **Actifs éligibles.** Seules les ressources chargées dans le dossier de ressources Experience Cloud (et les workflows pris en charge par cette intégration) sont incluses dans la portée, et non le catalogue [!DNL Dynamic Media Classic] complet.

## Configuration de Scene7 dans Target {#configure-scene7}

Procédez comme suit pour connecter [!DNL Dynamic Media Classic] ([!DNL Scene7]) :

1. Cliquez Sur **[!UICONTROL Administration]** > **[!UICONTROL Configuration De Scene7]**.
1. Entrez les informations de votre compte [!DNL Dynamic Media Classic] :

   | Champ | Description |
   | --- | --- |
   | **Région** | Région de votre compte [!DNL Dynamic Media] : Amérique du Nord, Europe ou Asie. |
   | **Dossier ad hoc** | Emplacement du contenu en dehors du dossier cible que vous téléchargez manuellement vers [!DNL Dynamic Media]. |
   | **Adresse e-mail** | Adresse e-mail utilisée pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]). |
   | **Mot De Passe** | Mot de passe utilisé pour se connecter à [!DNL Dynamic Media Classic] ([!DNL Scene7]). |

   ![Champs de configuration Scene7](/help/main/administrating-target/assets/scene7-1.png)

1. Cliquez sur **[!UICONTROL Envoyer]**.
