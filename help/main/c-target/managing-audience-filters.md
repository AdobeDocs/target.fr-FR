---
keywords: ciblage;filtre d’audience;audiences;filtre
description: Découvrez comment utiliser les filtres d’audience dans  [!DNL Adobe Target] pour afficher les données des visiteurs qui partagent des caractéristiques.
title: Puis-je utiliser les filtres d’audience pour la création de rapports ?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 72%

---

# Filtres d’audiences pour la création de rapports

Les filtres d’audiences (ou audiences) dans [!DNL Adobe Target] sont des groupes de visiteurs qui partagent une caractéristique spécifique ou un ensemble de caractéristiques.

Appliquez des filtres d’audiences pour préciser quelles audiences utiliser pour la création de rapports. Vous pouvez sélectionner une audience et comparer ses performances au trafic général. Par exemple, vous voulez comprendre si vos gagnants sont différents pour diverses sources de trafic, par rapport au trafic général. Les filtres d’audiences vous aident à découvrir les audiences qui doivent être ciblées sur un contenu différent. Le gagnant n’est généralement pas le même pour tous les trafics.

Par exemple, les visiteurs qui arrivent sur votre page à partir d’un certain moteur de recherche peuvent constituer une audience. D’autres audiences peuvent dépendre du sexe, de l’âge, de l’emplacement, de l’état de l’inscription, de l’historique des achats ou de tout autre détail collecté concernant vos visiteurs. Les filtres d’audiences permettent de diviser le trafic des visiteurs et de comparer les performances des expériences pour chaque segment de trafic.

Lorsque vous prévoyez d’utiliser des filtres d’audiences pour une activité, tenez compte des recommandations suivantes :

* **Les visiteurs peuvent appartenir à plusieurs audiences.** Si deux audiences sont configurées (par exemple, &quot;nouveaux visiteurs&quot; et &quot;visiteurs provenant de Google&quot;) et qu’une personne répond aux deux critères, ce visiteur est comptabilisé et suivi dans les deux audiences. Ainsi, le total des visiteurs dans les audiences ne correspond pas au nombre de visiteurs d’une activité.
* **Configurez les audiences avant de lancer l’activité.** Les données de l’audience ne peuvent pas être extraites rétroactivement. Si vous ne configurez pas les filtres d’audiences avant de lancer l’activité, puis décidez finalement de les utiliser alors que l’activité est en cours d’exécution depuis quelque temps déjà, vous ne collecterez pas les données pendant la période déjà écoulée.
* **Commencez par créer entre deux et quatre audiences.** Concentrez-vous sur les informations de base, telles que la source du trafic.
* **Renommez les audiences à votre convenance.** Vous pouvez renommer une audience sans affecter les données, pour la rendre plus parlante au vu des résultats collectés, même si l’activité est active.
* **Entrez des valeurs précises.** Les paramètres des filtres d’audiences sont sensibles à la casse. Par exemple, si vous utilisez une audience qui filtre les villes, vous devez utiliser une condition « OU » afin d’inclure les variantes d’orthographe et de casse possibles, comme « Vienne », « vienne », « wien » et « Wien ».
* **Les audiences créées à partir de la liste [!UICONTROL Audiences] sont réutilisables.** Il est impossible de réutiliser les audiences créées dans le cadre d’une activité.

Les sections ci-après fournissent davantage d’informations sur la configuration d’audiences et la création de rapports à leur sujet :

| Tâche | Rubrique |
|--- |--- |
| Créez l’activité ou le test approprié. | [Activités et tests](/help/main/c-intro/target-key-concepts.md) |
| Créez des audiences, si nécessaire. | [Création d’un public](/help/main/c-target/c-audiences/create-audience.md) |
| Combinez plusieurs audiences, si nécessaire. | [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md) |
| Appliquez les audiences sur la page Objectifs et paramètres. | Test A/B : [Objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization : [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Ciblage d’expérience : [Objectifs et paramètres](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Test multivarié : [Objectifs et paramètres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations : [Paramètres d’activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Paramètres d’activité : [Paramètres d’activité](/help/main/c-activities/activity-settings.md) |
| Affichez les rapports qui contiennent des informations sur vos filtres d’audiences. | [Paramètres des rapports](/help/main/c-reports/c-report-settings/report-settings.md) |
