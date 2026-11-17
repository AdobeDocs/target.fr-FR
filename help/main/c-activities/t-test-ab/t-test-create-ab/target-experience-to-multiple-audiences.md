---
keywords: audiences multiples, versions d’expérience, ciblage de versions d’expérience
description: Découvrez comment cibler différents segments d’audience avec des versions de la même expérience dans des activités A/B.
title: Puis-je utiliser plusieurs versions d’expérience dans une activité A/B ?
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
TQID: 'https://experienceleague.adobe.com/FleyH-u5cWI5vku9E4-RMWeIc95WgPy-VQ-eytxka18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 8%
---
# Audiences d’expériences multiples dans un test A/B {#multiple-experience-audiences}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment cibler différentes audiences avec des versions de la même expérience dans une activité A/B, illustré par un cas d’utilisation avec les étapes à suivre et les bonnes pratiques.

>[!ENDSHADEBOX]

Dans les activités A/B [!DNL Adobe Target], vous pouvez cibler des versions d’une même expérience sur différentes audiences. Vous pouvez configurer plusieurs audiences pour une expérience dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) ou dans le compositeur d’expérience d’après les formulaires.

Les données sont collectées pour l’expérience, quelle que soit la version. Le rapport présente donc les performances de l’expérience, et non de chaque version. Les visiteurs peuvent également basculer entre les audiences d’expérience à mesure que leur profil change. Ils ne sont pas bloqués dans la même expérience pendant toute la durée de vie de l’activité.

## Cas d’utilisation {#use-case}

Vous testez deux expériences :

* une bannière géociblée

* une bannière générique.

La bannière de chaque zone géographique doit être différente, mais l’objectif du test est de déterminer si le géociblage fonctionne mieux que le contenu générique.

Si vous configurez une expérience distincte pour chaque emplacement, vous mesurez les performances de chaque zone géographique par rapport aux autres. Vous ne mesurez pas si le géo-ciblage permet d’atteindre vos objectifs de succès par rapport à la bannière générique.

Dans ce cas, vous avez besoin de versions de l’expérience spécifiques à une zone géographique, afin de pouvoir tester l’expérience géociblée par rapport à un contrôle non géociblé.

Pour configurer les versions spécifiques à une zone géographique :

1. [Créez une activité A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) comme vous le feriez normalement.

   Lorsque vous configurez une expérience qui comporte plusieurs versions, sélectionnez l’audience pour chaque version, comme décrit dans les étapes suivantes.

1. Sélectionnez l’expérience, puis cliquez sur **[!UICONTROL Configurer]** > **[!UICONTROL Audiences multiples]**.

1. Dans le volet **[!UICONTROL Audiences d’expérience]**, cliquez sur l’icône **[!UICONTROL Ajouter une audience]** ( ![Icône Ajouter](/help/main/assets/icons/Add.svg) ), puis sélectionnez la première audience que vous souhaitez cibler. Reproduisez cette procédure pour chaque audience.

   Si l’audience n’existe pas encore, [créez-la](/help/main/c-target/c-audiences/create-audience.md) et configurez-la.

1. Poursuivre la configuration de l’activité.

## Bonnes pratiques {#best-practices}

* Choisissez des audiences s’excluant mutuellement. Si un visiteur est admissible pour plusieurs audiences, le contenu de toutes ces audiences est renvoyé et le contenu de la dernière audience répertoriée s’affiche sur la page. Cela s’applique aux activités créées dans le compositeur d’expérience visuelle.
* Les audiences d’entrée d’activité définies dans le diagramme sont combinées aux audiences d’expérience à l’aide d’une condition AND. Pour rejoindre l’activité, un visiteur doit être qualifié pour l’audience de l’activité et pour l’une des audiences de l’expérience.
* Ajout des mêmes audiences en tant que segment pour la création de rapports. Cela vous permet d’examiner les résultats du test au niveau élevé de l’expérience A par rapport à B, et au niveau inférieur de l’expérience A par rapport à B uniquement pour « browser lang ja_JP ». Cela fonctionne uniquement pour les rapports basés sur [!DNL Target], et non pour les rapports basés sur [!DNL Analytics].
