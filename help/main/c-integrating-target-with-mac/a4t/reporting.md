---
keywords: analytics for target;a4t;analytics en tant que source des rapports;analytics
description: Découvrez comment utiliser Analytics pour [!DNL Target] (A4T). A4T permet d’accéder aux rapports Analytics pour [!DNL Target] activités qui utilisent des mesures Analytics et des segments d’audience.
title: Comment utiliser les rapports dans A4T ?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 34%

---

# Rapports A4T

Utilisation [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T) vous donne accès à [!DNL Analytics] rapports pour votre [!DNL Target] activités.

Vous pouvez afficher des rapports pour vos activités dans les deux [!DNL Analytics] et [!DNL Target].

Pour les bonnes pratiques de création de rapports à l’aide de [!DNL Analytics] pour [!DNL Target], [visite de Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Aperçu {#section_035A62D65608423285D8A5A54731E2C5}

Les [!DNL Analytics] et [!DNL Target] Les rapports mesurent les participants (les personnes qui participent aux tests) plutôt que les visiteurs du site.

Chaque fois qu’un visiteur voit le contenu de l’activité sur la page, [!DNL Target] effectue un appel direct de serveur à serveur vers [!DNL Analytics], y compris l’activité et l’expérience que le visiteur a vues. [!DNL Target] également des appels [!DNL Analytics] chaque fois que la conversion est effectuée. [!DNL Analytics][!DNL Analytics] ajoute la conversion en tant que nouvel événement spécifique nommé « Conversion des activités », qui est suivi avec d’autres données collectées par [!DNL Analytics].

Lorsque la variable [!UICONTROL Sélectionner] est utilisée et vous effectuez un tri sur *Participants*, alors seules les expériences qui ont reçu des participants au cours de la période sélectionnée sont affichées dans les rapports.

>[!NOTE]
>
>Rapports générés [!DNL Target] ont une latence de quatre minutes. Pour les activités optimisées par A4T, dans la variable [!DNL Target] et [!DNL Analytics] , jusqu’à 24 heures peuvent s’écouler entre l’enregistrement initial de l’activité et la ventilation des données du rapport par expériences. Les données collectées au cours de ces premières 24 heures sont toujours exactes et sont affectées à l’expérience appropriée.

## Rapports dans Analytics {#analytics}

Dans [!DNL Analytics], plusieurs dimensions et mesures sont disponibles une fois l’intégration A4T activée.

### Dimensions

* [!UICONTROL Analytics pour Target] - Identifiant parent transmis par le biais de l’intégration. Le format de cette dimension est le suivant : `Activity ID:Experience ID:3rd ID`. Les dimensions ci-dessous sont des classifications de cette dimension.
* [!UICONTROL Activités Target]
* [!UICONTROL Contenus Target]
* [!UICONTROL Activité Target] > [!UICONTROL Expérience]
* [!UICONTROL 3e identifiant] - peut être ignoré

### Mesures

* [!UICONTROL Impressions d’activité] - Correspond à la variable [!UICONTROL Participants] dans la variable [!DNL Target] rapport.
* [!UICONTROL Conversions des activités] - Correspond à la variable [!UICONTROL Conversions personnalisées] dans la variable [!DNL Target] rapport.

Dans [!DNL Analysis Workspace], utilisez le [!UICONTROL Analytics pour Target] pour analyser votre [!DNL Target] activités et expériences avec effet élévateur et degré de confiance. Pour plus d’informations, voir [Panneau Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr) dans le *Guide sur les outils Analytics*.

>[!IMPORTANT]
>
>Si votre [!UICONTROL Activités Target] rapport dans [!DNL Analytics] répertorie &quot;non spécifié&quot; au lieu de répertorier vos activités, une mise à jour est requise pour votre compte configuré. Contactez l’assistance à la clientèle pour résoudre ce problème.

Pour obtenir des informations détaillées et des exemples, ouvrez le [Analytics et Target : Bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutoriel fourni par Adobe Experience League.

## Rapports dans [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] est utilisé comme source de création de rapports ; les rapports dans [!DNL Target] afficher les données collectées à partir de [!DNL Analytics]. Le rapport diffère quelque peu des autres [!DNL Target] rapports :

* Le [!UICONTROL Audiences] La liste affiche les audiences disponibles pour votre [!DNL Analytics] suite de rapports.
* Le [!UICONTROL Mesure] affiche chaque mesure disponible via [!DNL Analytics].

   Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

   Les nombres qui augmentent sont affichés comme positifs dans le rapport, même lorsqu’une augmentation n’est pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

Vous pouvez appliquer la mesure ou l’audience au rapport dans [!DNL Target] une fois l’activité lancée, ou même une fois le test terminé. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Cliquez sur pour afficher le [!DNL Analytics] rapport directement à partir de la page du rapport d’activité.

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Au cours de la création de l’activité, vous devez indiquer un objectif pour cette dernière dans la page [!UICONTROL Paramètres]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. Un test avec [!DNL Analytics] uses [!DNL Adobe Analytics] segments plutôt que [!DNL Target] audiences.

## Exécution de calculs hors ligne pour Analytics pour Adobe Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour plus d’informations, voir [Réalisation de calculs hors ligne pour Analytics for Target (A4T)](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
