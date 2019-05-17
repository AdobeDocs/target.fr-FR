---
description: Cette rubrique aborde certains problèmes courants qui se produisent lors de l’utilisation d’Analytics comme source de création des rapports pour Target (A4T).
keywords: serveur de suivi analytics;A4T;segments analytics;suites de rapports;données incorrectes;orphelin;sdid;VisitorAPI.js;mboxMCSDID;fantôme;non spécifié
seo-description: Cette rubrique aborde certains problèmes courants qui se produisent lors de l’utilisation d’Analytics comme source de création des rapports pour Target (A4T).
seo-title: Résolution des problèmes d’intégration d’Analytics et de Target (A4T)
solution: Target
subtopic: Test multivarié
title: Résolution des problèmes d’intégration d’Analytics et de Target (A4T)
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Résolution des problèmes d’intégration d’Analytics et de Target (A4T){#troubleshoot-the-analytics-and-target-integration-a-t}

Cette rubrique aborde certains problèmes courants qui se produisent lors de l’utilisation d’Analytics comme source de création des rapports pour Target (A4T).

## Les activités n’affichent pas de données dans Analytics, mais sont répertoriées comme « non spécifiées ».{#section_EB97F0499B0E40E69A21C30DC539BF67}

Plusieurs raisons peuvent être à l’origine de ce problème :

* La classification dans [!DNL Target] n’a pas été entièrement traitée.

   La classification peut prendre jusqu’à 24 heures à partir du premier enregistrement de l’activité.

* La suite de rapports ne contient aucune donnée, mais [!DNL Target] a tenté de classer les accès. [!DNL Target] ne peut pas classer les données tant que le premier accès n’a pas eu lieu.

   Assurez-vous que la suite de rapports compte au moins un accès.

* L’appel à la classification de [!DNL Target] à [!DNL Analytics] a échoué.

   [Contactez l’Assistance clientèle](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir de l’aide.

Il arrive parfois que les données s’affichent correctement dans les rapports, mais qu’elles redeviennent « non spécifiées » car une nouvelle activité a été ajoutée sans que la classification n’ait été terminée. Rappelez-vous que la classification des rapports peut prendre jusqu’à 24 heures après le premier enregistrement.

>[!NOTE]
>
>Remarque : Aucune donnée n’est perdue si les données sont répertoriées comme « non spécifiées ». Les données sont correctement affectées à l’activité ou à l’expérience appropriée une fois la classification exécutée.

## Mes données Analytics présentent un nombre exagéré de visiteurs ou de visites depuis le démarrage de A4T.  {#section_4BE374E573D44FB7918611699B74F58E}

Pour plus d’informations, voir [Minimisation du nombre de visiteurs et de visites exagérés dans A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## L’effet élévateur estimé dans les recettes ne présente pas les données appropriées. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Les détails de l’effet élévateur et de la confiance ne sont pas disponibles dans Analytics. Néanmoins, ils sont disponibles dans les rapports Target.

## Les activités n’apparaissent pas dans les rapports Analytics.  {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Les activités de A4T exigent qu’un serveur de suivi Analytics soit spécifié. Voir [Utilisation d’un serveur de suivi Analytics](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) pour s&#39;assurer que le serveur de suivi Analytics est correctement configuré.

>[!NOTE]
>
>Si vous utilisez Adobe Analytics comme source des rapports de votre activité, vous ne devez pas spécifier de serveur de suivi durant la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## Mes segments Analytics n’apparaissent pas dans Target.  {#section_DEE87F1557834F448E99381D3D02EEEF}

Vérifiez que vous disposez des autorisations adéquates avant de créer des activités A4T.

* Vous devez être membre du groupe d’accès aux services web dans Adobe Analytics pour pouvoir utiliser Analytics en tant que source de création de rapports pour Target.
* Vous devez être membre d’un ou plusieurs groupes Experience Cloud ayant accès à Analytics et Target.
* Vérifiez qu’Analytics et Target s’affichent dans la section Applications marketing située dans la barre de navigation gauche.

## Les mesures des taux de rebond, des rebonds et des sorties apparaissent comme valeurs positives dans les rapports.  {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Il s’agit d’un problème connu.

Bien que ces mesures soient négatives, l’effet élévateur s’affiche comme si elles étaient positives dans les rapports Target. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

## La suite de rapports dont j’ai besoin n’apparaît pas.  {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La liste des suites de rapports qui apparaît dans Target Standard/Premium est la liste des suites de rapports qui ont été configurées pour Analytics en tant que source des rapports pour Target. Cela signifie que vous ne verrez peut-être pas chaque suite de rapports que vous possédez. Si la suite de rapports que vous recherchez n’est pas répertoriée, contactez le service à la clientèle pour qu’ils l’activent.

## Je ne vois pas autant de données que prévu dans les rapports. {#section_75002584FA63456D8D9086172925DD8D}

Passez en revue votre mise en œuvre, en particulier sur les pages où les visiteurs répondent aux critères des expériences et vérifiez la correspondance des ID de données supplémentaires dans les appels à [!DNL Target] et à [!DNL Analytics]. Dans l’appel à [!DNL Target], l’ID supplémentaire est contenu dans le paramètre `mboxMCSDID`. Dans l’appel à [!DNL Analytics], l’ID supplémentaire est contenu dans le paramètre `sdid`.

Si aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Target], vérifiez que le fichier [!DNL VisitorAPI.js] est chargé avant [!DNL at.js] ou [!DNL mbox.js]. S’il aucun ID de données supplémentaire n’est présent dans l’appel à [!DNL Analytics], vérifiez que l’appel à [!DNL Target] se déclenche avant l’appel à [!DNL Analytics].

Pour plus d’informations, voir [Analytics pour implémentation de Target](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou contactez le [Service d’assistance clientèle](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).