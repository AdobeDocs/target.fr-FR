---
description: 'Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. '
keywords: implémenter;implémentation;mise en œuvre;lancement d’adobe;démarrer;rediriger
seo-description: 'Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. '
seo-title: Mise en œuvre de Target avec Adobe Launch
title: Mise en œuvre de Target avec Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 19834da75f163d6357bc9b986a23f0bc1fea6d8e

---


# Mise en œuvre de Target avec Adobe Launch{#implement-target-using-adobe-launch}

Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. 

## Mise en œuvre de Target avec Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes. 

Le tableau suivant répertorie les différentes sources fournissant plus d’informations sur Launch :

| Ressource | Détails |
|--- |--- |
| [Implémentation de Target à l&#39;aide du didacticiel sur l&#39;extension Adobe Target](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Ce tutoriel contient des instructions étape par étape pour l’implémentation d’Adobe Target dans un site Web avec le lancement. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d&#39;un tutoriel plus important qui explique comment mettre en œuvre Adobe Launch, ainsi que les autres solutions Adobe Experience Cloud. |
| [Documentation Adobe Launch](https://docs.adobelaunch.com/getting-started) | Informations sur le déploiement et la gestion de l’ensemble des balises d’analyse, de marketing et de publicité nécessaires pour alimenter les expériences client pertinentes. |
| [Documentation d&#39;Adobe Target Extension](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | Informations sur la mise en œuvre de Target à l’aide de Launch. |

## Avantages de la mise en œuvre d’at.js avec l’extension Target Launch {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez Adobe Launch pour mettre at.js en œuvre. Pour cette raison, nous vous conseillons vivement d’utiliser Adobe Launch plutôt que DTM ou une mise en œuvre manuelle d’at.js.

* **Permet le déploiement asynchrone de Target :** pour plus d’informations, voir « Extension Adobe Target avec un déploiement asynchrone » dans la [Documentation Extension Adobe Target](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension).
* **Résout la condition Analytics Target Race :** Comme l’appel Analytics peut être déclenché avant l’appel Target, l’appel Target n’est pas associé à l’appel Analytics, ce qui peut entraîner des données incorrectes. À partir de Launch 0.6.0, l’extension Target Launch assure que l’appel de la balise Analytics attend la fin de l’appel Target, réussi ou non. Cela devrait résoudre le problème d’incohérence de données que les clients ont pu rencontrer.
* **Empêche la gestion des offres de redirection incorrectes :** lorsque vous disposez de Target et d’Analytics sur la page et qu’une offre de redirection est en cours d’exécution par Target, il peut arriver que le système de suivi d’Analytics déclenche une requête alors qu’il ne devrait pas car l’utilisateur est redirigé vers une autre URL. Si vous mettez Target et Analytics en œuvre via Launch, vous n’êtes pas confronté à ce problème car avec l’utilisation de Launch, Target indique à Analytics d’abandonner la requête de balise Analytics.

