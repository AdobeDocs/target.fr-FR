---
title: Création de rapports
description: Découvrez comment afficher les rapports d’indicateur de fonctionnalité dans Indicateurs à l’aide de Customer Journey Analytics.
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# Création de rapports {#reporting}

Flags diffuse les rapports via **Customer Journey Analytics (CJA)**. Il n’existe pas d’onglet Résultats ou Rapports dans la console ; à la place, un bouton **Rapport** sur chaque indicateur de fonctionnalité ou groupe de fonctionnalités ouvre un tableau de bord CJA étendu pour cet élément.

## Conditions préalables {#prerequisites}

Avant d’afficher des rapports, vérifiez les points suivants :

1. La création de rapports est configurée pour votre application. Voir [Configurer la création de rapports avec Customer Journey Analytics](#setup).
1. Votre indicateur de fonction ou votre groupe de fonctions est actif et a accumulé des données.

## Affichage d’un rapport {#view-report}

Pour ouvrir un rapport pour un indicateur de fonction ou un groupe de fonctions :

1. Accédez à l’indicateur de fonctionnalité ou au groupe de fonctionnalités dans la console.
1. Sélectionnez **Rapport**.

Un tableau de bord Customer Journey Analytics étendu s’ouvre, affichant les données de cet indicateur ou de ce groupe de fonctionnalités. Le tableau de bord comprend :

* **Participants** — Nombre total d’utilisateurs qualifiés pour la fonctionnalité (variante + population témoin combinées)
* **Population témoin** — Nombre d&#39;utilisateurs affectés à la population témoin (utilisateurs ayant bénéficié de l&#39;expérience par défaut)
* **Répartition des variantes** — Nombre cumulé d’utilisateurs inscrits dans chaque variante et dans la population témoin
* **Inscription quotidienne** — Graphiques au niveau des jours montrant l’inscription dans chaque variante et dans la population témoin au fil du temps

## Configuration de la création de rapports avec Customer Journey Analytics {#setup}

La création de rapports nécessite un jeu de données Customer Journey Analytics connecté à votre application Flags. Contactez le support des indicateurs ou votre représentant Adobe pour activer le reporting pour votre application.

>[!NOTE]
>
>L’identité transmise dans la demande de fonctionnalité n’a pas besoin d’être liée à un profil. L’évaluation se produit au moment de l’exécution et l’événement est envoyé à Customer Journey Analytics.

## Voir également {#see-also}

* [Créer votre premier indicateur de fonctionnalité](create-your-first-feature-flag.md)
* [Test A/B avec indicateurs de fonctionnalité](a-b-testing.md)
* [Créer un groupe de fonctionnalités](create-a-feature-group.md)

<!-- -->
