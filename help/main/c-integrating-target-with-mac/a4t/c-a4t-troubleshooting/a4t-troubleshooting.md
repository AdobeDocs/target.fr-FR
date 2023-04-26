---
keywords: serveur de suivi analytics;A4T;segments analytics;suites de rapports;données incorrectes;orphelin;sdid;VisitorAPI.js;mboxMCSDID;fantôme;non spécifié
description: Explorez les problèmes courants rencontrés par les clients lors de l’utilisation d’Analytics for  [!DNL Target]  (A4T).
title: Comment résoudre les problèmes d’intégration d’Analytics et de  [!DNL Target]  (A4T) ?
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: ht
source-wordcount: '960'
ht-degree: 100%

---

# Résolution des problèmes d’intégration d’Analytics et de [!DNL Target] (A4T)

Cette rubrique aborde certains problèmes courants qui se produisent lors de l’utilisation d’[!DNL Adobe Analytics] comme source de création des rapports pour [!DNL Adobe Target] (A4T).

## Les activités n’affichent pas de données dans Analytics, mais sont répertoriées comme « non spécifiées ». {#unspecified}

Il existe plusieurs raisons pour lesquelles les données s’affichent comme « non spécifiées » :

* La classification dans [!DNL Target] n’a pas été entièrement traitée.

   La classification prend généralement entre 24 et 72 heures pour classer les rapports après le premier enregistrement.

* La suite de rapports ne contient aucune donnée, mais [!DNL Target] a tenté de classer les accès. [!DNL Target] ne peut pas classer les données tant que le premier accès n’a pas eu lieu.

   Assurez-vous que la suite de rapports compte au moins un accès.

* L’appel à la classification de [!DNL Target] à [!DNL Analytics] a échoué.

   [Contactez l’Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir de l’aide.

Si vous ventilez la ligne « non spécifié » par la dimension « Analytics for Target » et qu’elle ne contient aucun ID d’activité, cela signifie que tout est classé correctement. Si les ID d’activité y sont répertoriés, cela indique un problème de classification.

>[!NOTE]
>
>Il arrive parfois que les données s’affichent correctement dans les rapports, mais qu’elles redeviennent « non spécifiées » car une nouvelle activité a été ajoutée sans que la classification ait été terminée. N’oubliez pas que le classement des rapports après le premier enregistrement prend généralement entre 24 et 72 heures.
>
>Remarque : Aucune donnée n’est perdue si les données sont répertoriées comme « non spécifiées ». Les données sont correctement affectées à l’activité ou à l’expérience appropriée une fois la classification exécutée.

## Les rapports d’activité A4T comprennent une ligne avec de nombreux événements « non spécifiés ». {#added_unspecified_events}

Votre rapport peut contenir une ligne d’événements « [!UICONTROL Non spécifiés] », selon la mesure que vous utilisez pour afficher vos données.

En règle générale, cette ligne s’affiche si vous choisissez une mesure commune dans le rapport qui n’est pas spécifique à [!DNL Target] (par exemple, [!UICONTROL Pages vues], [!UICONTROL Visites], [!UICONTROL Visiteurs uniques], etc.). Dans ce cas, la ligne [!UICONTROL « Non spécifié »] comprend toutes les [!UICONTROL Pages vues], [!UICONTROL Visites], et [!UICONTROL Visiteurs uniques] qui ne sont pas associés aux activités [!DNL Target].

Cette ligne ne contient aucune information relative à [!DNL Target] (par exemple, aucun visiteur, aucune visite ou impression). Pour plus d’informations, consultez la section [« Non spécifié », « Aucun », « Autre » et « Inconnu » dans les rapports](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=fr) dans les *notes techniques d’Analytics*.

Si vous choisissez une mesure spécifique à [!DNL Target] dans le rapport, la ligne [!UICONTROL « Non spécifié »] ne s’affiche pas. La seule façon d’éviter de l’avoir dans le rapport consiste à définir un appel à [!DNL Target] à chaque requête envoyée à partir de cette page, ce qui n’est ni courant ni nécessaire.

## L’effet élévateur estimé dans les recettes ne présente pas les données appropriées. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Les détails de l’effet élévateur et de la confiance ne sont pas disponibles dans Analytics. Néanmoins, ils sont disponibles dans les rapports Target.

## Les activités n’apparaissent pas dans les rapports Analytics. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Les activités A4T exigent qu’un serveur de suivi Analytics soit spécifié. Pour vérifier que votre serveur de suivi Analytics est correctement configuré, consultez la page [Utilisation d’un serveur de suivi Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

>[!NOTE]
>
>Vous n’avez pas besoin de spécifier de serveur de suivi lors de la création de l’activité si vous utilisez la version 0.9.1 d’at.js (ou ultérieure). La bibliothèque at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## Mes segments Analytics n’apparaissent pas dans Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Vérifiez que vous disposez des autorisations adéquates avant de créer des activités A4T.

* Vous devez être membre du groupe d’accès aux services web dans Adobe Analytics pour pouvoir utiliser Analytics en tant que source de création de rapports pour Target.
* Vous devez être membre d’un ou plusieurs groupes Experience Cloud ayant accès à Analytics et Target.
* Vérifiez qu’Analytics et Target s’affichent dans la section Applications marketing située dans la barre de navigation gauche.

## Les mesures des taux de rebond, des rebonds et des sorties apparaissent comme valeurs positives dans les rapports. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Ces mesures qui apparaissent comme positives dans les rapports sont un problème connu.

Bien que ces mesures soient négatives, l’effet élévateur s’affiche comme si elles étaient positives dans les rapports Target. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

## La suite de rapports dont j’ai besoin ne s’affiche pas. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La liste des suites de rapports qui apparaît dans [!DNL Target Standard/Premium] est la liste des suites de rapports qui ont été configurées pour [!DNL Analytics] en tant que source des rapports pour [!DNL Target] (A4T). Il se peut que vous ne voyiez pas toutes les suites de rapports que vous détenez.

Si vous utilisez plusieurs sources de rapports, les suites de rapports doivent aussi être présentes dans la source de rapports par défaut définie dans [!DNL Target]. Si les suites de rapports ne figurent pas dans la source de rapports par défaut, elles ne s’affichent pas.

Si la suite de rapports que vous recherchez ne s’affiche toujours pas, contactez le [service clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour qu’ils l’activent.

## Je ne vois pas autant de données que prévu dans les rapports. {#section_75002584FA63456D8D9086172925DD8D}

Passez en revue votre mise en œuvre, en particulier sur les pages où les visiteurs répondent aux critères des expériences et vérifiez la correspondance des ID de données supplémentaires dans les appels à [!DNL Target] et à [!DNL Analytics]. 

* **at.js 1.x** : dans l’appel à [!DNL Target], l’ID supplémentaire est contenu dans le paramètre `mboxMCSDID`. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.
* **at.js 2.x** : dans l’appel à [!DNL Target], l’ID supplémentaire est renvoyé dans l’en-tête HTTP comme valeur pour `experienceCloud.analytics.supplementalDataId`. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.

La méthode la plus simple pour examiner l’ID supplémentaire est d’utiliser le débogueur Adobe Experience Platform.

Si vous n’avez pas installé le débogueur, consultez la page [Présentation du débogueur Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html?lang=fr).

![Débogueur](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

Si aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Target], vérifiez que le fichier [!DNL VisitorAPI.js] est chargé avant [!DNL at.js]. S’il aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Analytics], vérifiez que l’appel à [!DNL Target] se déclenche avant l’appel à [!DNL Analytics].

Pour plus d’informations, voir [Analytics pour implémentation de Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou contactez le [Service d’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
