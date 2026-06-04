---
keywords: Ciblage;filtre d’audience;audiences;filtre
description: Découvrez comment utiliser les filtres d’audience dans  [!DNL Adobe Target]  pour afficher les données des visiteurs qui partagent des caractéristiques .
title: Puis-je utiliser des filtres d’audience pour la création de rapports ?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
TQID: https://experienceleague.adobe.com/7h16ay64Y1IVu2CbkEJny-rnGms80q8X7G6gOM1P900
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2: id: b6f5758b-84f7-4943-8b05-1297a046943cid: e73b329c-f712-4a22-abe7-bfbf3be6d0f9id: ed58f4a1-16eb-4c8c-b505-be9da766a9ecid: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 59%

---

# Filtres d’audiences pour la création de rapports

Les filtres d’audience (ou audiences) dans [!DNL Adobe Target] sont des groupes de visiteurs qui partagent une caractéristique ou un ensemble de caractéristiques spécifique.

Appliquez des filtres d’audiences pour préciser quelles audiences utiliser pour la création de rapports. Vous pouvez sélectionner une audience et comparer ses performances au trafic général. Par exemple, vous voulez comprendre si vos gagnants sont différents pour diverses sources de trafic, par rapport au trafic général. Les filtres d’audience vous aident à découvrir les audiences qui doivent potentiellement cibler différents contenus. Le gagnant n’est généralement pas le même pour tous les trafics.

Par exemple, les visiteurs qui arrivent sur votre page à partir d’un certain moteur de recherche peuvent constituer une audience. D’autres audiences peuvent dépendre du sexe, de l’âge, de l’emplacement, de l’état de l’inscription, de l’historique des achats ou de tout autre détail collecté concernant vos visiteurs. Les filtres d’audiences permettent de diviser le trafic des visiteurs et de comparer les performances des expériences pour chaque segment de trafic.

Lorsque vous prévoyez d’utiliser des filtres d’audiences pour une activité, tenez compte des recommandations suivantes :

* **Les visiteurs peuvent appartenir à plusieurs audiences.** Si deux audiences sont configurées (par exemple, « nouveaux visiteurs » et « visiteurs de Google ») et qu’une personne répond aux deux critères, elle est comptabilisée et suivie dans les deux audiences. Ainsi, le total des visiteurs dans les audiences ne correspond pas au nombre de visiteurs d’une activité.
* **Configurez les audiences avant de lancer l’activité.** Les données d’audience ne peuvent pas être récupérées rétroactivement. Si vous ne configurez pas les filtres d’audiences avant de lancer l’activité, puis décidez finalement de les utiliser alors que l’activité est en cours d’exécution depuis quelque temps déjà, vous ne collecterez pas les données pendant la période déjà écoulée.
* **Commencez par deux à quatre audiences.** Concentrez-vous sur les informations de base, telles que la source du trafic.
* **Renommez les audiences selon les besoins.** Vous pouvez renommer une audience sans affecter les données afin que le nom de l’audience soit plus significatif pour les résultats collectés, même si l’activité est active.
* **Entrez des valeurs précises.** Les valeurs des filtres d’audience sont sensibles à la casse. Par exemple, si vous utilisez une audience qui filtre les villes, vous devez utiliser une condition « OU » afin d’inclure les variantes d’orthographe et de casse possibles, comme « Vienne », « vienne », « wien » et « Wien ».
* **Les audiences créées à partir de la liste [!UICONTROL Audiences] sont réutilisables.** Les audiences créées dans le cadre d’une activité ne peuvent pas être réutilisées.

Les sections ci-après fournissent davantage d’informations sur la configuration d’audiences et la création de rapports à leur sujet :

| Tâche | Rubrique |
|--- |--- |
| Créez l’activité ou le test approprié. | [Activités et tests](/help/main/c-intro/target-key-concepts.md) |
| Créez des audiences, si nécessaire. | [Création d’un audience](/help/main/c-target/c-audiences/create-audience.md) |
| Combinez plusieurs audiences, si nécessaire. | [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md) |
| Appliquez les audiences sur la page Objectifs et paramètres. | Test A/B : [Objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization : [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Ciblage d’expérience : [Objectifs et paramètres](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Test multivarié : [Objectifs et paramètres](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommandations : [Paramètres d’activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Paramètres d’activité : [Paramètres d’activité](/help/main/c-activities/activity-settings.md) |
| Affichez les rapports qui contiennent des informations sur vos filtres d’audiences. | [Paramètres des rapports](/help/main/c-reports/c-report-settings/report-settings.md) |
