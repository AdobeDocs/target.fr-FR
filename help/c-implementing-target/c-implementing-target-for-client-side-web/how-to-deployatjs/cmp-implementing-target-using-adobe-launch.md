---
description: Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.
keywords: implémenter;implémentation;mise en œuvre;lancement d’adobe;démarrer;rediriger
seo-description: Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.
seo-title: Mise en œuvre de Target avec Adobe Launch
title: Mise en œuvre de Target avec Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 56bfceba22df830933aa005bf7faf24d4d6c09ba

---


# Mise en œuvre de Target avec Adobe Launch{#implement-target-using-adobe-launch}

Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

## Mise en œuvre de Target avec Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch est la nouvelle génération de plateforme de gestion des balises d’Adobe. C’est la méthode préconisée pour la mise en œuvre d’Adobe Target. Launch offre aux clients un moyen simple de déployer et gérer toutes les balises d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

Le tableau suivant répertorie les différentes sources fournissant plus d’informations sur Launch :

| Ressource | Détails |
|--- |--- |
| [Implémentation de Target à l&#39;aide du didacticiel sur l&#39;extension Adobe Target](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Ce tutoriel contient des instructions étape par étape pour l’implémentation d’Adobe Target dans un site Web avec Launch. Les rubriques incluent l’ajout de la bibliothèque JavaScript at.js, le déclenchement de la mbox globale, l’ajout de paramètres et l’intégration à d’autres solutions. Cet article fait partie d’un tutoriel plus important qui explique comment mettre en œuvre Adobe Launch, ainsi que les autres solutions Adobe Experience Cloud. |
| [Documentation Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html) | Informations sur le déploiement et la gestion de l’ensemble des balises d’analyse, de marketing et de publicité nécessaires pour alimenter les expériences client pertinentes. |
| [Documentation d&#39;Adobe Target Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Informations sur la mise en œuvre de Target à l’aide de Launch. |

## Avantages de la mise en œuvre d’at.js avec l’extension Target Launch {#section_48B3F938B6F8491DAF798E0DB54EF304}

Les avantages suivants s’appliquent uniquement si vous utilisez Adobe Launch pour mettre at.js en œuvre. Pour cette raison, nous vous conseillons vivement d’utiliser Adobe Launch plutôt que DTM ou une mise en œuvre manuelle d’at.js.

* **Solves Analytics and Target Concurrence Condition :** Puisque l&#39;appel Analytics pourrait être déclenché avant l&#39;appel de Target, l&#39;appel Target n&#39;est pas assemblé à l&#39;appel Analytics. Cela peut entraîner des données incorrectes. À compter de 0.6.0, l&#39;extension de lancement Target garantit que l&#39;appel de balise Analytics attend jusqu&#39;à ce que l&#39;appel Target se termine, avec succès ou non. Cela devrait résoudre le problème d’incohérence de données que les clients ont pu rencontrer.
* **Empêche la gestion des offres de redirection incorrecte :** Si vous disposez de Target et d&#39;Analytics sur la page et qu&#39;une offre de redirection est exécutée par Target, il se peut que le suivi Analytics déclenche une requête lorsqu&#39;il ne le devrait pas (car l&#39;utilisateur est redirigé vers une autre URL). Si vous implémentez Target et Analytics au moyen du lancement, ce problème n&#39;est pas résolu. Avec Launch, Target demande à Analytics d&#39;abandonner la demande de balise Analytics.
