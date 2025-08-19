---
keywords: audience;règles d’audience;créer une audience;création d’une audience;audience ciblée;audience avec création de rapports;audience avec rapport;segment;paramètres de profil personnalisés;définition de l’audience;liste d’audiences
description: Découvrez comment utiliser les audiences dans  [!DNL Adobe Target].
title: Comment utiliser la liste d’audiences ?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 22%

---

# Créer des audiences

Les audiences dans [!DNL Adobe Target] déterminent qui peut voir le contenu et les expériences d’une activité ciblée.

Les audiences sont utilisées partout où le ciblage est disponible. Lors du ciblage d’une activité, vous disposez des options suivantes :

* Sélectionnez une audience réutilisable dans la liste [!UICONTROL Audiences]
* [Créer une audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) et la cibler
* [Combiner plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer une audience ad hoc

Vous pouvez également utiliser les données d’audience collectées par [!DNL Adobe Analytics] pour le ciblage et la personnalisation en temps réel dans [!DNL Target] et d’autres applications [!DNL Adobe Experience Cloud]. Voir [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) dans le guide *Composants de l’interface centrale d’Experience Cloud*.

Il existe deux types d’audiences dans [!DNL Target] :

* **Ciblage des audiences :** utilisé pour diffuser différents contenus à différents types de visiteurs et visiteuses.
* **Audiences de rapports :** utilisé pour déterminer comment différents types de visiteurs répondent au même contenu afin que vous puissiez analyser les résultats de vos tests.

  Dans [!DNL Target], vous pouvez configurer les audiences avec création de rapports seulement si vous utilisez [!DNL Target] comme source des rapports. Si vous utilisez [Adobe Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), vous devez configurer vos audiences de création de rapports dans [!DNL Analytics].

## Utiliser la liste [!UICONTROL Audiences] {#use-list}

Pour accéder à la liste [!UICONTROL Audiences], cliquez sur **[!UICONTROL Audiences]** dans la barre de menus supérieure :

![[!UICONTROL Audiences] la liste](assets/audiences_list.png)

La liste [!UICONTROL Audiences] contient les audiences que vous pouvez utiliser dans vos activités. Utilisez la liste [!UICONTROL Audiences] pour créer, modifier, dupliquer, copier ou combiner des audiences. La liste affiche également la source dans laquelle l’audience a été créée :

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

  >[!NOTE]
  >
  >La source [!DNL Adobe Experience Platform] est disponible pour tous les clients [!DNL Target] utilisant le [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}. Les audiences disponibles à partir du [!DNL Adobe Experience Platform] peuvent être utilisées telles quelles ou [combinées avec des audiences existantes](/help/main/c-target/combining-multiple-audiences.md).
  >
  >Les utilisateurs doivent disposer d’un statut [!UICONTROL Approver] ou supérieur dans [!DNL Target] pour configurer [!DNL Target] cartes [!UICONTROL Destinations] dans AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
  >
  >Pour plus d’informations, voir [Utilisation des audiences de Adobe Experience Platform](#aep).

Les audiences prédéfinies, telles que « [!UICONTROL New Visitors] » et « [!UICONTROL Returning Visitors] », ne peuvent pas être renommées.

Lorsque vous travaillez avec des audiences créées à l’origine dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], [!DNL Target] vous avertit si vous référencez une audience dans [!DNL Target] activités qui ont été supprimées ultérieurement dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Si une audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], une icône d’avertissement dans la liste des [!UICONTROL Audience] et le sélecteur d’audience s’affiche. Une info-bulle dans l’interface utilisateur de [!DNL Target] indique également que l’audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Si vous tentez de combiner plusieurs audiences, parmi lesquelles une audience supprimée, ou si vous venez d’enregistrer une activité faisant référence à une audience supprimée, un message d’avertissement apparaît.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. Lors de la création d’une audience, faites glisser les attributs que vous souhaitez utiliser pour cibler votre activité dans la fenêtre du créateur d’audiences. Si l’attribut souhaité ne s’affiche pas, il n’a pas été déclenché par une mbox. D’autres paramètres de mbox personnalisés sont disponibles dans la liste déroulante [!UICONTROL Custom Parameters] .

Utilisez le bouton [!UICONTROL Filters] pour filtrer la liste [!UICONTROL Audiences] par source : [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud] et [!DNL Adobe Experience Platform].

![Option Filtres dans la liste des [!UICONTROL Audiences]](assets/filters.png)

Utilisez la zone de [!UICONTROL Search audiences] pour rechercher votre liste de [!UICONTROL Audiences]. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste [!UICONTROL Audiences] par nom d’audience ou par date de sa dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Affichage des définitions d’audience {#section_11B9C4A777E14D36BA1E925021945780}

Vous pouvez afficher les détails de la définition de l’audience sur une carte pop-up à différents endroits dans l’interface utilisateur de [!DNL Target] sans ouvrir l’audience. Cette fonctionnalité s&#39;applique aux audiences créées dans [!DNL Target Standard/Premium] et aux audiences importées depuis [!DNL Target Classic] ou créées via l&#39;API.

Par exemple, la carte de définition d’audience suivante est accessible en cliquant sur l’icône [!UICONTROL View Details] de l’audience souhaitée :

![Activités > Définition d’audience](assets/audience_definition_list.png)

La carte de définition d’audience suivante est accessible en cliquant sur l’icône [!UICONTROL View Details] sur la page [!UICONTROL Overview] d’une activité :

![Activités > Définition d’audience](assets/view-details-activity-overview.png)

La carte de définition de l’audience affiche le type, la source et les attributs de l’audience. Cliquez sur **[!UICONTROL View full details]** pour afficher d’autres activités qui font référence à cette audience, le cas échéant. Si vous affichez une carte de définition d’audience à partir de la page [!UICONTROL Overview] d’une activité, cliquez sur **[!UICONTROL Audience Usage]**.

Les informations d’utilisation des audiences peuvent vous aider à éviter tout impact accidentel sur d’autres activités lors de la modification des audiences. Ces informations comprennent les [!UICONTROL Live Activities], les [!UICONTROL Inactive Activities], les [!UICONTROL Archived Activities] et les [!UICONTROL Syncing Activities]. Cette fonctionnalité est disponible pour toutes les audiences (audiences de bibliothèque et [audiences d’activité uniquement](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si une audience est [combinée avec une autre audience](/help/main/c-target/combining-multiple-audiences.md) et que l’audience combinée est utilisée pour créer une activité, les informations d’utilisation des deux audiences répertorient cette activité nouvellement créée.

![image audience_definition_list_usage](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Utiliser des audiences d’[!DNL Adobe Experience Platform] {#aep}

Les audiences créées dans [!DNL Adobe Experience Platform] fournissent des données client plus riches et permettent d’offrir une personnalisation plus poussée.

Pour plus d’informations, voir [Utilisation des audiences d’ [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## Vidéo de formation : utilisation des audiences ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comprend des informations sur l’utilisation des audiences.

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Utilisation d’audiences à des fins de création passive de rapports dans une activité
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)
