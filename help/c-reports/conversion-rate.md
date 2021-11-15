---
keywords: Ciblage
description: Découvrez comment Adobe [!DNL Target] affiche et calcule le taux de conversion, l’effet élévateur, le degré de confiance et l’intervalle de confiance pour chaque expérience.
title: Comment afficher le taux de conversion, l’effet élévateur et le degré de confiance ?
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 4e3a94554dd9c1e8cc6e98eda10d454536bc9b1f
workflow-type: tm+mt
source-wordcount: '2136'
ht-degree: 58%

---

# Taux de conversion

Le taux de conversion, l’effet élévateur, le degré de confiance et l’intervalle de confiance sont signalés pour chaque expérience.

L’illustration ci-dessous montre l’en-tête du diagramme pour un exemple d’activité avec les en-têtes [!UICONTROL Taux de conversion], [!UICONTROL Effet élévateur] et [!UICONTROL Degré de confiance] surlignés.

![](assets/conversion-rate.jpg)

>[!NOTE]
>
>Dans toutes les données, les commandes en double sont ignorées si un `orderID` est transmis. Le rapport d’audit répertorie les commandes dupliquées ignorées.

## Taux de conversion {#section_07A36846C4E84D0881906809B9CE5A74}

Montre le taux de conversion, le degré de confiance et l’intervalle médians ainsi que le nombre de conversions.

Par exemple, examinez la colonne du rapport Taux de conversion suivante :

![](assets/conversion-rate-detail.jpg)

La première ligne concerne l’expérience de contrôle. Elle affiche un taux de conversion de 15 % avec trois conversions. La seconde ligne, Expérience B, affiche un taux de conversion de 15 %, avec un intervalle de confiance de plus ou moins 15,65 % et trois conversions.

>[!NOTE]
>
>L’intervalle de confiance n’est actuellement calculé que pour les mesures binaires.

## Effet élévateur {#section_0F409572C720433D9378092ABC999982}

Compare le taux de conversion de chaque expérience à l’expérience de contrôle.

Effet élévateur = (TC expérience - TC contrôle) / TC contrôle

Si le contrôle est égal à 0, il n’y a aucun effet élévateur sous forme de pourcentage.


## Données de vente au détail {#section_30A674731BA6440E9BB93C421BE990EE}

La valeur de commande moyenne (AOV), les recettes par visiteur (RPV) et les données de vente s’affichent pour chaque expérience si vous avez inséré une commande d’emplacement (`orderConfirmPage`) et sélectionnez-la comme mbox de conversion.

## Degré de confiance et intervalle de confiance {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

Pour chaque expérience, le degré de confiance et l’intervalle de confiance s’affichent.

Vous pouvez effectuer des calculs d’analyse hors ligne pour for Target (A4T), mais cela nécessite d’exporter les données vers [!DNL Analytics]Analytics. Pour plus d’informations, reportez-vous à la section « Réalisation de calculs hors ligne pour Analytics for Target (A4T) » ci-dessous.

### Degré de confiance {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

La confiance d’une expérience ou d’une offre affichée est une probabilité (exprimée en pourcentage) d’obtenir un résultat moins extrême que celui réellement observé, si l’hypothèse nulle est vraie, c’est-à-dire si les taux de conversion entre cette expérience ou cette offre ne diffèrent pas de ceux de l’expérience ou de l’offre de contrôle. En termes de p-valeurs, ce degré de confiance s’affiche entre 1 et p-valeur. En d’autres termes, une confiance plus élevée indique que les données sont moins cohérentes avec l’hypothèse que l’offre/l’expérience de contrôle et non de contrôle ont des taux de conversion égaux. La confiance s’arrondit à 100,00 % lorsqu’elle est supérieure ou égale à 99,995 %.

![](assets/conf_report.png)  ![](assets/conf_report_detail.png)

Afin de garantir des résultats stables, tâchez, avant toute décision professionnelle, de patienter jusqu’à ce que la taille de l’échantillon soit suffisamment conséquente et que les quatre barres de fiabilité d’une ou de plusieurs expériences restent homogènes pendant une certaine durée.


### Intervalle de confiance {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>L’intervalle de confiance n’est actuellement calculé que pour les mesures binaires.

Le *intervalle de confiance* est une plage d’estimations dans laquelle la valeur réelle de la mesure se trouve à un degré de confiance donné. Target affiche toujours des intervalles de confiance de 95 %. L’intervalle de confiance est représenté par un pourcentage +/- gris clair dans la colonne Taux de conversion. Dans l’exemple ci-dessous, l’intervalle de confiance pour l’effet élévateur de l’expérience B est de plus ou moins 15,65 %.

