---
keywords: expérience;contrôle;personnalisation automatisée;ciblage automatique
description: Découvrez comment sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une activité de [!UICONTROL ] (AP) ou de [!UICONTROL ciblage automatique] dans  [!DNL Adobe Target].
title: Comment puis-je utiliser une expérience spécifique en tant que contrôle dans une activité [!UICONTROL ] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3aid: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 840
ht-degree: 36%

---

# Sélectionnez le contrôle de votre activité  ou [!UICONTROL Ciblage automatique]

Vous pouvez sélectionner une expérience diffusée de manière aléatoire ou une expérience spécifique à utiliser comme contrôle lors de la création d’une activité de [](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [[!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer le trafic de contrôle vers les expériences spécifiques, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle vers ce contrôle.

Les options permettant de définir un contrôle dans les activités  et [!UICONTROL Ciblage automatique] sont un peu différentes des autres types d’activités. Dans un [!UICONTROL Test A/B] manuel, vous pouvez modifier ce que les rapports indiquent comme étant votre contrôle et l’effet élévateur est calculé en fonction du taux de conversion de cette expérience de contrôle. Vous pouvez effectuer facilement cette modification car le trafic est diffusé de manière aléatoire à chacune des expériences que vous avez incluses dans votre activité, quelle que soit la commande initialement définie. En d’autres termes, la sélection du contrôle n’a aucune incidence sur la manière dont le trafic est diffusé. Dans les activités  et [!UICONTROL Ciblage automatique], votre décision concernant le choix du contrôle a une incidence sur la manière dont le trafic des visiteurs est diffusé. Par conséquent, vous devez réfléchir plus attentivement à votre décision.

Deux options sont disponibles pour votre contrôle dans vos activités  et [!UICONTROL Ciblage automatique] :

* **Diffusion aléatoire** : pour un contrôle aléatoire, le pourcentage de contrôle du trafic diffuse aléatoirement toutes les expériences de l’activité, sans tenir compte du profil du visiteur. Vous pouvez considérer le contrôle comme une réponse à la question « Si je diffuse simplement une expérience (ou une offre) de manière aléatoire aux visiteurs et visiteuses et que je ne prends pas en compte leurs profils, quel est le taux de conversion de cette expérience (ou offre) ? » Le contrôle est semblable à un test [!UICONTROL A/B] dans votre activité d’IA. Il peut s’avérer utile d’avoir ces informations sur le taux de conversion non personnalisé pour chaque expérience ou offre, afin de comprendre à quel moment analyser les résultats de votre activité.

* **Expérience spécifique** : un contrôle d’expérience spécifique vous permet de comparer le trafic généré par [!DNL Target] modèles de personnalisation à une expérience spécifique définie par le spécialiste marketing (par exemple, votre page d’accueil par défaut). Avec cette option, le pourcentage de contrôle du trafic est diffusé de manière aléatoire au trafic pour cette seule expérience.

## Définition d’une expérience spécifique comme contrôle

1. Lors de la création ou de la modification d’une activité [ ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ou [[!UICONTROL Ciblage automatique]](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configurez les expériences selon vos besoins.
1. Sur la page [!UICONTROL Ciblage] (étape 2 du workflow en trois parties), cliquez sur l’expérience de contrôle pour afficher les options [!UICONTROL Contrôle] dans le volet de droite.

   ![Panneau de contrôle](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Dans la liste déroulante [!UICONTROL Contrôle], sélectionnez [!UICONTROL Expérience aléatoire] ou sélectionnez l’expérience que vous souhaitez utiliser pour le contrôle.

1. Cliquez sur le contrôle [!UICONTROL Affectation du trafic], puis spécifiez l’affectation du trafic souhaitée pour l’expérience de contrôle et les autres expériences.

   ![Rail d’affectation du trafic](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   Pour un contrôle d’expérience spécifique, 10 à 30 % sont conseillés.

1. Passez à la page [!UICONTROL  Objectifs et paramètres ].

## Limites et considérations connues

Gardez les points suivants à l’esprit lors de l’utilisation d’une expérience spécifique comme contrôle :

* Il n’est pas conseillé de modifier l’expérience de contrôle dans une activité déjà active. La dernière expérience de contrôle sélectionnée est nommée dans les rapports (même si les anciens rapports sont basés sur une autre expérience).
* Il n’est pas conseillé de supprimer l’expérience de contrôle.
* Il est déconseillé d’ajouter de nombreuses nouvelles offres ou expériences à une activité en direct avec une expérience spécifique, car le contrôle n’est pas conseillé.
* Dans les activités , il n’est pas conseillé de cibler l’expérience de contrôle afin de contraindre davantage les personnes pouvant voir cette expérience.
* Dans les activités , les informations sur l’effet élévateur et le degré de confiance ne sont *PAS* disponibles dans le rapport au niveau de l’offre si une expérience spécifique est sélectionnée. Les informations d’effet élévateur et de confiance sont disponibles au niveau du trafic global « ciblé » et « de contrôle » pour l’activité . Les informations sur l’effet élévateur et la confiance sont disponibles si « aléatoire » est sélectionné comme contrôle. Cette différence est due au fait que la comparaison du taux de conversion d’une expérience spécifique vers le taux de conversion d’une offre n’est pas logique en raison de la différence d’unités. Les informations disponibles dans une activité de [!UICONTROL ciblage automatique] sont les mêmes, quel que soit le type de contrôle sélectionné.
* Étant donné que le trafic de contrôle est dirigé vers une seule expérience ou un seul ensemble d’offres lorsque vous sélectionnez l’expérience comme contrôle (par rapport à aléatoire, où le montant du trafic de contrôle est fractionné en fonction du nombre d’expériences ou d’offres dans votre activité), il n’est généralement pas nécessaire d’utiliser autant de trafic pour effectuer un flux vers le contrôle. 10 % est un bon point de départ.
* Si vous effectuez l’une des activités suivantes pour une activité en direct avec une expérience spécifique comme contrôle, le contrôle est automatiquement réinitialisé sur des expériences diffusées de manière aléatoire (au lieu de l’expérience spécifique précédemment sélectionnée) :

   * Suppression d’une expérience
   * Supprimer un emplacement ou une offre ( uniquement)
   * Exclure une expérience manuellement, par le biais de la suppression des offres en double ou d’un groupe d’exclusion ( uniquement)
