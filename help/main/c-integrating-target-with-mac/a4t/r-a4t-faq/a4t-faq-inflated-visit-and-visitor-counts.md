---
keywords: faq;questions fréquentes;analytics for target;a4T;exagéré;visite;visiteur;accès partiel;orphelin;accès partiel
description: Trouvez des réponses aux questions sur le nombre exagéré de visiteurs ou de visites lors de l’utilisation d’Analytics pour [!DNL Target] (A4T). Découvrez comment réduire les "données partielles".
title: Où puis-je trouver des questions fréquentes sur le nombre exagéré de visiteurs ou de visites avec A4T ?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 61%

---

# FAQ sur le nombre exagéré de visiteurs ou de visites - A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Pourquoi mes données Analytics présentent-elles des visites qui n’ont pas de pages vues ni d’autres valeurs variables ? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

When [!DNL Adobe Analytics] est utilisé pour mesurer [!DNL Target] activités (appelées A4T), [!DNL Analytics] collecte des données qui ne sont pas disponibles lorsqu’il n’y a pas de [!DNL Target] activité sur la page. Cela est dû au fait que l’activité [!DNL Target] déclenche un appel en haut de la page, tandis qu’[!DNL Analytics] déclenche généralement ses appels de collecte de données au bas de la page. Dans l’implémentation d’A4T actuelle, l’Adobe inclut ces données supplémentaires chaque fois qu’une [!DNL Target] l&#39;activité était principale.

Pour plus d’informations, voir [Minimiser le nombre de visites et de visiteurs gonflés au format A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Qu’est-ce qu’un accès à données partielles ? {#section_59A203E289564576BF6821F96B0B9E11}

Un accès à données partielles survient lorsqu’une balise [!DNL Target] située en haut de la page se déclenche mais qu’une balise [!DNL Analytics] située au bas de la page ne se déclenche pas. Il y a plusieurs raisons à cette situation. Dans le [!DNL A4T] mise en oeuvre à ce jour, l’Adobe inclut des données partielles sur ces accès chaque fois qu’une [!DNL Target] l&#39;activité était principale. À l’avenir, Adobe inclura ces données supplémentaires uniquement lorsque la variable [!DNL Target] et [!DNL Analytics] les balises ont été déclenchées.

Pour plus d’informations, voir [Minimisation du nombre de visiteurs et de visites exagérés dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate un pic du nombre de visites. Comment puis-je savoir si ces visites sont causées par des accès à données partielles ? {#section_28506672C6224ED18AC74F6A02F6F811}

Vous pouvez contacter [le service à la clientèle Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour récupérer un rapport Données partielles. Ces informations ne sont pas disponibles directement dans l’interface utilisateur [!DNL Analytics].

## Quelles sont les causes possibles des accès à données partielles ? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Les accès à données partielles résultent souvent d’une implémentation incorrecte, par exemple en cas d’identifiants de suites de rapports mal alignés. Il existe également des causes légitimes telles que les pages lentes, les erreurs de page, les offres de redirection dans une activité ou les versions de bibliothèque obsolètes.

Plus d’informations, reportez-vous à la section « Quelles sont les causes des données partielles » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate la présence d’accès à données partielles. Que puis-je faire pour nettoyer mes données ? {#section_CBE778A9D07A469E8FF98F68BACC7124}

Vous pouvez créer une suite de rapports virtuelle pour exclure les données partielles historiques de vos rapports.

Pour plus d’informations, reportez-vous à la section « Comment puis-je afficher les tendances historiques sans les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Que puis-je faire pour empêcher mes pages de générer des accès à données partielles ? {#section_4B00E7E618444BE98A0798DE98F08B21}

À compter du 14 novembre 2016, Adobe inclura des données uniquement lorsque la variable [!DNL Target] et [!DNL Analytics] les balises ont été déclenchées. Cette modification n’est pas rétroactive. Si vos rapports historiques affichent des nombres exagérés, vous pouvez les exclure de vos rapports en créant une suite de rapports virtuelle. Voir &quot;Comment puis-je afficher les tendances historiques sans les données partielles ?&quot; in [Minimisation du nombre de visiteurs ou de visites exagéré dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Il existe également des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Si les données d’accès à données partielles sont supprimées des rapports, n’ai-je pas perdu de valeur ? [!DNL Target] ou les données Analytics ? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

Inclusion de données partielles dans [!DNL Analytics] les rapports fournissent des informations supplémentaires, mais ils créent également des incohérences par rapport aux données historiques des périodes où il n’y avait pas de [!DNL Target] activités en cours d’exécution. L’inclusion de données d’accès partiel peut entraîner des problèmes pour [!DNL Analytics] utilisateurs qui analysent les tendances au fil du temps.

Il existe des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Existe-t-il des types particuliers ? [!DNL Target] activités qui sont plus susceptibles de générer des accès à données partielles ? {#section_69837442A9B84366BEFDA4588B31E574}

Les offres de redirection redirigent immédiatement l’utilisateur vers une page différente, ce qui signifie que l’appel [!DNL Analytics] ne se déclenche pas sur la première page.
