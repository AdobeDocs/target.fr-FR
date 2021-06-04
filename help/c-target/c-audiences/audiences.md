---
keywords: audience;règles d’audience;créer une audience;création d’une audience;audience ciblée;audience avec création de rapports;audience avec rapport;segment;paramètres de profil personnalisés;définition de l’audience;liste d’audiences
description: Découvrez comment utiliser la liste [!UICONTROL Audiences] dans Adobe [!DNL Target] et comment afficher les cartes Définition d’audience qui contiennent les détails d’audience et les informations d’utilisation.
title: Comment utiliser la liste d’audiences ?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 06a5fda72a649c4037cb78d3e670747cd297a64d
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 60%

---

# Créer des audiences

Les audiences de [!DNL Adobe Target] déterminent qui voit le contenu et les expériences dans une activité ciblée.

Les audiences sont utilisées partout où le ciblage est disponible. Lors du ciblage d’une activité, vous pouvez disposer des options suivantes :

* Sélectionnez une audience réutilisable dans la liste [!UICONTROL Audiences]
* [Créer une ](/help/c-target/creating-activity-only-audience.md) audience spécifique à une activité et la cibler
* [Combinaison de plusieurs ](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) audiences pour créer une audience ad hoc

Vous pouvez également utiliser les données d’audience collectées par [!DNL Adobe Analytics] pour un ciblage en temps réel et une personnalisation dans [!DNL Target] et d’autres applications [!DNL Adobe Experience Cloud]. Voir [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) dans le guide *Composants de l’interface centrale Experience Cloud*.

[!DNL Target] définit deux types d’audiences :

* **Audiences avec ciblage :** Utilisé pour diffuser un contenu différent à différents types de visiteurs.
* **Audiences avec création de rapports :** Utilisé pour déterminer comment différents types de visiteurs répondent au même contenu pour vous permettre d’analyser vos résultats de test.

   Dans [!DNL Target], vous pouvez configurer les audiences avec création de rapports seulement si vous utilisez [!DNL Target] comme source des rapports. Si vous utilisez [ Adobe Analytics comme source des rapports](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), vous devez configurer les audiences avec création de rapports dans [!DNL Analytics].

## Utilisation de la liste [!UICONTROL Audiences]

Pour accéder à la liste des [!UICONTROL audiences], cliquez sur **[!UICONTROL Audiences]** dans la barre de menu supérieure :

![Liste Audiences](/help/c-target/c-audiences/assets/audiences_list.png)

La liste [!UICONTROL Audiences] comporte toutes les audiences que vous pouvez utiliser dans vos activités. Utilisez la liste [!UICONTROL Audiences] pour créer, modifier, supprimer, copier ou combiner des audiences. La liste indique également la source où l’audience a été créée ([!DNL Target], [!DNL Target Classic] et [!DNL Experience Cloud]). Les audiences prédéfinies, telles que &quot;[!UICONTROL Nouveaux visiteurs]&quot; et &quot;[!UICONTROL Visiteurs récurrents]&quot;, ne peuvent pas être renommées.

Lorsque vous travaillez avec des audiences qui ont été créées à l’origine dans [!DNL Experience Cloud], Target vous alerte si vous référencez une audience dans des activités [!DNL Target] qui ont été supprimées ultérieurement dans [!DNL Experience Cloud].

* Si une audience a été supprimée dans [!DNL Experience Cloud], une icône d’avertissement s’affiche dans la liste [!UICONTROL Audience] et dans le sélecteur d’audience. Une info-bulle dans l’interface utilisateur vous prévient également que l’audience a été supprimée dans [!DNL Experience Cloud].
* Si vous tentez de combiner plusieurs audiences, parmi lesquelles une audience supprimée, ou si vous venez d’enregistrer une activité faisant référence à une audience supprimée, un message d’avertissement apparaît.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. Lors de l’ajout d’une audience, cliquez sur l’attribut que vous souhaitez utiliser pour cibler votre activité. Si l’attribut souhaité n’apparaît pas, il n’a pas été déclenché par une mbox. D’autres paramètres mbox personnalisés sont disponibles dans la liste déroulante [!UICONTROL Paramètres personnalisés].

Utilisez le bouton [!UICONTROL Filtres] pour filtrer la liste [!UICONTROL Audiences] par source : [!DNL Adobe Target], [!DNL Adobe Target Classic] et [!DNL Experience Cloud].

