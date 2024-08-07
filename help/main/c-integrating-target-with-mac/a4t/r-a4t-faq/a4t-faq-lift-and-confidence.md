---
keywords: faq;questions fréquentes;analytics pour target;a4T;effet élévateur;ad hoc;créateur de rapport;degré de confiance
description: Trouvez des réponses aux questions sur l’effet élévateur et le degré de confiance lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser les rapports Analytics pour les activités  [!DNL Target] .
title: Où puis-je trouver des informations sur l’effet élévateur et le degré de confiance avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# FAQ sur l’effet élévateur et le degré de confiance - A4T

Cette rubrique contient des réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lors de l’utilisation de [!DNL Adobe Analytics] comme source des rapports pour [!DNL Adobe Target] (A4T).

## Puis-je effectuer des calculs hors ligne pour A4T ? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++Réponse
Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape avec les exportations de données dans [!DNL Analytics]. Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Comment est calculé l’effet élévateur ? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++Réponse
L’effet élévateur est la différence de pourcentage entre les résultats de la page de contrôle et une variante de test réussie.

+++

## Comment est calculé le degré de confiance ? {#section_97DB24D833E742988318CA65DA65DAD9}

+++Réponse
Le degré de confiance est une probabilité, exprimée en pourcentage, qui est égale à `1 - p-value`, où le `p-value` est calculé à partir d’un test en t. Voir [Calculs statistiques dans les tests A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Pourquoi n’ai-je pas accès à l’effet élévateur et au degré de confiance pour les mesures calculées ? {#lift-confidence}

+++Réponse
Les mesures calculées ne sont actuellement pas prises en charge dans les fonctions d’effet élévateur et de degré de confiance. Analytics calcule les mesures à un niveau agrégé, plutôt qu’au niveau du visiteur. La confiance, en particulier, est un calcul au niveau du visiteur.

Les événements non calculés (standard) sont pris en charge dans l’effet élévateur et le degré de confiance. Ils deviennent le numérateur dans la fonction d’effet élévateur ; le numérateur ne peut pas être un calcul lui-même. Le dénominateur correspond aux mesures de normalisation (impressions, visites ou visiteurs). Parmi les exemples d’événements standard, citons les commandes, les recettes, les conversions d’activités, les événements personnalisés 1-1000, etc. Les mesures d’optimisation courantes, telles que le taux de conversation (commandes/visiteurs) et le RPV (recettes/visiteur) sont prises en charge dans l’effet élévateur et le degré de confiance.

Voici quelques exemples de mesures ou de cas d’utilisation non pris en charge :

* Valeur de commande moyenne (recettes/commande, par visiteur). La valeur de commande moyenne n’est pas prise en charge, car le numérateur est une mesure calculée. Il est préférable de prendre en compte les deux mesures d’influence de la valeur de commande moyenne : Recettes par visiteur et Taux de conversion.
* Mesures calculées qui sont la somme des événements standard. Vous pouvez, par exemple, effectuer le suivi de dix formulaires de piste différents en dix événements distincts, puis les additionner pour obtenir le nombre total d’envois de pistes. Une méthode recommandée pour effectuer le suivi de ces événements consiste à mettre en oeuvre un seul événement d’envoi de piste dans Analytics, puis à utiliser un eVar pour collecter le type de formulaire de piste. L’utilisation de cette méthode nécessite moins de variables et garantit que vous pouvez utiliser la mesure d’envoi de piste unique dans les fonctions d’effet élévateur et de confiance.

+++

## Comment A4T gère-t-il les calculs du degré de confiance ? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++Réponse
[!DNL Adobe Analytics] traite toutes les mesures comme non binaires et, par conséquent, calcule la confiance/les valeurs-p d’une manière différente de l’utilisation de mesures binaires dans un test en t standard. En particulier, les calculs utilisés par A4T permettent à chaque utilisateur d’obtenir un résultat de mesure continue (et non pas seulement 1 ou 0 pour chaque utilisateur), de sorte que la variance (ou l’écart type relatif) de chaque expérience doit être calculé de manière appropriée. Les commandes extrêmes ne sont pas prises en compte. En outre, le calcul du degré de confiance n’applique pas de correction Bonferroni pour plusieurs offres.

+++

## L’effet élévateur et le degré de confiance sont-ils compatibles avec Ad Hoc et Report Builder ? Si cela n’est pas possible en natif, puis-je le faire moi-même ? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++Réponse
L’effet élévateur et le degré de confiance ne fonctionnent pas dans Ad Hoc ou Report Builder et ne peuvent pas être calculés vous-même pour les variables continues. Il est possible de les calculer manuellement pour les mesures binaires.
+++
