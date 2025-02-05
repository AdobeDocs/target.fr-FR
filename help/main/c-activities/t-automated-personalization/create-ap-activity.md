---
keywords: automated personalization;ap
description: Découvrez comment créer une activité [!UICONTROL Automated Personalization] (AP) à l’aide de l’[!UICONTROL Visual Experience Composer] .
title: Comment créer une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '1844'
ht-degree: 24%

---

# Création d’une activité [!UICONTROL Automated Personalization]

Créez une activité [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

Le workflow de l’activité [!UICONTROL Automated Personalization] (AP) dans [!DNL Target] diffère de celui des autres types d’activités.

1. Dans la liste [!DNL Target] [!UICONTROL Activities] , cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

1. Pour utiliser le [!UICONTROL Visual Experience Composer] (VEC), cliquez sur **[!UICONTROL Visual]**.

   Pour utiliser le [!UICONTROL Form-Based Experience Composer], sélectionnez [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >En plus du compositeur d’expérience visuelle et de l’[!UICONTROL Form-Based Experience Composer], [!DNL Target] propose le [!UICONTROL Single Page Application VEC] . Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le VEC, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) [Choisissez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Dans la zone de **[!UICONTROL Enter Activity URL]**, spécifiez votre [URL d’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez remplacer l’URL par défaut par une autre URL.

   [!DNL Target] ne fait pas de distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://wwww.adobe.com`] correspondent.

1. Cliquez sur **[!UICONTROL Create]**.

   La page avec l’URL spécifiée s’ouvre dans le VEC.

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

1. Modifiez les éléments de la page comme expliqué dans les options du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Vous pouvez sélectionner plusieurs images à la fois depuis le gestionnaire des ressources. Vous pouvez ainsi visualiser rapidement la page avec chacune des images paramétrées pour l’activité. Vous pouvez également facilement modifier des éléments de texte dans vos offres. Lorsque vous modifiez un élément, des barres s’affichent sur l’élément pour indiquer que vous l’avez modifié.

1. Cliquez sur l’icône **[!UICONTROL Manage Content]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ) pour configurer les combinaisons disponibles.

   Une boîte de dialogue s’affiche avec deux options en haut de l’écran : [!UICONTROL Experiences] et [!UICONTROL Offers].

   >[!NOTE]
   >
   >Bien que vous puissiez créer jusqu’à 30 000 expériences dans une activité AP, celle-ci fonctionne mieux lorsque moins de 5 000 expériences sont utilisées. Cette même limite est appliquée même lorsque l’activité a activé l’option [!UICONTROL Disalow Duplicates].

   La liste [!UICONTROL Experiences] affiche chaque élément de contenu sélectionné pour l’activité et l’emplacement auquel il est affecté.

   Vous pouvez exclure des expériences spécifiques en cochant la case en regard de l’expérience souhaitée, puis en cliquant sur l’icône [!UICONTROL Exclude] .

   Vous pouvez exclure ou inclure des expériences par lots en cochant la case correspondant aux expériences pertinentes, puis en cliquant sur l’icône [!UICONTROL Exclude] .

1. (Conditionnel) Cliquez sur **[!UICONTROL Offers]** pour sélectionner des éléments de contenu et les affecter à des groupes de génération de rapports ou permettre uniquement à certains visiteurs de voir certaines offres avec ciblage.

   Pour plus d’informations sur les groupes de génération de rapports, voir [Offrir des groupes de génération de rapports dans Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disalow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.-->

1. Cliquez sur **[!UICONTROL Done]** lorsque vous avez terminé de configurer le contenu de votre activité.

1. Cliquez sur **[!UICONTROL Targeting]** en haut de la [!UICONTROL Visual Experience Composer] pour passer à l’étape suivante du workflow guidé en trois étapes.

   L’étape **Ciblage** vous est familière si vous avez utilisé d’autres types d’activités [!DNL Target]. Ici, vous pouvez sélectionner une audience et spécifier le pourcentage de visiteurs et visiteuses qui voient chaque expérience.

   Le diagramme de flux s’ouvre.

   ![Étape de ciblage du test AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

   Le diagramme de flux vous guide tout au long des étapes d’affectation d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur le contrôle **[!UICONTROL All Visitors]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL All Visitors] est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Replace]** ( ![icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue [!UICONTROL Add Audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Assign Audience]**.

      Vous pouvez cliquer sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Si vous devez créer une nouvelle audience qui n’est pas encore dans le [!UICONTROL Audience Library], cliquez sur **Créer une audience**. Au cours du workflow [création d’audience](/help/main/c-target/c-audiences/audiences.md) vous pouvez choisir parmi les options suivantes :

      * **[!UICONTROL Audience Library]** : créez une audience à la demande qui est enregistrée dans le [!UICONTROL Audience Library] et qui peut être réutilisée dans d’autres activités.
      * **[!UICONTROL This activity only]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans le [!UICONTROL Audience Library] et qui ne peut être utilisée que dans l’activité actuelle.

   1. Cliquez sur **[!UICONTROL Visitor Percentage]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui souhaitent rejoindre l’activité.

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Cliquez sur le contrôle **[!UICONTROL Traffic Allocation]** pour effectuer une sélection parmi les options suivantes :

   ![Options de l’objectif d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Si votre objectif est de tester l’algorithme, utilisez une répartition de 50/50 % des visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Suggérée pour une utilisation avec des « expériences aléatoires » comme contrôle.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** si votre objectif est de créer une activité « toujours active », placez 10 % des visiteurs dans le contrôle. Cette option permet de s’assurer qu’il y a suffisamment de données pour que les algorithmes continuent à apprendre au fil du temps. Le compromis ici est qu&#39;en l&#39;exchange de la personnalisation d&#39;une plus grande proportion de votre trafic, vous avez moins de précision dans ce qu&#39;est exactement l&#39;ascenseur. Quel que soit votre objectif, cette option est la répartition recommandée du trafic lors de l’utilisation d’une expérience spécifique comme contrôle.
   * **[!UICONTROL Custom Allocation]:** fractionnez manuellement le pourcentage selon vos besoins.

1. (Conditionnel) Dans la liste déroulante [!UICONTROL Control], [sélectionnez une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou sélectionnez [!UICONTROL Random Experience.]

   L’expérience de contrôle présente une comparaison permettant de déterminer l’effet élévateur fourni par le test automatisé.

   [!UICONTROL Automated Personalization] mesure toujours les performances par rapport à une population témoin. Une règle de bonne pratique consiste à placer au moins 10 % d’entrants dans le groupe témoin. Si votre objectif est de tester si l’algorithme de personnalisation des données qui lui sont fournies fonctionne mieux qu’aucune personnalisation (par exemple, le contrôle diffusé de manière aléatoire), une répartition de 50/50 % du trafic entre le contrôle et l’algorithme de personnalisation est la manière la plus rapide et la plus précise d’atteindre cet objectif. Si vous souhaitez maximiser la quantité de trafic personnalisé et que vous vous souciez moins de comprendre l’effet élévateur exact généré par votre activité, une répartition de 10/90 % du trafic entre le contrôle et l’algorithme de personnalisation est le moyen le plus rapide et le plus précis d’atteindre cet objectif.

   >[!NOTE]
   >
   >Dans les activités [!UICONTROL Automated Personalization], les critères d’entrée (ciblage des URL, règles de modèle et cibles d’audience) sont évalués pour chaque requête. Dans les versions précédentes, les critères d’entrée étaient évalués une seule fois par session.

1. Cliquez sur **[!UICONTROL Next]** pour afficher la page **[!UICONTROL Goals & Settings]**.
1. Configurez l’activité avec les paramètres suivants, puis cliquez sur **[!UICONTROL Save & Close]**.

   | Paramètre | Description |
   |--- |--- |
   | [!UICONTROL Name] | Nommez l’activité. Attribuez à l’activité un nom suffisamment explicite pour que les membres de l’équipe puissent la reconnaître dans la liste [!UICONTROL Activities]. Consultez le tableau ci-dessus pour identifier les caractères qui ne sont pas autorisés dans le nom d’une activité. |
   | [!UICONTROL Objective] | (Facultatif) Saisissez l’intention du test. L’intention vous aide à vous souvenir de l’objectif de l’activité. |
   | [!UICONTROL Priority] | Selon vos paramètres, l’interface utilisateur [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou activer les priorités affinées de 0 à 999.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Si cette option n’est pas activée dans [!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].<P>Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez l’option [!UICONTROL Enable Fine-Grained Priorities] à la position « Activé ».<P>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :<ul><li>0 = Faible</li><li>999 = Élevé</li></ul>Pour les activités créées dans les versions précédentes d’[!DNL Target Standard/Premium], [!UICONTROL Low] priorité est convertie en 0, [!UICONTROL Medium] priorité est convertie en 5 et [!UICONTROL High] priorité est convertie en 10. Vous pouvez ajuster ces valeurs si besoin.<P>**Remarque** : avant de pouvoir désactiver cette option après l’utilisation de priorités affinées, toutes les priorités doivent être redéfinies sur 0, 5 et 10. |
   | [!UICONTROL Duration] | Définissez les dates de début et de fin de l’activité. Vous pouvez sélectionner [!UICONTROL When Activated] ou spécifier une date et une heure spécifiques. |
   | [!UICONTROL Optimization Goal] | Spécifiez l’objectif d’optimisation, qui se compose de deux paramètres :<ul><li>Ce que vous souhaitez mesurer avec l’activité.</li><li>L’action exécutée par un participant à l’activité qui montre que l’objectif a été atteint.</li></ul>Vous pouvez choisir de nommer l’objectif d’optimisation en sélectionnant les trois points à droite de [!UICONTROL My Primary Goal]. [!UICONTROL Automated Personalization] activités peuvent mesurer des [!UICONTROL Conversion] ou des [!UICONTROL Revenue]. La conversion peut être réalisée en affichant une page ou une mbox. Les clics peuvent également être suivis.<P>L’objectif principal devient également la mesure de modélisation utilisée par le système de modélisation pour calculer le succès de l’expérience.<P>Les visiteurs peuvent être maintenus dans l’activité à des fins de suivi après avoir atteint l’objectif de modélisation. Par exemple, une activité [!UICONTROL Automated Personalization] est souvent utilisée pour améliorer les taux de clic, et cela est défini comme objectif de modélisation. Néanmoins, il est important de voir dans quelle mesure l’augmentation des taux de clics mène à une conversion finale. De ce fait, le suivi par l’intermédiaire de la conversion finale est essentiel.<P>Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.<P>Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.<P>L’option [!UICONTROL Add Dependency] permet à la mesure de succès d’être incrémentée si une autre mesure de succès a été atteinte ou n’a pas été atteinte.<P>Pour ajouter une dépendance :<ol><li>Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Advanced Settings]** dans le menu à trois points situé à droite de [!UICONTROL Additional Goal].</li><li>Cliquez sur l’option **[!UICONTROL Add Dependency]** au bas de la section [!UICONTROL Reporting Settings] .</li><li>Faites glisser et déposez les mesures de votre choix depuis le volet de gauche vers le volet de droite, puis cliquez sur [!UICONTROL Reached] pour basculer le paramètre entre [!UICONTROL Reached] et [!UICONTROL Not Reached].</li></ol>Vous pouvez modifier ou supprimer des dépendances après leur ajout. |
   | [!UICONTROL Conversion Metric] | Par défaut, la mesure de conversion est identique à la mesure d’objectif d’optimisation. Cependant, vous pouvez définir une mesure de conversion distincte en décochant l’option [!UICONTROL Same as Optimization Goal] . |
   | [!UICONTROL Additional Metrics] | Ajoutez les mesures de création de rapports supplémentaires que vous souhaitez utiliser. Vous pouvez ajouter des mesures de conversion ou de recettes.<P>**Remarque** : la mesure [!UICONTROL Engagement] n’est pas prise en charge en tant que mesure supplémentaire. L’interface utilisateur de [!DNL Target] peut vous permettre de sélectionner la mesure de [!UICONTROL Engagement], mais les données ne s’affichent pas correctement dans les rapports. |
   | [!UICONTROL Audiences for Reporting] | Ajoutez des audiences pour permettre le filtrage par audiences dans les rapports. Par défaut, le rapport affiche les résultats pour tous les visiteurs qualifiés. Ajoutez des audiences pour filtrer les résultats et obtenir des sous-ensembles plus spécifiques de visiteurs.<P>**Remarque** : contrairement aux autres types d’activité, [!UICONTROL Automated Personalization] ne pouvez pas utiliser [!UICONTROL Adobe Analytics] comme source de création de rapports (A4T). |
   | [!UICONTROL Notes] | Saisissez toute information utile pour vous ou pour d’autres membres de l’équipe au sujet de votre activité. Le volet [!UICONTROL Notes] peut être redimensionné. |

   Lorsque vous nommez ou renommez une mesure, les caractères suivants ne sont pas autorisés :

   | Caractère | Description |
   |--- |--- |
   | / | Barre oblique |
   | ? | Point d’interrogation |
   | # | Croisillon |
   | : | Deux-points |
   | = | Égal |
   | + | Plus |
   | - | Moins |
   | @ | Arobase |

Une fois que vous avez cliqué sur **[!UICONTROL Save & Close]**, la page [!UICONTROL Overview] de l’activité s’affiche. Cliquez sur **Aperçu des expériences** pour prévisualiser vos expériences une fois diffusées. Un pop-up s’affiche, que vous pouvez utiliser pour afficher et partager des liens vers vos expériences AP sur votre site afin d’obtenir un « véritable aperçu » des expériences en dehors du [!UICONTROL Visual Experience Composer] d’[!UICONTROL Target] (VEC). Vous devez partager les liens provenant du message pour partager l’aperçu. Il n’est pas possible de cliquer sur un lien pour copier directement l’URL à partir du navigateur. La copie du lien entraîne la présence dans l’URL d’un paramètre qui affiche correctement la page uniquement lorsque vous accédez à la page à partir du lien du message.

Pour plus d’informations sur la création de rapports, reportez-vous à la page [Rapports Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
