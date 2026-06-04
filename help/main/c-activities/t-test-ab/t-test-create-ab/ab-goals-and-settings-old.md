---
keywords: paramètres d’activité;objectifs et paramètres A/B;paramètres de création de rapports;mesures des objectifs;mesures de réussite;mesures de réussite dépendantes;paramètres avancés;objectif principal;mesures supplémentaires;objectif;priorité;durée;solution de création de rapports;objectif;audiences pour la création de rapports;Quelle mesure de réussite doit être atteinte avant d’incrémenter cette mesure;Que se passera-t-il quand un utilisateur aura atteint cette mesure d’objectif;remarques
description: Découvrez comment utiliser la page [!UICONTROL &#x200B; Objectifs et paramètres &#x200B;] pour spécifier des informations sur les objectifs d’une activité A/B.
title: Comment spécifier les objectifs et les paramètres dans une activité a [!DNL Target] A/B ?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '1411'
ht-degree: 37%

---

# Objectifs et paramètres

La page [!UICONTROL Objectifs et paramètres] de [!DNL Adobe Target] vous permet de spécifier des informations sur les objectifs de l’activité.

Les paramètres disponibles varient selon que vous utilisez Target ou [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) comme source de création de rapports.

## [!UICONTROL Paramètres d’activité] {#section_DCBDC354261F420EBD4B43EA34947BAC}

La section [!UICONTROL Paramètres d’activité] de la page [!UICONTROL Objectifs et paramètres] permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Objectif &#x200B;] | Saisissez une intention facultative. L’objectif peut être toute information qui vous aide, vous et les membres de votre équipe, à identifier l’activité. |
| [!UICONTROL Priorité] | Selon vos paramètres, l’interface utilisateur [!DNL Target] et les options de [!UICONTROL Priorité] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Faible], [!UICONTROL Medium] ou [!UICONTROL Élevé], ou activer des priorités affinées de 0 à 999.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Si cette option n’est pas activée dans [!UICONTROL Administration] (valeur par défaut), spécifiez une priorité : [!UICONTROL Faible], [!UICONTROL Medium] ou [!UICONTROL Élevée].<P>Pour activer [priorités affinées](/help/main/administrating-target/reporting.md), cliquez sur [!UICONTROL Administration] > [!UICONTROL Rapports], puis activez l’option [!UICONTROL Activer les priorités affinées] à la position « Activé ». <P>Si cette option est activée, spécifiez une valeur comprise entre 0 et 999 : 0 = [!UICONTROL Faible] et 999 = [!UICONTROL Élevée]. <P>Pour les activités créées dans les versions précédentes d’[!DNL Target], la priorité [!UICONTROL Faible] est convertie en 0, la priorité [!UICONTROL Medium] est convertie en 5 et la priorité [!UICONTROL Élevée] est convertie en 10. Vous pouvez ajuster ces valeurs si besoin.<P>Remarque : avant de pouvoir désactiver cette option après l’utilisation de priorités affinées, toutes les priorités doivent être définies sur 0, 5 et 10. |
| Durée | L’activité peut démarrer lorsqu’elle est approuvée. Vous pouvez également définir une date et une heure de début spécifiques. De même, l’activité peut s’arrêter lorsqu’elle est désactivée ou selon la date et l’heure de fin que vous spécifiez. Le sélecteur d’heure utilise une horloge de 24 heures, 00:00 correspondant à minuit. Le fuseau horaire est défini sur celui configuré dans votre navigateur. Pour en utiliser un autre, définissez votre navigateur sur un fuseau horaire différent, puis redémarrez-le. |

## [!UICONTROL Paramètres de création de rapports] {#section_13119392051044FBA6387D9B3B1C43CF}

La section [!UICONTROL Paramètres de création de rapports] de la page [!UICONTROL Objectifs et paramètres] permet de configurer les options suivantes :