![Option Filtres dans la   liste des audiences](/help/c-target/c-audiences/assets/filters.png)

Utilisez la zone [!UICONTROL Rechercher des audiences] pour effectuer une recherche dans votre liste [!UICONTROL Audiences]. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste d’[!UICONTROL audiences] par nom d’audience ou par date de dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Affichage des définitions d’audience {#section_11B9C4A777E14D36BA1E925021945780}

Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle à différents emplacements de l’interface utilisateur de Target sans ouvrir l’audience. Cette fonctionnalité s’applique aux audiences créées dans [!DNL Target Standard/Premium] et aux audiences importées depuis [!DNL Target Classic] ou créées via l’API.

Par exemple, la carte de définition de l’audience suivante est accessible en cliquant sur l’icône [!UICONTROL Afficher les détails] pour l’audience souhaitée :

![Activités > Définition d’audience](assets/audience_definition_list.png)

La carte de définition de l’audience suivante est accessible en cliquant sur l’icône [!UICONTROL Afficher les détails] de la page [!UICONTROL Aperçu] d’une activité :

![Activités > Définition d’audience](/help/c-target/c-audiences/assets/view-details-activity-overview.png)

La carte de définition de l’audience indique le type, la source et les attributs de l’audience. Cliquez sur **[!UICONTROL Afficher tous les détails]** pour afficher d’autres activités qui référencent cette audience, le cas échéant. Si vous affichez une carte de définition d’audience à partir de la page [!UICONTROL Aperçu] d’une activité, cliquez sur **[!UICONTROL Utilisation de l’audience]**.

Les informations d’utilisation de l’audience peuvent vous aider à éviter tout impact accidentel sur d’autres activités lors de la modification des audiences. Les informations portent sur les activités actives, activités inactives, activités archivées et la synchronisation d’activités. Cette fonctionnalité est disponible pour toutes les audiences (audiences de bibliothèque et [les audiences d’activité uniques](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si une audience est combinée à une autre audience et que l’audience combinée est utilisée pour créer une activité, les informations d’utilisation des deux audiences répertorient cette activité nouvellement créée.

![](assets/audience_definition_list_usage.png)

La carte de définition de l’audience suivante est destinée à une audience importée depuis Adobe Experience Cloud. Dans ce cas, l’audience a été importée depuis Adobe Audience Manager (AAM).

![Onglet Utilisation sur la carte Définition d’audience](assets/audience_definition_mc.png)

Les détails suivants sont disponibles pour les types d’audience importés suivants :

| Type d’audience | Détails |
|--- |--- |
| Audience mobile | Nom marketing, Fournisseur et Modèle.<br>L’opérateur `matches | does not match` s’affiche au lieu de l’`equals | does not equal`<br>![audience mobile importée](/help/c-target/c-audiences/assets/imported_mobile_audience.png). |
| Audience de comportement des visiteurs | **user.categoryAffinity :** `categoryAffinity` avec le paramètre `FAVORITE`.<br>![Surveillance ](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**d’affinité catégorielle importée** : le service de surveillance est égal à true.<br>**Aucun service de surveillance :** Monitoring service equals false.<br>![Surveillance importée](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| Audiences utilisant l’opérateur SAUF | **Règle unique** : Target affiche l’audience au format `[All Visitor AND [NOT [rule]`. Une règle unique NON s’affiche avec l’opérateur « ET » avec l’audience `AllVisitor`.<br>![Audience non importée](/help/c-target/c-audiences/assets/imported_not_audience.png) |

Gardez les points suivants à l’esprit lorsque vous travaillez avec des audiences importées :

* Les audiences cibles d’expression ne sont plus prises en charge dans Target Standard/Premium.
* Target Standard/Premium ne prend pas en charge certaines audiences obsolètes ou a amélioré les opérateurs pour faciliter l’utilisation. De ce fait, la définition d’une audience importée, même si elle fonctionne selon la définition, ne signifie pas qu’elle est désormais disponible pour création dans l’interface Standard/Premium. Par exemple, les audiences sociales sont visibles avec leurs règles, mais Target Standard/Premium ne permet pas de créer des audiences sociales.

## Vidéo de formation : Utilisation des audiences ![Badge de tutoriel](/help/assets/tutorial.png)

Cette vidéo comprend des informations sur l’utilisation des audiences.

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Utilisation d’audiences à des fins de création passive de rapports dans une activité
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)
