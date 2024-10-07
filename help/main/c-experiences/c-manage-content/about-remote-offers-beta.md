---
keywords: offre distante;contenu en cache;contenu dynamique;type d’url
description: Découvrez comment tirer parti des offres distantes dans  [!DNL Target]  pour héberger du contenu externe à partir d’un CMS ou d’autres systèmes.
title: Comment créer des offres distantes ?
feature: Experiences and Offers
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: e83ad57e-716d-4595-b5cf-3a882fcb9e37
source-git-commit: c7d6998ffb048b1a7895e4c48b557cdb16ff510c
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 19%

---

# Créer des offres distantes

Utilisez des offres distantes pour héberger du contenu en dehors de [!DNL Adobe Target], ce qui permet à [!DNL Target] de référencer et de diffuser ce contenu sur les sites Web des utilisateurs. Ce contenu peut résider dans un système de gestion de contenu (CMS) ou un autre système pour des raisons de facilité d’utilisation ou de sécurité.

>[!NOTE]
>
>Cet article contient des informations sur les mises à jour apportées à l’interface utilisateur de [!DNL Target] qui fait actuellement partie d’un programme Beta. L’équipe [!DNL Adobe Target] active souvent de nouvelles fonctionnalités pour certains clients à des fins de test et de commentaire. Une fois la période de test terminée, ces fonctionnalités sont activées pour tous les clients dans les prochaines versions de [!DNL Target Standard/Premium] et annoncées dans les notes de mise à jour.

Les offres distantes peuvent être créées sur la page [!UICONTROL Offers] > [!UICONTROL Code Offers] ou dans le [compositeur d’expérience d’après Forms](/help/main/c-experiences/form-experience-composer.md). Vous ne pouvez pas créer ni appliquer d’offres distantes dans le [!UICONTROL Visual Experience Composer] (VEC). Le contenu est injecté dans les emplacements de requête [!DNL Target]. Ces emplacements ne sont donc probablement pas appropriés pour une requête [!DNL Target] globale.

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

* Si votre offre réside dans le même domaine que les demandes [!DNL Target], l’option [!UICONTROL Cached] vous permet d’utiliser des URL relatives pour décrire l’emplacement de votre offre.

  Cela signifie que lorsque vous déplacez votre activité des serveurs d’évaluation vers la production, le contenu est automatiquement accessible sans avoir à modifier manuellement l’URL.

* Si votre test implique des données générées dynamiquement par votre serveur, l’option [!UICONTROL Dynamic] peut être le bon choix.
* Si vous prévoyez de tester uniquement l’aspect du contenu de votre offre distante existante, utilisez le [!UICONTROL Visual Experience Composer] pour modifier l’aspect du contenu renvoyé par le système de gestion de contenu.
* Utilisez la [matrice de sélection des offres distantes](#reference_B23BEDD29DDD47709A7651AFD27E776B) (ci-dessous) pour choisir l’offre qui vous convient le mieux à votre cas spécifique. Si vous avez des questions, contactez le représentant du compte.

## Créer une offre distante à partir de la page [!UICONTROL Code Offers]

1. Cliquez sur **[!UICONTROL Offers]**, puis sélectionnez l’onglet **[!UICONTROL Code Offers]**.

1. Cliquez sur **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Dans la boîte de dialogue [!UICONTROL Create Remote Offer], attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Offers].

