---
keywords: offre distante;contenu en cache;contenu dynamique;type d’url
description: Découvrez comment utiliser les offres distantes dans [!DNL Target] pour héberger du contenu externe (contenu dans un CMS ou un autre système).
title: Comment créer des offres distantes ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
source-git-commit: 26cb9d6a2359714f41acaf91c6e26a7e0ac93238
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 21%

---

# Créer des offres distantes

Utilisez les offres distantes pour héberger hors de [!DNL Adobe Target] du contenu que référence [!DNL Target] et diffuse sur les sites web des utilisateurs. Ce contenu peut se trouver dans un système de gestion de contenu (CMS) ou un autre système, que ce soit par facilité ou pour des raisons de sécurité.

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à la variable [!DNL Target] interface utilisateur qui fait actuellement partie d’un programme bêta. La variable [!DNL Adobe Target] L’équipe active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités seront activées pour tous les clients à l’avenir. [!DNL Target Standard/Premium] versions et annoncées dans les notes de mise à jour.

Les offres distantes peuvent être créées sur la page [!UICONTROL Offers] > [!UICONTROL Code Offers] ou dans le [Compositeur d’expérience d’après Forms](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres distantes dans la variable [!UICONTROL Visual Experience Composer] (VEC). Le contenu est injecté dans la variable [!DNL Target] emplacements de requête, de sorte que ces emplacements ne sont probablement pas appropriés pour une [!DNL Target] requête.

Voici quelques exemples d’offres distantes :

* les différentes versions de ventes croisées ;
* les messages des paniers dynamiques ;
* les formulaires ;
* les calculateurs ;
* les mises à jour de taux d’intérêt.
* Emails
* Kiosques
* assistants vocaux

## Bonnes pratiques relatives à l’utilisation d’offres distantes {#section_7718512D08E14121B6F6B8C38134F4BC}

Bonnes pratiques pour l’utilisation d’offres distantes dans vos activités :

* Si votre offre réside dans le même domaine que la variable [!DNL Target] requêtes, à l’aide de [!UICONTROL Cached] vous permet d’utiliser des URL relatives pour décrire l’emplacement de votre offre.

  Cela signifie que lorsque vous déplacez votre activité des serveurs d’évaluation vers la production, le contenu est automatiquement accessible sans avoir à modifier manuellement l’URL.

* Si votre test implique des données générées dynamiquement par votre serveur, la variable [!UICONTROL Dynamic] peut être le bon choix.
* Si vous prévoyez de tester uniquement l’aspect du contenu de votre offre distante existante, utilisez la méthode [!UICONTROL Visual Experience Composer] pour modifier l’aspect du contenu renvoyé par le système de gestion de contenu.
* Utilisez la variable [Matrice de sélection des offres distantes](#reference_B23BEDD29DDD47709A7651AFD27E776B) (ci-dessous) pour vous aider à choisir l’offre la mieux adaptée à votre cas spécifique. Si vous avez des questions, contactez le représentant du compte.

## Créez une offre distante à partir du [!UICONTROL Code Offers] page

1. Cliquez sur **[!UICONTROL Offers]**, puis sélectionnez la variable **[!UICONTROL Code Offers]** .

   ![Offres > Offres (code)](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Cliquez sur **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

   ![Boîte de dialogue Créer une offre distante](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la variable [!UICONTROL Assets] bibliothèque .

1. (Conditionnel) Si vous avez un événement [Compte Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez une [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Spécifiez le type d’URL de redirection.

   Voir [Type d’URL de redirection : mise en cache ou dynamique](#url-type) ci-dessous pour plus d’informations.

1. Spécifiez l’URL distante absolue pour l’offre distante.

1. Cliquez sur **[!UICONTROL Create]**.

## Créez une offre distante à l’aide de la fonction [!UICONTROL Form-Based Experience Composer]

1. Lors de la création d’une activité à l’aide de la variable [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage du **[!UICONTROL Content]** .

   ![Section Contenu du compositeur d’expérience d’après les formulaires](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Cliquez sur le bouton **[!UICONTROL Default Content]** liste déroulante, puis cliquez sur **[!UICONTROL Change Remote Offer]**.

   ![Modifier l’option Offre distante](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Boîte de dialogue Créer une offre distante](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la variable [!UICONTROL Assets] bibliothèque .

1. Spécifiez le type d’URL de redirection.

   Voir [Type d’URL de redirection : mise en cache ou dynamique](#url-type) ci-dessous pour plus d’informations.

1. Spécifiez l’URL distante de l’offre distante.

1. Cliquez sur **[!UICONTROL Save]**.

## Type d’URL de redirection : mise en cache ou dynamique {#url-type}

Les informations suivantes vous aident à comprendre les différences entre les deux options :

### URL mise en cache

Le contenu d’une offre distante en mémoire cache est diffusé à partir de [!DNL Target].

Toutes les deux heures, [!DNL Target] récupère le contenu à l’URL distante, puis le stocke dans [!DNL Target]. Lorsque les visiteurs chargent un site avec une expérience qui inclut une offre distante, [!DNL Target] offre.

Les offres distantes mises en cache offrent une sécurité renforcée car un utilisateur s’est connecté à [!DNL Target] ne peut pas modifier le contenu. Pour modifier le contenu, une personne doit enregistrer , ou un autre système, et modifier le contenu à cet endroit.

Vous pouvez spécifier une URL absolue ou relative pour une offre distante en mémoire cache.

### URL dynamique

Une offre distante dynamique est diffusée à partir de la gestion de contenu ou d’un autre système plutôt que depuis [!DNL Target].

Vous pouvez ne pas souhaiter que le contenu soit régulièrement mis en cache puis diffusé par [!DNL Target] chaque fois que des visiteurs chargent un site avec une expérience qui inclut une offre distante. Vous souhaitez plutôt appeler le système qui héberge le contenu, éventuellement transmettre des informations spécifiques afin que l’offre renvoyée puisse être dynamique (ou différente) pour chaque utilisateur. Par exemple, si un utilisateur se connecte à un site web pour une carte de crédit incluant une expérience avec une offre distante dynamique, vous pouvez transférer des paramètres dans l’URL pour les informations de compte de l’utilisateur. Le site web peut ensuite fournir des informations spécifiques à l’utilisateur, telles que son solde.

Cliquez sur **[!UICONTROL Add Parameter]** pour ajouter une ou plusieurs [!DNL Target] requêtes ou paramètres de requête.

## Utiliser des offres distantes dans les activités

Vous devez appliquer des offres distantes à l’aide de la variable [!UICONTROL Form-Based Experience Composer]. Vous ne pouvez actuellement pas appliquer d’offres distantes à l’aide de la variable [!UICONTROL Visual Experience Composer] (VEC).

La variable [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] est une interface de création d’offres et d’expériences non visuelles utile pour créer des expériences à utiliser dans [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] lorsque la variable [!UICONTROL Visual Experience Composer] n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser la variable [!UICONTROL Form-Based Experience Composer] pour créer des expériences qui utilisent des offres distantes.

1. Créez ou modifiez une activité dans le [!UICONTROL Form-Based Experience Composer].

   Voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement souhaité et ajoutez toute amélioration de l’audience nécessaire.

1. Cliquez sur la liste déroulante du **[!UICONTROL Content]** , puis cliquez sur **[!UICONTROL Change Remote Offer]**.

   ![Modifier l’option Offre distante](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Sélectionnez l’offre distante souhaitée dans la [!UICONTROL Select Remote Offer] , puis cliquez sur **[!UICONTROL Done]**.

1. Terminez la configuration de l’activité.

## Fonctionnement des offres distantes dynamiques {#concept_CC2A969420B34364A9FA78C1CE251818}

Une offre distante dynamique applique la technologie de page dynamique pour transmettre des valeurs à l’offre.

L’offre est exécutée une fois la page affichée. Un iFrame invisible rassemble les données, les copie hors du cadre et les insère sur la page, chargeant ainsi les valeurs transmises.

![image remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

1. Le navigateur du visiteur demande une page à votre serveur.

2. Le navigateur effectue le rendu de la page, y compris les mbox.

3. `mboxCreate` L’appel comprend les paramètres nécessaires au rendu du contenu dynamique.

4. [!DNL Target] renvoie l’URL avec l’emplacement du contenu dynamique et ses paramètres. Définit un iFrame dans la zone mbox.

5. Le navigateur demande l’URL et effectue le rendu dans la page.

## Matrice de sélection des offres distantes {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matrice de sélection des offres distantes vous permet de déterminer le type d’offre distante à choisir : [!UICONTROL Cached] ou [!UICONTROL Dynamic].

| Fonctionnalité | En mémoire cache | Dynamique |
|--- |--- |--- |
| Mises à jour chaque fois qu’un visiteur émet une requête | Non | Oui |
| Mises à jour du contenu | Mise en cache toutes les deux heures | Mise à jour immédiate à chaque requête |
| Durée de chargement | Plus rapide | Plus lent en raison du traitement des requêtes |
| JavaScript visible dans la page | Oui | Non, mais peut transmettre par URL |
| Les offres peuvent inclure du code JavaScript | Oui | Oui |
| URL de l’offre | Absolu ou Relatif | Relatif |
| Ordinateur émettant la requête | Serveurs Adobe | Ordinateur du visiteur qui stocke les cookies de celui-ci |

## Vidéo de formation : compositeur d’après les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo présente une démonstration de la fonction [!UICONTROL Form-Based Experience Composer], que vous pouvez utiliser pour créer des offres distantes.

* Créez une activité à l’aide du [!UICONTROL Form-Based Experience Composer]
* Comprendre quand utiliser [!UICONTROL Form-Based Experience Composer] par rapport à la valeur [!UICONTROL Visual Experience Composer]
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)