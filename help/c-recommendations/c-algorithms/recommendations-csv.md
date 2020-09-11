---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Téléchargez un fichier CSV pour personnaliser vos recommandations.
title: Téléchargement de critères personnalisés
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1893'
ht-degree: 65%

---


# ![PREMIUM](/help/assets/premium.png) Téléchargement de critères personnalisés{#upload-custom-criteria}

Téléchargez un fichier CSV pour personnaliser vos recommandations.

## Accès à l’écran Créer de nouveaux critères

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une [!DNL Recommendations] activité à l’aide du compositeur [!UICONTROL d’expérience] visuelle, vous accédez immédiatement à l’écran [!UICONTROL Sélectionner les critères] après avoir sélectionné un élément sur votre page et cliqué sur [!UICONTROL Remplacer par Recommendations], Insérer Recommendations Before ou sur Insérer Recommendations After.  Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Créer des critères]**. Si vous créez un nouveau critère, vous avez la possibilité d’enregistrer vos critères pour les utiliser avec d’autres [!DNL Recommendations] activités. For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Créer de nouveaux critères] en utilisant la première méthode : l’écran **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** de bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Télécharger des critères]** personnalisés.

1. Configurez les informations dans les sections suivantes.

## Informations fondamentales {#info}

1. Saisissez un **[!UICONTROL Nom de critère]**.

   C’est le nom « interne » utilisé pour décrire ce critère. Par exemple, vous voulez peut-être appeler votre critère « Produits générant la marge la plus élevée », mais vous ne voulez pas que ce titre soit affiché publiquement. Reportez-vous à la prochaine étape pour configurer le titre destiné au public.

   ![Section Informations de base](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Saisissez un **[!UICONTROL Titre d’affichage]** destiné à l’audience qui apparaîtra sur la page pour n’importe quelle recommandation qui utilise ce critère.

   Vous pouvez par exemple souhaiter afficher « Les personnes qui ont consulté cet article ont aussi consulté celui-ci » ou « Produits similaires » lorsque vous utilisez ce critère pour afficher des recommandations.

1. Saisissez une courte **[!UICONTROL Description]** du critère.

   La description doit vous aider à identifier les critères et peut inclure des informations sur l’objectif des critères.

1. Sélectionnez un secteur industriel vertical en fonction des objectifs de votre activité de recommandations.

   | Secteur industriel vertical | Objectif |
   |--- |--- |
   | Vente au détail / commerce électronique | Conversion entraînant un achat |
   | Génération de piste / B2B / Services financiers | Conversion sans achat |
   | Médias / Publication | Engagement |

   Les autres options de critère sont modifiées en fonction du secteur industriel vertical que vous sélectionnez.

1. Sélectionnez un **[!UICONTROL Type de page]**.

   Vous pouvez sélectionner plusieurs types de page.

   Le secteur industriel vertical et les types de page sont utilisés pour classer les critères enregistrés, ce qui facilite la réutilisation des critères pour d’autres activités [!DNL Recommendations].

1. Sélectionnez une **[!UICONTROL Clé de recommandation]**.

   Pour plus d’informations sur la base des critères sur une clé, voir [Baser la recommandation sur une clé de recommandation](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. Sélectionnez la **[!UICONTROL Logique de recommandation]**.

   Pour plus d’informations sur les options de logique de recommandation, consultez les [Critères](../../c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

## Contenu {#content}

Content rules determine what happens if the number of recommended items does not fill your [recommendations design](/help/c-recommendations/c-design-overview/design-overview.md). It is possible for [!DNL Recommendations] criteria to return fewer recommendations than your design calls for. Par exemple, si votre conception comporte des emplacements pour quatre éléments, mais que vos critères entraînent la recommandation de deux éléments seulement, vous pouvez laisser les emplacements restants vides ou utiliser des recommandations de sauvegarde pour remplir les emplacements supplémentaires.

![Section Contenu](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Facultatif) Faites glisser la bascule Rendu **[!UICONTROL de conception]** partiel vers la position &quot;Activé&quot;.

   Le plus grand nombre d’emplacements possible sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants. Si cette option est désactivée et qu’il n’y a pas suffisamment de contenu pour remplir tous les emplacements disponibles, les recommandations ne sont pas diffusées et le contenu par défaut s’affiche à la place.

   Activez cette option si vous souhaitez que les recommandations soient servies avec des emplacements vides. Utilisez les recommandations de sauvegarde si vous souhaitez que les emplacements de recommandation soient remplis avec du contenu basé sur vos critères, avec des emplacements vides remplis avec du contenu similaire ou populaire provenant de votre site, comme expliqué à l’étape suivante.

1. (Facultatif) Faites glisser la bascule **[!UICONTROL Afficher le Recommendations]** de sauvegarde vers la position &quot;Activé&quot;.

   Remplissez les emplacements vides restants de la conception avec une sélection aléatoire des produits les plus consultés sur l’ensemble du site.

   L’utilisation de recommandations de sauvegarde permet de s’assurer que votre conception de recommandation remplit tous les emplacements disponibles. Supposons que vous ayez une conception 4 x 1, comme illustré ci-dessous :

   ![Conception 4 x 1](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supposons que vos critères entraînent la recommandation de deux éléments seulement. Si vous activez l’option Rendu [!UICONTROL de conception] partiel, les deux premiers emplacements sont remplis, mais les deux autres emplacements restent vides. Cependant, si vous activez l’option [!UICONTROL Afficher le Recommendations] de sauvegarde, les deux premiers emplacements sont remplis selon vos critères spécifiés et les deux autres emplacements sont remplis selon vos recommandations de sauvegarde.

   La matrice suivante montre le résultat que vous observerez lors de l’utilisation des options de rendu [!UICONTROL de conception] partiel et de Recommendations [!UICONTROL de] sauvegarde :

   | Rendu de conception partiel | Recommandations de sauvegarde | Résultats |
   |--- |--- |--- |
   | Désactivé | Désactivé | Si un nombre inférieur de recommandations est renvoyé par rapport à celui attendu par la conception, cette dernière est remplacée par le contenu par défaut et aucune recommandation n’est affichée. |
   | Activé | Désactivé | La conception est rendue, mais elle peut inclure des espaces vides si un nombre inférieur de recommandations par rapport à celui attendu est renvoyé. |
   | Activé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est partiellement affichée.<br>Si le critère ne renvoie aucune recommandation et si les règles d’inclusion limitent les recommandations de sauvegarde à zéro, la conception est remplacée par le contenu par défaut. |
   | Désactivé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est replacée par le contenu par défaut et aucune recommandation n’est affichée. |

   Pour plus d’informations, voir [Utilisation d’une recommandation](/help/c-recommendations/c-algorithms/backup-recs.md)de sauvegarde.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Afficher la Recommendations]** de sauvegarde à l’étape précédente, vous pouvez activer l’option **[!UICONTROL Appliquer les règles d’inclusion aux recommandations]** de sauvegarde.

   Les règles d’inclusion déterminent les éléments qui sont inclus dans vos recommandations. Les options disponibles dépendent du secteur industriel vertical.

   For more details, see [Specify inclusion rules](#inclusion) below.

1. (Facultatif) Faites glisser l’option **[!UICONTROL Recommander les articles]** achetés précédemment vers la position &quot;Activé&quot;.

   Ce paramètre est basé sur `productPurchasedId`. Le comportement par défaut est de ne pas recommander des articles précédemment achetés. En général, vous ne souhaitez pas promouvoir des articles qu’un client a récemment achetés. Il est utile si vous vendez des articles que les gens n’achètent en général qu’une fois, comme des kayaks. Si vous vendez des articles que les gens reviennent acheter à plusieurs reprises, comme du shampoing ou d&#39;autres articles personnels, vous devez activer cette option.

## Règles d’inclusion {#inclusion}

Plusieurs options vous aident à préciser les éléments qui s’affichent dans vos recommandations. Vous pouvez utiliser des règles d’inclusion lors de la création de critères ou de promotions.

![Règles d’inclusion](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Les règles d’inclusion sont facultatives. Cependant, le fait de définir ces détails vous permet de mieux contrôler les éléments qui apparaissent dans vos recommandations. Chaque détail configuré précise les critères d’affichage.

Vous pouvez, par exemple, choisir d’afficher uniquement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 € et 45 €. Vous pouvez également pondérer chaque attribut, de telle sorte que la probabilité d’affichage soit plus élevée pour les éléments qui présentent plus d’intérêt pour vos activités.

Par exemple, vous pouvez choisir d’afficher les offres d’emploi pour les visiteurs qui visitent votre site uniquement à partir de certaines villes et qui possèdent les diplômes universitaires requis.

Les options de règle d’inclusion varient selon le secteur industriel vertical. Par défaut, les règles d’inclusion sont appliquées aux recommandations de sauvegarde.

>[!IMPORTANT]
>
>Veuillez utiliser les règles d’inclusion avec prudence. Elles se révèlent utiles si, par exemple, des règles en vigueur dans votre entreprise interdisent la recommandation d’une marque pendant la consultation d’une autre marque. L’utilisation de cette fonctionnalité a toutefois un coût. Si vous empêchez l’affichage de certains éléments alors qu’ils devraient normalement être affichés selon les critères d’activité, l’effet élévateur risque d’être amoindri.

Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Pour créer une règle d’inclusion simple, comme mentionné précédemment, afin d’afficher seulement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 et 45 €, procédez comme suit :

1. Définissez une gamme de prix pour les produits que vous souhaitez recommander.
1. Définissez la valeur de stock minimale pour les produits que vous souhaitez recommander.
1. Configurez la recommandation de manière à afficher uniquement les éléments qui répondent à certains critères.

   ![](assets/Recs_InclusionRules.png)

   Vous pouvez indiquer que les éléments sont inclus uniquement lorsque l’un des attributs de la liste répond (ou ne répond pas) à l’une ou plusieurs des conditions spécifiées.

   Les évaluateurs disponibles dépendent de la valeur que vous sélectionnez dans la première liste déroulante. Vous pouvez inclure plusieurs éléments. Ces éléments sont évalués par l’opérateur OU.

   Plusieurs règles sont associées à l’aide de l’opérateur ET.

   >[!NOTE]
   >
   >Cette option limite les éléments affichés dans la recommandation. Elle n’affecte pas les pages sur lesquelles la recommandation est affichée. Pour limiter l’emplacement d’affichage de la recommandation, sélectionnez les pages dans le compositeur d’expérience.

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Téléchargement d’un fichier CSV

1. Sélectionnez l’**[!UICONTROL emplacement]** de votre fichier CSV.

   ![Télécharger la section CSV](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   Le fichier CSV doit être correctement formaté pour pouvoir être téléchargé. Cliquez sur **[!UICONTROL Télécharger le modèle CSV]** pour obtenir un fichier CSV correctement formaté.

   Vous avez le choix entre deux options :

   * **FTP :** Pour transférer le fichier CSV depuis un serveur FTP, sélectionnez l’option **[!UICONTROL FTP]**, puis saisissez les informations requises. Vous pouvez utiliser le chiffrement SSL, qui transfère le fichier CSV en toute sécurité au moyen du protocole FTPS.
   * **URL :** Pour télécharger votre fichier CSV à partir d’une URL, sélectionnez **[!UICONTROL URL]**, puis saisissez une URL de flux.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   >[!NOTE]
   >
   >Les entités de critères personnalisés (lignes) peuvent comporter jusqu’à 1 000 éléments recommandés (colonnes).

Les mises à jour de critères personnalisés sont par défaut « cumulatives ». Les nouvelles paires clé-valeur spécifiées dans le fichier de chargement CSV remplacent les paires clé-valeur existantes. Les paires clé-valeur existantes qui n’ont pas de clés spécifiées dans le téléchargement CSV seront toujours disponibles pour la diffusion. Elles arriveront à expiration dans 31 jours à compter du dernier téléchargement dans le fichier CSV.

Contactez le service à la clientèle pour permettre au paramètre d’ignorer les résultats existants qui ne sont pas inclus dans le prochain chargement CSV. Si ce paramètre est activé, seules les clés présentes dans le fichier de flux CSV personnalisé seront disponibles pour la livraison. Ce paramètre s’applique à tous les critères personnalisés.

Les flux de critères personnalisés sont mis à jour une fois toutes les 24 heures.

Le statut de chargement et de synchronisation de votre chargement de critères personnalisés est visible au bas de chaque carte de critère sur la page Recommandations > Critère. Vous pouvez également voir l’état dans la boîte de dialogue Modifier lors de la modification des critères personnalisés.

Le flux d’un chargement sans erreur est composé des étapes suivantes : Planifié > Téléchargement du fichier du flux > Importation > Réussite.

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| Message d’erreur | Détails |
|--- |--- |
| Erreur inconnue | Indique une erreur technique interne. |
| Erreur d’analyse | Indique probablement un problème de format du fichier du flux. Corrigez le format du fichier et enregistrez à nouveau l’algorithme. Cela redémarre le processus de téléchargement du fichier. |
| Serveur introuvable | Fournissez une adresse IP ou un nom d’hôte visible sur Internet. |
| Erreur d’informations d’identification | Fournissez un nom d’utilisateur et un mot de passe valides pour un compte actif sur le serveur. |
| Répertoire introuvable | Fournissez un répertoire qui existe sur le serveur. |
| Fichier introuvable | Fournissez le nom d’un fichier qui existe sur le serveur dans le répertoire indiqué. |

## Vidéo de formation : Créer des critères dans Recommendations (12:33) ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo contient les informations suivantes (les détails sur le transfert de critères personnalisés commencent à 11h43) :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)