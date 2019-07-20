---
description: Sélectionnez une expérience à utiliser comme contrôle lors de la création d'une activité de personnalisation automatisée ou de ciblage automatique.
keywords: expérience ; contrôle ; la personnalisation automatisée ; ciblage automatique
seo-description: Sélectionnez une expérience à utiliser comme contrôle lors de la création d'une activité de personnalisation automatisée ou de ciblage automatique dans Adobe Target.
seo-title: Utilisation d'une expérience spécifique comme contrôle dans Adobe Target
solution: Target,Analytics
title: Utilisation d'une expérience spécifique comme contrôle
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![PREMIUM](/help/assets/premium.png) Sélectionnez le contrôle de votre activité de personnalisation automatisée ou de ciblage automatique.

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

Cette fonctionnalité vous permet d'acheminer le trafic de contrôle vers les expériences appropriées, en fonction du pourcentage d'affectation du trafic configuré dans l'activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle.

Les options permettant de définir un contrôle dans les activités AP et AT sont légèrement différentes des autres types d'activité. Dans un test A/B manuel, vous pouvez modifier les rapports affichés comme contrôle et l'effet élévateur est calculé en fonction du taux de conversion de cette expérience de contrôle. Vous pouvez faciliter cette modification car le trafic est affecté de manière aléatoire à chacune des expériences que vous avez incluses dans votre activité, quelle que soit la commande initialement définie. En d'autres termes, la sélection du contrôle n'a aucune incidence sur le mode de diffusion du trafic. Dans les activités AP et AT, votre décision sur les éléments à choisir a une incidence sur le mode de diffusion du trafic des visiteurs. Par conséquent, vous devez mieux réfléchir à votre décision.

Vous disposez de deux options pour votre contrôle dans vos activités AP et AT : expériences servies de manière aléatoire ou une expérience spécifique.

* **Diffusé de manière aléatoire**: Pour un contrôle aléatoire, le pourcentage de contrôle du trafic diffuse de manière aléatoire toutes les expériences de l'activité, sans tenir compte du profil du visiteur. Vous pouvez penser au contrôle pour répondre à la question : « Si je propose simplement une expérience (ou offre) aux visiteurs et qu'ils ne tiennent pas compte de leurs profils, quel est le taux de conversion de cette expérience (ou offre) ?  » » Le contrôle est semblable à un test A/B dans votre activité AI. Il peut s'avérer utile d'avoir ces informations du taux de conversion non personnalisé pour chaque expérience ou offre afin de comprendre à quel moment analyser les résultats de votre activité.

* **Expérience spécifique**: Un contrôle d'expérience spécifique permet de comparer le trafic diffusé par les modèles de personnalisation de Target à une expérience spécifique définie par le spécialiste du marketing (par exemple, votre page d'accueil par défaut). Avec cette option, le pourcentage de contrôle du trafic diffuse le trafic de manière aléatoire pour cette seule expérience.

## Définition d'une expérience spécifique comme contrôle

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. Spécifiez l'affectation de trafic souhaitée pour l'expérience de contrôle et les autres expériences.

   Pour un contrôle d'expérience spécifique, 10 à 30 % sont conseillés.

1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## Limites et considérations connues

Tenez compte des points suivants lorsque vous utilisez une expérience spécifique comme contrôle :

* Il n'est pas conseillé de modifier l'expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports (même si les anciens rapports reposent sur une autre expérience).
* Il n'est pas conseillé de supprimer l'expérience de contrôle.
* Il n'est pas conseillé d'ajouter un grand nombre d'offres/d'expériences à une activité en direct avec une expérience spécifique lorsque le contrôle est déconseillé.
* Dans les activités AP, notamment le ciblage sur l'expérience de contrôle qui pourrait contraindre davantage la personne qui peut voir cette expérience non conseillée.
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. Les informations d'effet élévateur et de confiance sont disponibles au niveau global de trafic « ciblé » ou « contrôle » pour l'activité AP. Les informations d'effet élévateur et de confiance sont disponibles si « aléatoire » est sélectionné comme contrôle. Cette différence est due au fait que la comparaison du taux de conversion d'une expérience spécifique vers le taux de conversion d'une offre n'est pas logique en raison de la différence d'unités. Les informations disponibles dans une activité AT sont les mêmes, quel que soit le type de contrôle sélectionné.
* Etant donné que le trafic de contrôle passe à une expérience unique ou à une série d'offres lorsque vous sélectionnez l'expérience comme contrôle (par rapport à aléatoire, où le montant du trafic de contrôle est fractionné sur le nombre d'expériences ou d'offres dans votre activité), il n'est généralement pas nécessaire d'utiliser autant de trafic pour effectuer un flux vers le contrôle. 10 % est un bon point de départ.
* Si vous effectuez l'une des activités suivantes pour une activité en direct avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l'expérience spécifique précédemment sélectionnée) :

   * Suppression d'une expérience
   * Suppression d'un emplacement ou d'une offre (AP uniquement)
   * Exclure une expérience manuellement, en supprimant les offres en double ou via un groupe d'exclusion (AP uniquement)

