---
keywords: compositeur d’expérience d’après les formulaires, compositeur basé sur les formulaires, ajustements
description: Découvrez comment utiliser le compositeur  [!DNL Target] ’expérience d’après les Adobes pour la création d’expériences non visuelles. Utilisez ce compositeur lorsque le compositeur d’expérience visuelle n’est pas disponible ou n’est pas pratique à utiliser.
title: Comment utiliser le compositeur d’expérience d’après les formulaires ?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 33%

---

# Compositeur d’expérience d’après les formulaires

Le [!UICONTROL Form-Based Experience Composer] [!DNL Adobe Target] est une interface de création d’offres et d’expériences non visuelles qui est utile pour créer des expériences à utiliser dans des activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] et [!UICONTROL Recommendations] lorsque le [!UICONTROL Visual Experience Composer] (VEC) n’est pas disponible ou pratique à utiliser. Par exemple, vous pouvez utiliser le compositeur d’expérience d’après les formulaires pour créer des expériences et des offres à diffuser dans des e-mails, des kiosques et des assistants vocaux.

Si vous créez une activité [!UICONTROL Recommendations], il n’y a aucune expérience. Choisissez votre critère et votre conception. Si vous choisissez plusieurs critères ou conceptions, [!UICONTROL Target] génère automatiquement les expériences.

1. Cliquez sur **[!UICONTROL Create Activity]**, puis sélectionnez le type d’activité à créer.

   Le [!UICONTROL Form-Based Experience Composer] est disponible pour les activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] et [!UICONTROL Recommendations].

1. Sélectionnez **[!UICONTROL Form]** dans la boîte de dialogue [!UICONTROL Create Activity].