1. (Conditionnel) Si vous disposez d’un [compte Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez l’ [espace de travail](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) de votre choix.

1. Spécifiez le type d’URL de redirection.

   Pour plus d’informations, voir [Type d’URL de redirection : [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic]](#url-type) ci-dessous.

1. Spécifiez l’URL distante absolue pour l’offre distante.

1. Cliquez sur **[!UICONTROL Create]**.

## Créez une offre distante à l’aide de [!UICONTROL Form-Based Experience Composer]

1. Lors de la création d’une activité à l’aide du [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md), sélectionnez l’emplacement d’affichage de la section **[!UICONTROL Content]**.

1. Cliquez sur la liste déroulante **[!UICONTROL Default Content]**, puis sur **[!UICONTROL Change Remote Offer]**.

1. Cliquez sur **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

1. Attribuez un nom explicite à l’offre.

   Un nom explicite vous aide, ainsi que d’autres personnes, à trouver rapidement l’offre dans la bibliothèque [!UICONTROL Assets].

1. Spécifiez le type d’URL de redirection.

   Pour plus d’informations, voir [Type d’URL de redirection : [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic]](#url-type) ci-dessous.

1. Spécifiez l’URL distante de l’offre distante.

1. Cliquez sur **[!UICONTROL Save]**.

## Type d’URL de redirection : [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic] {#url-type}

Les informations suivantes vous aident à comprendre les différences entre les deux options :

### [!UICONTROL Onsite Cached] URL

Le contenu d’une offre distante en mémoire cache est diffusé à partir de [!DNL Target].

Toutes les deux heures, [!DNL Target] récupère le contenu à l’URL distante, puis le stocke dans [!DNL Target]. Lorsque des visiteurs chargent un site avec une expérience qui inclut une offre distante, [!DNL Target] diffuse l’offre.

Les offres distantes en mémoire cache offrent une sécurité améliorée, car une personne connectée à [!DNL Target] ne peut pas modifier le contenu. Pour modifier le contenu, quelqu’un doit se connecter à la gestion de contenu ou à un autre système, et modifier le contenu à cet endroit.

Vous pouvez spécifier une URL absolue ou relative pour une offre distante en mémoire cache.

### [!UICONTROL Onsite Dynamic] URL

Une offre distante dynamique est diffusée à partir de la gestion de contenu ou d’un autre système plutôt qu’à partir de [!DNL Target].

Vous pouvez ne pas souhaiter que le contenu soit régulièrement mis en cache puis diffusé par [!DNL Target] chaque fois que des visiteurs chargent un site avec une expérience qui inclut une offre distante. Vous souhaitez plutôt appeler le système qui héberge le contenu, éventuellement transmettre des informations spécifiques afin que l’offre renvoyée puisse être dynamique (ou différente) pour chaque utilisateur. Par exemple, si un utilisateur se connecte à un site web pour une carte de crédit incluant une expérience avec une offre distante dynamique, vous pouvez transférer des paramètres dans l’URL pour les informations de compte de l’utilisateur. Le site web peut ensuite fournir des informations spécifiques à l’utilisateur, telles que son solde.

Vous pouvez cliquer sur **[!UICONTROL Add Parameter]** pour ajouter une ou plusieurs requêtes ou paramètres de requête [!DNL Target].

## Utiliser des offres distantes dans les activités

Vous devez appliquer des offres distantes à l’aide de [!UICONTROL Form-Based Experience Composer]. Actuellement, vous ne pouvez pas appliquer d’offres distantes à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] est une interface de création d’expérience et d’offres non visuelles qui est utile pour créer des expériences à utiliser dans les activités [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Recommendations] lorsque [!UICONTROL Visual Experience Composer] n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le [!UICONTROL Form-Based Experience Composer] pour créer des expériences qui utilisent des offres distantes.

1. Créez ou modifiez une activité dans le [!UICONTROL Form-Based Experience Composer].

   Voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour obtenir des instructions détaillées étape par étape.

1. Indiquez l’emplacement souhaité et ajoutez toute amélioration de l’audience nécessaire.

1. Cliquez sur la liste déroulante de la section **[!UICONTROL Content]**, puis cliquez sur **[!UICONTROL Change Remote Offer]**.

1. Sélectionnez l’offre distante souhaitée dans la boîte de dialogue [!UICONTROL Select Remote Offer], puis cliquez sur **[!UICONTROL Done]**.

1. Terminez la configuration de l’activité.

## Fonctionnement des offres distantes dynamiques {#concept_CC2A969420B34364A9FA78C1CE251818}

Une offre distante dynamique applique la technologie de page dynamique pour transmettre des valeurs à l’offre.

L’offre est exécutée une fois la page affichée. Un iFrame invisible rassemble les données, les copie hors du cadre et les insère sur la page, chargeant ainsi les valeurs transmises.

![remote_offer_howitwork_2 image](assets/remote_offer_howitworks_2.jpeg)

1. Le navigateur du visiteur demande une page à votre serveur.

2. Le navigateur effectue le rendu de la page, y compris les mbox.

3. L’appel `mboxCreate` comprend les paramètres nécessaires au rendu du contenu dynamique.

4. [!DNL Target] renvoie l’URL avec l’emplacement du contenu dynamique et ses paramètres. Définit un iFrame dans la zone mbox.

5. Le navigateur demande l’URL et effectue le rendu dans la page.

## Matrice de sélection des offres distantes {#reference_B23BEDD29DDD47709A7651AFD27E776B}

La matrice de sélection des offres distantes permet de déterminer le type d’offre distante à choisir : [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic].

| Fonctionnalité | Mise en cache sur site | Onsite Dynamic |
|--- |--- |--- |
| Mises à jour chaque fois qu’un visiteur émet une requête | Non | Oui |
| Mises à jour du contenu | Mise en cache toutes les deux heures | Mise à jour immédiate à chaque requête |
| Durée de chargement | Plus rapide | Plus lent en raison du traitement des requêtes |
| JavaScript visible dans la page | Oui | Non, mais peut transmettre par URL |
| Les offres peuvent inclure du code JavaScript | Oui | Oui |
| URL de l’offre | Absolu ou Relatif | Relatif |
| Ordinateur émettant la requête | Serveurs Adobe | Ordinateur du visiteur qui stocke les cookies de celui-ci |

## Vidéo de formation : Compositeur d’après les formulaires ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit une démonstration de [!UICONTROL Form-Based Experience Composer], que vous pouvez utiliser pour créer des offres distantes.

* Créez une activité à l’aide de [!UICONTROL Form-Based Experience Composer]
* Comprendre quand utiliser [!UICONTROL Form-Based Experience Composer] et [!UICONTROL Visual Experience Composer]
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
