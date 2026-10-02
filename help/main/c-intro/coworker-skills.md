---
keywords: Adobe Target;Collègue;IA;compétences;expérimentation;Recommendations
title: Compétences des collègues pour Adobe Target
description: Découvrez les compétences des collègues disponibles pour Adobe Target, notamment la découverte d’activités, la création de tests, l’analyse, la composition de l’audience et le dépannage de Recommendations.
feature: Overview
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: 4b90f47050b63c7e1e6ac5019d45a7b99b3a33b8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%
---

# Compétences des collègues pour Adobe Target {#coworker-skills}

>[!BEGINSHADEBOX]

**Sur cette page :** découvrez les compétences de collègue disponibles pour Adobe Target, notamment les compétences pour explorer les activités et les audiences, créer et configurer des tests, analyser les performances, composer des audiences et gérer les recommandations.

>[!ENDSHADEBOX]

Les compétences de collègues aident les utilisateurs d’Adobe Target à utiliser le langage naturel pour explorer leurs programmes de test et de personnalisation, créer et configurer des activités, analyser les résultats et résoudre les problèmes de diffusion. Décrivez ce que vous souhaitez faire dans la conversation avec vos collègues, puis passez en revue les recommandations, la configuration ou l’analyse renvoyées avant d’entreprendre une action.

[!DNL Adobe Target] outils MCP et Coworker sont documentés séparément et fournissent différentes fonctionnalités :