1. (Conditionnel) Si vous êtes un client [Target Premium](/help/main/c-intro/intro.md#premium) dans la liste déroulante **[!UICONTROL Choose Workspace]**, choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   L’option [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) est une fonctionnalité [Target Premium](/help/main/c-intro/intro.md) qui peut ne pas s’afficher si votre entreprise dispose d’une licence [!UICONTROL Target Standard].

1. Choisissez une propriété.

1. Cliquez sur **[!UICONTROL Create]**.

   La [!UICONTROL Form-Based Experience Composer] s’ouvre.

   Cet écran est différent si vous créez une activité [!UICONTROL Recommendations]. Les activités [!UICONTROL Recommendations] n’incluent pas d’expériences.

1. &#x200B;
   1. Cliquez sur l’icône **[!UICONTROL Rename]** ( ![Icône Renommer](/help/main/assets/icons/MoreSmallListVert.svg) ), cliquez sur **[!UICONTROL Rename]**, attribuez un nom à l’activité, puis cliquez sur **[!UICONTROL Save]**.

   Le nom de l’activité ne peut pas commencer par l’un des caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence De Caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule plus |
   | ;- | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, est égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, Au signe |
   | `[` » | Crochet ouvert, guillemets doubles |
   |  »`]` | Guillemets doubles, crochet fermant |

1. Sélectionnez un emplacement.

   Lorsque vous cliquez dans la zone de [!UICONTROL Select Location], une liste des emplacements disponibles s&#39;affiche. Sélectionnez l’un de ces emplacements.

   Vous pouvez également saisir un emplacement qui n’est pas répertorié ici. Ceci peut s’avérer utile lorsque la mbox n’a pas encore été créée ou consultée sur une page. Saisissez le nom de l’emplacement. Soyez prudent lorsque vous saisissez un emplacement qui n’existe pas encore. Si l’orthographe ou la capitalisation ne correspond pas à l’orthographe et à la capitalisation lorsque l’appel mbox est passé, l’activité ne sera pas diffusée. Les emplacements saisis manuellement sont enregistrés dans la liste des emplacements disponibles. La prochaine fois que vous tenterez de sélectionner un emplacement saisi manuellement, il sera disponible dans la liste déroulante [!UICONTROL Select Location] pour cette activité.

   >[!NOTE]
   >
   >La création d’un emplacement saisi manuellement lors de la création de l’activité ne crée pas automatiquement de nouvel emplacement. Le nom de l’emplacement n’est enregistré que dans le contexte de l’activité. L’emplacement est créé en cas d’appel de diffusion de contenu. Une fois l’emplacement créé, il pourra être utilisé dans d’autres activités, pour créer des audiences, etc. dans la liste déroulante des emplacements disponibles.

1. Cliquez sur **[!UICONTROL Add Audience Refinements]**, choisissez une ou plusieurs [audiences](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) pour cette activité, puis cliquez sur **[!UICONTROL Done]**.

   Dans la [!UICONTROL Form-based Experience Composer], les améliorations ont été remplacées par des fonctionnalités d’audience complètes. Les perfectionnements apportés aux activités existantes ont été migrés vers des [audiences d’activité uniquement](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Sélectionnez le type de contenu que vous souhaitez voir à cet emplacement.

1. Pour le type de contenu que vous avez sélectionné, indiquez le contenu.

   **Modifier l’offre HTML :** choisissez une offre HTML.

   **Modifier une offre d’images :** sélectionnez une image enregistrée dans la bibliothèque de contenu de Target.

   Vous pouvez également ajouter un lien à une image (clic publicitaire, destination, entrée, etc.)

   1. Cliquez sur [!UICONTROL Change Image Offer].
   1. Sélectionnez l’image souhaitée, puis cliquez sur [!UICONTROL Edit Links].
   1. Indiquez l’URL ou la page de votre site souhaitée, puis cliquez sur [!UICONTROL Update].

   **Modifier l’offre JSON :** choisissez une offre json.

   **Modifier le fragment d’expérience :** sélectionnez un fragment d’expérience. Pour plus d’informations, voir [ Fragment d’expérience ](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Modifier l’offre de redirection :** sélectionnez une offre de redirection. Pour plus d’informations, voir [Création d’offres de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Modifier l’offre distante :** sélectionnez une offre distante. Pour plus d’informations, voir [Création d’offres distantes](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Créer une offre HTML :**

   1. Cliquez sur [!UICONTROL Offers], puis sélectionnez l’onglet [!UICONTROL Code Offers] .
   1. Cliquez sur [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code HTML dans la zone Code.
   1. Cliquez sur [!UICONTROL Save].

   **Création d’offres JSON :**

   1. Cliquez sur [!UICONTROL Offers], puis sélectionnez l’onglet [!UICONTROL Code Offers] .
   1. Cliquez sur [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Saisissez le nom de l’offre.
   1. Saisissez ou copiez votre code JSON dans la zone Code.
   1. Cliquez sur [!UICONTROL Save].

   **Ajouter une recommandation :**

   Pour une activité Recommendations , la liste déroulante Contenu propose l&#39;option [!UICONTROL Add Recommendation] . Cliquez sur **[!UICONTROL Add Recommendation]**, puis sélectionnez le type de page. Suivez ensuite les étapes habituelles telles que définies dans l’interface pour [créer une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Lors de la sélection de critères de recommandation dans le compositeur d’expérience d’après les formulaires, il existe désormais un lien direct vers la carte de critère sélectionnée, ce qui vous permet de modifier rapidement et facilement les critères.

   Sur la page [!UICONTROL Targeting] du workflow guidé en trois étapes [!DNL Target] :

   **Ajouter une décision d’offre :**

   Ajoutez une offre créée dans [!DNL Adobe Journey Optimizer] (AJO) à une activité [!DNL Adobe Target] pour présenter la meilleure offre et la meilleure expérience dynamique aux visiteurs de votre site web ou mobile à l’aide de l’offer decisioning. Cette option est disponible uniquement pour les activités de [!UICONTROL A/B Test] et de [!UICONTROL Experience Targeting] manuels (XT).

   Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Facultatif, pour les activités [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] et [!UICONTROL Experience Targeting]) Pour répéter ce processus pour d’autres emplacements, cliquez sur **[!UICONTROL Add Location]** et configurez l’emplacement et le contenu.
1. Cliquez sur **[!UICONTROL Next]**, puis effectuez les étapes de création de l’activité comme d’habitude pour votre type d’activité.

* [Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Création d’une activité de recommandations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vidéo de formation : compositeur basé sur les formulaires ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit une démonstration du compositeur d’après les formulaires.

* Création d’une activité à l’aide du compositeur d’expérience d’après les formulaires
* Comprendre à quel moment utiliser le compositeur d’expérience d’après les formulaires et le compositeur d’expérience visuelle
* Utilisation des ajustements pour cibler un emplacement

>[!VIDEO](https://video.tv.adobe.com/v/17390)
