---
keywords: serveur de suivi analytics;A4T;segments analytics;suites de rapports;données incorrectes;orphelin;sdid;VisitorAPI.js;mboxMCSDID;fantôme;non spécifié
description: Découvrez les problèmes courants rencontrés par les clients lors de l’utilisation d’Analytics pour  [!DNL Target] (A4T).
title: Dépannage d’Analytics et de l’intégration  [!DNL Target] Comment puis-je résoudre le problème (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 42%

---

# Résolution des problèmes d’intégration Analytics et [!DNL Target] (A4T)

Cette rubrique aborde certains problèmes courants qui se sont produits lors de l’utilisation de [!DNL Adobe Analytics] comme source de rapports pour [!DNL Adobe Target] (A4T).

## Les activités n’affichent pas de données dans Analytics, mais sont répertoriées comme « non spécifiées ».{#unspecified}

Il existe plusieurs raisons pour lesquelles les données peuvent apparaître comme &quot;non spécifiées&quot; :

* La classification dans [!DNL Target] n’a pas été entièrement traitée.

   La classification prend généralement de 24 à 72 heures pour classer les rapports après le premier enregistrement.

* La suite de rapports ne contient aucune donnée, mais [!DNL Target] a tenté de classer les accès. [!DNL Target] ne peut pas classer les données tant que le premier accès n’a pas eu lieu.

   Assurez-vous que la suite de rapports compte au moins un accès.

* L’appel à la classification de [!DNL Target] à [!DNL Analytics] a échoué.

   [Contactez l’Assistance clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir de l’aide.

Si vous ventilez la ligne &quot;non spécifiée&quot; par la dimension &quot;Analyses pour la Cible&quot; et qu’elle ne contient aucun identifiant d’activité, cela signifie que tout est correctement classifié. Si les identifiants d’activité y sont répertoriés, cela sert d’indication pour un problème de classification.

>[!NOTE]
>
>Il arrive que les données s’affichent correctement dans les rapports, puis qu’elles redeviennent &quot;non spécifiées&quot;, car une nouvelle activité ajoutée n’a pas encore terminé la classification. Rappelez-vous qu’il faut généralement de 24 à 72 heures pour classer les rapports après le premier enregistrement.
>
>Remarque : Aucune donnée n’est perdue si les données sont répertoriées comme « non spécifiées ». Les données sont correctement affectées à l’activité ou à l’expérience appropriée une fois la classification exécutée.

## Les rapports d’Activité A4T incluent une ligne avec de nombreux événements &quot;non spécifiés&quot;. {#added_unspecified_events}

Une ligne de événements &quot;[!UICONTROL Non spécifié]&quot; peut s’afficher dans votre rapport, selon la mesure utilisée pour afficher vos données.

En règle générale, cette ligne s’affiche si vous choisissez une mesure commune dans le rapport qui n’est pas spécifique à [!DNL Target] (par exemple, [!UICONTROL Vues de page], [!UICONTROL Visites], [!UICONTROL Visiteurs uniques], etc.). Dans ce cas, la ligne [!UICONTROL &quot;Non spécifié&quot;] comprend toutes les [!UICONTROL Vues de page], [!UICONTROL Visites] et [!UICONTROL Visiteurs uniques] qui ne sont pas associés aux activités [!DNL Target].

Cette ligne n’est associée à aucune information [!DNL Target] (par exemple, aucun visiteur, aucune visite ou aucune impression). Pour plus d’informations, voir [&quot;Non spécifié&quot;, &quot;Aucun&quot;, &quot;Autre&quot; et &quot;Inconnu&quot; dans rapports](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) dans les *notes techniques Analytics*.

Si vous choisissez une mesure [!DNL Target] spécifique dans le rapport, cette ligne [!UICONTROL &quot;Non spécifié&quot;] ne s’affiche pas. Le seul moyen d&#39;éviter de l&#39;inclure dans le rapport consiste à définir un appel [!DNL Target] sur chaque requête envoyée à partir de cette page, ce qui n&#39;est pas courant ni nécessaire.

## Mes données Analytics présentent un nombre exagéré de visiteurs ou de visites depuis le démarrage de A4T. {#section_4BE374E573D44FB7918611699B74F58E}

Pour plus d’informations, voir [Minimisation du nombre de visiteurs et de visites exagérés dans A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## L’effet élévateur estimé dans les recettes ne présente pas les données appropriées. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Les détails de l’effet élévateur et de la confiance ne sont pas disponibles dans Analytics. Néanmoins, ils sont disponibles dans les rapports Target.

## Les activités n’apparaissent pas dans les rapports Analytics.  {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Les activités de A4T exigent qu’un serveur de suivi Analytics soit spécifié. Voir [Utilisation d’un serveur de suivi Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) pour vous assurer que votre serveur de suivi Analytics est configuré correctement.

>[!NOTE]
>
>Il n’est pas nécessaire de spécifier un serveur de suivi lors de la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## Mes segments Analytics n’apparaissent pas dans Target.  {#section_DEE87F1557834F448E99381D3D02EEEF}

Vérifiez que vous disposez des autorisations adéquates avant de créer des activités A4T.

* Appartenant au groupe Accès aux services Web en Adobe Analytics pour pouvoir utiliser Analytics en tant que source de rapports pour la Cible
* Faites partie d’un ou de plusieurs groupes d’Experience Cloud qui ont accès à Analytics et à la Cible.
* Vérifiez qu’Analytics et Target s’affichent dans la section Applications marketing située dans la barre de navigation gauche.

## Les mesures des taux de rebond, des rebonds et des sorties apparaissent comme valeurs positives dans les rapports.  {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Ces mesures apparaissant comme positives dans les rapports sont un problème connu.

Bien que ces mesures soient négatives, l’effet élévateur s’affiche comme si elles étaient positives dans les rapports Target. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

## La suite de rapports dont j’ai besoin ne s’affiche pas. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La liste des suites de rapports qui s’affiche dans [!DNL Target Standard/Premium] correspond à la liste des suites de rapports qui ont été configurées pour [!DNL Analytics] en tant que source de rapports pour [!DNL Target] (A4T). Il se peut que vous ne voyiez pas toutes les suites de rapports que vous détenez.

Si vous utilisez plusieurs sources de rapports, les suites de rapports doivent également être présentes dans la source de rapports par défaut définie dans [!DNL Target]. Si les suites de rapports ne se trouvent pas dans la source de rapports par défaut, elles ne s’affichent pas.

Si vous ne voyez toujours pas la suite de rapports que vous recherchez, contactez le [service à la clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour l’activer.

## Je ne vois pas autant de données que prévu dans les rapports. {#section_75002584FA63456D8D9086172925DD8D}

Passez en revue votre mise en œuvre, en particulier sur les pages où les visiteurs répondent aux critères des expériences et vérifiez la correspondance des ID de données supplémentaires dans les appels à [!DNL Target] et à [!DNL Analytics]. 

* **at.js 1.x** : Dans l’ [!DNL Target] appel, l’ID supplémentaire est contenu dans le  `mboxMCSDID` paramètre. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.
* **at.js 2.x** : Dans l’ [!DNL Target] appel, l’ID supplémentaire est renvoyé dans l’en-tête HTTP en tant que valeur pour  `experienceCloud.analytics.supplementalDataId`. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.

Le moyen le plus simple d’examiner l’ID supplémentaire consiste à utiliser le débogueur Adobe Experience Platform.

Si vous n’avez pas installé le débogueur, voir [Introduction au débogueur Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Débogueur](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

Si aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Target], vérifiez que le fichier [!DNL VisitorAPI.js] est chargé avant [!DNL at.js] ou [!DNL mbox.js]. S’il aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Analytics], vérifiez que l’appel à [!DNL Target] se déclenche avant l’appel à [!DNL Analytics].

Pour plus d’informations, voir [Analytics pour implémentation de Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou contactez le [Service d’assistance clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
