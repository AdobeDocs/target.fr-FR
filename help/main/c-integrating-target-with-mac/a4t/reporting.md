---
keywords: analytics for target;a4t;analytics en tant que source des rapports;analytics
description: Découvrez comment utiliser Analytics pour [!DNL Target] (A4T). A4T permet d’accéder aux rapports Analytics pour [!DNL Target] activités qui utilisent des mesures Analytics et des segments d’audience.
title: Comment utiliser les rapports dans A4T ?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 48%

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

## Exécution de calculs hors ligne pour Analytics pour Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Vous pouvez effectuer des calculs hors ligne pour les intervalles de confiance et de confiance pour A4T à l’aide de la variable [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) fichier Excel, mais nécessite une étape avec l’exportation des données dans [!DNL Analytics].

Pour A4T, nous utilisons une [Le test en t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test)Calcul de {target=_blank} pour les variables continues (plutôt que les mesures binaires). Dans Analytics, un visiteur est suivi en permanence et chaque action effectuée est comptabilisée. Ainsi, si le visiteur achète à plusieurs reprises ou visite une mesure de succès plusieurs fois, ces accès supplémentaires sont comptabilisés. La mesure devient ainsi une variable continue. Pour effectuer le calcul du test en t de Welch, la &quot;somme des carrés&quot; est nécessaire pour calculer la variance, utilisée dans le dénominateur de la statistique en t. [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explique les détails des formules mathématiques utilisées. La somme des carrés peut être récupérée à partir de [!DNL Analytics]. Pour obtenir la somme des données de carrés, vous devez effectuer une exportation de niveau visiteur pour la mesure vers laquelle s’effectue l’optimisation, pour une période donnée.

Si, par exemple, vous effectuez une optimisation pour les pages vues par visiteur, vous exportez un exemple du nombre total de pages vues par visiteur pour une période spécifiée, peut-être quelques jours (quelques milliers de points de données sont tout ce dont vous avez besoin). Vous calculez ensuite chaque valeur au carré et faites la sommes des totaux (l’ordre des opérations est critique ici). Cette valeur de « somme des carrés » est ensuite utilisée dans le calculateur de confiance complet. Utilisez la section « recettes » de cette feuille de calcul pour ces valeurs.

**Pour utiliser la fonction d’exportation de données d’[!DNL Analytics], procédez comme suit :**

1. Connectez-vous à [!DNL Adobe Analytics].
1. Cliquez sur **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]**.
1. Dans l’onglet **[!UICONTROL Demande de Data Warehouse]**, remplissez les champs.

   Pour plus d’informations sur chaque champ, voir « Description des demandes de Data Warehouse » dans [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Champ | Instructions |
   |--- |--- |
   | Nom de la demande | Indiquez un nom pour la demande. |
   | Date de création du rapport | Spécifiez une période et une granularité.<br>Pour la première demande, il est recommandé de ne pas choisir plus d’une heure ou d’un jour de données. Plus la période demandée est longue, plus le traitement des fichiers de Data Warehouse est long. Il est donc préférable de commencer par demander les données de périodes courtes afin de s’assurer que le fichier renvoie le résultat attendu. Ensuite, accédez au gestionnaire de requêtes, dupliquez la demande et demandez plus de données la deuxième fois. En outre, si vous passez la granularité sur autre chose que &quot;Aucun&quot;, la taille du fichier augmente considérablement.<br>![Data Warehouse ](/help/main/c-reports/assets/datawarehouse.png) |
   | Segments disponibles | Appliquez un segment, le cas échéant. |
   | Ventilations | Sélectionnez les dimensions souhaitées : La dimension Standard est prête à l’emploi tandis que la dimension Personnalisée inclut les eVars et les props. Il est recommandé d’utiliser &quot;Identifiant visiteur&quot; si des informations au niveau de l’identifiant visiteur sont nécessaires, plutôt que &quot;Identifiant visiteur Experience Cloud&quot;.<ul><li>L’identifiant visiteur est l’identifiant final utilisé par Analytics. Il s’agit de l’AID (si le client est hérité) ou du MID (si le client est nouveau ou a effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud).</li><li>L’identifiant visiteur Experience Cloud est défini uniquement pour les nouveaux clients ou ceux qui ont effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud.</li></ul> |
   | Mesures | Sélectionnez les mesures souhaitées. La mesure Standard est prête à l’emploi, alors que la mesure Personnalisée inclut des événements personnalisés. |
   | Aperçu du rapport | Vérifiez les paramètres avant de planifier le rapport.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Planifier la livraison du rapport | Entrez une adresse e-mail à laquelle envoyer le fichier, nommez le fichier, puis sélectionnez [!UICONTROL Envoyer immédiatement].<br>Remarque : Le fichier peut être envoyé par FTP à l’aide des [!UICONTROL Options de remise avancées]<br>![Planifier la livraison](/help/main/c-reports/assets/datawarehouse3.png). |

1. Cliquez sur **[!UICONTROL Demander ce rapport]**.

   La livraison du fichier peut prendre jusqu’à 72 heures, selon le volume de données demandé. Vous pouvez vérifier la progression de la demande à tout moment en cliquant sur [!UICONTROL Outils] > [!UICONTROL Data Warehouse] > [!UICONTROL Gestionnaire de requêtes].

   Si vous souhaitez demander à nouveau des données que vous avez demandées par le passé, vous pouvez dupliquer une ancienne requête du [!UICONTROL Gestionnaire de requêtes] selon les besoins.

Pour plus d’informations sur [!DNL Data Warehouse], voir les liens suivants dans la documentation d’aide d’[!DNL Analytics] :

* [Créer une demande Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Bonnes pratiques relatives aux Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
