---
keywords: personnalisation automatisée;ap
description: Découvrez comment créer une activité [!UICONTROL Automated Personalization] (AP) à l’aide de [!UICONTROL Visual Experience Composer].
title: Comment créer une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez ce qui est inclus dans Target Premium."
feature: Automated Personalization
hide: true
hidefromtoc: true
exl-id: fe6e5130-53a0-4254-8299-b52086c20004
source-git-commit: 8bfad2fe6804c241deec6c8ea70e2f8e7d79d8c6
workflow-type: tm+mt
source-wordcount: '1767'
ht-degree: 28%

---

# Créer une activité [!UICONTROL Automated Personalization]

Créez une activité [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] à l’aide du [!UICONTROL Visual Experience Composer] (VEC).

Le workflow d’activité [!UICONTROL Automated Personalization] (AP) dans [!DNL Target] varie en fonction du workflow des autres types d’activité.

1. Dans la liste [!DNL Target] [!UICONTROL Activities], cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

1. Pour utiliser le [!UICONTROL Visual Experience Composer] (VEC), cliquez sur **[!UICONTROL Visual]**.

   Pour utiliser le [!UICONTROL Form-Based Experience Composer], sélectionnez [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le VEC et [!UICONTROL Form-Based Experience Composer], [!DNL Target] offre le [!UICONTROL Single Page Application VEC]. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le compositeur d’expérience visuelle, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) [Sélectionnez un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Dans la zone **[!UICONTROL Enter Activity URL]**, spécifiez votre [URL d&#39;activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez passer de la valeur par défaut à une autre URL.

   [!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://wwww.adobe.com`] correspondent tous les deux.

1. Cliquez sur **[!UICONTROL Create]**.

   La page avec l’URL spécifiée s’ouvre dans le VEC.

1. Cliquez sur l’icône **[!UICONTROL Rename]** ( ![Icône Renommer](/help/main/assets/icons/MoreSmallListVert.svg) ), cliquez sur **[!UICONTROL Rename]**, nommez l’activité, puis cliquez sur **[!UICONTROL Save]**.

   Le nom de l’activité ne peut pas commencer par les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence de caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule, plus |
   | ; - | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, Égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, signe At |
   | `[`&quot; | Crochets droits ouverts, guillemets doubles |
   | &quot;`]` | Guillemets doubles, crochet fermant |

1. Modifiez les éléments de la page comme expliqué dans les options du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Vous pouvez sélectionner plusieurs images à la fois depuis le gestionnaire des ressources. Vous pouvez ainsi visualiser rapidement la page avec chacune des images configurées pour l’activité. Vous pouvez également facilement modifier des éléments de texte dans vos offres. Lorsque vous modifiez un élément, des barres s’affichent sur l’élément pour indiquer que vous l’avez modifié.

1. Cliquez sur **[!UICONTROL Manage Content]** pour configurer les combinaisons disponibles.

   ![Option Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Une boîte de dialogue s’affiche avec trois options en haut de l’écran : [!UICONTROL Experiences], [!UICONTROL Offers] et [!UICONTROL Exclusion Groups].

   ![Boîte de dialogue Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Bien que vous puissiez créer jusqu’à 30 000 expériences dans une activité AP, l’activité est la plus performante lorsque moins de 5 000 expériences sont utilisées. Cette même limite est appliquée même lorsque l’activité a activé l’option [!UICONTROL Disalow Duplicates].

   La liste [!UICONTROL Experiences] affiche chaque élément de contenu sélectionné pour l’activité et l’emplacement auquel il est affecté.

   Vous pouvez exclure des expériences spécifiques en survolant l’expérience souhaitée, puis en cliquant sur l’icône [!UICONTROL Exclude].

   ![Action de survol de l’icône Exclure](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Vous pouvez exclure ou inclure des expériences par lots en cochant la case correspondant aux expériences pertinentes, puis en cliquant sur l’icône [!UICONTROL Exclude] dans le coin supérieur droit de la boîte de dialogue.

   ![Options d’exclusion par lots](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Vous pouvez filtrer cette vue sous forme de liste pour afficher uniquement les activités incluses ou exclues en cliquant sur la liste déroulante [!UICONTROL Status] .

1. (Conditionnel) Cliquez sur **[!UICONTROL Offers]** pour sélectionner des éléments de contenu et les affecter aux groupes de génération de rapports ou uniquement autoriser certains visiteurs à voir certaines offres avec le ciblage.

   Pour plus d’informations sur les groupes de génération de rapports, voir [Groupes de génération de rapports d’offres dans Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Conditionnel) Cliquez sur **[!UICONTROL Exclusion Groups]** pour choisir une combinaison d’éléments que vous souhaitez exclure de l’activité.

   ![Onglet Groupes d’exclusion de la boîte de dialogue Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Bien que vous puissiez créer jusqu’à 30 000 expériences dans un test AP, l’algorithme obtient son meilleur résultat lorsque moins de 10 000 expériences distinctes sont utilisées. Cette même limite est appliquée même lorsque l’activité a activé l’option [!UICONTROL Disalow Duplicates].

   Si votre activité ne comprend pour l’instant aucun groupe d’exclusion, cliquez sur **Créer un groupe d’exclusion**. Vous pouvez appliquer un filtre pour créer une liste affichant uniquement les combinaisons à exclure. Nommez votre groupe d’exclusion, puis cliquez sur **Enregistrer**.

   Pour modifier un groupe d’exclusion existant, survolez le groupe que vous souhaitez modifier, puis cliquez sur l’icône en forme de crayon.

1. Cliquez sur **[!UICONTROL Done]** lorsque vous avez terminé de configurer le contenu de votre activité.

1. L’étape **Ciblage** vous semble familière si vous avez utilisé d’autres types d’activité [!DNL Target]. Ici, vous pouvez sélectionner une audience et spécifier le pourcentage de visiteurs qui visualisent l’expérience de contrôle en cliquant sur la liste déroulante **[!UICONTROL Custom Allocation]**, puis sur **Suivant**.

   La liste déroulante [!UICONTROL Custom Allocation] vous permet de choisir parmi les options suivantes :

   ![Liste déroulante Objectif d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Si votre objectif est de tester l’algorithme, utilisez une répartition de 50/50 % des visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Suggestion d’utilisation avec &quot;expériences aléatoires&quot; comme contrôle.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** Si votre objectif est de créer une activité &quot;toujours active&quot;, placez 10 % des visiteurs dans le contrôle. Cette option garantit qu’il existe suffisamment de données pour que les algorithmes continuent d’apprendre au fil du temps. Le compromis ici est qu&#39;en exchange pour personnaliser une plus grande partie de votre trafic, vous avez moins de précision dans l&#39;effet élévateur exact. Quel que soit votre objectif, cette option est le trafic recommandé lors de l’utilisation d’une expérience spécifique comme contrôle.
   * **[!UICONTROL Custom Allocation]:** répartissez manuellement le pourcentage selon vos besoins.

1. (Conditionnel) Dans la liste déroulante [!UICONTROL Control], [sélectionnez une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou sélectionnez [!UICONTROL Random Experience.]

   L’expérience de contrôle présente une comparaison permettant de déterminer l’effet élévateur fourni par le test automatisé.

   [!UICONTROL Automated Personalization] mesure toujours les performances par rapport à une population témoin. Une règle de bonne pratique consiste à placer au moins 10 % d’entrants dans le groupe témoin. Si votre objectif est de tester si l’algorithme de personnalisation sur les données qu’il reçoit est plus performant qu’aucune personnalisation (par exemple, le contrôle diffusé de manière aléatoire), une répartition de trafic de 50/50 entre le contrôle et l’algorithme de personnalisation est la manière la plus rapide et la plus précise d’atteindre cet objectif. Si vous souhaitez maximiser le volume de trafic personnalisé et que vous souhaitez moins comprendre l’effet élévateur exact généré par votre activité, une répartition de trafic de 10/90 entre le contrôle et l’algorithme de personnalisation est la méthode la plus rapide et la plus précise pour atteindre cet objectif.

   >[!NOTE]
   >
   >Dans les activités [!UICONTROL Automated Personalization], les critères d’entrée (ciblage d’URL, règles de modèle et cibles d’audience) sont évalués pour chaque requête. Dans les versions précédentes, les critères d’entrée étaient évalués une seule fois par session.

1. Cliquez sur **[!UICONTROL Next]** pour afficher la page **[!UICONTROL Goals & Settings]**.
1. Configurez l’activité avec les paramètres suivants, puis cliquez sur **[!UICONTROL Save & Close]**.

   | Paramètre | Description |
   |--- |--- |
   | [!UICONTROL Name] | Nommez l’activité. Donnez à l’activité un nom suffisamment descriptif pour que les membres de l’équipe puissent le reconnaître dans la liste [!UICONTROL Activities]. Consultez le tableau ci-dessus pour identifier les caractères qui ne sont pas autorisés dans le nom d’une activité. |
   | [!UICONTROL Objective] | (Facultatif) Saisissez l’intention du test. L’intention vous aide à vous souvenir de l’objectif de l’activité. |
   | [!UICONTROL Priority] | Selon vos paramètres, l’interface utilisateur de [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou vous pouvez activer les priorités affinées de 0 à 999.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Si cette option n&#39;est pas activée dans [!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].<P>Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez l’option [!UICONTROL Enable Fine-Grained Priorities].<P>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :<ul><li>0 = Faible</li><li>999 = Élevé</li></ul>Pour les activités créées dans les versions précédentes de [!DNL Target Standard/Premium], la priorité [!UICONTROL Low] est convertie en 0, la priorité [!UICONTROL Medium] est convertie en 5 et la priorité [!UICONTROL High] en 10. Vous pouvez ajuster ces valeurs si besoin.<P>**Remarque** : avant de pouvoir désactiver cette option après avoir utilisé des priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10. |
   | [!UICONTROL Duration] | Définissez les dates de début et de fin de l’activité. Vous pouvez sélectionner [!UICONTROL When Activated] ou spécifier une date et une heure spécifiques. |
   | [!UICONTROL Optimization Goal] | Spécifiez l’objectif d’optimisation, qui se compose de deux paramètres :<ul><li>Ce que vous souhaitez mesurer avec l’activité.</li><li>L’action exécutée par un participant à l’activité qui montre que l’objectif a été atteint.</li></ul>Vous pouvez choisir de nommer l’objectif d’optimisation en sélectionnant les trois points situés à droite de [!UICONTROL My Primary Goal]. Les activités [!UICONTROL Automated Personalization] peuvent mesurer [!UICONTROL Conversion] ou [!UICONTROL Revenue]. La conversion peut être obtenue en affichant une page ou une mbox. Les clics peuvent également être suivis.<P>L’objectif principal devient également la mesure de modélisation utilisée par le système de modélisation pour calculer le succès de l’expérience.<P>Les visiteurs peuvent être maintenus dans l’activité à des fins de suivi après avoir atteint l’objectif de modélisation. Par exemple, une activité [!UICONTROL Automated Personalization] est souvent utilisée pour améliorer les taux de clics, et elle est définie comme objectif de modélisation. Néanmoins, il est important de voir dans quelle mesure l’augmentation des taux de clics mène à une conversion finale. De ce fait, le suivi par l’intermédiaire de la conversion finale est essentiel.<P>Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.<P>Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.<P>L’option [!UICONTROL Add Dependency] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.<P>Pour ajouter une dépendance :<ol><li>Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Advanced Settings]** sous le menu à trois points situé à droite de [!UICONTROL Additional Goal].</li><li>Cliquez sur l’option **[!UICONTROL Add Dependency]** au bas de la section [!UICONTROL Reporting Settings].</li><li>Faites glisser les mesures de votre choix depuis le volet de gauche vers le volet de droite, puis cliquez sur [!UICONTROL Reached] pour passer du paramètre [!UICONTROL Reached] à [!UICONTROL Not Reached].</li></ol>Vous pouvez modifier ou supprimer des dépendances après leur ajout. |
   | [!UICONTROL Conversion Metric] | Par défaut, la mesure de conversion est identique à la mesure d’objectif d’optimisation. Cependant, vous pouvez définir une mesure de conversion distincte en désactivant l’option [!UICONTROL Same as Optimization Goal]. |
   | [!UICONTROL Additional Metrics] | Ajoutez d’autres mesures de création de rapports à utiliser. Vous pouvez ajouter des mesures de conversion ou de recettes.<P>**Remarque** : La mesure [!UICONTROL Engagement] n’est pas prise en charge en tant que mesure supplémentaire. L’interface utilisateur de [!DNL Target] peut vous permettre de sélectionner la mesure [!UICONTROL Engagement], mais les données ne s’affichent pas correctement dans les rapports. |
   | [!UICONTROL Audiences for Reporting] | Ajoutez des audiences pour permettre le filtrage par audiences dans les rapports. Par défaut, le rapport affiche les résultats pour tous les visiteurs qualifiés. Ajoutez des audiences pour filtrer les résultats et obtenir des sous-ensembles plus spécifiques de visiteurs.<P>**Remarque** : Contrairement aux autres types d’activité, [!UICONTROL Automated Personalization] ne peut pas utiliser [!UICONTROL Adobe Analytics] comme source de création de rapports (A4T). |
   | [!UICONTROL Notes] | Saisissez des informations utiles pour vous ou d’autres membres de l’équipe sur votre activité. Le volet [!UICONTROL Notes] peut être redimensionné. |

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

Une fois que vous avez cliqué sur **[!UICONTROL Save & Close]**, la page [!UICONTROL Overview] de l’activité s’affiche. Cliquez sur **Aperçu des expériences** pour prévisualiser l’apparence de vos expériences lors de leur diffusion. Une fenêtre contextuelle s’affiche que vous pouvez utiliser pour afficher et partager des liens vers vos expériences AP sur votre site afin d’obtenir un &quot;véritable aperçu&quot; des expériences en dehors du [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC). Vous devez partager les liens provenant du message pour partager l’aperçu. Le fait de cliquer sur un lien, puis de copier l’URL directement à partir du navigateur ne fonctionne pas. Si vous copiez le lien, l’URL contient un paramètre qui affiche correctement la page uniquement lorsque vous accédez à la page à partir du lien contenu dans le message.

Pour plus d’informations sur la création de rapports, reportez-vous à la page [Rapports Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
