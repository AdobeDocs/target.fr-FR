---
keywords: paramètres d’activité;objectifs et paramètres A/B;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectif;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur aura atteint cette mesure d’objectif;remarques
description: Découvrez comment utiliser le [!UICONTROL Objectifs et paramètres] page [!DNL Adobe Target] pour spécifier des informations sur les objectifs d’une activité A/B.
title: Comment spécifier les objectifs et les paramètres dans une [!DNL Target] Activité A/B ?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 53%

---

# Objectifs et paramètres

La variable [!UICONTROL Objectifs et paramètres] page [!DNL Adobe Target] est l’emplacement où vous spécifiez des informations sur les objectifs de l’activité.

Les paramètres disponibles dépendent si vous utilisez Target ou [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) comme source des rapports.

## [!UICONTROL Paramètres d’activité] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La variable [!UICONTROL Paramètres d’activité] de la [!UICONTROL Objectifs et paramètres] vous permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Intention] | Saisissez une intention facultative. L’objectif peut être toute information qui vous aide, ainsi que les membres de votre équipe, à identifier l’activité. |
| [!UICONTROL Priorité] | Selon vos paramètres, la variable [!DNL Target] Interface utilisateur et options pour [!UICONTROL Priorité] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Faible], [!UICONTROL Volume moyen], ou [!UICONTROL Élevée]ou vous pouvez activer les priorités affinées de 0 à 999.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Si cette option n’est pas activée dans [!UICONTROL Administration] (valeur par défaut), spécifiez une priorité : [!UICONTROL Faible], [!UICONTROL Volume moyen], ou [!UICONTROL Élevée].<P>Pour activer [priorités affinées](/help/main/administrating-target/reporting.md), cliquez sur [!UICONTROL Administration] > [!UICONTROL Reporting], puis faites basculer le [!UICONTROL Activation des priorités affinées] à la position &quot;Activé&quot;. <P>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 : 0 = [!UICONTROL Faible] et 999 = [!UICONTROL Élevée]. <P>Pour les activités créées dans les versions précédentes de [!DNL Target], [!UICONTROL Faible] La priorité est convertie en 0, [!UICONTROL Volume moyen] est converti en 5 et [!UICONTROL Élevée] est converti en 10. Vous pouvez ajuster ces valeurs si besoin.<P>Remarque : avant de pouvoir désactiver cette option, après avoir utilisé les priorités affinées, toutes les priorités doivent être reconfigurées sur 0, 5 et 10. |
| Durée | L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le. |

## [!UICONTROL Paramètres de création de rapports] {#section_13119392051044FBA6387D9B3B1C43CF}

La variable [!UICONTROL Paramètres de création de rapports] de la [!UICONTROL Objectifs et paramètres] vous permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Source de création de rapports] | Spécifier la collecte des données [!DNL Adobe Target] ou de [!DNL Adobe Analytics]. Voir [Adobe Analytics en tant que source de création de rapports pour Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour découvrir les différences entre les solutions de création de rapports et les avantages de chacune. Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour [!DNL Target], vous sélectionnez une [!DNL Analytics] suite de rapports à recevoir [!DNL Target] données d’activité.<P>Pour spécifier une source de création de rapports, faites d’abord votre choix parmi les options suivantes : [!DNL Analytics] société à laquelle votre compte est lié, puis sélectionnez la suite de rapports appropriée à l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] sont disponibles pour sélection. Si vous ne voyez pas les suites de rapports attendues, essayez d’abord de vous déconnecter et de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports n’apparaît toujours pas dans la liste, contactez l’assistance clientèle.<P>Si une source de création de rapports est spécifiée dans les paramètres de votre compte, la source spécifiée est utilisée et ce paramètre n’est pas visible.<P>Remarque : Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour préserver la cohérence des rapports. |
| [!UICONTROL Mesure de l’objectif] | Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez un [!UICONTROL Conversion] , puis définissez les paramètres qui déterminent le moment où la réussite est atteinte. Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Remarque : Si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL Conversion]. [!DNL Analytics] ne peuvent pas être sélectionnées en tant qu’objectif. Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.<P>Si cette option est activée, la variable [!UICONTROL Valeur estimée de la conversion] (non disponible pour le champ [!UICONTROL Score de page] (mesures) fournit une valeur pour votre objectif, mais pas pour les autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de recettes ([!UICONTROL Recettes par visiteur], [!UICONTROL Valeur de commande moyenne], [!UICONTROL Total ventes], et [!UICONTROL Commandes]), l’estimation utilise [!UICONTROL Recettes par visiteur]. Les données sont de type devise.<P>Après avoir atteint l’objectif de l’activité, un visiteur continue à voir le contenu de l’activité, sauf si le visiteur est admissible pour une activité de priorité plus élevée. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Cela diffère du comportement par défaut dans [!DNL Target Classic], qui comptabilise les visiteurs comme nouveaux s’ils voient à nouveau l’activité. |
| [!UICONTROL Mesures supplémentaires] | Créez des mesures de succès supplémentaires. Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la variable [!DNL Analytics] suite de rapports sont appliquées. |
| [!UICONTROL Audiences pour les rapports] | Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences aux rapports pour afficher uniquement des informations sur des audiences spécifiques. Ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] en tant que solution de création de rapports. L’audience définie pour la variable [!DNL Analytics] suite de rapports est appliquée. |

