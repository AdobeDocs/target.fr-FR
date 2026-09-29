---
title: Groupes de fonctionnalités pour contrôler plusieurs fonctionnalités
description: Découvrez comment les groupes de fonctionnalités dans les indicateurs vous permettent de regrouper et de gérer les indicateurs de fonctionnalités associés dans les applications en une seule unité.
badge: label="Beta" type="Informative"
hide: true
exl-id: dfeb7eff-34f1-4cb5-9c3e-a40d1eda3016
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%
---
# Groupes de fonctionnalités pour contrôler plusieurs fonctionnalités {#feature-groups}

Un indicateur [fonctionnalité](what-is-a-feature-flag.md) contrôle une seule fonctionnalité. Lorsque vous devez gérer plusieurs indicateurs de fonctionnalité associés ensemble (et vous assurer qu’ils atteignent la même audience), vous utilisez un **groupe de fonctionnalités**.

## Fonctionnement d&#39;un groupe de fonctionnalités {#what-it-does}

Un groupe de fonctionnalités regroupe plusieurs indicateurs de fonctionnalité et vous permet d’appliquer une seule règle d’audience à tous en même temps. Cela s’avère utile lorsqu’une seule fonctionnalité face à l’utilisateur ou à l’utilisatrice couvre plusieurs applications ou services.

Prenons l’exemple d’une fonctionnalité de collaboration qui implique des modifications sur une application de bureau, une application mobile et un service principal. En créant un groupe de fonctionnalités avec des indicateurs des trois applications, vous pouvez ouvrir la fonctionnalité à 1 % des utilisateurs, et vous assurer que ces utilisateurs bénéficient d&#39;une expérience cohérente sur les trois surfaces simultanément.

## Regroupement de plusieurs applications {#cross-application}

Les groupes de fonctionnalités prennent en charge la gestion de fonctionnalités entre applications. Les indicateurs associés à plusieurs applications peuvent être regroupés.


<!-- -->
