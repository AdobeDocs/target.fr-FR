---
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial hit;orphaned;orphan;partial-hit
description: Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).
title: FAQ sur le nombre exagéré de visiteurs ou de visites - A4T
feature: null
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 100%

---


# FAQ sur le nombre exagéré de visiteurs ou de visites - A4T{#inflated-visit-and-visitor-counts-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Pourquoi mes données Analytics présentent-elles des visites qui n’ont pas de pages vues ni d’autres valeurs variables ?{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

Lorsqu’[!DNL Adobe Analytics] est utilisé pour mesurer les activités [!DNL Target] (sous le nom A4T), [!DNL Analytics] collecte des données supplémentaires qui ne sont pas disponibles lorsqu’il n’y a pas d’activité [!DNL Target] sur la page. Cela est dû au fait que l’activité [!DNL Target] déclenche un appel en haut de la page, tandis qu’[!DNL Analytics] déclenche généralement ses appels de collecte de données au bas de la page. Dans l’implémentation d’A4T actuelle, nous avons inclus ces données supplémentaires chaque fois qu’une activité [!DNL Target] était active.

Pour plus d’informations, voir [Minimiser le nombre de visites et de visiteurs gonflés au format A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Qu’est-ce qu’un accès à données partielles ?{#section_59A203E289564576BF6821F96B0B9E11}

Un accès à données partielles survient lorsqu’une balise [!DNL Target] située en haut de la page se déclenche mais qu’une balise [!DNL Analytics] située au bas de la page ne se déclenche pas. Plusieurs raisons peuvent être à l’origine de ce phénomène. Dans l’implémentation d’[!DNL A4T] actuelle, nous avons inclus ces données supplémentaires chaque fois qu’une activité [!DNL Target] était active. À l’avenir, nous inclurons ces données supplémentaires uniquement en cas de déclenchement des balises [!DNL Target] et [!DNL Analytics].

Pour plus d’informations, voir [Minimisation du nombre de visiteurs et de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate un pic du nombre de visites. Comment puis-je savoir s’il est dû à des accès à données partielles ? {#section_28506672C6224ED18AC74F6A02F6F811}

Vous pouvez contacter [le service à la clientèle Adobe](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour récupérer un rapport Données partielles. Ces informations ne sont pas disponibles directement dans l’interface utilisateur [!DNL Analytics].

## Quelles sont les causes possibles des accès à données partielles ?{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Les accès à données partielles résultent souvent d’une implémentation incorrecte, par exemple en cas d’identifiants de suites de rapports mal alignés. Il existe également des causes légitimes telles que les pages lentes, les erreurs de page, les offres de redirection dans une activité ou les versions de bibliothèque obsolètes.

Plus d’informations, reportez-vous à la section « Quelles sont les causes des données partielles » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Je constate la présence d’accès à données partielles. Que puis-je faire pour nettoyer mes données ? {#section_CBE778A9D07A469E8FF98F68BACC7124}

Vous pouvez créer une suite de rapports virtuelle pour exclure les données partielles historiques de vos rapports.

Pour plus d’informations, reportez-vous à la section « Comment puis-je afficher les tendances historiques sans les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Que puis-je faire pour empêcher mes pages de générer des accès à données partielles ?{#section_4B00E7E618444BE98A0798DE98F08B21}

À compter du 14 novembre 2016, nous inclurons ces données supplémentaires uniquement en cas de déclenchement des balises [!DNL Target] et [!DNL Analytics]. Cette modification n’est pas rétroactive. Si vos rapports historiques indiquent des nombres exagérés et que vous souhaitez les exclure de vos rapports, vous pouvez créer une suite de rapports virtuelle, comme expliqué à la section « Comment puis-je afficher les tendances historiques sans les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Il existe également des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Si les données des accès à données partielles sont supprimées des rapports, ne perdons-nous pas des données Target ou Analytics importantes ?{#section_EBC39E8A0F6A40E58F51E776936F7D9E}

L’inclusion des données partielles dans les rapports [!DNL Analytics] fournit des informations supplémentaires, mais crée également des incohérences par rapport aux données historiques des périodes où aucune activité [!DNL Target] n’était active. Cela peut être source de problèmes pour les utilisateurs d’[!DNL Analytics] qui analysent les tendances qui se dégagent au fil du temps.

Il existe des mesures que vous pouvez prendre pour minimiser les accès à données partielles. Plus d’informations, reportez-vous à la section « Quelles sont les bonnes pratiques pour réduire les données partielles ? » dans [Minimisation du nombre de visiteurs ou de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Certains types particuliers d’activités Target sont-ils plus susceptibles de générer des accès à données partielles ?{#section_69837442A9B84366BEFDA4588B31E574}

Les offres de redirection redirigent immédiatement l’utilisateur vers une page différente, ce qui signifie que l’appel [!DNL Analytics] ne se déclenche pas sur la première page.
