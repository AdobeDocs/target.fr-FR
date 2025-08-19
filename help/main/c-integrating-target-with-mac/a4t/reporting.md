---
keywords: analytics for target;a4t;analytics comme source des rapports;analytics
description: Découvrez comment utiliser Analytics for  [!DNL Target] (A4T). A4T permet d’accéder aux rapports Analytics pour  [!DNL Target]  activités qui utilisent les mesures Analytics et les segments d’audience.
title: Comment utiliser les rapports dans A4T ?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# Rapports A4T

L’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T) vous donne accès aux rapports [!DNL Analytics] pour vos activités [!DNL Target].

Vous pouvez afficher des rapports pour vos activités dans [!DNL Analytics] et [!DNL Target].

Pour connaître les bonnes pratiques en matière de reporting à l’aide de [!DNL Analytics] for [!DNL Target], [consultez cette page Adobe Spark](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Aperçu {#section_035A62D65608423285D8A5A54731E2C5}

Les rapports [!DNL Analytics] et [!DNL Target] mesurent les visiteurs et visiteuses qui accèdent au site (c’est-à-dire les personnes qui participent aux tests).

Chaque fois qu’un visiteur voit le contenu de l’activité sur la page, [!DNL Target] appelle directement le [!DNL Analytics] serveur à serveur, y compris l’activité et l’expérience qu’il a vues. [!DNL Target] appelle également [!DNL Analytics] chaque fois que la conversion est effectuée. [!DNL Analytics] ajoute la conversion sous la forme d’un nouvel événement [!DNL Analytics] spécifique nommé « Conversion d’activité », qui est suivi avec d’autres données collectées par [!DNL Analytics].

Lorsque l’opération [!UICONTROL Select] est utilisée et que vous effectuez un tri sur *Participants*, seules les expériences ayant reçu des participants au cours de la période sélectionnée s’affichent dans les rapports.

>[!NOTE]
>
>Les rapports optimisés par [!DNL Target] ont une latence de quatre minutes. Pour les activités optimisées par A4T, dans les rapports [!DNL Target] et [!DNL Analytics], il peut s’écouler jusqu’à 24 heures après l’enregistrement initial de l’activité avant que les données du rapport ne puissent être divisées par expériences. Les données collectées au cours de ces premières 24 heures sont toujours exactes et sont affectées à l’expérience appropriée.

## Rapports dans Analytics {#analytics}

Dans [!DNL Analytics], plusieurs dimensions et mesures sont disponibles une fois l’intégration A4T activée.

### Dimensions

* [!UICONTROL Analytics for Target] - Identifiant parent transmis par l’intégration. Le format de cette dimension est `Activity ID:Experience ID:3rd ID`. Les dimensions ci-dessous sont des classifications de cette dimension.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - peut être ignoré

### Mesures

* [!UICONTROL Activity Impressions] - Correspond au numéro de [!UICONTROL Entrants] dans le rapport [!DNL Target].
* [!UICONTROL Activity Conversions] - Correspond au numéro de [!UICONTROL Custom Conversions] dans le rapport [!DNL Target].

Dans [!DNL Analysis Workspace], utilisez le panneau [!UICONTROL Analytics for Target] pour analyser en toute confiance vos activités et expériences [!DNL Target]. Pour plus d’informations, consultez [Panneau Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=fr) dans le *Guide des outils d’Analytics*.

>[!IMPORTANT]
>
>Si le rapport de [!UICONTROL Target Activities] dans [!DNL Analytics] répertorie « non spécifié » au lieu de répertorier vos activités, une mise à jour est requise sur le compte configuré. Contactez l’assistance à la clientèle pour résoudre ce problème.

Pour obtenir des informations détaillées et des exemples, reportez-vous au tutoriel [Analytics et Target : bonnes pratiques relatives à l’analyse](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) fourni par Adobe Experience League.

## Rapports dans [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

Lorsque [!DNL Analytics] est utilisé comme source de création de rapports, les rapports dans [!DNL Target] affichent les données collectées à partir de [!DNL Analytics]. Le rapport diffère quelque peu des autres rapports [!DNL Target] :

* La liste [!UICONTROL Audiences] répertorie les audiences disponibles pour votre suite de rapports [!DNL Analytics].
* La liste [!UICONTROL Metric] affiche toutes les mesures disponibles via [!DNL Analytics].

  Chaque mesure est disponible, y compris toute mesure personnalisée ou calculée intégrée à [!DNL Analytics].

  Toute augmentation est considérée comme positive dans le rapport, même si elle n’est pas souhaitée. Par exemple, même si vous souhaitez un taux de rebond plus bas, le taux de rebond plus élevé s’affiche comme gagnant avec l’effet élévateur le plus élevé. Tenez compte de ce problème et des mesures similaires et choisissez si vous préférez diminuer ou augmenter les chiffres lors de la prise de décisions basées sur les rapports.

Vous pouvez appliquer la mesure ou l’audience au rapport dans [!DNL Target] une fois que l’activité a commencé ou même une fois le test terminé. Il n’est pas nécessaire que vous sachiez exactement au préalable ce que vous voulez mesurer.

Cliquez pour afficher le rapport d’[!DNL Analytics] complet directement à partir de la page du rapport d’activité.

## Création de l’activité {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Lors de la création de l’activité, vous devez spécifier un objectif pour l’activité sur la page de [!UICONTROL Settings]. Cet objectif devient la mesure par défaut du rapport et est systématiquement répertorié en tant que première option dans le sélecteur de mesures. Vous ne pouvez pas sélectionner de segments pour la création de rapports comme vous le feriez pour une activité classique Target. Un test avec [!DNL Analytics] utilise des segments [!DNL Adobe Analytics] plutôt que des audiences [!DNL Target].

## Exécution de calculs hors ligne pour Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Vous pouvez effectuer des calculs hors ligne pour les intervalles de confiance et de confiance pour A4T à l’aide du fichier Excel [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx), mais il nécessite une étape avec des exportations de données dans [!DNL Analytics].

Pour A4T, nous utilisons un calcul [test t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} pour les variables continues (plutôt que pour les mesures binaires). Dans Analytics, un visiteur est suivi en permanence et chaque action effectuée est comptabilisée. Ainsi, si le visiteur achète à plusieurs reprises ou visite une mesure de succès plusieurs fois, ces accès supplémentaires sont comptabilisés. La mesure devient ainsi une variable continue. Pour effectuer le calcul du test t de Welch, la « somme des carrés » est nécessaire pour calculer la variance, qui est utilisée dans le dénominateur de la statistique t. [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explique les détails des formules mathématiques utilisées. La somme des carrés peut être extraite de [!DNL Analytics]. Pour obtenir la somme des données de carrés, vous devez effectuer une exportation de niveau visiteur pour la mesure vers laquelle s’effectue l’optimisation, pour une période donnée.

Par exemple, si vous effectuez une optimisation des pages vues par visiteur, vous exporterez un échantillon du nombre total de pages vues par visiteur pour une période spécifiée, peut-être deux jours (quelques milliers de points de données sont tout ce dont vous avez besoin). Vous calculez ensuite chaque valeur au carré et faites la sommes des totaux (l’ordre des opérations est critique ici). Cette valeur de « somme des carrés » est ensuite utilisée dans le calculateur de confiance complet. Utilisez la section « recettes » de cette feuille de calcul pour ces valeurs.

**Pour utiliser la fonction d’exportation de données d’[!DNL Analytics], procédez comme suit :**

1. Connectez-vous à [!DNL Adobe Analytics].
1. Cliquez sur **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. Dans l’onglet **[!UICONTROL Data Warehouse Request]** , renseignez les champs .

   Pour plus d’informations sur chaque champ, voir « Description des demandes de Data Warehouse » dans [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Champ | Instructions |
   |--- |--- |
   | Nom de la demande | Indiquez un nom pour la demande. |
   | Date de création du rapport | Spécifiez une période et une granularité.<br>Pour la première demande, il est recommandé de ne pas choisir plus d’une heure ou d’un jour de données. Plus la période demandée est longue, plus le traitement des fichiers de Data Warehouse est long. Il est donc préférable de commencer par demander les données de périodes courtes afin de s’assurer que le fichier renvoie le résultat attendu. Ensuite, accédez au gestionnaire de requêtes, dupliquez la demande et demandez plus de données la deuxième fois. En outre, si vous affectez à la granularité une valeur autre que « Aucune », la taille du fichier augmentera considérablement.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segments disponibles | Appliquez un segment, le cas échéant. |
   | Ventilations | Sélectionnez les dimensions souhaitées : la norme est prête à l’emploi, tandis que la personnalisée inclut les eVars et les props. Il est recommandé d’utiliser « Identifiant visiteur » si des informations au niveau de l’identifiant visiteur sont nécessaires, plutôt que « Identifiant visiteur Experience Cloud ».<ul><li>L’identifiant visiteur est l’identifiant final utilisé par Analytics. Il s’agit de l’AID (si le client est hérité) ou du MID (si le client est nouveau ou a effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud).</li><li>L’identifiant visiteur Experience Cloud est défini uniquement pour les nouveaux clients ou ceux qui ont effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud.</li></ul> |
   | Mesures | Sélectionnez les mesures souhaitées. La mesure Standard est prête à l’emploi, alors que la mesure Personnalisée inclut des événements personnalisés. |
   | Aperçu du rapport | Vérifiez les paramètres avant de planifier le rapport.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Planifier la livraison du rapport | Saisissez une adresse e-mail à laquelle envoyer le fichier, nommez le fichier, puis sélectionnez [!UICONTROL Send Immediately].<br>Remarque : le fichier peut être livré par FTP sous [!UICONTROL Advanced Delivery Options]<br>![Planifier la livraison](/help/main/c-reports/assets/datawarehouse3.png). |

1. Cliquez sur **[!UICONTROL Request this Report]**.

   La livraison du fichier peut prendre jusqu’à 72 heures, selon le volume de données demandé. Vous pouvez vérifier à tout moment l’état d’avancement de votre demande en cliquant sur [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Si vous souhaitez demander à nouveau les données que vous avez demandées dans le passé, vous pouvez dupliquer une ancienne demande à partir du [!UICONTROL Request Manager], si nécessaire.

Pour plus d’informations sur [!DNL Data Warehouse], voir les liens suivants dans la documentation d’aide d’[!DNL Analytics] :

* [Créer une requête Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Bonnes pratiques Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