![](assets/conversion_rate.png)

**Exemple :** Le RPV observé d’une expérience est de 10 $ et ses 95 % **intervalle de confiance** est compris entre 5 et 15 $. Inconnu de nous, son vrai RPV est de 12$. Ensuite, si nous avons exécuté ce test plusieurs fois, 95 % du temps que l’intervalle de confiance que nous calculons contiendra la variable _true_ valeur du RPV de 12 $.

**Quels éléments influent sur l’intervalle de confiance ?** La formule de calcul des intervalles de confiance suit les méthodes statistiques habituelles.

* **Taille de l’échantillon :** lorsque les échantillons sont plus importants, l’intervalle se rétrécit ou s’affine. Cela est préférable car cela signifie que vos rapports se rapprochent davantage de la valeur réelle de la mesure de succès.
* **Écart type réduit** : davantage de résultats semblables (AOV, nombres ou visiteurs effectuant une conversion chaque jour) réduisent l’écart type.

## Calcul de la confiance et comment l’exécuter hors ligne {#section_86F7C231943043A5B8B6BFE67B706E3B}

Le [rapport CSV téléchargé](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B.

Pour calculer ces mesures calculées, téléchargez le [Calculateur de confiance complet](/help/assets/complete_confidence_calculator.xlsx) fichier Excel pour saisir la valeur de l’activité ou consulter la variable [calculs statistiques utilisés par Target](/help/assets/statistical-calculations.pdf).

>[!NOTE]
>
>Ce calculateur sert uniquement pour les rapports basés sur Target, pas pour les rapports A4T.

## Exécution de calculs hors ligne pour Analytics pour Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Vous pouvez effectuer des calculs hors ligne pour A4T, mais cela nécessite une étape relative aux exportations de données dans [!DNL Analytics].

Pour A4T, nous utilisons le calcul du test en t de Student pour les variables continues (plutôt que pour les mesures binaires). Dans Analytics, un visiteur est suivi en permanence et chaque action effectuée est comptabilisée. Ainsi, si le visiteur achète à plusieurs reprises ou visite une mesure de succès plusieurs fois, ces accès supplémentaires sont comptabilisés. La mesure devient ainsi une variable continue. Pour effectuer le calcul du test en t de Student, la &quot;somme des carrés&quot; est nécessaire pour calculer la variance, utilisée dans le dénominateur de la statistique en t. [Ce document explique les détails](/help/assets/statistical-calculations.pdf) des formules mathématiques utilisées. La somme des carrés peut être récupérée à partir de [!DNL Analytics]. Pour obtenir la somme des données de carrés, vous devez effectuer une exportation de niveau visiteur pour la mesure vers laquelle s’effectue l’optimisation, pour une période donnée.

Par exemple, si l’optimisation porte sur les pages vues par visiteur, vous exportez un échantillon du nombre total de pages vues par visiteur pour une période spécifique, peut-être quelques jours (quelques milliers de points de données sont tout ce dont vous avez besoin). Vous calculez ensuite chaque valeur au carré et faites la sommes des totaux (l’ordre des opérations est critique ici). Cette valeur de « somme des carrés » est ensuite utilisée dans le calculateur de confiance complet. Utilisez la section « recettes » de cette feuille de calcul pour ces valeurs.

**Pour utiliser la fonction d’exportation de données d’[!DNL Analytics], procédez comme suit :**

1. Connectez-vous à [!DNL Adobe Analytics].
1. Cliquez sur **[!UICONTROL Outils]** > **[!UICONTROL Data Warehouse]**.
1. Dans l’onglet **[!UICONTROL Demande de Data Warehouse]**, remplissez les champs.

   Pour plus d’informations sur chaque champ, voir « Description des demandes de Data Warehouse » dans [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Champ | Instructions |
   |--- |--- |
   | Nom de la demande | Indiquez un nom pour la demande. |
   | Date de création du rapport | Spécifiez une période et une granularité.<br>Pour la première demande, il est recommandé de ne pas choisir plus d’une heure ou d’un jour de données. Plus la période demandée est longue, plus le traitement des fichiers de Data Warehouse est long. Il est donc préférable de commencer par demander les données de périodes courtes afin de s’assurer que le fichier renvoie le résultat attendu. Ensuite, accédez au gestionnaire de requêtes, dupliquez la demande et demandez plus de données la deuxième fois. De plus, si vous définissez une autre granularité que « Aucune », la taille du fichier augmente considérablement.<br>![Data Warehouse ](/help/c-reports/assets/datawarehouse.png) |
   | Segments disponibles | Appliquez un segment, le cas échéant. |
   | Ventilations | Sélectionnez les dimensions souhaitées : La dimension Standard est prête à l’emploi tandis que la dimension Personnalisée inclut les eVars et les props. Il est recommandé d’utiliser « l’identifiant visiteur » si des informations sur le niveau d’identification du visiteur sont nécessaires, plutôt que « l’identifiant visiteur Experience Cloud ».<ul><li>L’identifiant visiteur est l’identifiant final utilisé par Analytics. Il s’agit de l’AID (si le client est hérité) ou du MID (si le client est nouveau ou a effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud).</li><li>L’identifiant visiteur Experience Cloud est défini uniquement pour les nouveaux clients ou ceux qui ont effacé les cookies depuis le lancement du service d’identification des visiteurs Marketing Cloud.</li></ul> |
   | Mesures | Sélectionnez les mesures souhaitées. La mesure Standard est prête à l’emploi, alors que la mesure Personnalisée inclut des événements personnalisés. |
   | Aperçu du rapport | Vérifiez les paramètres avant de planifier le rapport.<br>![Data Warehouse 2](/help/c-reports/assets/datawarehouse2.png) |
   | Planifier la livraison du rapport | Entrez une adresse e-mail à laquelle envoyer le fichier, nommez le fichier, puis sélectionnez [!UICONTROL Envoyer immédiatement].<br>Remarque : Le fichier peut être envoyé par FTP à l’aide des [!UICONTROL Options de remise avancées]<br>![Planifier la livraison](/help/c-reports/assets/datawarehouse3.png). |

1. Cliquez sur **[!UICONTROL Demander ce rapport]**.

   La livraison du fichier peut prendre jusqu’à 72 heures, selon le volume de données demandé. Vous pouvez vérifier la progression de la demande à tout moment en cliquant sur [!UICONTROL Outils] > [!UICONTROL Data Warehouse] > [!UICONTROL Gestionnaire de requêtes].

   Si vous souhaitez demander à nouveau des données que vous avez demandées par le passé, vous pouvez dupliquer une ancienne demande à partir du [!UICONTROL Gestionnaire de requêtes], le cas échéant.

Pour plus d’informations sur [!DNL Data Warehouse], voir les liens suivants dans la documentation d’aide d’[!DNL Analytics] :

* [Créer une demande Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Bonnes pratiques relatives aux Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

## Méthodologie de calcul {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

Vous avez la possibilité d’afficher les rapports selon différentes méthodologies de comptabilisation, afin de comprendre l’influence de vos activités sur les utilisateurs tout au long de leur vie ou durant une seule session.

La méthodologie de calcul est prise en charge pour les types d’activité suivants :

* Test A/B

   Une exception toutefois : les activités A/B à ciblage automatique sont seulement compatibles avec la méthodologie de calcul « Visite » par défaut.

* Ciblage d’expérience (XT)
* Test multivarié (MVT)

   En ce qui concerne le rapport de contribution des éléments de test multivarié, Target ne prend pas en charge les impressions d’activité pour les mesures de type Recettes.

* Recommandations

Seule la méthodologie de calcul par défaut (Visites) est actuellement prise en charge avec les activités d’Automated Personalization.

Vous pouvez afficher les rapports selon les méthodologies de comptabilisation suivantes :

* **Visiteur** : participant unique à l’activité, pour la durée de cette dernière.

   Un utilisateur est compté comme nouveau participant s’il consulte le site à l’aide d’un nouvel ordinateur ou d’un nouveau navigateur, s’il supprime les cookies ou s’il effectue une conversion puis revient à l’activité avec le même cookie. Un participant est identifié par le PCID dans le cookie de sa mbox. Si le PCID change, cette personne est considérée comme un nouveau visiteur.

* **Visite :** participant unique à une expérience durant une seule session de navigateur de 30 minutes.

   Si un utilisateur revient sur le site après une conversion ou après en avoir été absent pendant au moins 30 minutes, il est compté comme une nouvelle visite. Une visite est identifiée par `sessionID` dans le cookie de la mbox du visiteur. Lorsque `sessionID` change, la visite est considérée comme nouvelle.

* **Affichage impression/page :** comptée à chaque fois qu’un visiteur charge une page de l’activité.

   Par exemple, une seule visite peut inclure plusieurs impressions de votre page d’accueil.

>[!NOTE]
>
>En règle générale, les comptes sont déterminés en fonction des cookies et de l’activité des sessions. Si, toutefois, vous atteignez le point de conversion final d’une activité, puis entrez à nouveau dans cette activité, vous êtes considéré comme un nouveau participant et une nouvelle visite dans l’activité. C’est le cas même si les valeurs PCID et `sessionID` ne changent pas.

## Pourquoi ? [!DNL Target] recommander l’utilisation des t-tests de Student ? {#t-test}

Les tests A/B sont des expériences permettant de comparer la valeur moyenne de certaines mesures commerciales dans une variante de contrôle (également appelée expérience) à la valeur moyenne de la même mesure dans une ou plusieurs expériences alternatives.

[!DNL Target] recommande d’utiliser [Le test en t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test), car elles nécessitent moins d’hypothèses que les alternatives telles que les tests z et sont le test statistique approprié pour effectuer des comparaisons par paires de mesures commerciales (quantitatives) entre des expériences de contrôle et d’autres expériences.

### Plus de détails

Lors de l’exécution de tests A/B en ligne, chaque utilisateur/visiteur est affecté de manière aléatoire à une seule variante. Ensuite, nous effectuons des mesures des mesures commerciales intéressantes (par exemple, conversions, commandes, recettes, etc.) pour les visiteurs dans chaque variante. Le test statistique que nous utilisons teste ensuite l’hypothèse selon laquelle la mesure commerciale moyenne (par exemple, taux de conversion, commandes par utilisateur, recettes par utilisateur, etc.) est égal à pour le contrôle et une variante donnée.

Bien que la mesure commerciale elle-même puisse être distribuée selon une distribution arbitraire, la distribution de la moyenne de cette mesure (dans chaque variante) doit converger vers une distribution normale via la variable [Théorie de limite centrale](https://en.wikipedia.org/wiki/Central_limit_theorem). Bien qu’il n’existe aucune garantie quant à la vitesse à laquelle cette répartition d’échantillonnage de la moyenne convergera vers la normale, cette condition est généralement atteinte étant donné l’échelle des visiteurs lors des tests en ligne.

Compte tenu de cette normalité de la moyenne, la statistique de test à utiliser peut être affichée selon une répartition en t, car il s’agit du ratio d’une valeur distribuée normalement (la différence de moyens de la mesure commerciale) à un terme de mise à l’échelle basé sur une estimation des données (l’erreur standard de la différence de moyens). Le **test en t** est alors le test d’hypothèse approprié, étant donné que la statistique de test suit une distribution en t.

### Pourquoi d’autres tests ne sont pas utilisés

A **z-test** est techniquement inapproprié, car dans le scénario de test A/B classique, le dénominateur de la statistique de test n’est pas dérivé d’une variance connue et doit plutôt être estimé à partir des données. Toutefois, pour les échantillons suffisamment volumineux, le test en z et le test en t sont identiques.

**Tests au carré** ne sont pas utilisées car elles sont appropriées pour déterminer s’il existe une relation qualitative entre deux variantes (c’est-à-dire une hypothèse nulle qu’il n’y a pas de différence entre les variantes). Les tests en t sont plus adaptés au scénario de _quantitativement_ comparaison des mesures.

Le **Test d’interface utilisateur MannWhitney** est un test non paramétrique, qui est approprié lorsque la distribution d’échantillonnage de la mesure commerciale moyenne (pour chaque variante) n’est pas distribuée normalement. Cependant, comme nous l’avons mentionné plus haut, étant donné l’ampleur du trafic impliqué dans les tests en ligne, le théorème central des limites s’applique généralement, de sorte que le test en t peut être appliqué en toute sécurité.

Méthodes plus complexes comme **ANOVA** (qui généralisent les tests en t à plus de deux variantes) peut être appliqué lorsqu’un test comporte plus de deux expériences (&quot;tests A/Bn&quot;). Cependant, ANOVA répond à la question &quot;si toutes les variantes ont la même moyenne&quot;, tandis que dans le test A/Bn classique, nous sommes plus intéressés par _Quelle variante spécifique_ est la meilleure. Dans [!DNL Target]Par conséquent, nous appliquons des tests t réguliers comparant chaque variante à un contrôle, avec une correction Bonferroni pour tenir compte des comparaisons multiples.