* [MCP cible](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md) documente les outils individuels exposés par le serveur MCP direct, y compris leurs types d’activités pris en charge, les paramètres, les autorisations et la portée de lecture ou d’écriture.
* [Coworker](https://experienceleague.adobe.com/fr/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/overview#target-activities-and-audiences) fournit une couche d’orchestration en langage naturel distincte qui peut combiner les fonctionnalités et appliquer des workflows supplémentaires.

Le tableau suivant présente une comparaison de haut niveau des fonctionnalités associées.

| Fonction | MCP Target | Coworker |
| --- | --- | --- |
| Liste des expériences en cours d’exécution, des audiences, des offres ou des éléments récemment modifiés | Oui | Oui |
| Création d’une activité Automated Personalization | Non | Non |
| Création d’une audience cible | Oui | Oui |
| Créez une activité de compositeur d’expérience visuelle Target, une activité de ciblage d’expérience ou un test A/B | Oui | Oui |
| Création d’une activité Target Recommendations | Oui | Oui |
| Création d’une offre HTML ou JSON dans Target | Oui | Oui |
| Utilisation d’un fragment de contenu AEM dans une activité Target | Non | Oui |
| Recommandez ce qui fonctionne et ce qui doit être testé ensuite | Aucun conseil ou conseil générique | Oui |


## Plug-in Target

Les compétences suivantes sont disponibles sous le plug-in **Target** :

* **Parcourir Target**

  Permet la découverte, le contrôle et le comptage des entités Target en lecture seule, y compris les activités, les audiences, les offres et la configuration associée.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Répertorier mes activités actives. »
* « Combien d’activités sont en cours d’exécution ? »
* « Montrez-moi les audiences et les offres utilisées par cette activité. »

>[!ENDSHADEBOX]

* **Verdict relatif à l’activité Target**

  Détermine si une activité est prête à être expédiée, si elle doit attendre davantage de données, si elle doit s’arrêter ou si elle doit être corrigée. Pour cela, vous utilisez des calculs d’importance et des contrôles de configuration.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Dois-je expédier ce test ? »
* « Cette activité est-elle prête à s’arrêter ? »
* « La configuration d’activité actuelle rencontre-t-elle des problèmes ? »

>[!ENDSHADEBOX]

* **Conception de Target**

  Crée et configure des activités et des offres, génère des URL d’assurance qualité et crée ou optimise du contenu d’offre.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Créez un test A/B pour la page d’accueil. »
* « Créez une offre pour l’expérience des visiteurs récurrents. »
* « Générez une URL d’assurance qualité pour cette activité. »

>[!ENDSHADEBOX]

* **compositeur d’expérience visuelle Target**

  Crée et modifie les activités du compositeur d’expérience visuelle et leurs audiences de diffusion de pages.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Créez un test A/B du compositeur d’expérience visuelle pour la page d’accueil. »
* « Modifiez le titre de héros dans mon activité VEC. »
* « Créez une audience de diffusion de page pour cette activité du compositeur d’expérience visuelle. »

>[!ENDSHADEBOX]

* **Configuration de Target**

  Les guides terminent la création de l’activité A/B, ciblage d’expérience ou compositeur d’expérience visuelle, y compris les conditions préalables, la planification, l’assurance qualité et l’activation.

>[!BEGINSHADEBOX]

    *Exemple d’invites :*
    
    * « Aidez-moi à créer mon premier test. »
    * « De quoi ai-je besoin avant de créer une activité de ciblage d’expérience ? »
    * « Découvrez-moi comment planifier, contrôler la qualité et activer cette activité. »

>[!ENDSHADEBOX]

* **Intelligence Target**

  Audits Ciblez les programmes sur les risques, les collisions, les erreurs de configuration, les problèmes d’hygiène et les gains rapides.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Contrôler mes activités Target. »
* « Rechercher les collisions ou les risques de configuration dans mes activités. »
* « Quels gains rapides peuvent améliorer l’hygiène de mon programme Target ? »

>[!ENDSHADEBOX]

* **Stratège Target**

  Analyse les données historiques de Target pour identifier les modèles gagnants et recommande des tests futurs.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Que dois-je tester ensuite en fonction des résultats passés ? »
* « Quels modèles apparaissent dans mes tests les plus performants ? »
* « Recommandez un test de suivi en fonction des résultats de cette activité. »

>[!ENDSHADEBOX]

* **Calculateur de test Target**

  Planifie la taille de l’échantillon A/B/n, la durée et l’effet élévateur détectable pour les mesures de conversion et de chiffre d’affaires, avec la correction de Bonferroni pour plusieurs comparaisons.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « De quelle taille d’échantillon ai-je besoin ? »
* « Pendant combien de temps dois-je exécuter ce test A/B pour détecter une augmentation de 5 % ? »
* « Quel effet élévateur détectable puis-je mesurer avec ce trafic ? »

>[!ENDSHADEBOX]

* **Rapport Portfolio Target**

  Fournit des cumuls de performances en lecture seule et à l’échelle du programme, ainsi qu’une analyse des tendances et de l’élan des activités.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Quels sont mes tests les plus performants et les moins performants ? »
* « Afficher les tendances de performances dans mes activités. »
* « Quelles activités ont gagné ou perdu de leur élan récemment ? »

>[!ENDSHADEBOX]

* **Compositeur d’audience cible**

  Crée ou modifie des audiences natives pour Target à partir de descriptions en langage naturel ou de règles explicites.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Créez une audience pour les visiteurs mobiles récurrents. »
* « Modifiez cette audience pour inclure les visiteurs provenant de la recherche organique. »
* « Créez une audience cible pour les visiteurs qui ont consulté la page de tarification. »

>[!ENDSHADEBOX]

* **Recommandations Target**

  Gère et fonctionne avec les activités et configurations de Target Recommendations.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Créez une activité Recommendations. »
* « Afficher mes activités et configurations Recommendations. »
* « Mettez à jour les paramètres de cette activité Recommendations. »

>[!ENDSHADEBOX]

* **Diagnostic des recommandations Target**

  Diagnostique les problèmes de diffusion, de configuration, de catalogue et de flux de Recommendations.

>[!BEGINSHADEBOX]

*Exemples d’invites :*

* « Pourquoi mes recommandations n’apparaissent-elles pas ? »
* « Diagnostiquez la configuration des flux et du catalogue pour cette activité Recommendations. »
* « Des problèmes de diffusion ou de configuration affectent-ils mes recommandations ? »

>[!ENDSHADEBOX]
