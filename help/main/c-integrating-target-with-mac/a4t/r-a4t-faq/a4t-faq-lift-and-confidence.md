---
keywords: faq;questions fréquentes;analytics pour target;a4T;effet élévateur;ad hoc;créateur de rapport;degré de confiance
description: Trouvez des réponses aux questions sur l’effet élévateur et le degré de confiance lorsque vous utilisez Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser la création de rapports Analytics pour les activités  [!DNL Target] .
title: Où puis-je trouver des informations sur l’effet élévateur et le degré de confiance avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 25%

---

# FAQ sur l’effet élévateur et le degré de confiance - A4T

Cette rubrique contient les réponses aux questions fréquentes sur l’effet élévateur et le degré de confiance lorsque vous utilisez [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Puis-je effectuer des calculs hors ligne pour A4T ? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++Réponse
Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics]. Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Comment est calculé l’effet élévateur ? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++Réponse
L’effet élévateur correspond à la différence de pourcentage entre les résultats de la page de contrôle et la variante d’un test réussi.

+++

## Comment est calculé le degré de confiance ? {#section_97DB24D833E742988318CA65DA65DAD9}

+++Réponse
Le niveau de confiance est une probabilité, exprimée en pourcentage, qui est égale à `1 - p-value`, où la `p-value` est calculée à partir d’un test t. Voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Pourquoi n’ai-je pas accès à l’effet élévateur et au degré de confiance pour les mesures calculées ? {#lift-confidence}

+++Réponse
Les mesures calculées ne sont actuellement pas prises en charge dans les fonctions d’effet élévateur et de confiance. Analytics calcule les mesures au niveau des agrégats, plutôt qu’au niveau des visiteurs. Le degré de confiance, en particulier, est un calcul au niveau du visiteur.

Les événements non calculés (standard) sont pris en charge dans l’effet élévateur et le degré de confiance. Ils deviennent le numérateur dans la fonction d’effet élévateur ; le numérateur ne peut pas être un calcul lui-même. Le dénominateur est la mesure de normalisation (impressions, visites ou visiteurs). Parmi les exemples d’événements standard, citons les commandes, le chiffre d’affaires, les conversions d’activité, les événements personnalisés 1 à 1 000, etc. Les mesures d’optimisation courantes, telles que le taux de conversation (Commandes/Visiteur) et la valeur prédictive positive (Recettes/Visiteur), sont prises en charge dans l’effet élévateur et le degré de confiance.

Voici quelques exemples de mesures ou de cas d’utilisation non pris en charge :

* Valeur de commande moyenne (chiffre d’affaires/commande, par visiteur). AOV n’est pas pris en charge, car le numérateur est une mesure calculée. Il est plutôt recommandé de prendre en compte les deux mesures d’influence d’AOV : le chiffre d’affaires par visiteur et le taux de conversion.
* Mesures calculées qui sont la somme des événements standard. Par exemple, vous pouvez effectuer le suivi de dix formulaires de prospect différents en dix événements distincts, puis les ajouter ensemble pour obtenir le nombre total d’envois de prospects. Une méthode recommandée pour suivre ces événements consiste à implémenter un événement d’envoi de prospect unique dans Analytics, puis à utiliser une eVar pour collecter le type de formulaire de prospect. L’utilisation de cette méthode nécessite moins de variables et garantit que vous pouvez utiliser la mesure d’envoi de prospect unique dans les fonctions d’effet élévateur et de confiance.

+++

## Comment A4T gère-t-il les calculs du degré de confiance ? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++Réponse
[!DNL Adobe Analytics] traite toutes les mesures comme non binaires et calcule donc les valeurs de confiance/p différemment de l’utilisation de mesures binaires dans un test t standard. Plus précisément, les calculs utilisés par A4T permettent à chaque utilisateur d’avoir un résultat de mesure continu (pas seulement 1 ou 0 pour chaque utilisateur), de sorte que la variance (ou, de manière associée, l’écart type) pour chaque expérience doit être calculée correctement. Les ordres extrêmes ne sont pas pris en compte. En outre, le calcul de confiance n’applique pas de correction Bonferroni pour les offres multiples.

+++

## L’effet élévateur et le degré de confiance sont-ils compatibles avec Ad Hoc et Report Builder ? Si cela n’est pas possible en natif, puis-je le faire moi-même ? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++Réponse
L’effet élévateur et le degré de confiance ne sont pas compatibles avec le Report Builder ou ad hoc et vous ne pouvez pas les calculer vous-même pour des variables continues. Il est possible de les calculer manuellement pour les mesures binaires.
+++
