---
keywords: analytics pour target, a4t, analytics en tant que source des rapports
description: Découvrez comment utiliser Analytics pour la Cible (A4T). A4T permet d’accéder aux rapports Analytics pour les activités de Cible qui utilisent les mesures et les segments d’audience Analytics.
title: Comment utiliser le Rapports dans A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 37%

---


# Rapports A4T{#a-t-reporting}

L&#39;utilisation de [!DNL Analytics] comme source de rapports pour [!DNL Target] (A4T) vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target].

Vous pouvez vue des rapports pour vos activités dans [!DNL Analytics] et [!DNL Target].

Pour connaître les meilleures pratiques de rapports utilisant [!DNL Analytics] pour [!DNL Target], [visitez cette page Adobe Spark](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Aperçu {#section_035A62D65608423285D8A5A54731E2C5}

Les rapports [!DNL Analytics] et [!DNL Target] mesurent tous deux les participants (les personnes qui entrent dans les tests), plutôt que les visiteurs sur le site.

Chaque fois qu’un visiteur voit le contenu de l’activité sur la page, [!DNL Target] effectue un appel direct de serveur à serveur à [!DNL Analytics], y compris l’activité et l’expérience que le visiteur a vues. [!DNL Target] appelle également  [!DNL Analytics] chaque fois que la conversion est effectuée. [!DNL Analytics][!DNL Analytics] ajoute la conversion en tant que nouvel événement spécifique nommé « Conversion des activités », qui est suivi avec d’autres données collectées par [!DNL Analytics].

Lorsque l’opération [!UICONTROL Sélectionner] est utilisée et que vous effectuez un tri sur *Participants*, seules les expériences qui ont reçu des participants au cours de la période sélectionnée sont affichées dans les rapports.

>[!NOTE]
>
>Les rapports générés par [!DNL Target] ont une latence de quatre minutes. Pour les activités générées par A4T, dans les rapports [!DNL Target] et [!DNL Analytics], il peut s’écouler jusqu’à 24 heures après l’enregistrement initial de l’activité avant que les données du rapport ne puissent être ventilées par expérience. Les données collectées au cours de ces premières 24 heures sont toujours exactes et sont affectées à l’expérience appropriée.

## Rapports dans Analytics {#analytics}

Dans [!DNL Analytics], plusieurs dimensions et mesures sont disponibles une fois l’intégration A4T activée.

### Dimensions

* [!UICONTROL Analytics pour la Cible]  : identifiant parent transmis par l’intégration. Le format de cette dimension est `Activity ID:Experience ID:3rd ID`. Les dimensions ci-dessous sont des classifications de cette dimension.
* [!UICONTROL Activités Target]
* [!UICONTROL Contenus Target]
* [!UICONTROL Cible Activité] >  [!UICONTROL Expérience]
* [!UICONTROL 3e identifiant]  - peut être ignoré

### Mesures

* [!UICONTROL Impressions]  d’Activité : correspond au nombre de   participants dans le  [!DNL Target] rapport.
* [!UICONTROL Conversions]  d&#39;Activité : correspond au nombre de  [!UICONTROL conversions ] personnalisées dans le  [!DNL Target] rapport.

Dans [!DNL Analysis Workspace], utilisez le panneau [!UICONTROL Analyses pour la Cible] pour analyser vos [!DNL Target] activités et expériences avec effet élévateur et confiance. Pour plus d’informations, voir le [panneau Analyses pour la Cible (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) du *Guide des outils Analytics*.

>[!IMPORTANT]
>
>Si votre rapport [!UICONTROL Activités de Cible] dans [!DNL Analytics] listes &quot;non spécifié&quot; au lieu de répertorier vos activités, une mise à jour est requise pour votre compte configuré. Contactez l’assistance à la clientèle pour résoudre ce problème.

Pour obtenir des informations détaillées et des exemples, ouvrez la section [Analyses et Cible : Didacticiel sur les meilleures pratiques pour l’Analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fourni par Adobe Experience League.

## Rapports dans Target  {#section_C0D1F17F88374B6690BF904D7B83B42E}

Lorsque [!DNL Analytics] est utilisé comme source de rapports, les rapports dans [!DNL Target] affichent les données collectées à partir de [!DNL Analytics]. Le rapport diffère quelque peu des autres rapports [!DNL Target] :

* La liste [!UICONTROL Audiences] affiche les audiences disponibles pour votre suite de rapports [!DNL Analytics].
* La liste [!UICONTROL Mesure] affiche chaque mesure disponible par [!DNL Analytics].

   Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

   Gardez à l’esprit que tout chiffre qui augmente est indiqué comme positif dans le rapport, même lorsque qu’une augmentation n’est en fait pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

Vous pouvez appliquer la mesure ou l&#39;audience au rapport dans [!DNL Target] après le démarrage de l&#39;activité, ou même après la fin du test. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Cliquez pour vue du rapport complet [!DNL Analytics] directement à partir de la page du rapport d&#39;activité.

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Au cours de la création de l’activité, vous devez indiquer un objectif pour cette dernière dans la page [!UICONTROL Paramètres]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. Un test avec [!DNL Analytics] utilise des segments [!DNL Adobe Analytics] plutôt que des audiences [!DNL Target].

## Exécution de calculs hors ligne pour Analytics pour la Cible (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour plus d’informations, voir [Réalisation de calculs hors ligne pour Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
