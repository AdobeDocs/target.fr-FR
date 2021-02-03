---
keywords: faq;questions fréquentes;analytics pour target;a4T;effet élévateur;ad hoc;créateur de rapport;degré de confiance
description: Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
title: Effet élévateur et degré de confiance - FAQ sur A4T
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 50%

---


# FAQ sur l’effet élévateur et le degré de confiance - A4T{#lift-and-confidence-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Puis-je effectuer des calculs hors ligne pour A4T ?{#section_55B5B750E17D414CAECBEECE27B15D81}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics]. Pour plus d’informations, consultez les « Performances des calculs hors ligne pour Analytics pour Target (A4T) » dans [niveau de confiance et intervalle de fiabilité](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Comment est calculé l’effet élévateur ?{#section_8CAE788EED5646C4B1D64A0D22070734}

L’effet élévateur correspond à la différence de pourcentage entre les résultats de la page de contrôle et la variante d’un test réussi.

## Comment est calculé le degré de confiance ? {#section_97DB24D833E742988318CA65DA65DAD9}

Le degré de confiance est la probabilité selon laquelle le taux de conversion mesuré diffère du taux de conversion de la page gagnante pour des raisons autres que le hasard seul.

## Pourquoi n’ai-je pas accès à l’effet élévateur et au degré de confiance pour les mesures calculées ?  {#lift-confidence}

Actuellement, les mesures calculées ne sont pas prises en charge dans les fonctions d’effet élévateur et de fiabilité. Cela est dû au fait qu’Analytics calcule les mesures au niveau de l’agrégat plutôt qu’au niveau du visiteur. La confiance, en particulier, est un calcul au niveau du visiteur.

Les événements non calculés (standard) sont pris en charge dans l’effet élévateur et la fiabilité. Ils deviennent le numérateur dans la fonction d&#39;effet élévateur ; le numérateur ne peut pas être un calcul lui-même. Le dénominateur correspond aux mesures de normalisation (impressions, visites ou visiteurs). Voici quelques exemples de événements standard : commandes, recettes, conversions d&#39;activités, événements personnalisés 1-1000, etc. Cela signifie que les mesures d’optimisation courantes, telles que le taux de conversation (Commandes/Visiteur) et les recettes par visiteur (Recettes/Visiteur), sont prises en charge dans l’effet élévateur et la fiabilité.

Voici quelques exemples de mesures non prises en charge ou de cas d’utilisation :

* Valeur de commande moyenne (Recettes/Commande, par Visiteur). AOV n’est pas pris en charge car le numérateur est une mesure calculée. Au lieu de cela, il est recommandé d&#39;examiner les deux mesures influençant l&#39;AOV - Recettes par Visiteur et Taux de conversion.
* Mesures calculées qui représentent la somme des événements standard. Par exemple, vous pouvez suivre dix formulaires de piste différents en dix événements distincts, puis les additionner pour obtenir le total des soumissions de pistes. Une méthode recommandée pour effectuer le suivi de ces événements consiste à implémenter un seul événement d’envoi de piste dans Analytics, puis à utiliser un eVar pour collecter le type de formulaire de piste. L&#39;utilisation de cette méthode nécessite moins de variables et vous permet d&#39;utiliser la mesure d&#39;envoi de piste unique dans les fonctions d&#39;effet élévateur et de fiabilité.

## Comment A4T gère-t-il les calculs du degré de confiance ?  {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T utilise des calculs de mesure non binaires avec la somme des données au carré. La variance est calculée grâce à la somme des données au carré. Les commandes extrêmes ne sont pas prises en compte. De plus, le calcul de la confiance n&#39;applique pas de correction Bonferroni pour plusieurs offres.

## L’effet élévateur et le degré de confiance sont-ils compatibles avec Ad Hoc et Report Builder ? Si cela n’est pas possible en natif, puis-je le faire moi-même ? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

L’effet élévateur et le degré de confiance ne sont pas compatibles avec le Report Builder ou ad hoc et vous ne pouvez pas les calculer vous-même pour des variables continues. Il est possible de les calculer manuellement pour les mesures binaires.
