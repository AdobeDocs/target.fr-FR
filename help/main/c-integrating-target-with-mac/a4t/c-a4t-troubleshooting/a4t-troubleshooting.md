---
keywords: serveur de suivi analytics;A4T;segments analytics;suites de rapports;données incorrectes;orphelin;sdid;VisitorAPI.js;mboxMCSDID;fantôme;non spécifié
description: Explorez les problèmes courants rencontrés par les clients lors de l’utilisation d’Analytics pour [!DNL Target] (A4T).
title: Comment résoudre les problèmes liés à Analytics et [!DNL Target] Intégration (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 39%

---

# Résolution des problèmes d’Analytics et de [!DNL Target] intégration (A4T)

Cette rubrique aborde certains problèmes courants qui se produisent lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Les activités n’affichent pas de données dans Analytics, mais sont répertoriées comme « non spécifiées ». {#unspecified}

Il existe plusieurs raisons pour lesquelles les données s’affichent comme &quot;non spécifié&quot; :

* La classification dans [!DNL Target] n’a pas été entièrement traitée.

   La classification prend généralement de 24 à 72 heures pour classer les rapports après le premier enregistrement.

* La suite de rapports ne contient aucune donnée, mais [!DNL Target] a tenté de classer les accès. [!DNL Target] ne peut pas classer les données tant que le premier accès n’a pas eu lieu.

   Assurez-vous que la suite de rapports compte au moins un accès.

* L’appel à la classification de [!DNL Target] à [!DNL Analytics] a échoué.

   [Contactez l’Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir de l’aide.

Si vous ventilez la ligne &quot;non spécifié&quot; par la dimension &quot;Analytics pour Target&quot; et qu’elle ne contient aucun ID d’activité, cela signifie que tout est correctement classé. Si les ID d’activité y sont répertoriés, cela sert d’indication pour un problème de classification.

>[!NOTE]
>
>Il arrive que les données s’affichent correctement dans les rapports, mais qu’elles redeviennent &quot;non spécifiées&quot;, car une nouvelle activité a été ajoutée sans que la classification n’ait été terminée. N’oubliez pas que la classification des rapports après le premier enregistrement prend généralement entre 24 et 72 heures.
>
>Remarque : Aucune donnée n’est perdue si les données sont répertoriées comme « non spécifiées ». Les données sont correctement affectées à l’activité ou à l’expérience appropriée une fois la classification exécutée.

## Les rapports d’activité A4T incluent une ligne avec de nombreux événements &quot;non spécifiés&quot;. {#added_unspecified_events}

Il peut y avoir une[!UICONTROL Non spécifié]&quot;ligne d’événements affichée dans votre rapport, en fonction de la mesure avec laquelle vous utilisez pour afficher vos données.

En règle générale, cette ligne s’affiche si vous choisissez une mesure commune dans le rapport qui n’est pas [!DNL Target]spécifique (par exemple, [!UICONTROL Pages vues], [!UICONTROL Visites], [!UICONTROL Visiteurs uniques], etc.). Dans ce cas, la variable [!UICONTROL &quot;Non spécifié&quot;] comprend toutes les [!UICONTROL Pages vues], [!UICONTROL Visites], et [!UICONTROL Visiteurs uniques] qui ne sont pas associés à [!DNL Target] activités.

Cette ligne n’aura aucune [!DNL Target]- informations associées (par exemple, aucun visiteur, aucune visite ou impression). Pour plus d’informations, voir [&quot;Non spécifié&quot;, &quot;Aucun&quot;, &quot;Autre&quot; et &quot;Inconnu&quot; dans les rapports](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) dans le *Notes techniques d’Analytics*.

Si vous choisissez un [!DNL Target]mesure spécifique dans le rapport, que [!UICONTROL &quot;Non spécifié&quot;] ne s’affiche pas. La seule façon d’éviter de l’inclure dans le rapport consiste à définir une [!DNL Target] appel à chaque requête envoyée à partir de cette page, ce qui n’est pas courant ou nécessaire.

## Mes données Analytics présentent un nombre exagéré de visiteurs ou de visites depuis le démarrage de A4T. {#section_4BE374E573D44FB7918611699B74F58E}

Pour plus d’informations, voir [Minimiser le nombre de visites et de visiteurs gonflés au format A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## L’effet élévateur estimé dans les recettes ne présente pas les données appropriées. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Les détails de l’effet élévateur et de la confiance ne sont pas disponibles dans Analytics. Néanmoins, ils sont disponibles dans les rapports Target.

## Les activités n’apparaissent pas dans les rapports Analytics. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Les activités de A4T exigent qu’un serveur de suivi Analytics soit spécifié. Voir [Utilisation d’un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) pour vous assurer que votre serveur de suivi Analytics est configuré correctement.

>[!NOTE]
>
>Vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## Mes segments Analytics n’apparaissent pas dans Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Vérifiez que vous disposez des autorisations adéquates avant de créer des activités A4T.

* Appartenant au groupe d’accès aux services Web dans Adobe Analytics pour pouvoir utiliser Analytics comme source de création de rapports pour Target
* Faites partie d’un ou de plusieurs groupes d’Experience Cloud ayant accès à Analytics et Target.
* Vérifiez qu’Analytics et Target s’affichent dans la section Applications marketing située dans la barre de navigation gauche.

## Les mesures des taux de rebond, des rebonds et des sorties apparaissent comme valeurs positives dans les rapports. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Ces mesures qui apparaissent comme positives dans les rapports sont un problème connu.

Bien que ces mesures soient négatives, l’effet élévateur s’affiche comme si elles étaient positives dans les rapports Target. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

## La suite de rapports dont j’ai besoin ne s’affiche pas. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La liste des suites de rapports qui apparaît dans [!DNL Target Standard/Premium] est la liste des suites de rapports qui ont été configurées pour [!DNL Analytics] comme source de création de rapports pour [!DNL Target] (A4T). Il se peut que vous ne voyiez pas toutes les suites de rapports que vous détenez.

Si vous utilisez plusieurs sources de création de rapports, les suites de rapports doivent être présentes dans la source de création de rapports par défaut définie dans [!DNL Target] ainsi que . Si les suites de rapports ne figurent pas dans la source de création de rapports par défaut, elles ne s’affichent pas.

Si vous ne voyez toujours pas la suite de rapports que vous recherchez, contactez [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour l’activer.

## Je ne vois pas autant de données que prévu dans les rapports. {#section_75002584FA63456D8D9086172925DD8D}

Passez en revue votre mise en œuvre, en particulier sur les pages où les visiteurs répondent aux critères des expériences et vérifiez la correspondance des ID de données supplémentaires dans les appels à [!DNL Target] et à [!DNL Analytics]. 

* **at.js 1.x**: Dans le [!DNL Target] , l’ID supplémentaire est contenu dans la variable `mboxMCSDID` . Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.
* **at.js 2.x**: Dans le [!DNL Target] , l’ID supplémentaire est renvoyé dans l’en-tête HTTP comme valeur pour `experienceCloud.analytics.supplementalDataId`. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.

La méthode la plus simple pour examiner l’ID supplémentaire consiste à utiliser le débogueur Adobe Experience Platform.

Si vous n’avez pas installé le débogueur, voir [Présentation du débogueur Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Débogueur](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

S’il n’existe aucun ID de données supplémentaire dans la variable [!DNL Target] appelez, confirmez que la variable [!DNL VisitorAPI.js] Le fichier est chargé avant [!DNL at.js]. S’il aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Analytics], vérifiez que l’appel à [!DNL Target] se déclenche avant l’appel à [!DNL Analytics].

Pour plus d’informations, voir [Analytics pour implémentation de Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou contactez le [Service d’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
