---
keywords: audience;audience rules;create audience;creating audience;targeting audience;reporting audience;report audience;segment;custom profile parameters;audience definition;audiences list
description: Les audiences dans Adobe Target déterminent qui verra le contenu et les expériences d’une activité ciblée.
title: Création d’audiences dans Adobe Target
feature: audiences
topic: Advanced,Standard,Classic
uuid: 994eed40-11ca-460e-827c-75a4db8a942d
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 95%

---


# Créer des audiences{#create-audiences}

Les audiences dans Adobe Target déterminent qui verra le contenu et les expériences d’une activité ciblée.

Les audiences sont utilisées partout où le ciblage est disponible. Lors du ciblage d’une activité, vous pouvez sélectionner une audience réutilisable dans la liste [!UICONTROL Audiences], [créer une audience spécifique à l’activité](/help/c-target/creating-activity-only-audience.md) et la cibler ou [combiner plusieurs audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer une audience ad hoc.

Vous pouvez également utiliser les données d’audience collectées par [!DNL Analytics] pour un ciblage en temps réel et une personnalisation dans [!DNL Adobe Target] et d’autres solutions [!DNL Experience Cloud]. Consultez [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) dans le Guide *de l’utilisateur des services* principaux.

[!DNL Target] définit deux types d’audiences :

* **Audiences avec ciblage :** Utilisé pour diffuser un contenu différent à différents types de visiteurs.
* **Audiences avec création de rapports :** Utilisé pour déterminer comment différents types de visiteurs répondent au même contenu pour vous permettre d’analyser vos résultats de test.

   Dans [!DNL Target], vous pouvez configurer les audiences avec création de rapports seulement si vous utilisez [!DNL Target] comme source des rapports. Si vous utilisez [ Adobe Analytics comme source des rapports](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), vous devez configurer les audiences avec création de rapports dans [!DNL Analytics].

## Utilisation de la liste Audiences

Pour accéder à la liste des [!UICONTROL audiences], cliquez sur **[!UICONTROL Audiences]** dans la barre de menu supérieure :

![Liste Audiences](assets/audiences_list.png)

La liste [!UICONTROL Audiences] comporte toutes les audiences que vous pouvez utiliser dans vos activités. Utilisez la liste [!UICONTROL Audiences] pour créer, modifier, supprimer, copier ou combiner des audiences. La liste indique également la source où l’audience a été créée ([!DNL Target], [!DNL Target Classic], [!DNL Adobe Audience Manager (AAM),] [!DNL Experience Cloud], etc.). Les audiences prédéfinies, telles que Nouveaux visiteurs ou Visiteurs récurrents, ne peuvent pas être renommées.

Lors de l’utilisation d’audiences créées dans AAM, vous recevez une alerte si vous référencez dans les activités de Target une audience qui avait également été supprimée dans AAM.

* Lorsqu’une audience a été supprimée dans AAM, une icône d’avertissement apparaît dans la liste d’[!UICONTROL audiences] et dans le sélecteur d’audiences. Une info-bulle dans l’interface utilisateur vous prévient également que l’audience a été supprimée dans AAM.
* Si vous tentez de combiner plusieurs audiences, parmi lesquelles une audience supprimée, ou si vous venez d’enregistrer une activité faisant référence à une audience supprimée, un message d’avertissement apparaît.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. When adding an audience, click **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]**, then choose the parameter you want to use to target your activity. Si le paramètre souhaité ne s’affiche pas, il n’a pas été déclenché par une mbox. D’autres paramètres mbox personnalisés sont disponibles dans la liste déroulante [!UICONTROL Paramètres personnalisés].

Utilisez la zone de recherche pour effectuer des recherches dans votre liste d’[!UICONTROL audiences]. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste d’[!UICONTROL audiences] par nom d’audience ou par date de dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Affichage des définitions d’audience {#section_11B9C4A777E14D36BA1E925021945780}

Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle à différents emplacements de l’interface utilisateur de Target sans ouvrir l’audience. Cette fonctionnalité s’applique aux audiences créées dans Target Standard/Premium et aux audiences importées depuis Target Classic ou créées par l’intermédiaire de l’API.

Par exemple, la carte de définition de l’audience suivante est accessible en survolant une audience de la liste d’audiences, puis en cliquant sur l’icône Affichage :

![Activités > Définition d’audience](assets/audience_definition_list.png)

La carte de définition de l’audience suivante est accessible en cliquant sur l’icône Affichage de la page Aperçu d’une activité :

![Activités > Définition d’audience](assets/audience_definition_list.png)

Cliquez sur l’onglet [!UICONTROL Utilisation de l’audience] pour afficher les autres activités qui référencent cette audience, le cas échéant. Vous pouvez ainsi éviter toute répercussion accidentelle sur les autres activités lorsque vous modifiez les audiences. Les informations portent sur les activités actives, activités inactives, activités archivées et la synchronisation d’activités. Cette fonctionnalité est disponible pour toutes les audiences (audiences de bibliothèque et [les audiences d’activité uniques](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si une audience donnée est combinée à une autre et que cette audience cumulée est utilisée pour créer une activité, les informations d’utilisation relatives aux deux audiences mentionneront ces activités nouvellement créées.

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

## Vidéo de formation : Utilisation des audiences ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo comprend des informations sur l’utilisation des audiences.

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Utilisation d’audiences à des fins de création passive de rapports dans une activité
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)
