---
keywords: faq;questions fréquentes;analytics pour target;a4T;effet élévateur;ad hoc;créateur de rapport;degré de confiance
description: Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
title: FAQ sur l’effet élévateur et le degré de confiance - A4T
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# FAQ sur l’effet élévateur et le degré de confiance - A4T{#lift-and-confidence-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur les définitions de mesures et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Puis-je effectuer des calculs hors ligne pour A4T ?{#section_55B5B750E17D414CAECBEECE27B15D81}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics]. Pour plus d’informations, consultez les « Performances des calculs hors ligne pour Analytics pour Target (A4T) » dans [niveau de confiance et intervalle de fiabilité](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Comment est calculé l’effet élévateur ?{#section_8CAE788EED5646C4B1D64A0D22070734}

L’effet élévateur correspond à la différence de pourcentage entre les résultats de la page de contrôle et la variante d’un test réussi.

## Comment est calculé le degré de confiance ? {#section_97DB24D833E742988318CA65DA65DAD9}

Le degré de confiance est la probabilité selon laquelle le taux de conversion mesuré diffère du taux de conversion de la page gagnante pour des raisons autres que le hasard seul.

## Pourquoi n’ai-je pas accès à l’effet élévateur et au degré de confiance pour les mesures calculées ? {#section_D3E44E24782A409DBD88AE4D1595CB58}

L’effet élévateur et le degré de confiance ne peuvent actuellement pas être générés pour les mesures calculées. Cependant, dans la plupart des cas, cela ne pose pas de problème, car l’effet élévateur est normalisé par la mesure de normalisation. Par exemple, si vous sélectionnez l’effet élévateur pour les commandes et que la mesure de normalisation se rapporte aux visites, l’effet élévateur est calculé selon le ratio des deux, qui est le taux de conversion.

## Comment A4T gère-t-il les calculs du degré de confiance ? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

A4T utilise des calculs de mesure non binaires avec la somme des données au carré. La variance est calculée grâce à la somme des données au carré. Les commandes extrêmes ne sont pas prises en compte.

Tout segment Analytics peut être appliqué au rapport. Vous pouvez ainsi obtenir l’option « commande extrême » parmi d’autres options de segment. Une mesure peut également être conçue pour limiter des éléments tels que le nombre de conversions d’un visiteur.

## L’effet élévateur et le degré de confiance sont-ils compatibles avec Ad Hoc et Report Builder ? Si cela n’est pas possible en natif, puis-je le faire moi-même ? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

L’effet élévateur et le degré de confiance ne sont pas compatibles avec le Report Builder ou ad hoc et vous ne pouvez pas les calculer vous-même pour des variables continues. Il est possible de les calculer manuellement pour les mesures binaires.