## Paramètres avancés  {#section_E2FE441AFB324E498793ABB025ED9974}

La variable [!UICONTROL Paramètres avancés] de la [!UICONTROL Objectifs et paramètres] vous permet de configurer les options suivantes :

Pour définir les paramètres avancés, cliquez sur le bouton **[!UICONTROL Plus]** (points de suspension verticaux), puis cliquez sur **[!UICONTROL Paramètres avancés]**, comme illustré ci-dessous.

![Menu Paramètres avancés](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

![Paramètres avancés](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Paramètre | Description |
|--- |--- |
| [!UICONTROL Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ?] | Utilisez cette option pour comptabiliser une personne comme atteignant la mesure de succès uniquement si elle a déjà atteint une autre mesure de succès. Par exemple, une conversion d’activité peut uniquement être valide si le visiteur clique sur l’offre ou atteint une page spécifique avant la conversion. Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente. Définissez les deux (ou plus) mesures de succès avant de les rendre dépendantes l’une de l’autre. L’option [!UICONTROL Ajouter une dépendance] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte. Pour ajouter une dépendance :<ul><li>Après l’ajout de mesures supplémentaires, cliquez sur [!UICONTROL Paramètres avancés].</li><li>Cliquez sur l’option [!UICONTROL Ajouter une dépendance] :</li><li>Faites glisser les mesures souhaitées depuis le panneau de gauche vers le panneau de droite, puis cliquez sur [!UICONTROL Atteinte] pour passer du paramètre [!UICONTROL Atteinte] au paramètre [!UICONTROL Non atteinte].</li><li>Vous pouvez modifier ou supprimer des dépendances après leur ajout.</li></ul> |
| [!UICONTROL Que se passe-t-il une fois qu’un utilisateur atteint cette mesure d’objectif ?] | Trois options sont disponibles :<ul><li>Sélectionnez [!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité] pour spécifier comment le décompte est incrémenté.</li><li>Sélectionnez [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et autoriser le retour] pour spécifier quelle expérience affiche l’utilisateur s’il rentre dans l’activité.</li><li>Sélectionnez [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et bloquer le retour] pour spécifier ce qu’affiche l’utilisateur à la place du contenu de l’activité.</li></ul> |
| [!UICONTROL Comment sera incrémenté le décompte ?] | Il existe trois options d’incrémentation du décompte :<ul><li>[!UICONTROL Une fois par participant]</li><li>[!UICONTROL À chaque impression (actualisations de page exclues)]</li><li>[!UICONTROL À chaque impression]</li></ul> |

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

La variable [!UICONTROL Autres métadonnées] de la [!UICONTROL Objectifs et paramètres] vous permet de spécifier toute information utile sur votre activité afin de vous tenir à l’écoute des autres membres de l’équipe. Le volet Notes peut être redimensionné.|

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Paramètres d’activité (3:02) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

(https://video.tv.adobe.com/v/17381?captions=fre-fr)

### Création de tests A/B (8:36) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo présente la façon dont les paramètres d’activité s’intègrent dans le workflow guidé en trois étapes lors de la création d’une activité. Les objectifs et les paramètres sont abordés à partir de 05:30.

* Créer une activité A/B dans Adobe Target
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)
