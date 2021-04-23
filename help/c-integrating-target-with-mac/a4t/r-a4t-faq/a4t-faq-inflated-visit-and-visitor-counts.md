---
keywords: faq;questions fréquentes;analytics for target;a4T;exagéré;visite;visiteur;accès partiel;orphelin;accès partiel
description: Trouvez des réponses aux questions sur le nombre de visites et de visiteurs exagéré lors de l’utilisation d’Analytics pour  [!DNL Target] (A4T). Découvrez comment réduire les "données partielles".
title: Où puis-je trouver des FAQ sur le nombre de visites exagéré et de Visiteurs avec A4T ?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 61%

---

# FAQ sur le nombre exagéré de visiteurs ou de visites - A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Pourquoi mes données Analytics présentent-elles des visites qui n’ont pas de pages vues ni d’autres valeurs variables ?{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

Lorsque [!DNL Adobe Analytics] est utilisé pour mesurer les activités [!DNL Target] (appelée A4T), [!DNL Analytics] collecte des données qui ne sont pas disponibles lorsqu&#39;il n&#39;y a pas d&#39;activité [!DNL Target] sur la page. Cela est dû au fait que l’activité [!DNL Target] déclenche un appel en haut de la page, tandis qu’[!DNL Analytics] déclenche généralement ses appels de collecte de données au bas de la page. Dans l’implémentation d’A4T à ce jour, l’Adobe inclut ces données supplémentaires chaque fois qu’une activité [!DNL Target] était principale.

Pour plus d’informations, voir [Minimiser le nombre de visites et de visiteurs gonflés au format A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Qu’est-ce qu’un accès à données partielles ?{#section_59A203E289564576BF6821F96B0B9E11}

Un accès à données partielles survient lorsqu’une balise [!DNL Target] située en haut de la page se déclenche mais qu’une balise [!DNL Analytics] située au bas de la page ne se déclenche pas. Il y a plusieurs raisons à cette situation. Dans l&#39;implémentation de [!DNL A4T] à ce jour, l&#39;Adobe inclut des données partielles sur ces accès chaque fois qu&#39;une activité [!DNL Target] était principale. À l’avenir, l’Adobe n’inclura ces données supplémentaires que lorsque les balises [!DNL Target] et [!DNL Analytics] auront été déclenchées.

Pour plus d’informations, voir [Minimisation du nombre de visiteurs et de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate un pic du nombre de visites. Comment puis-je savoir si ces visites sont provoquées par des accès à données partielles ? {#section_28506672C6224ED18AC74F6A02F6F811}

Vous pouvez contacter [le service à la clientèle Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour récupérer un rapport Données partielles. Ces informations ne sont pas disponibles directement dans l’interface utilisateur [!DNL Analytics].

## Quelles sont les causes possibles des accès à données partielles ?{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Les accès à données partielles résultent souvent d’une implémentation incorrecte, par exemple en cas d’identifiants de suites de rapports mal alignés. Il existe également des causes légitimes telles que les pages lentes, les erreurs de page, les offres de redirection dans une activité ou les versions de bibliothèque obsolètes.

Plus d’informations, reportez-vous à la section « Quelles sont les causes des données partielles » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate la présence d’accès à données partielles. Que puis-je faire pour nettoyer mes données ? {#section_CBE778A9D07A469E8FF98F68BACC7124}

Vous pouvez créer une suite de rapports virtuelle pour exclure les données partielles historiques de vos rapports.

Pour plus d’informations, reportez-vous à la section « Comment puis-je afficher les tendances historiques sans les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Que puis-je faire pour empêcher mes pages de générer des accès à données partielles ?{#section_4B00E7E618444BE98A0798DE98F08B21}

Après le 14 novembre 2016, l’Adobe n’inclura les données que lorsque les balises [!DNL Target] et [!DNL Analytics] ont toutes deux été déclenchées. Cette modification n’est pas rétroactive. Si vos rapports historiques indiquent des comptes exagérés, vous pouvez les exclure de vos rapports en créant une suite de rapports virtuelle. Voir &quot;Comment puis-je Vue les tendances historiques sans données partielles ?&quot; dans [Minimisation du nombre de visites et de Visiteurs exagéré dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Il existe également des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Si les données d’accès à données partielles sont supprimées du rapports, ne perdez-vous pas les [!DNL Target] données importantes ou les données Analytics ? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

L&#39;inclusion de données partielles dans le rapports [!DNL Analytics] fournit des informations supplémentaires, mais crée également une incohérence avec les données historiques des périodes où aucune activité [!DNL Target] n&#39;était en cours d&#39;exécution. L’inclusion de données d’accès partiel peut poser des problèmes aux utilisateurs [!DNL Analytics] qui analysent les tendances au fil du temps.

Il existe des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Existe-t-il des types particuliers d&#39;activités [!DNL Target] qui sont plus susceptibles de provoquer des accès à données partielles ? {#section_69837442A9B84366BEFDA4588B31E574}

Les offres de redirection redirigent immédiatement l’utilisateur vers une page différente, ce qui signifie que l’appel [!DNL Analytics] ne se déclenche pas sur la première page.
