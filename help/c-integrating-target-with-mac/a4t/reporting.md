---
keywords: analytics pour target, a4t, analytics en tant que source des rapports
description: L’utilisation d’Analytics en tant que source des rapports pour Target (A4T) vous donne accès aux rapports Analytics pour vos activités Target.
title: Rapports A4T
subtopic: Test multivarié
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Rapports A4T{#a-t-reporting}

L’utilisation d’Analytics en tant que source des rapports pour Target (A4T) vous donne accès aux rapports Analytics pour vos activités Target.

Vous pouvez afficher des rapports pour vos activités dans Analytics et dans Target Standard/Premium.

Pour en savoir plus sur les bonnes pratiques en matière de création de rapports avec Analytics for Target, [rendez-vous sur cette page Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Aperçu {#section_035A62D65608423285D8A5A54731E2C5}

Les rapports Analytics comme les rapports Target mesurent les participants (les personnes qui participent aux tests) plutôt que les visiteurs du site.

Chaque fois qu’un visiteur voit le contenu des activités sur la page, Target émet un appel direct de serveur à serveur vers Analytics, en incluant l’activité et l’expérience que le visiteur a vues. Target appelle également Analytics chaque fois que la conversion est effectuée. Analytics ajoute la conversion en tant que nouvel événement Analytics spécifique nommé « Conversion des activités », qui est suivi avec d’autres données collectées par Analytics.

Lorsque l’opération de sélection est utilisée et que vous effectuez un tri selon les *Participants*, seules les expériences qui ont reçu des participants au cours de la période sélectionnée s’affichent dans les rapports.

>[!NOTE]
>
>Les rapports générés par Target ont une latence de quatre minutes. Pour les activités générées par A4T, à la fois dans les rapports Target et Analytics, il peut s’écouler jusqu’à 24 heures après l’enregistrement initial de l’activité avant que les données du rapport puissent être ventilées par expérience. Les données collectées au cours de ces premières 24 heures sont toujours exactes et sont affectées à l’expérience appropriée.

## Rapports dans Analytics {#section_F6884872DC864AE7913587FAED4CD11C}

Dans Analytics, cliquez sur **[!UICONTROL Cible]** &gt; **[!UICONTROL Activités cibles]** dans le volet de navigation de gauche. Dans Target, les rapports de l’activité affichent automatiquement les données, les mesures et les segments Analytics. Les données s’affichent dans ces rapports environ une heure après leur collecte auprès du site. Toutes les mesures, audiences et valeurs des rapports proviennent de la suite de rapports sélectionnée lorsque vous configurez l’activité.

Dans Analytics, utilisez le rapport Activités cibles pour afficher les résultats de votre activité Target. Les rapports Test&amp;Target (hérités) fournissent des informations sur vos anciennes intégrations de page de style du module externe Test&amp;Target et n’incluent pas les données Analytics for Target. Dans le rapport Activités, affichez les informations relatives à vos expériences Target. Cliquez sur **[!UICONTROL Mesures]**, puis sélectionnez le type de mesure **[!UICONTROL Target]**. Deux mesures sont disponibles pour votre rapport :

* **Entrées d’activité** : correspond au nombre de participants du rapport Target.
* **Conversions des activités** : correspond au nombre de conversions personnalisées du rapport Target.

>[!NOTE]
>
>Les informations sur l’effet élévateur et le degré de confiance Target sont également disponibles dans Analytics. Pour plus d’informations, voir Effet élévateur et degré de confiance [de](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) Target dans le Guide *des composants d’* Analytics.

>[!IMPORTANT]
>
>Si votre rapport Activités cibles dans Analytics indique « non spécifié » au lieu de répertorier vos activités, mettez à jour votre compte avec les privilèges d’accès. Contactez l’assistance à la clientèle pour résoudre ce problème.

## Rapports dans Target {#section_C0D1F17F88374B6690BF904D7B83B42E}

Lorsqu’Analytics est utilisé en tant que source de création de rapports, les rapports dans Target Standard affichent les données rassemblées depuis Analytics. Le rapport diffère quelque peu des autres rapports Target Standard :

* La liste Audiences affiche les audiences disponibles pour votre suite de rapports Analytics.
* La liste Mesure affiche chaque mesure disponible dans Analytics.

   Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à Analytics..

   Gardez à l’esprit que tout chiffre qui augmente est indiqué comme positif dans le rapport, même lorsque qu’une augmentation n’est en fait pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

Vous pouvez appliquer la mesure ou l’audience au rapport dans Target une fois que le test a commencé ou même une fois qu’il est terminé. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Cliquez pour afficher le rapport Analytics complet directement depuis la page des rapports de l’activité.

## Rapports dans Analysis Workspace {#reports-in-analysis-workspace}

Vous pouvez utiliser [!DNL Adobe Analysis Workspace] pour effectuer une analyse plus approfondie et visualiser les données ou découvrir les informations masquées sous la surface.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Au cours de la création de l’activité, vous devez indiquer un objectif pour cette dernière dans la page [!UICONTROL Paramètres]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. Un test avec Analytics utilise les segments Adobe Analytics au lieu des audiences Target Standard.

## Exécution de calculs hors ligne pour Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour plus d’informations, voir [Réalisation de calculs hors ligne pour Analytics for Target (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
