---
keywords: offre à distance ; matrice de sélection des offres à distance ; contenu en mémoire cache ; contenu dynamique ; type d’URL
description: Découvrez comment utiliser des offres distantes dans Adobe [!DNL Target] pour héberger du contenu externe (contenu dans un CMS ou un autre système). Découvrez pourquoi vous pouvez utiliser des offres distantes.
title: Comment créer des Offres distantes ?
feature: Expériences et Offres
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 47%

---

# Créer des offres distantes

Utilisez les offres distantes pour héberger hors de [!DNL Adobe Target] du contenu que référence [!DNL Target] et diffuse sur les sites web des utilisateurs. Ce contenu peut se trouver dans une gestion de contenu (CMS) ou un autre système, soit pour des raisons de facilité d&#39;utilisation, soit pour des raisons de sécurité.

>[!NOTE]
>
>Les offres distantes peuvent être créées sur la page [!UICONTROL Offres] > [!UICONTROL Offres de code] ou dans le [compositeur d’expérience basé sur les Forms](/help/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres distantes dans le compositeur d’expérience visuelle. Le contenu sera injecté dans les emplacements de requête [!DNL Target], de sorte qu’ils ne sont probablement pas appropriés pour une requête globale [!DNL Target].
>
>[!DNL Target Classic] fonctions similaires incluses : [!UICONTROL Offre sur votre site] et [!UICONTROL Offre hors Test&amp;Target].

Voici quelques exemples d’offres distantes :

* les différentes versions de ventes croisées ;
* les messages des paniers dynamiques ;
* les formulaires ;
* les calculateurs ;
* les mises à jour de taux d’intérêt.
* Emails
* Kiosques
* Assistants vocaux

## Meilleures pratiques pour l&#39;utilisation des offres distantes {#section_7718512D08E14121B6F6B8C38134F4BC}

Bonnes pratiques pour l’utilisation d’offres distantes dans vos activités :

* Si votre offre réside dans le même domaine que les demandes [!DNL Target], l’utilisation de l’option [!UICONTROL Mise en cache] permet d’utiliser des URL relatives pour décrire l’emplacement de votre offre.

   Cela signifie que lorsque vous déplacez l’activité des serveurs de test vers ceux de production, le contenu devient automatiquement accessible sans avoir à modifier l’URL manuellement.

* Si votre test implique des données générées dynamiquement par votre serveur, l’option [!UICONTROL Dynamique] peut être un bon choix.
* Si vous planifiez de tester uniquement l’apparence du contenu de votre offre distante existante, utilisez le [!UICONTROL compositeur d’expérience visuelle] pour modifier l’apparence du contenu renvoyé à partir du système de gestion du contenu.
* Utilisez la [matrice de sélection des Offres distantes](#reference_B23BEDD29DDD47709A7651AFD27E776B) (ci-dessous) pour vous aider à choisir l&#39;offre qui convient le mieux à votre cas spécifique. Si vous avez des questions, contactez le représentant du compte.

## Création d’une offre distante à partir de la page Offres du code

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.

   ![Offres > Offres de code](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre distante]**.

   ![Créer une Offre distante, boîte de dialogue](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Ressources].

1. Spécifiez le type d’URL de redirection.

   Voir [Type d’URL de redirection : Mise en cache ou dynamique](#url-type) ci-dessous pour plus d’informations.

1. Spécifiez l’URL distante de l’offre distante.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Création d’une offre distante à l’aide du compositeur d’expérience d’après les formulaires

1. Lors de la création d’une activité à l’aide du compositeur d’expérience d’après les formulaires ](/help/c-experiences/form-experience-composer.md), sélectionnez l’emplacement où afficher la section **[!UICONTROL Contenu]**.[

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur la liste déroulante **[!UICONTROL Contenu par défaut]**, puis sur **[!UICONTROL Modifier l’Offre distante]**.

   ![Modifier l’option Offre distante](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre distante]**.

   ![Créer une Offre distante, boîte de dialogue](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite aide les utilisateurs et vous-même à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Ressources].

1. Spécifiez le type d’URL de redirection.

   Voir [Type d’URL de redirection : Mise en cache ou dynamique](#url-type) ci-dessous pour plus d’informations.

1. Spécifiez l’URL distante de l’offre distante.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Type d’URL de redirection : Mise en cache ou dynamique {#url-type}

Les informations suivantes vous aident à comprendre les différences entre les deux options :

### URL mise en cache

Le contenu d’une offre distante en mémoire cache est diffusé à partir de [!DNL Target].

Toutes les deux heures, [!DNL Target] va chercher le contenu sur l’URL distante et le stocke ensuite dans [!DNL Target]. Lorsque des visiteurs chargent un site avec une expérience qui comprend une offre distante, l’offre est diffusée par [!DNL Target].

Les offres distantes mises en cache offrent une sécurité renforcée car une personne connectée à [!DNL Target] ne peut pas modifier le contenu. Pour modifier le contenu, l’utilisateur doit se connecter au gestionnaire de contenu ou à un autre système pour le modifier dans celui-ci.

Vous pouvez spécifier une URL absolue ou relative pour une offre distante en mémoire cache.

### URL dynamique

Une offre distante dynamique n’est pas diffusée à partir de [!DNL Target], mais du gestionnaire de contenu ou d’un autre système.

Vous pouvez ne pas souhaiter que le contenu soit régulièrement mis en cache et ensuite diffusé par [!DNL Target] lorsque des visiteurs chargent un site avec une expérience comportant une offre distante. Au lieu de cela, vous souhaitez appeler le système qui héberge le contenu, puis éventuellement transmettre des informations spécifiques afin que l’offre renvoyée puisse être dynamique (ou différente) pour chaque utilisateur. Par exemple, si un utilisateur se connecte à un site web pour une carte de crédit incluant une expérience avec une offre distante dynamique, vous pouvez transférer des paramètres dans l’URL pour les informations de compte de l’utilisateur. Le site web peut ensuite fournir des informations spécifiques à l’utilisateur, telles que son solde.

Vous pouvez cliquer sur **[!UICONTROL Paramètre d&#39;Ajoute]** pour ajouter une ou plusieurs requêtes [!DNL Target] ou paramètres de requête.

## Utiliser des offres distantes dans les activités

Vous devez appliquer des offres distantes à l’aide du compositeur d’expérience [!UICONTROL d’après les formulaires]. Actuellement, vous ne pouvez pas appliquer d’offres distantes à l’aide du compositeur d’expérience visuelle.

Le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience d’après les formulaires] est une interface de création d’offres et d’expériences non visuelles qui permet de créer des expériences à utiliser dans les [!UICONTROL tests A/B], [!UICONTROL ciblage d’expérience] (XT), [!UICONTROL Automated Personalization] (AP) et &lt;a9/ ] activités lorsque le compositeur d’expérience visuelle n’est pas disponible ou n’est pas pratique à utiliser. [!UICONTROL  Par exemple, vous pouvez utiliser le compositeur d’expérience d’après les formulaires ] pour créer des expériences qui utilisent des offres distantes.[!UICONTROL 

1. Créez ou modifiez une activité dans le [!UICONTROL compositeur d’expérience d’après les formulaires].

   Voir [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement de votre choix et ajoutez les affinements d’audience nécessaires.

1. Cliquez sur la liste déroulante de la section **[!UICONTROL Contenu]**, puis sur **[!UICONTROL Modifier l’Offre distante]**.

   ![Modifier l’option Offre distante](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Sélectionnez l&#39;offre distante de votre choix dans la boîte de dialogue [!UICONTROL Sélectionner l&#39;Offre distante], puis cliquez sur **[!UICONTROL Terminé]**.

1. Terminez la configuration de l’activité.

## Fonctionnement des offres distantes dynamiques {#concept_CC2A969420B34364A9FA78C1CE251818}

Une offre distante dynamique applique la technologie de page dynamique pour transmettre des valeurs à l’offre.

L’offre est exécutée une fois la page affichée. Un iframe invisible rassemble les données, les copie hors du cadre et les insère sur la page, en chargeant les valeurs transmises.

![](assets/remote_offer_howitworks_2.jpeg)

## Matrice de sélection des offres distantes {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matrice de sélection des offres distantes vous aide à déterminer le type d’offre distante à choisir : [!UICONTROL En mémoire cache] ou [!UICONTROL Dynamique].

| Fonctionnalité | En mémoire cache | Dynamique |
|--- |--- |--- |
| Mises à jour chaque fois qu’un visiteur émet une requête | Non | Oui |
| Mises à jour du contenu | Mise en cache toutes les 2 heures | Mise à jour immédiate à chaque requête |
| Durée de chargement | Plus rapide | Plus lent en raison du traitement des requêtes |
| JavaScript visible dans la page | Oui | Non, mais peut transmettre par URL |
| Les offres peuvent inclure du code JavaScript | Oui | Oui |
| URL de l’offre | Absolu    ou Relatif | Relatif |
| Ordinateur émettant la requête | Serveurs Adobe | Ordinateur du visiteur qui stocke les cookies de celui-ci |

## Vidéo de formation : Compositeur d’après les formulaires ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo fournit une démonstration du compositeur basé sur les formulaires, que vous pouvez utiliser pour créer des offres distantes.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
