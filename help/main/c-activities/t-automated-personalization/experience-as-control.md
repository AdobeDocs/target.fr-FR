---
keywords: expérience;contrôle;personnalisation automatisée;ciblage automatique
description: Découvrez comment sélectionner une expérience à utiliser comme contrôle lors de la création d’une activité de [!UICONTROL Automated Personalization] (AP) ou de [!UICONTROL Auto-Target] dans  [!DNL Adobe Target].
title: Comment puis-je utiliser une expérience spécifique en tant que contrôle dans une activité [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 39%

---

# Sélection du contrôle de votre activité [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]

Vous pouvez sélectionner une expérience diffusée de manière aléatoire ou une expérience spécifique à utiliser comme contrôle lors de la création d’une activité [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer le trafic de contrôle vers les expériences spécifiques, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers ce contrôle.

Les options permettant de définir un contrôle dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target] sont un peu différentes des autres types d’activités. Dans une [!UICONTROL A/B Test] manuelle, vous pouvez modifier ce que les rapports indiquent comme contrôle et l’effet élévateur est calculé en fonction du taux de conversion de cette expérience de contrôle. Vous pouvez effectuer facilement cette modification car le trafic est diffusé de manière aléatoire à chacune des expériences que vous avez incluses dans votre activité, quelle que soit la commande initialement définie. En d’autres termes, la sélection du contrôle n’a aucune incidence sur la manière dont le trafic est diffusé. Dans les activités [!UICONTROL Automated Personalization] et [!UICONTROL Auto-Target], votre décision sur ce que vous devez choisir en tant que contrôle a une incidence sur la manière dont le trafic des visiteurs est diffusé. Par conséquent, vous devez réfléchir plus attentivement à votre décision.

Deux options permettent de contrôler vos activités de [!UICONTROL Automated Personalization] et de [!UICONTROL Auto-Target] :

* **Diffusion aléatoire** : pour un contrôle aléatoire, le pourcentage de contrôle du trafic diffuse aléatoirement toutes les expériences de l’activité, sans tenir compte du profil du visiteur. Vous pouvez considérer le contrôle comme une réponse à la question « Si je diffuse simplement une expérience (ou une offre) de manière aléatoire aux visiteurs et visiteuses et que je ne prends pas en compte leurs profils, quel est le taux de conversion de cette expérience (ou offre) ? » Le contrôle est semblable à un [!UICONTROL A/B Test] dans votre activité d’IA. Il peut s’avérer utile d’avoir ces informations sur le taux de conversion non personnalisé pour chaque expérience ou offre, afin de comprendre à quel moment analyser les résultats de votre activité.

* **Expérience spécifique** : un contrôle d’expérience spécifique vous permet de comparer le trafic généré par [!DNL Target] modèles de personnalisation à une expérience spécifique définie par le spécialiste marketing (par exemple, votre page d’accueil par défaut). Avec cette option, le pourcentage de contrôle du trafic est diffusé de manière aléatoire au trafic pour cette seule expérience.

## Définition d’une expérience spécifique comme contrôle

1. Lors de la création ou de la modification d’une activité de [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ou d’[[!UICONTROL Auto-Target] activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configurez les expériences selon vos besoins.
1. Sur la page [!UICONTROL Targeting] (étape 2 du workflow en trois parties), cliquez sur l’expérience de contrôle pour afficher [!UICONTROL Control] options dans le volet de droite.

   ![Panneau de contrôle](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Dans la liste déroulante [!UICONTROL Control] , sélectionnez [!UICONTROL Random Experience] ou sélectionnez l’expérience souhaitée que vous souhaitez utiliser pour le contrôle.

1. Cliquez sur le contrôle de [!UICONTROL Traffic Allocation], puis spécifiez l’affectation du trafic souhaitée pour l’expérience de contrôle et les autres expériences.

   ![Rail d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   Pour un contrôle d’expérience spécifique, 10 à 30 % sont conseillés.

1. Continuez avec la page [!UICONTROL Goals & Settings].

## Limites et considérations connues

Gardez les points suivants à l’esprit lors de l’utilisation d’une expérience spécifique comme contrôle :

* Il n’est pas conseillé de modifier l’expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports (même si les anciens rapports sont basés sur une autre expérience).
* Il n’est pas conseillé de supprimer l’expérience de contrôle.
* Il est déconseillé d’ajouter de nombreuses nouvelles offres ou expériences à une activité en direct avec une expérience spécifique, car le contrôle n’est pas conseillé.
* Dans les activités [!UICONTROL Automated Personalization], il n’est pas conseillé de cibler l’expérience de contrôle afin de contraindre davantage les personnes pouvant voir cette expérience.
* Dans [!UICONTROL Automated Personalization] activités, les informations sur l’effet élévateur et le degré de confiance ne sont *PAS* disponibles dans le rapport au niveau de l’offre si une expérience spécifique est sélectionnée. Les informations d’effet élévateur et de confiance sont disponibles au niveau du trafic global « ciblé » par rapport au niveau du trafic de « contrôle » pour l’activité [!UICONTROL Automated Personalization]. Les informations sur l’effet élévateur et la confiance sont disponibles si « aléatoire » est sélectionné comme contrôle. Cette différence est due au fait que la comparaison du taux de conversion d’une expérience spécifique vers le taux de conversion d’une offre n’est pas logique en raison de la différence d’unités. Les informations disponibles dans une activité [!UICONTROL Auto-Target] sont les mêmes, quel que soit le type de contrôle sélectionné.
* Étant donné que le trafic de contrôle est dirigé vers une seule expérience ou un seul ensemble d’offres lorsque vous sélectionnez l’expérience comme contrôle (par rapport à aléatoire, où le montant du trafic de contrôle est fractionné en fonction du nombre d’expériences ou d’offres dans votre activité), il n’est généralement pas nécessaire d’utiliser autant de trafic pour effectuer un flux vers le contrôle. 10 % est un bon point de départ.
* Si vous effectuez l’une des activités suivantes pour une activité en direct avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l’expérience spécifique précédemment sélectionnée) :

   * Suppression d’une expérience
   * Supprimer un emplacement ou une offre ([!UICONTROL Automated Personalization] uniquement)
   * Exclure une expérience manuellement, par le biais de la suppression des offres en double ou d’un groupe d’exclusion ([!UICONTROL Automated Personalization] uniquement)
