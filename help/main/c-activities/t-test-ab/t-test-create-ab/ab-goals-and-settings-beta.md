---
keywords: paramètres d’activité;objectifs et paramètres A/B;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectif;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur aura atteint cette mesure d’objectif;remarques
description: Découvrez comment utiliser la page [!UICONTROL Goals and Settings] pour définir les objectifs de l’activité A/B.
title: Comment spécifier les objectifs et les paramètres dans une activité A/B  [!DNL Target] ?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: aeafb4d8-a486-46cf-8871-4c220bc3674e
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 30%

---

# Objectifs et paramètres

La page [!UICONTROL Goals & Settings] de [!DNL Adobe Target] est l’endroit où vous spécifiez des informations sur les objectifs de l’activité.

Les paramètres disponibles dépendent si vous utilisez Target ou [Analytics comme source des rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La section [!UICONTROL Activity Settings] de la page [!UICONTROL Goals & Settings] vous permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Objective] | Saisissez une intention facultative. L’objectif peut être toute information qui vous aide, ainsi que les membres de votre équipe, à identifier l’activité. |
| [!UICONTROL Priority] | Selon vos paramètres, l’interface utilisateur de [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou vous pouvez activer les priorités affinées de 0 à 999.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Si cette option n&#39;est pas activée dans [!UICONTROL Administration] (valeur par défaut), spécifiez une priorité : [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].<P>Pour activer les [priorités affinées](/help/main/administrating-target/reporting.md), cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis activez l’option [!UICONTROL Enable Fine-Grained Priorities]. <P>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 : 0 = [!UICONTROL Low] et 999 = [!UICONTROL High]. <P>Pour les activités créées dans les versions précédentes de [!DNL Target], la priorité [!UICONTROL Low] est convertie en 0, [!UICONTROL Medium] en 5 et [!UICONTROL High] en 10. Vous pouvez ajuster ces valeurs si besoin.<P>Remarque : Avant de pouvoir désactiver cette option après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10. |
| [!UICONTROL Duration] | L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le. |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

La section [!UICONTROL Reporting Settings] de la page [!UICONTROL Goals & Settings] vous permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Reporting Source] | Spécifiez les données de solution à partir desquelles collecter :<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Si une source de création de rapports est spécifiée dans les [paramètres du compte](/help/main/administrating-target/reporting.md), la source spécifiée est utilisée et ce paramètre n’est pas visible.<P>Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour préserver la cohérence des rapports.<P>**Adobe Analytics** : voir [Adobe Analytics as the Reporting Source for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour en savoir plus sur les différences entre les solutions de création de rapports et les avantages de chacune d’elles. Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir les données d’activité [!DNL Target].<P>Pour spécifier une source de création de rapports, faites d’abord votre choix parmi les [!DNL Analytics] sociétés auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] peuvent être sélectionnées. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous reconnecter à [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez l’assistance clientèle.<P><P>**Adobe Customer Journey Analytics** : voir [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].<P>La création de rapports [!DNL Target] dans [!DNL Customer Journey Analytics] est prise en charge dans les activités A/B avec fractionnement manuel du trafic. [!UICONTROL Auto-Target] et [!UICONTROL Auto-Allocate] Les activités A/B ne peuvent pas utiliser le reporting [!DNL Target] dans [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure [!UICONTROL Conversion], puis définissez les paramètres qui déterminent le moment où la réussite est atteinte. Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Remarque : Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL Conversion]. Les mesures [!DNL Analytics] ne peuvent pas être sélectionnées en tant qu’objectif. Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.<P>S’il est activé, le champ [!UICONTROL Estimated Value of the Conversion] (indisponible pour les mesures [!UICONTROL Page Score]) fournit une valeur pour votre objectif, mais pas pour les autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] et [!UICONTROL Orders]), l’estimation utilise [!UICONTROL Revenue per Visitor]. Les données sont de type devise.<P>Après avoir atteint l’objectif de l’activité, un visiteur continue à voir le contenu de l’activité, sauf si le visiteur est admissible pour une activité de priorité plus élevée. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Il s’agit d’un comportement différent du comportement par défaut dans [!DNL Target Classic], qui a comptabilisé les visiteurs comme nouveaux s’ils voient à nouveau l’activité. |
| [!UICONTROL Additional Metrics] | Créez des mesures de succès supplémentaires. Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la suite de rapports [!DNL Analytics] sont appliquées. |
| [!UICONTROL Audiences for Reporting] | Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement des informations sur des audiences spécifiques. Ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] comme solution de création de rapports. L’audience définie pour la suite de rapports [!DNL Analytics] est appliquée. |

## Paramètres avancés  {#section_E2FE441AFB324E498793ABB025ED9974}

La section [!UICONTROL Advanced Settings] de la page [!UICONTROL Goals & Settings] vous permet de configurer les options avancées.

Pour spécifier des paramètres avancés, cliquez sur l&#39;icône **[!UICONTROL More]** ( ![Icône More](/help/main/assets/icons/MoreSmallList.svg) ) dans la section [!UICONTROL My Primary Goal] , puis cliquez sur **[!UICONTROL Advanced Settings]**.

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

Les options disponibles sont les suivantes :

| Paramètre | Description |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | Utilisez cette option pour comptabiliser une personne comme atteignant la mesure de succès uniquement si elle a déjà atteint une autre mesure de succès. Par exemple, une conversion d’activité peut uniquement être valide si le visiteur clique sur l’offre ou atteint une page spécifique avant la conversion. Vous pouvez définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente. Définissez les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre. L’option [!UICONTROL Add Dependency] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte. Pour ajouter une dépendance :<ul><li>Après avoir ajouté des mesures supplémentaires, cliquez sur [!UICONTROL Advanced Settings].</li><li>Cliquez sur l’option [!UICONTROL Add Dependency] :</li><li>Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur [!UICONTROL Reached] pour passer du paramètre [!UICONTROL Reached] à [!UICONTROL  Not Reached].</li><li>Vous pouvez modifier ou supprimer des dépendances après leur ajout.</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | Trois options sont disponibles :<ul><li>Sélectionnez **[!UICONTROL Increment Count & Keep User in Activity]** pour spécifier comment le nombre est incrémenté.</li><li>Sélectionnez **[!UICONTROL Increment Count, Release User & Allow Reentry]** pour spécifier l’expérience que l’utilisateur voit s’il entre à nouveau dans l’activité.</li><li>Sélectionnez **[!UICONTROL Increment Count, Release User & Bar from Reentry]** pour spécifier ce que l’utilisateur voit à la place du contenu de l’activité.</li></ul> |
| [!UICONTROL How will the count be incremented?] | Il existe trois options d’incrémentation du décompte :<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

La section [!UICONTROL Other Metadata] de la page [!UICONTROL Goals & Settings] vous permet de spécifier toute information utile sur votre activité afin de vous tenir à portée de main ou d’autres membres de l’équipe. Le volet Notes peut être redimensionné.|
