---
title: Définir une fonctionnalité à déployer progressivement
description: Découvrez comment configurer un déploiement progressif en fonction d’un pourcentage pour un indicateur de fonctionnalité dans Indicateurs.
badge: label="Version bêta" type="Informative"
hide: true
exl-id: 1e03c533-398d-4a83-9f4a-c0419828b460
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 3%

---

# Définir une fonctionnalité à déployer progressivement {#gradual-rollout-feature}

Le pourcentage de déploiement d’un indicateur de fonctionnalité est configuré dans l’onglet **Détails de base**. Vous pouvez ajuster cette valeur à la hausse ou à la baisse à tout moment au fur et à mesure du déploiement.

## Fonctionnement {#how-it-works}

Lorsque vous définissez un pourcentage de déploiement, par exemple 25 %, ce pourcentage de l’audience définie est exposé à la fonctionnalité. Le pourcentage de déploiement est **obligatoire** et est défini par défaut sur **100 %** (la fonctionnalité est diffusée à l’ensemble de l’audience correspondante). Vous pouvez l’ajuster par incréments de **1 %**. Le pourcentage restant est placé dans la **population témoin**, qui reçoit l’expérience par défaut.

Vous pouvez augmenter ou réduire le pourcentage au fil du temps pour développer ou réduire le déploiement. La réduction du pourcentage à 0 % désactive la fonctionnalité pour tous les membres de l’audience sans supprimer l’indicateur.

## Voir également {#see-also}

* [Déploiement graduel](../../concepts/gradual-rollout.md)
* [Définir un groupe de fonctionnalités à déployer progressivement](set-feature-group-gradual-rollout.md)
* [Créer votre premier indicateur de fonctionnalité](create-your-first-feature-flag.md)

<!-- -->