| Paramètres | Description |
|--- |--- |
| [!UICONTROL Reporting Source] | Indiquez à partir de quelle solution les données sont collectées :<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Si une source de création de rapports est spécifiée dans les paramètres de votre [compte](/help/main/administrating-target/reporting.md), la source spécifiée est utilisée et ce paramètre n’est pas visible.<P>Vous ne pouvez pas modifier votre source de création de rapports une fois l’activité activée pour conserver la cohérence des rapports.<P>**Adobe Analytics** : consultez la section [Adobe Analytics en tant que Source de création de rapports pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour en savoir plus sur les différences entre les solutions de création de rapports et les avantages de chacune d’elles. Lorsque vous sélectionnez [!DNL Analytics] comme source de création de rapports pour les [!DNL Target], vous sélectionnez une suite de rapports [!DNL Analytics] pour recevoir des données d’activité [!DNL Target].<P>Pour spécifier une source de création de rapports, choisissez d’abord l’une des sociétés [!DNL Analytics] auxquelles votre compte est lié, puis sélectionnez la suite de rapports appropriée pour l’activité. Seules les suites de rapports configurées pour se connecter à [!DNL Adobe Target] peuvent être sélectionnées. Si les suites de rapports attendues ne s’affichent pas, essayez d’abord de vous déconnecter puis de vous reconnecter au [!DNL Adobe Experience Cloud] pour réessayer. Si la suite de rapports est toujours absente de la liste, contactez l’assistance clientèle.<P><P>**&#x200B;** : voir [[!DNL Target] création de rapports dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].<P>Les rapports [!DNL Target] dans [!DNL Customer Journey Analytics] sont pris en charge dans les activités A/B avec fractionnement manuel du trafic. Les activités A/B [!UICONTROL Ciblage automatique] et [!UICONTROL Affectation automatique] ne peuvent pas utiliser les rapports [!DNL Target] dans [!DNL Customer Journey Analytics]. |
| [!UICONTROL Mesure d’objectif] | Sélectionnez l’action entreprise par un visiteur pour atteindre l’objectif. Par exemple, choisissez une mesure [!UICONTROL Conversion], puis définissez les paramètres qui déterminent le moment où la réussite est atteinte. Pour plus d’informations sur le paramétrage des mesures, voir [Paramétrage des mesures](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Remarque : si la solution de création de rapports est définie sur [!DNL Analytics], la seule mesure d’objectif disponible est [!UICONTROL &#x200B; Conversion]. [!DNL Analytics] mesures ne peuvent pas être sélectionnées en tant qu’objectif. Lorsque vous sélectionnez votre mesure de succès, un sélecteur s’affiche. Utilisez ce sélecteur pour sélectionner les détails de la mesure de succès.<P>Si cette option est activée, le champ [!UICONTROL Valeur estimée de la conversion] (non disponible pour les mesures [!UICONTROL Score de page]) fournit une valeur pour votre objectif, mais pas pour d’autres mesures. Cette valeur permet à [!DNL Target] de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Pour toutes les mesures de chiffre d’affaires ([!UICONTROL Chiffre d’affaires par visiteur], [!UICONTROL Valeur moyenne de la commande], [!UICONTROL Total des ventes] et [!UICONTROL Commandes]), l’estimation utilise [!UICONTROL Chiffre d’affaires par visiteur]. Les données sont de type devise.<P>Une fois l’objectif d’activité atteint, le visiteur continue à voir le contenu de l’activité, sauf s’il est qualifié pour une activité prioritaire. Si le visiteur atteint à nouveau l’objectif, il est comptabilisé en tant que nouvelle conversion. Ce comportement est différent du comportement par défaut dans [!DNL Target Classic], qui comptabilise les visiteurs comme nouveaux s’ils voient à nouveau l’activité. |
| [!UICONTROL Mesures supplémentaires] | Créez des mesures de succès supplémentaires. Ce paramètre n’est pas disponible si la solution de création de rapports est définie sur [!DNL Analytics]. Dans ce cas, les mesures définies pour la suite de rapports [!DNL Analytics] sont appliquées. |
| [!UICONTROL Audiences pour le reporting] | Par défaut, les rapports présentent les résultats pour tous les visiteurs qualifiés. Vous pouvez ajouter des audiences de rapport pour afficher des informations sur des audiences spécifiques uniquement. Ce paramètre n’est pas disponible si vous choisissez [!DNL Analytics] comme solution de création de rapports. L’audience définie pour la suite de rapports [!DNL Analytics] est appliquée. |

## Paramètres avancés {#section_E2FE441AFB324E498793ABB025ED9974}

La section [!UICONTROL Paramètres avancés] de la page [!UICONTROL Objectifs et paramètres] permet de configurer les options suivantes :

Pour spécifier des paramètres avancés, cliquez sur l’icône **[!UICONTROL Plus]** (les points de suspension verticaux), puis sur **[!UICONTROL Paramètres avancés]**, comme illustré ci-dessous.

![Menu Paramètres avancés](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Si vous utilisez [!DNL Adobe Analytics] en tant que source de reporting, les paramètres sont gérés par le serveur [!DNL Analytics]. L’option Paramètres avancés n’est pas disponible.

![Paramètres avancés](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Paramètre | Description |
|--- |--- |
| [!UICONTROL Quelle mesure de succès doit être atteinte avant d’incrémenter cette mesure ?] | Utilisez cette option pour comptabiliser une personne comme ayant atteint la mesure de succès uniquement si elle a précédemment atteint une autre mesure de succès. Par exemple, une conversion d’activité peut n’être valide que si le visiteur clique sur l’offre ou atteint une page particulière avant la conversion. Vous avez la possibilité de définir une dépendance sur plusieurs mesures et choisir si la mesure doit être atteinte ou non pour que le décompte augmente. Définissez les deux mesures de succès (ou plusieurs) avant de pouvoir rendre l’une dépendante de l’autre. L’option [!UICONTROL Ajouter une dépendance] permet à la mesure de succès de s’incrémenter si une autre mesure de succès a été atteinte ou n’a pas été atteinte. Pour ajouter une dépendance :<ul><li>Après l’ajout de mesures supplémentaires, cliquez sur [!UICONTROL Paramètres avancés].</li><li>Cliquez sur l’option [!UICONTROL Ajouter une dépendance] :</li><li>Faites glisser et déposez les mesures de votre choix depuis le volet de gauche vers le volet de droite, puis cliquez sur [!UICONTROL Atteint] pour basculer le paramètre entre [!UICONTROL Atteint] et [!UICONTROL &#x200B; Non atteint].</li><li>Vous pouvez modifier ou supprimer des dépendances après leur ajout.</li></ul> |
| [!UICONTROL Que se passera-t-il lorsqu’un utilisateur rencontrera cette mesure d’objectif ?] | Trois options sont disponibles :<ul><li>Sélectionnez [!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité] pour spécifier comment le décompte est incrémenté.</li><li>Sélectionnez [!UICONTROL Incrémenter le décompte, libérer l’utilisateur et autoriser le retour] pour spécifier quelle expérience affiche l’utilisateur s’il rentre dans l’activité.</li><li>Sélectionnez [!UICONTROL Incrémenter le décompte, Libérer l’utilisateur et la barre de la rentrée] pour spécifier ce que l’utilisateur voit au lieu du contenu de l’activité.</li></ul> |
| [!UICONTROL Comment le décompte sera-t-il incrémenté ?] | Il existe trois options d’incrémentation du décompte :<ul><li>[!UICONTROL Une fois par participant]</li><li>[!UICONTROL À chaque impression (à l’exclusion des actualisations de page)]</li><li>[!UICONTROL À Chaque Impression]</li></ul> |

Reportez-vous à [Mesures de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) pour plus d’informations sur les paramètres avancés.

## Autres métadonnées {#section_2E8917BEFB954480A4206B9E9E917F80}

La section [!UICONTROL Autres métadonnées] de la page [!UICONTROL Objectifs et paramètres] vous permet de spécifier toute information utile à garder à portée de main pour vous-même ou d’autres membres de l’équipe. Le volet Notes peut être redimensionné.|

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Paramètres d’activité (3:02) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

(https://video.tv.adobe.com/v/17381?captions=fre-fr)

### Création de tests A/B (8:36) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo présente la façon dont les paramètres d’activité s’intègrent dans le workflow guidé en trois étapes lors de la création d’une activité. Les objectifs et les paramètres sont discutés à partir de 5 :30.

* Créer une activité A/B dans Adobe Target
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/29261?captions=fre_fr)
