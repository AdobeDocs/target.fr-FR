---
title: Demander une version
description: Découvrez comment demander une nouvelle version coordonnée dans Flags et quelles informations fournir.
hide: true
exl-id: 8eee84b2-fbd5-4713-90ac-92fd7b74c163
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 3%

---

# Demander une version {#request-a-release}

## Conditions préalables {#prerequisites}

* Vous disposez du rôle **Gestionnaire de versions**
* Votre application est intégrée : consultez la section [Intégration de votre application](../applications/onboard-your-application.md)

>[!TIP]
>
>Avant de demander une version, déterminez si un groupe de fonctionnalités multi-équipes répond à vos besoins avec moins de frais généraux : il est en libre-service et prend en charge un ciblage d’audience plus riche.

## Soumettre une demande d’assistance {#submit}

La création de version n’est pas en libre-service. Contactez l’assistance Flags pour demander une nouvelle version. Fournissez les informations suivantes :

| Champ | Description |
|---|---|
| **Nom** | Nom unique de la version. N’incluez pas d’espaces dans le nom de la version. |
| **Équipe** | L’équipe qui possédera la version. |
| **Environnement** | Environnement dans lequel la version doit être créée (évaluation ou production). |
| **Objectif** | Brève description de ce que cette version va déployer et pourquoi. |
| **Applications** | Application(s) à inclure dans la version. |
| **Durée** | Durée pendant laquelle la version doit rester active. Les rejets devraient être clôturés ou définis dans les trois mois. Si vous avez besoin de plus de temps, fournissez une justification commerciale. |

>[!NOTE]
>
>Le nombre de versions actives à un moment donné est limité. Planifiez la planification ou la fermeture de votre version dans les trois mois afin de libérer de la capacité pour d’autres équipes.

## Après la création de la version {#after}

Une fois que vous avez reçu la confirmation que la version a été créée, connectez-vous à la console et terminez la configuration de la version. Voir [Workflow de publication de bout en bout](release-workflow-end-to-end.md) pour la séquence complète des étapes.

## Voir également {#see-also}

* [Workflow de publication complet](release-workflow-end-to-end.md)
* [Mise à jour des règles d’audience de version](update-release-audience-rules.md)
* [États de la version](release-states.md)

<!-- -->
