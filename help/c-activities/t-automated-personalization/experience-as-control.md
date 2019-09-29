---
description: Sélection d’une expérience à utiliser en tant que contrôle lors de la création d’une Automated Personalization (Personnalisation automatisée) ou d’une activité de ciblage automatique.
keywords: expérience;contrôle;personnalisation automatisée;ciblage automatique
seo-description: Sélection d’une expérience à utiliser comme contrôle lors de la création d’une activité Automated Personalization (Personnalisation automatisée) ou de ciblage automatique dans Adobe Target.
seo-title: Utilisation d’une expérience spécifique comme contrôle dans Adobe Target
solution: Target,Analytics
title: Utilisation d’une expérience spécifique comme contrôle
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![PREMIUM](/help/assets/premium.png) Sélection du contrôle de votre activité Automated Personalization ou de ciblage automatique

Vous pouvez sélectionner une expérience diffusée de manière aléatoire ou une expérience spécifique à utiliser comme contrôle lors de la création d’une activité [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [ciblage automatique](/help/c-activities/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer le trafic de contrôle vers les expériences spécifiques, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers ce contrôle.

Les options permettant de définir un contrôle dans les activités AP et AT sont légèrement différentes des autres types d’activité. Dans un test A/B manuel, vous pouvez modifier les rapports qui s’affichent comme votre contrôle, et l’effet élévateur est calculé en fonction du taux de conversion de cette expérience de contrôle. Vous pouvez effectuer facilement cette modification car le trafic est diffusé de manière aléatoire à chacune des expériences que vous avez incluses dans votre activité, quelle que soit la commande initialement définie. En d’autres termes, la sélection du contrôle n’a aucune incidence sur le mode de diffusion du trafic. Dans les activités AP et AT, le choix de votre contrôle a une incidence sur le mode de diffusion du trafic des visiteurs. Par conséquent, votre décision doit être plus réfléchie.

Vous disposez de deux options pour votre contrôle dans vos activités AP et AT : expériences diffusées de manière aléatoire ou expérience spécifique.

* **Diffusée de manière aléatoire** : Pour un contrôle aléatoire, le pourcentage de contrôle du trafic est diffusé de manière aléatoire dans toutes les expériences de l’activité, sans tenir compte du profil du visiteur. Il est utile de considérer le contrôle comme la réponse à la question : « Si je diffuse simplement une expérience (ou offre) aux visiteurs sans tenir compte de leurs profils, quel est le taux de conversion de cette expérience (ou offre) ? » Le contrôle est semblable à un test A/B dans votre activité AI. Il peut s’avérer utile d’avoir ces informations sur le taux de conversion non personnalisé pour chaque expérience ou offre, afin de comprendre à quel moment analyser les résultats de votre activité.

* **Expérience spécifique** : Un contrôle d’expérience spécifique permet de comparer le trafic diffusé par les modèles de personnalisation de Target à une expérience spécifique définie par le spécialiste du ’ (par exemple, votre page d’accueil par défaut). Avec cette option, le pourcentage de contrôle du trafic est diffusé de manière aléatoire au trafic pour cette seule expérience.

## Définition d’une expérience spécifique comme contrôle

1. Lors de la création d’une [activité AP](/help/c-activities/t-automated-personalization/create-ap-activity.md) ou d’une [activité AT](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configurez les expériences selon vos besoins.
1. Sur la page [!UICONTROL Ciblage] (étape 2 du workflow assisté en trois parties), sélectionnez l’expérience souhaitée comme contrôle.
1. Spécifiez l’affectation de trafic souhaitée pour l’expérience de contrôle et les autres expériences.

   Pour un contrôle d’expérience spécifique, 10 à 30 % sont conseillés.

1. Passez à la page [!UICONTROL Objectifs et paramètres].

## Limites et considérations connues

Tenez compte des éléments suivants lorsque vous utilisez une expérience spécifique comme contrôle :

* Il n’est pas conseillé de modifier l’expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports (même si les anciens rapports sont basés sur une autre expérience).
* Il n’est pas conseillé de supprimer l’expérience de contrôle.
* Il n’est pas conseillé d’ajouter un grand nombre d’offres/d’expériences à une activité en direct avec une expérience spécifique comme contrôle est déconseillé.
* Dans les activités AP, il n’est pas conseillé d’inclure un ciblage sur l’expérience de contrôle qui pourrait limiter davantage le nombre de profils qui peuvent voir l’expérience.
* Dans les activités AP, les informations sur l’effet élévateur et la confiance ne sont *PAS* disponibles dans le rapport au niveau de l’offre si une expérience spécifique est sélectionnée. Les informations sur l’effet élévateur et la confiance sont disponibles au niveau global de trafic « ciblé » ou « contrôle » pour l’activité AP. Les informations sur l’effet élévateur et la confiance sont disponibles si « aléatoire » est sélectionné comme contrôle. Cette différence est due au fait que la comparaison du taux de conversion d’une expérience spécifique vers le taux de conversion d’une offre n’est pas logique en raison de la différence d’unités. Les informations disponibles dans une activité AT sont les mêmes, quel que soit le type de contrôle sélectionné.
* Étant donné que le trafic de contrôle est dirigé vers une seule expérience ou un seul ensemble d’offres lorsque vous sélectionnez l’expérience comme contrôle (par rapport à aléatoire, où le montant du trafic de contrôle est fractionné en fonction du nombre d’expériences ou d’offres dans votre activité), il n’est généralement pas nécessaire d’utiliser autant de trafic pour effectuer un flux vers le contrôle. 10 % est un bon point de départ.
* Si vous effectuez l’une des activités suivantes pour une activité en direct avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l’expérience spécifique précédemment sélectionnée) :

   * Suppression d’une expérience
   * Suppression d’un emplacement ou d’une offre (AP uniquement)
   * Exclusion manuelle d’une expérience, en supprimant les offres en double ou via un groupe d’exclusion (AP uniquement)

