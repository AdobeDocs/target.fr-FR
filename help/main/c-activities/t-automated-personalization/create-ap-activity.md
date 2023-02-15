---
keywords: personnalisation automatisée;ap;audiences;ensemble;random forest;variance résiduelle;variance d’erreur;valeur de durée de vie
description: Découvrez comment créer une [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] en utilisant la variable [!UICONTROL Compositeur d’expérience visuelle].
title: Comment créer une [!UICONTROL Automated Personalization] Activité ?
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 8a791d4266cb03fef498ac6f852d4a5755ba66a6
workflow-type: tm+mt
source-wordcount: '1854'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) Création d’une activité de personnalisation automatisée

Créez un [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target] en utilisant la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC).

Le [!UICONTROL Automated Personalization] Workflow d’activité (AP) dans [!DNL Adobe Target] varie par rapport au workflow des autres types d’activité.

1. Dans la [!DNL Target] [!UICONTROL Activités] liste, cliquez sur **[!UICONTROL Création d’une activité]** > **[!UICONTROL Automated Personalization]**.

   ![Créer une activité : Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Pour utiliser le VEC, cliquez sur **[!UICONTROL Visuel (par défaut)]**.

   ![Boîte de dialogue Créer une activité Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   Pour utiliser la variable [!UICONTROL Compositeur d’expérience d’après les formulaires], sélectionnez [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >En plus du VEC et de [!UICONTROL Compositeur d’expérience d’après les formulaires], [!DNL Target] offre la variable [!UICONTROL VEC d’application d’une seule page]. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le compositeur d’expérience visuelle, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) [Choisir un espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Vérifiez ou saisissez l’URL d’activité, puis cliquez sur **[!UICONTROL Suivant]**.

   >[!NOTE]
   >
   >[!DNL Target] ne fait pas la distinction entre les protocoles d’URL ([!DNL https] et [!DNL http]). Par conséquent, [!DNL `http://www.adobe.com`] et [!DNL `https://wwww.adobe.com`] se correspondent.

   La page avec l’URL spécifiée s’ouvre dans le VEC.

1. Pour nommer l’activité, cliquez sur le bouton **[!UICONTROL Nom]** et saisissez le nom de l’activité.

   ![Champ Nom](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   Le nom de l’activité ne peut pas commencer par les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   De plus, le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes : &#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;, &#39;[&quot;&#39;, &#39;&quot;]&#39;, &#39;[&#39;&#39;, &#39;&#39;]&#39;.

1. Modifiez les éléments de la page comme expliqué dans les options du [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Vous pouvez sélectionner plusieurs images à la fois depuis le gestionnaire des ressources. Vous pouvez ainsi consulter rapidement la page avec chacune des images configurées pour l’activité. Vous pouvez également facilement modifier des éléments de texte dans vos offres. Lorsque vous modifiez un élément, des barres s’affichent sur l’élément pour indiquer que vous l’avez modifié.

1. Cliquez sur **[!UICONTROL Gérer le contenu]** pour configurer les combinaisons disponibles.

   ![Option Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Une boîte de dialogue s’affiche avec trois options en haut de l’écran : [!UICONTROL Expériences], [!UICONTROL Offres], et [!UICONTROL Groupes d’exclusion].

   ![Boîte de dialogue Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Bien que vous puissiez créer jusqu’à 30 000 expériences dans une activité PA, l’activité est la plus optimale lorsque moins de 5 000 expériences sont utilisées. Cette même limite est appliquée même si l’activité a activé l’option [!UICONTROL Refuser les doublons].

   Le [!UICONTROL Expériences] La liste affiche chaque élément de contenu sélectionné pour l’activité et l’emplacement auquel il est affecté.

   Vous pouvez exclure des expériences spécifiques en pointant sur l’expérience souhaitée, puis en cliquant sur le bouton [!UICONTROL Exclure] icône .

   ![Action de survol de l’icône Exclure](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Vous pouvez exclure ou inclure des expériences par lots en cochant la case correspondant aux expériences pertinentes, puis en cliquant sur le bouton [!UICONTROL Exclure] dans le coin supérieur droit de la boîte de dialogue.

   ![Options d’exclusion par lots](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   Vous pouvez filtrer cette vue sous forme de liste de manière à afficher uniquement les activités incluses ou exclues en cliquant sur la liste déroulante [!UICONTROL État].

1. (Conditionnel) Cliquez sur **[!UICONTROL Offres]** pour sélectionner des éléments de contenu et les affecter aux groupes de génération de rapports ou uniquement autoriser certains visiteurs à voir certaines offres avec le ciblage.

   Pour plus d’informations sur les groupes de génération de rapports, voir [Offrir des groupes de génération de rapports dans Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Conditionnel) Cliquez sur **[!UICONTROL Groupes d’exclusion]** pour choisir une combinaison d’éléments à exclure de l’activité.

   ![Onglet Groupes d’exclusion de la boîte de dialogue Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Bien que vous puissiez créer jusqu’à 30 000 expériences dans un test AP, l’algorithme fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont utilisées. Cette même limite est appliquée même si l’activité a activé l’option [!UICONTROL Refuser les doublons].

   Si votre activité ne comprend pour l’instant aucun groupe d’exclusion, cliquez sur **Créer un groupe d’exclusion**. Vous pouvez appliquer un filtre pour créer une liste affichant uniquement les combinaisons à exclure. Nommez votre groupe d’exclusion, puis cliquez sur **Enregistrer**.

   Pour modifier un groupe d’exclusion existant, survolez le groupe que vous souhaitez modifier, puis cliquez sur l’icône en forme de crayon.

1. Cliquez sur **[!UICONTROL Terminé]** lorsque vous avez terminé de configurer le contenu de votre activité.

1. Le **Ciblage** vous me semble familier si vous avez utilisé d’autres [!DNL Target] types d’activité. Ici, vous pouvez sélectionner une audience et spécifier le pourcentage de visiteurs qui visualisent l’expérience de contrôle en cliquant sur le **[!UICONTROL Affectation personnalisée]** liste déroulante, puis cliquez sur **Suivant**.

   La liste déroulante [!UICONTROL Affectation personnalisée] vous permet de choisir parmi les options suivantes :

   ![Liste déroulante Objectif d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Évaluer l’algorithme de personnalisation (50/50)]:** Si votre objectif est de tester l’algorithme, utilisez une répartition de 50/50 % des visiteurs entre le contrôle et l’algorithme ciblé. Cette répartition produira l’estimation de l’effet élévateur la plus précise. Suggestion d’utilisation avec &quot;expériences aléatoires&quot; comme contrôle.
   * **[!UICONTROL Maximiser le trafic de personnalisation (90/10)]:** Si votre objectif est de créer une activité &quot;toujours active&quot;, affectez 10 % des visiteurs dans le contrôle. Cette option garantit qu’il existe suffisamment de données pour que les algorithmes continuent d’apprendre au fil du temps. Notez que le compromis ici est qu’en échange de la personnalisation d’une plus grande partie de votre trafic, vous avez moins de précision dans l’effet élévateur exact. Quel que soit votre objectif, il s’agit du trafic recommandé lors de l’utilisation d’une expérience spécifique comme contrôle.
   * **[!UICONTROL Affectation personnalisée]:** Divisez manuellement le pourcentage suivant vos besoins.

1. (Conditionnel) Dans la liste déroulante [!UICONTROL Contrôle], [sélectionnez une expérience spécifique à utiliser comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou sélectionnez [!UICONTROL Expérience aléatoire.]

   L’expérience de contrôle présente une comparaison permettant de déterminer l’effet élévateur fourni par le test automatisé.

   [!UICONTROL Automated Personalization mesure toujours les performances par rapport à un groupe de contrôle. ] Une règle de bonne pratique consiste à placer au moins 10 % d’entrants dans le groupe témoin. Si votre objectif consiste à déterminer si l’algorithme de personnalisation appliqué aux données fonctionne mieux qu’en l’absence de personnalisation (c’est-à-dire lorsque le contrôle est servi au hasard), la répartition du trafic selon un pourcentage de 50/50 entre le contrôle et l’algorithme de personnalisation serait la manière la plus rapide et la plus précise d’atteindre le résultat recherché. Si vous souhaitez maximiser la quantité de trafic personnalisé et que vous êtes moins préoccupé par la compréhension de l’effet élévateur exact généré par votre activité, la répartition du trafic selon un pourcentage de 10/90 entre le contrôle et l’algorithme de personnalisation serait la manière la plus rapide et la plus précise d’atteindre le résultat recherché.

   >[!NOTE]
   >
   >Dans [!UICONTROL Automated Personalization] les activités, les critères d’entrée (ciblage d’URL, règles de modèle et cibles d’audience) sont évalués pour chaque requête. Dans les versions précédentes, les critères d’entrée étaient évalués une seule fois par session.

1. Cliquez sur **[!UICONTROL Suivant]** pour afficher la page **[!UICONTROL Objectifs et paramètres]**.
1. **[!UICONTROL Configurez l’activité avec les paramètres suivants, puis cliquez sur Enregistrer et fermer]**.

   | Paramètre | Description |
   |--- |--- |
   | [!UICONTROL Nom] | Nommez l’activité. Donnez à l’activité un nom suffisamment descriptif pour que les membres de l’équipe puissent le reconnaître dans la variable [!UICONTROL Activités] liste. Consultez le tableau ci-dessus pour identifier les caractères qui ne sont pas autorisés dans le nom d’une activité. |
   | [!UICONTROL Intention] | (Facultatif) Saisissez l’intention du test. L’intention vous aide à vous souvenir de l’objectif de l’activité. |
   | [!UICONTROL Priorité] | En fonction de vos paramètres, l’interface utilisateur et les options pour [!UICONTROL Priorité] peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.<br>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<br>Si cette option n’est pas activée dans [!UICONTROL Administration] > [!UICONTROL Reporting] (valeur par défaut), spécifiez une priorité : Faible, Moyen ou Élevé.<br>Pour activer les priorités affinées, cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez la fonction [!UICONTROL Activation des priorités affinées] à la position &quot;Activé&quot;.<br>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 :<ul><li>0 = Faible</li><li>999 = Élevé</li></ul>Pour les activités créées dans les anciennes versions de [!DNL Target Standard/Premium], la priorité Faible correspond à 0, Moyen à 5 et Élevé à 10. Vous pouvez ajuster ces valeurs si besoin.<br>**Remarque** : avant de pouvoir désactiver cette option, après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10. |
   | [!UICONTROL Durée] | Définissez les dates de début et de fin de l’activité. Vous pouvez sélectionner [!UICONTROL Lorsqu’il est activé] ou vous pouvez spécifier une date et une heure spécifiques. |
   | [!UICONTROL Objectif d’optimisation] | Spécifiez l’objectif d’optimisation, qui se compose de deux paramètres :<ul><li>Ce que vous souhaitez mesurer avec l’activité.</li><li>L’action exécutée par un participant à l’activité qui montre que l’objectif a été atteint.</li></ul>Vous pouvez choisir de nommer l’objectif d’optimisation en sélectionnant les trois points situés à droite de [!UICONTROL Mon Principal objectif]. [!UICONTROL Automated Personalization] les activités peuvent être mesurées ; [!UICONTROL Conversion] ou [!UICONTROL Recettes]. La conversion peut être obtenue en visualisant une page ou une mbox. Les clics peuvent également être suivis.<br>L’objectif principal devient également la mesure de modélisation, utilisée par le système de modélisation pour calculer le succès de l’expérience.<br>Les visiteurs peuvent être maintenus dans l’activité à des fins de suivi après avoir atteint l’objectif de modélisation. Par exemple, une [!UICONTROL Automated Personalization] L’activité est utilisée pour améliorer les taux de clics, définie comme objectif de modélisation. Néanmoins, il est important de voir dans quelle mesure l’augmentation des taux de clics mène à une conversion finale. De ce fait, le suivi par l’intermédiaire de la conversion finale est essentiel.<br>Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente.<br>Vous devez définir les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre.<br>L’option Ajouter une dépendance permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte.<br>Pour ajouter une dépendance :<ol><li>Après avoir ajouté des mesures supplémentaires, cliquez sur **[!UICONTROL Paramètres]**[!UICONTROL  sous le menu à trois points à droite de l’option Objectif supplémentaire].</li><li>Cliquez sur l’option **[!UICONTROL Ajouter une dépendance]** au bas de la section [!UICONTROL Paramètres de création de rapports].</li><li>Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur [!UICONTROL Atteinte] pour passer du paramètre [!UICONTROL Atteinte] au paramètre [!UICONTROL Non atteinte]</li></ol>Vous pouvez modifier ou supprimer des dépendances après leur ajout. |
   | [!UICONTROL Mesure de conversion] | Par défaut, la mesure de conversion est identique à la mesure d’objectif d’optimisation. Cependant, vous pouvez définir une mesure de conversion distincte en désactivant l’option [!UICONTROL Identique à l’objectif d’optimisation]. |
   | [!UICONTROL Mesures supplémentaires] | Ajoutez d’autres mesures de création de rapports à utiliser. Vous pouvez ajouter des mesures de conversion ou de recettes.<br>**Remarque** : la mesure Engagement n’est pas prise en charge en tant que mesure supplémentaire. L’interface utilisateur peut vous permettre de sélectionner la variable [!UICONTROL Engagement] , mais les données ne s’affichent pas correctement dans les rapports. |
   | [!UICONTROL Audiences pour les rapports] | Ajoutez des audiences pour permettre le filtrage par audiences dans les rapports. Par défaut, le rapport affiche les résultats pour tous les visiteurs qualifiés. Ajoutez des audiences pour filtrer les résultats et obtenir des sous-ensembles plus spécifiques de visiteurs.<br>**Remarque**: Contrairement à d’autres types d’activité, [!UICONTROL Automated Personalization] impossible d’utiliser [!UICONTROL Adobe Analytics] comme source des rapports (A4T). |
   | [!UICONTROL Remarques] | Entrez des informations sur l’activité qui soient utiles pour vous et d’autres membres de l’équipe. Le [!UICONTROL Remarques] est redimensionnable. |

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

Après avoir cliqué sur **[!UICONTROL Enregistrer et fermer]**, le de l’activité [!UICONTROL Présentation] s’affiche. Cliquez sur **Aperçu des expériences** pour prévisualiser l’aspect de vos expériences lors de leur diffusion. Une fenêtre contextuelle s’affiche, que vous pouvez utiliser pour afficher et partager des liens vers vos expériences AP sur votre site, afin d’obtenir un &quot;véritable aperçu&quot; des expériences en dehors de [!UICONTROL Cible]Compositeur d’expérience visuelle d’ . Vous devez partager les liens provenant du message pour partager l’aperçu. Le fait de cliquer sur un lien, puis de copier l’URL directement à partir du navigateur ne fonctionnera pas. Si vous copiez le lien, l’URL contient un paramètre qui affiche correctement la page uniquement lorsque vous accédez à la page à partir du lien contenu dans le message.

Pour plus d’informations sur la création de rapports, reportez-vous à la page [Rapports Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
