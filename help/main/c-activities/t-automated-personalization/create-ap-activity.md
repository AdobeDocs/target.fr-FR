---
keywords: automated personalization;ap
description: Découvrez comment créer une activité [!UICONTROL Automated Personalization] (AP) à l’aide du [!UICONTROL compositeur d’expérience visuelle].
title: Comment créer une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
TQID: 'https://experienceleague.adobe.com/5eUFwob4BekIJP4SM2lrSDQam4h1AXIByJjM7-1RNL8'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c86619f0c004279bf4d9b871c84bf2e37ba932b7
workflow-type: tm+mt
source-wordcount: '1963'
ht-degree: 18%
---
# Création d’une activité [!UICONTROL Automated Personalization] {#create-ap-activity}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer une activité **[!UICONTROL Automated Personalization]** (AP) dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC). Vous créez vos expériences, définissez le ciblage et une population témoin, puis configurez les objectifs et les paramètres.

>[!ENDSHADEBOX]

Le workflow de l’activité **[!UICONTROL Automated Personalization]** dans [!DNL Target] diffère du workflow des autres types d’activités. Elle suit le workflow guidé en trois étapes du **[!UICONTROL compositeur d’expérience visuelle]** :

1. [Création d’expériences](#build-experiences)
1. [Définir le ciblage](#set-targeting)
1. [Configurer les objectifs et les paramètres](#configure-goals-and-settings)

## Avant de commencer {#before-you-begin}

Pour des performances optimales, maintenez vos activités de **[!UICONTROL ciblage automatique]** et de **[!UICONTROL Automated Personalization]** dans les limites suivantes :

* 4 à 6 emplacements, avec 4 à 6 offres par emplacement.
* Moins de 5 000 expériences au total pour de meilleurs résultats. La limite stricte est de 30 000 et la même limite s&#39;applique lorsque l&#39;option **[!UICONTROL Interdire les doublons]** est activée.

Le nombre total d’expériences augmente à partir de la combinaison cartésienne d’emplacements et d’offres. Des configurations plus volumineuses peuvent ralentir le chargement ou la modification du **[!UICONTROL compositeur d’expérience visuelle]**.

## Étape 1 : création d’expériences {#build-experiences}

Définissez le pool de variations de contenu pour lequel **[!UICONTROL Automated Personalization]** peut personnaliser. Plus vos expériences et offres sont riches et distinctes, plus l’algorithme peut faire correspondre le contenu approprié à chaque visiteur.

### Création de l’activité {#create-activity}

Démarrez l’activité et ouvrez la page que vous souhaitez personnaliser dans le **[!UICONTROL Compositeur d’expérience visuelle]** (VEC).

1. Dans la liste [!DNL Target] **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Automated Personalization]**.

   ![](../assets/ap-activities-2.png)

1. Choisissez votre compositeur d’expérience :

   * Pour utiliser le **[!UICONTROL compositeur d’expérience visuelle]** (VEC), cliquez sur **[!UICONTROL Visual]**.

   * Pour utiliser le **[!UICONTROL compositeur d’expérience d’après les formulaires]**, sélectionnez **[!UICONTROL Formulaire]** à la place. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

     >[!NOTE]
     >
     >Outre le compositeur d’expérience visuelle et le **[!UICONTROL compositeur d’expérience d’après les formulaires]**, [!DNL Target] propose le **[!UICONTROL compositeur d’expérience visuelle d’application d’une seule page]**. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md). Pour obtenir des informations de dépannage sur le VEC, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

     ![](../assets/ap-activities-3.png)

1. (Conditionnel) [Choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Dans la zone **[!UICONTROL Saisir l’URL d’activité]**, spécifiez votre [URL d’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md). Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez remplacer l’URL par défaut par une autre URL.

   Notez que [!DNL Target] ne fait pas de distinction entre les protocoles d&#39;URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://www.adobe.com`] correspondent.

1. Cliquez ensuite sur **[!UICONTROL Créer]**. La page avec l’URL spécifiée s’ouvre dans le VEC.

1. Pour nommer l’activité, cliquez sur l’icône **[!UICONTROL Modifier]** ( ![Icône Modifier](/help/main/assets/icons/Edit.svg) ) et spécifiez un nom explicite pour l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

   {{activity-name-rules}}

   ![](../assets/ap-activities-1.png)

### Concevoir le contenu {#design-content}

Configurez le contenu que l’algorithme peut combiner et excluez les expériences dont vous ne voulez pas.

1. Modifiez les éléments de la page comme expliqué dans la section [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   * Pour prévisualiser plusieurs images rapidement, sélectionnez plusieurs images à la fois à partir du gestionnaire de ressources. Vous pouvez ensuite afficher la page avec chacune des images configurées pour l’activité.
   * Pour modifier le texte de vos offres, modifiez l’élément de texte directement sur la page.

   Lorsque vous modifiez un élément, des barres s’affichent sur cet élément pour indiquer que vous l’avez modifié.

1. Cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ) pour configurer les combinaisons disponibles.

   La boîte de dialogue **[!UICONTROL Gérer le contenu]** s’ouvre avec deux onglets : **[!UICONTROL Expériences]** et **[!UICONTROL Offres]**.

   ![](../assets/ap-activities-4.png)

1. Dans l’onglet **[!UICONTROL Expériences]**, passez en revue la liste des éléments de contenu et l’emplacement auquel chacun est affecté.

1. (Facultatif) Pour exclure des expériences de l’activité, cochez la case de chaque expérience à exclure, puis cliquez sur l’icône **[!UICONTROL Exclure]**.

   Pour plus d’options, voir [Gestion des exclusions](/help/main/c-activities/t-automated-personalization/managing-exclusions.md).

   ![](../assets/ap-activities-5.png)

1. (Conditionnel) Cliquez sur l’onglet **[!UICONTROL Offres]** pour gérer les offres de l’activité.

   * Pour organiser les offres pour le compte rendu des performances, sélectionnez des éléments de contenu et affectez-les à des groupes de compte rendu des performances. Pour plus d’informations, voir [Offrir des groupes de génération de rapports dans Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).
   * Pour limiter le nombre de personnes qui voient une offre, utilisez le ciblage pour permettre à seulement certains visiteurs de voir cette offre.

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the **[!UICONTROL Disallow Duplicates]** option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.
-->

1. Cliquez sur **[!UICONTROL Terminé]** lorsque vous avez terminé de configurer le contenu de votre activité.

## Étape 2 : définition du ciblage {#set-targeting}

Choisissez les visiteurs qui rejoignent l’activité et la proportion de votre trafic exposée. Associez-les à une population témoin afin que [!DNL Target] puisse mesurer les avantages de la personnalisation de l’effet élévateur.

1. Cliquez sur **[!UICONTROL Ciblage]** en haut du **[!UICONTROL Compositeur d’expérience visuelle]** pour passer à l’étape suivante du workflow guidé en trois étapes.

   ![Étape de ciblage du test AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

1. (Conditionnel) Cliquez sur le contrôle **[!UICONTROL Tous les visiteurs]** pour [sélectionner une autre audience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) pour l’activité et définir son pourcentage de visiteur.

   L’audience **[!UICONTROL Tous les visiteurs]** est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche. Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Cliquez sur le contrôle **[!UICONTROL Affectation du trafic]** et choisissez l&#39;une des options suivantes :

   ![Options de l’objectif d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   +++Options de l’objectif d’affectation du trafic

   | Option | Quand l’utiliser |
   |--- |--- |
   | **[!UICONTROL Évaluer l&#39;algorithme Personalization (50/50)]** | Votre objectif est de tester l’algorithme. Les visiteurs sont répartis 50/50 entre le contrôle et l’algorithme ciblé. Cette division donne l’estimation la plus précise de l’effet élévateur, et il s’agit du moyen le plus rapide et le plus précis de tester si l’algorithme fonctionne mieux qu’aucune personnalisation (par exemple, un contrôle diffusé aléatoirement). Suggérée pour une utilisation avec des « expériences aléatoires » comme contrôle. |
   | **[!UICONTROL Maximiser Le Trafic Personalization (90/10)]** | Votre objectif est de créer une activité « toujours active ». 10 % des visiteurs accèdent au contrôle, ce qui garantit qu’il y a suffisamment de données pour que les algorithmes continuent à apprendre au fil du temps. Il s’agit de la méthode la plus rapide et la plus précise pour maximiser la quantité de trafic personnalisé lorsque vous êtes moins préoccupé par l’effet élévateur exact. Le compromis est que vous avez moins de précision dans ce que l&#39;ascenseur exact est. Quel que soit votre objectif, cette option est le partage de trafic recommandé lorsque vous utilisez une expérience spécifique comme contrôle. |
   | **[!UICONTROL Affectation personnalisée]** | Vous souhaitez fractionner le pourcentage manuellement. |

   +++

1. (Conditionnel) Dans la liste déroulante **[!UICONTROL Contrôle]**, [sélectionnez une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou sélectionnez **[!UICONTROL Expérience aléatoire]**.

   L’expérience de contrôle présente une comparaison permettant de déterminer l’effet élévateur fourni par le test automatisé. **[!UICONTROL Automated Personalization]** mesure toujours les performances par rapport à une population témoin. Une règle de bonne pratique consiste à placer au moins 10 % d’entrants dans le groupe témoin.

   >[!NOTE]
   >
   >Dans les activités **[!UICONTROL Automated Personalization]**, les critères d’entrée (ciblage des URL, règles de modèle et cibles d’audience) sont évalués pour chaque requête. Dans les versions précédentes, les critères d’entrée étaient évalués une seule fois par session.

## Étape 3 : configurer les objectifs et les paramètres {#configure-goals-and-settings}

Dites à [!DNL Target] à quoi ressemble le succès. L’objectif d’optimisation que vous choisissez est la mesure sur laquelle l’algorithme de personnalisation s’entraîne. Choisissez donc le résultat le plus important pour cette activité.

1. Cliquez sur **[!UICONTROL Suivant]** pour afficher la page **[!UICONTROL Objectifs et paramètres]**.

1. Configurez l&#39;activité avec les paramètres suivants, puis cliquez sur **[!UICONTROL Enregistrer et fermer]**.

   | Paramètre | Description |
   |--- |--- |
   | **[!UICONTROL Nom]** | Nommez l’activité. Attribuez à l’activité un nom suffisamment explicite pour que les membres de l’équipe puissent la reconnaître dans la liste **[!UICONTROL Activités]**. Suivez les règles de nom d’activité décrites à l’[Étape 1 : création d’expériences](#build-experiences). |
   | **[!UICONTROL Objectif]** | (Facultatif) Saisissez l’intention du test. L’intention vous aide à vous souvenir de l’objectif de l’activité. |
   | **[!UICONTROL Priorité]** | Détermine l’activité qui s’affiche lorsque plusieurs activités partagent un emplacement et une audience. Voir [Définir la priorité](#set-priority). |
   | **[!UICONTROL Durée]** | Définissez les dates de début et de fin de l’activité. Vous pouvez sélectionner **[!UICONTROL Une fois activé]** ou spécifier une date et une heure spécifiques. |
   | **[!UICONTROL Objectif D’Optimisation]** | Mesure en fonction de laquelle l’algorithme de personnalisation s’entraîne. Voir [Définir l’objectif d’optimisation](#set-optimization-goal). |
   | **[!UICONTROL Mesure De Conversion]** | Par défaut, la mesure de conversion est identique à la mesure d’objectif d’optimisation. Cependant, vous pouvez définir une mesure de conversion distincte en décochant l’option **[!UICONTROL Identique à l’objectif d’optimisation]**. |
   | **[!UICONTROL Mesures Supplémentaires]** | Ajoutez les mesures de création de rapports supplémentaires que vous souhaitez utiliser. Vous pouvez ajouter des mesures de conversion ou de recettes.<P>**Remarque** : la mesure **[!UICONTROL Engagement]** n’est pas prise en charge en tant que mesure supplémentaire. L’interface utilisateur [!DNL Target] peut vous permettre de sélectionner la mesure **[!UICONTROL Engagement]**, mais les données ne s’affichent pas précisément dans les rapports. |
   | **[!UICONTROL Audiences pour la création de rapports]** | Ajoutez des audiences pour permettre le filtrage par audiences dans les rapports. Par défaut, le rapport affiche les résultats pour tous les visiteurs qualifiés. Ajoutez des audiences pour filtrer les résultats et obtenir des sous-ensembles plus spécifiques de visiteurs.<P>**Remarque** : contrairement aux autres types d’activité, **[!UICONTROL Automated Personalization]** ne peut pas utiliser **[!UICONTROL Adobe Analytics]** comme source de création de rapports (A4T). |
   | **[!UICONTROL Remarques]** | Saisissez toute information utile pour vous ou pour d’autres membres de l’équipe au sujet de votre activité. Le volet **[!UICONTROL Notes]** peut être redimensionné. |

   Lorsque vous nommez ou renommez une mesure, les caractères suivants ne sont pas autorisés : `/`, `?`, `#`, `:`, `=`, `+`, `-` et `@`.

### Définir la priorité {#set-priority}

Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

Selon vos paramètres, l’interface utilisateur [!DNL Target] et les options de **[!UICONTROL Priorité]** varient :

* **Priorités héritées (par défaut) :** Si les priorités affinées ne sont pas activées, spécifiez une priorité de **[!UICONTROL Faible]**, **[!UICONTROL Medium]** ou **[!UICONTROL Élevée]**.
* **Priorités affinées :** spécifiez une valeur comprise entre 0 et 999, où 0 = Faible et 999 = Élevé. Pour activer cette option, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Rapports]**, puis activez l’option **[!UICONTROL Activer les priorités affinées]** sur la position « Activé ».

Pour les activités créées dans les versions précédentes de [!DNL Target Standard/Premium], la priorité **[!UICONTROL Basse]** est convertie en 0, la priorité **[!UICONTROL Medium]** est convertie en 5 et la priorité **[!UICONTROL Élevée]** est convertie en 10. Vous pouvez ajuster ces valeurs si besoin.

>[!NOTE]
>
>Avant de pouvoir désactiver les priorités affinées après les avoir utilisées, toutes les priorités doivent être définies sur 0, 5 et 10.

### Définir l’objectif d’optimisation {#set-optimization-goal}

L’objectif d’optimisation comprend deux paramètres :

* Ce que vous souhaitez mesurer avec l’activité.
* Action entreprise par un participant à une activité qui montre que l’objectif a été atteint

Vous pouvez choisir de nommer l’objectif d’optimisation en sélectionnant les trois points à droite de **[!UICONTROL Mon objectif de Principal]**. Les activités **[!UICONTROL Automated Personalization]** peuvent mesurer les **[!UICONTROL conversions]** ou les **[!UICONTROL recettes]**. La conversion peut être réalisée en affichant une page ou une mbox. Les clics peuvent également être suivis.

L’objectif principal devient également la mesure de modélisation utilisée par le système de modélisation pour calculer le succès de l’expérience.

Les visiteurs peuvent être maintenus dans l’activité à des fins de suivi après avoir atteint l’objectif de modélisation. Par exemple, une activité **[!UICONTROL Automated Personalization]** est souvent utilisée pour améliorer les taux de clic, et cela est défini comme objectif de modélisation. Cependant, il est important de voir comment l’augmentation du taux de clics mène à la conversion finale. Le suivi de la conversion finale est donc essentiel.

#### Faire dépendre une mesure d’une autre {#add-dependency}

Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente. Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre. L’option **[!UICONTROL Ajouter une dépendance]** permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.

Pour ajouter une dépendance :

1. Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Paramètres avancés]** dans le menu à trois points situé à droite de **[!UICONTROL Objectif supplémentaire]**.

1. Cliquez sur l’option **[!UICONTROL Ajouter une dépendance]** au bas de la section **[!UICONTROL Paramètres de rapports]**.

1. Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur **[!UICONTROL Atteinte]** pour passer du paramètre **[!UICONTROL Atteinte]** au paramètre **[!UICONTROL Non atteinte]**.

Vous pouvez modifier ou supprimer des dépendances après leur ajout.

## Prévisualiser vos expériences {#preview-experiences}

Vérifiez l’aspect de vos expériences sur votre site avant de lancer l’activité.

1. Après avoir cliqué sur **[!UICONTROL Enregistrer et fermer]**, la page **[!UICONTROL Aperçu]** de l’activité s’affiche. Cliquez Sur **Aperçu Des Expériences**.

1. Dans la fenêtre pop-up qui s’affiche, affichez et partagez des liens vers vos expériences AP sur votre site. Ces liens vous donnent un « véritable aperçu » des expériences en dehors du **[!UICONTROL compositeur d’expérience visuelle**[!UICONTROL  de Target ]**]** (VEC).

   >[!NOTE]
   >
   >Vous devez partager les liens provenant du message pour partager l’aperçu. Il n’est pas possible de cliquer sur un lien pour copier directement l’URL à partir du navigateur. La copie du lien entraîne la présence dans l’URL d’un paramètre qui affiche correctement la page uniquement lorsque vous accédez à la page à partir du lien du message.

Pour plus d’informations sur la création de rapports, reportez-vous à la page [Rapports Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
