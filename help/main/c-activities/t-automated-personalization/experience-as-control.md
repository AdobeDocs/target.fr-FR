---
keywords: expérience;contrôle;personnalisation automatisée;ciblage automatique
description: Découvrez comment sélectionner une expérience à utiliser comme contrôle lors de la création d’une [!UICONTROL Automated Personalization] (AP) ou [!UICONTROL Ciblage automatique] activité dans [!DNL Adobe Target].
title: Comment utiliser une expérience spécifique comme contrôle dans une [!UICONTROL Automated Personalization] Activité ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 29f8c19e24443e84b8d900f630495d163530f80e
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 42%

---

# Sélectionnez le contrôle correspondant à votre [!UICONTROL Automated Personalization] ou [!UICONTROL Ciblage automatique] activité

Vous pouvez sélectionner une expérience diffusée de manière aléatoire ou une expérience spécifique à utiliser comme contrôle lors de la création d’une [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [[!UICONTROL Ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) .

Cette fonctionnalité vous permet d’acheminer le trafic de contrôle vers les expériences spécifiques, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers ce contrôle.

Options de définition d’un contrôle dans [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] Les activités sont légèrement différentes des autres types d’activité. Dans un manuel [!UICONTROL Test A/B], vous pouvez modifier ce que le rapport indique comme votre contrôle et l’effet élévateur est calculé en fonction du taux de conversion de cette expérience de contrôle. Vous pouvez effectuer facilement cette modification car le trafic est diffusé de manière aléatoire à chacune des expériences que vous avez incluses dans votre activité, quelle que soit la commande initialement définie. En d’autres termes, la sélection du contrôle n’a aucune incidence sur le mode de diffusion du trafic. Dans [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités, votre décision sur ce que vous choisissez comme contrôle a un impact sur la manière dont le trafic des visiteurs est traité. Par conséquent, vous devez réfléchir plus attentivement à votre décision.

Deux options sont disponibles pour votre contrôle dans votre [!UICONTROL Automated Personalization] et [!UICONTROL Ciblage automatique] activités :

* **Diffusé de manière aléatoire**: pour un contrôle aléatoire, le pourcentage de contrôle du trafic est diffusé de manière aléatoire dans toutes les expériences de l’activité, sans tenir compte du profil de ce visiteur. Vous pouvez considérer le contrôle comme une réponse à la question &quot;Si je diffuse simplement une expérience (ou offre) aux visiteurs sans tenir compte de leurs profils, quel est le taux de conversion de cette expérience (ou offre) ?&quot; Le contrôle est semblable à un [!UICONTROL Test A/B] dans votre activité AI. Il peut s’avérer utile d’avoir ces informations sur le taux de conversion non personnalisé pour chaque expérience ou offre, afin de comprendre à quel moment analyser les résultats de votre activité.

* **Expérience spécifique**: un contrôle d’expérience spécifique vous permet de comparer le trafic traité par [!DNL Target] des modèles de personnalisation pour une expérience spécifique définie par le marketeur (par exemple, votre page d’accueil par défaut). Avec cette option, le pourcentage de contrôle du trafic est diffusé de manière aléatoire au trafic pour cette seule expérience.

## Définition d’une expérience spécifique comme contrôle

1. Lorsque vous créez ou modifiez une [[!UICONTROL Automated Personalization] activité](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ou [[!UICONTROL Ciblage automatique] activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configurez les expériences selon vos besoins.
1. Sur la page [!UICONTROL Ciblage] (étape 2 du workflow assisté en trois parties), sélectionnez l’expérience souhaitée comme contrôle.
1. Spécifiez l’affectation de trafic souhaitée pour l’expérience de contrôle et les autres expériences.

   Pour un contrôle d’expérience spécifique, 10 à 30 % sont conseillés.

1. Passez à la page [!UICONTROL Objectifs et paramètres].

## Limites et considérations connues

Gardez les points suivants à l’esprit lorsque vous utilisez une expérience spécifique comme contrôle :

* Il n’est pas conseillé de modifier l’expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports (même si les anciens rapports sont basés sur une autre expérience).
* Il n’est pas conseillé de supprimer l’expérience de contrôle.
* Il n’est pas conseillé d’ajouter de nombreuses nouvelles offres ou expériences à une activité en direct avec une expérience spécifique comme contrôle.
* Dans [!UICONTROL Automated Personalization] Il n’est pas conseillé d’inclure un ciblage sur l’expérience de contrôle qui pourrait limiter davantage les personnes qui peuvent voir cette expérience.
* Dans [!UICONTROL Automated Personalization] les informations sur les activités, l’effet élévateur et le degré de confiance sont *NOT* disponibles dans le rapport au niveau de l’offre si une expérience spécifique est sélectionnée. Les informations sur l’effet élévateur et le degré de confiance sont disponibles au niveau de trafic &quot;ciblé&quot; global par rapport au niveau de &quot;contrôle&quot; pour la variable [!UICONTROL Automated Personalization] activité. Les informations sur l’effet élévateur et la confiance sont disponibles si « aléatoire » est sélectionné comme contrôle. Cette différence est due au fait que la comparaison du taux de conversion d’une expérience spécifique vers le taux de conversion d’une offre n’est pas logique en raison de la différence d’unités. Les informations disponibles dans une [!UICONTROL Ciblage automatique] l’activité est la même, quel que soit le type de contrôle sélectionné.
* Étant donné que le trafic de contrôle est dirigé vers une seule expérience ou un seul ensemble d’offres lorsque vous sélectionnez l’expérience comme contrôle (par rapport à aléatoire, où le montant du trafic de contrôle est fractionné en fonction du nombre d’expériences ou d’offres dans votre activité), il n’est généralement pas nécessaire d’utiliser autant de trafic pour effectuer un flux vers le contrôle. 10 % est un bon point de départ.
* Si vous effectuez l’une des activités suivantes pour une activité en direct avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l’expérience spécifique précédemment sélectionnée) :

   * Suppression d’une expérience
   * Supprimer un emplacement ou une offre ([!UICONTROL Automated Personalization] uniquement)
   * Exclure une expérience manuellement, en supprimant les offres en double ou via un groupe d’exclusion ([!UICONTROL Automated Personalization] uniquement)
