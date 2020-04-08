---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
title: FAQ sur l’effet élévateur et le degré de confiance - A4T
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: a06747412ba93cacb012e0d68334590fc3d52ab7

---


# FAQ sur l’effet élévateur et le degré de confiance - A4T{#lift-and-confidence-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Puis-je effectuer des calculs hors ligne pour A4T ?{#section_55B5B750E17D414CAECBEECE27B15D81}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics]. Pour plus d’informations, consultez les « Performances des calculs hors ligne pour Analytics pour Target (A4T) » dans [niveau de confiance et intervalle de fiabilité](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Comment est calculé l’effet élévateur ?{#section_8CAE788EED5646C4B1D64A0D22070734}

L’effet élévateur correspond à la différence de pourcentage entre les résultats de la page de contrôle et la variante d’un test réussi.

## Comment est calculé le degré de confiance ? {#section_97DB24D833E742988318CA65DA65DAD9}

Le degré de confiance est la probabilité selon laquelle le taux de conversion mesuré diffère du taux de conversion de la page gagnante pour des raisons autres que le hasard seul.

## Pourquoi n’ai-je pas accès à l’effet élévateur et au degré de confiance pour les mesures calculées ? {#lift-confidence}

L’effet élévateur et le degré de confiance ne sont actuellement pas pris en charge par les mesures calculées. Cependant, dans la plupart des cas, cela ne doit pas poser de problème car le  calculé dans le rapport A4T est déjà une mesure calculée dans laquelle le dénominateur est la mesure de normalisation (instances, visites ou). Si, par exemple, vous sélectionnez la mesure Commandes et que la mesure de normalisation est, le  (commandes/) est calculé automatiquement via le  A4T. La mesure d’effet élévateur résultante reflète la différence dans ce entre les expériences de texte par rapport à la mesure par défaut.

La plupart des mesures calculées pour l’optimisation tombent dans l’un des deux  de suivants :  des mesures  ou d’autres calculs de conversion, tels que Valeur de commande moyenne (AOV).

 mesures  sont utilisées lorsqu’une organisation utilise un unique pour capturer différentes &quot;saveurs&quot; de la conversion d’enregistrement. Par exemple, si vous avez pour objectif de promouvoir les envois de formulaire de piste et que vous avez dix formulaires de piste différents, vous pouvez créer un unique pour comptabiliser chaque type de conversion de formulaire. Pour voir la quantité totale de tous les formulaires de piste envoyés, vous devez créer une mesure calculée simple pour les additionner. Une méthode plus moderne et plus efficace pour effectuer ce suivi consiste à mettre en oeuvre un unique d’envoi de piste dans Analytics, puis à utiliser une eVar pour collecter le type de formulaire de piste. L’utilisation de cette méthode nécessite moins de variables et élimine la nécessité de   des mesures individuelles et vous avez toujours la possibilité de voir la conversion globale de formulaire de piste et de la ventiler par type de formulaire de piste à l’aide de l’eVar. Cela permet également d’éliminer la nécessité de  mesures  lors de l’évaluation des performances d’un de.

Une autre mesure calculée courante, Valeur de commande moyenne, n’est pas prise en charge actuellement avec effet élévateur et degré de confiance, car la mesure de normalisation n’est pas une mesure standard (instances, visites ou). Au lieu de cela, il est recommandé de garder un oeil sur les deux mesures influençant les valeurs de commande moyenne, Recettes par et .

## Comment A4T gère-t-il les calculs du degré de confiance ? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T utilise des calculs de mesure non binaires avec la somme des données au carré. La variance est calculée grâce à la somme des données au carré. Les commandes extrêmes ne sont pas prises en compte.

Tout segment Analytics peut être appliqué au rapport. Vous pouvez ainsi obtenir l’option « commande extrême » parmi d’autres options de segment. Une mesure peut également être conçue pour limiter des éléments tels que le nombre de conversions d’un visiteur.

## L’effet élévateur et le degré de confiance sont-ils compatibles avec Ad Hoc et Report Builder ? Si cela n’est pas possible en natif, puis-je le faire moi-même ? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

L’effet élévateur et le degré de confiance ne sont pas compatibles avec le Report Builder ou ad hoc et vous ne pouvez pas les calculer vous-même pour des variables continues. Il est possible de les calculer manuellement pour les mesures binaires.
