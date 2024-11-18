---
keywords: audiences multiples, versions d’expérience, ciblage de versions d’expérience
description: Découvrez comment cibler différents segments d’audience avec des versions de la même expérience dans des activités A/B.
title: Puis-je utiliser plusieurs versions d’expérience dans une activité A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 791423e3-c748-4771-b824-c5ba6d3d6c32
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 52%

---

# Audiences d’expériences multiples dans un test A/B

Vous pouvez cibler des versions d’une même expérience sur différentes audiences dans des activités A/B [!DNL Adobe Target]. Vous pouvez configurer plusieurs audiences pour une expérience dans le [!UICONTROL Visual Experience Composer] (VEC) ou dans le compositeur d’expérience d’après les formulaires.

Les visiteurs peuvent basculer entre les audiences d’expérience à mesure que leur profil change. Les visiteurs ne sont pas bloqués dans la même expérience pendant la durée de vie de l’activité.

Par exemple, si votre site utilise un design cohérent pour différentes pages ou produits, et que vous souhaitez utiliser la même expérience pour des audiences multiples (comme des visiteurs utilisant des navigateurs dans des langues différentes), vous pouvez définir plusieurs versions de cette expérience. Vous pourriez présenter la même expérience aux utilisateurs de langue anglaise ou japonaise, avec la langue du texte pour seule différence. Les données sont collectées pour l’expérience, indépendamment de la langue, et le rapport relate donc les performances de l’expérience, sans prendre en compte la version.

Ne pouvant pas définir de versions d’expérience, vous devriez définir différents tests pour chaque langue (dans le cadre de cet exemple), puis rassembler manuellement les résultats afin d’obtenir une idée sur la manière dont une expérience unique en deux langues pourrait s’exécuter. Cette option conduit à des résultats moins précis. Dans le cadre de certains tests, ces calculs pourraient même s’avérer être inutiles en raison de la manière dont les visiteurs sont sélectionnés de manière aléatoire.

En créant différentes versions d’une expérience, vous recevez des informations plus précises, en évitant d’avoir à effectuer des calculs ou des suppositions manuelles.

## Scénario

Vous testez deux expériences, une bannière géociblée et une bannière générique. La bannière de chaque zone géographique doit être différente, mais le test global consiste à déterminer si le géociblage est préférable à l’affichage de contenu générique. Si vous configurez une expérience distincte pour chaque emplacement, vous allez en fait mesurer les performances de chaque géo par rapport à l’autre, plutôt que de déterminer si le géociblage permet d’atteindre vos objectifs de succès en les comparant à la bannière générique.

Dans ce cas, vous avez besoin de versions de l’expérience spécifiques à la zone géographique afin de pouvoir tester l’expérience géociblée par rapport à un contrôle non géociblé.

1. [Créez une activité A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) comme vous le feriez normalement.

   Lors de la configuration de l’expérience aux multiples versions, sélectionnez l’audience de chaque version tel que décrit dans la procédure suivante.

1. Sélectionnez l’expérience, puis cliquez sur **[!UICONTROL Configure]** > **[!UICONTROL Multiple Audiences]**.

1. Cliquez sur l’icône **[!UICONTROL Add Audience]** ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) dans le volet [!UICONTROL Experience Audiences], puis sélectionnez la première audience que vous souhaitez cibler. Reproduisez cette procédure pour chaque audience.

   Si l’audience n’existe pas encore, cliquez sur [Créer une audience](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558) et configurez-la.

   Lorsqu’un visiteur répond aux critères de plusieurs audiences, le contenu de l’ensemble de ces audiences est transmis, mais seul le dernier de la liste apparaît véritablement sur la page.

1. Poursuivre la configuration de l’activité.

## Bonnes pratiques

* Choisissez des audiences mutuellement exclusives. Si l’activité a été créée dans le compositeur d’expérience visuelle, si un visiteur correspond à plusieurs audiences, le contenu de chaque audience est renvoyé, le contenu de l’audience étant répertorié pour la dernière fois s’affichant sur la page.
* Les audiences d’entrée d’activité définies dans le diagramme sont combinées aux audiences d’expérience en utilisant la condition ET. Pour accéder à une activité, le visiteur doit répondre aux critères d’audience de l’activité et à ceux de l’une des audiences d’expérience.
* Ajout des mêmes audiences en tant que segment pour la création de rapports. Vous pouvez ainsi consulter les résultats du test au niveau élevé de l’expérience A par rapport à B, et au niveau inférieur de l’expérience A par rapport à B pour le simple &quot;lang du navigateur ja_JP&quot;. Cela fonctionne uniquement pour les rapports basés sur [!DNL Target] et non sur [!DNL Analytics].
