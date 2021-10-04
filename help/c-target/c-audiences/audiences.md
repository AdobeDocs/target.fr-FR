---
keywords: audience;règles d’audience;créer une audience;création d’une audience;audience ciblée;audience avec création de rapports;audience avec rapport;segment;paramètres de profil personnalisés;définition de l’audience;liste d’audiences
description: Découvrez comment utiliser la liste [!UICONTROL Audiences] dans  [!DNL Adobe Target].
title: Comment utiliser la liste d’audiences ?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: b74cccdc43c34367819ed8a908a304b567d7ecbb
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 34%

---

# Créer des audiences

Les audiences de [!DNL Adobe Target] déterminent qui voit le contenu et les expériences dans une activité ciblée.

Les audiences sont utilisées partout où le ciblage est disponible. Lors du ciblage d’une activité, vous disposez des options suivantes :

* Sélectionnez une audience réutilisable dans la liste [!UICONTROL Audiences]
* [Créer une ](/help/c-target/creating-activity-only-audience.md) audience spécifique à une activité et la cibler
* [Combinaison de plusieurs ](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) audiences pour créer une audience ad hoc

Vous pouvez également utiliser les données d’audience collectées par [!DNL Adobe Analytics] pour un ciblage en temps réel et une personnalisation dans [!DNL Target] et d’autres applications [!DNL Adobe Experience Cloud]. Voir [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) dans le guide *Composants de l’interface centrale Experience Cloud*.

Il existe deux types d’audiences dans [!DNL Target] :

* **Ciblage des audiences :** utilisé pour diffuser du contenu différent à différents types de visiteurs.
* **Audiences avec création de rapports :**  permet de déterminer comment différents types de visiteurs répondent au même contenu afin que vous puissiez analyser les résultats de test.

   Dans [!DNL Target], vous pouvez configurer les audiences avec création de rapports seulement si vous utilisez [!DNL Target] comme source des rapports. Si vous utilisez [ Adobe Analytics comme source des rapports](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), vous devez configurer les audiences avec création de rapports dans [!DNL Analytics].

## Utilisation de la liste [!UICONTROL Audiences] {#use-list}

Pour accéder à la liste des [!UICONTROL audiences], cliquez sur **[!UICONTROL Audiences]** dans la barre de menu supérieure :

![Liste Audiences](assets/audiences_list.png)

La liste [!UICONTROL Audiences] contient les audiences que vous pouvez utiliser dans vos activités. Utilisez la liste [!UICONTROL Audiences] pour créer, modifier, dupliquer, copier ou combiner des audiences. La liste présente également la source dans laquelle l’audience a été créée:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >La source [!DNL Adobe Experience Platform] est disponible pour tous les clients [!DNL Target] qui utilisent le [SDK Web Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Les audiences disponibles à partir de [!DNL Adobe Experience Platform] peuvent être utilisées en l’état ou [combinées avec les audiences existantes](/help/c-target/combining-multiple-audiences.md).

Les audiences prédéfinies, telles que &quot;[!UICONTROL Nouveaux visiteurs]&quot; et &quot;[!UICONTROL Visiteurs récurrents]&quot;, ne peuvent pas être renommées.

Lorsque vous utilisez des audiences créées à l’origine dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], [!DNL Target] vous alerte si vous référencez une audience dans des activités [!DNL Target] qui ont été supprimées ultérieurement dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Si une audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], une icône d’avertissement s’affiche dans la liste [!UICONTROL Audience] et le sélecteur d’audience. Une info-bulle dans l’interface utilisateur [!DNL Target] indique également que l’audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Si vous tentez de combiner plusieurs audiences, parmi lesquelles une audience supprimée, ou si vous venez d’enregistrer une activité faisant référence à une audience supprimée, un message d’avertissement apparaît.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. Lors de la création d’une audience, faites glisser les attributs à utiliser pour cibler votre activité dans la fenêtre du créateur d’audiences. Si l’attribut souhaité ne s’affiche pas, l’attribut n’a pas été déclenché par une mbox. D’autres paramètres mbox personnalisés sont disponibles dans la liste déroulante [!UICONTROL Paramètres personnalisés].

Utilisez le bouton [!UICONTROL Filtres] pour filtrer la liste [!UICONTROL Audiences] par source : [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud] et [!DNL Adobe Experience Platform].

![Option Filtres dans la   liste des audiences](assets/filters.png)

Utilisez la zone [!UICONTROL Rechercher des audiences] pour effectuer une recherche dans votre liste [!UICONTROL Audiences]. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste d’[!UICONTROL audiences] par nom d’audience ou par date de dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Affichage des définitions d’audience {#section_11B9C4A777E14D36BA1E925021945780}

Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle à différents endroits dans l’interface utilisateur de [!DNL Target] sans ouvrir l’audience. Cette fonctionnalité s’applique aux audiences créées dans [!DNL Target Standard/Premium] et aux audiences importées depuis [!DNL Target Classic] ou créées via l’API.

Par exemple, la carte de définition de l’audience suivante est accessible en cliquant sur l’icône [!UICONTROL Afficher les détails] pour l’audience souhaitée :

![Activités > Définition d’audience](assets/audience_definition_list.png)

La carte de définition de l’audience suivante est accessible en cliquant sur l’icône [!UICONTROL Afficher les détails] de la page [!UICONTROL Aperçu] d’une activité :

![Activités > Définition d’audience](assets/view-details-activity-overview.png)

La carte de définition de l’audience indique le type, la source et les attributs de l’audience. Cliquez sur **[!UICONTROL Afficher tous les détails]** pour afficher d’autres activités qui référencent cette audience, le cas échéant. Si vous affichez une carte de définition d’audience à partir de la page [!UICONTROL Aperçu] d’une activité, cliquez sur **[!UICONTROL Utilisation de l’audience]**.

Les informations d’utilisation de l’audience peuvent vous aider à éviter tout impact accidentel sur d’autres activités lors de la modification des audiences. Les informations incluent [!UICONTROL Activités actives], [!UICONTROL Activités inactives], [!UICONTROL Activités archivées] et [!UICONTROL Activités de synchronisation]. Cette fonctionnalité est disponible pour toutes les audiences (audiences de bibliothèque et [les audiences d’activité uniques](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si une audience est [combinée à une autre audience](/help/c-target/combining-multiple-audiences.md) et que l’audience combinée est utilisée pour créer une activité, les informations d’utilisation des deux audiences répertorient cette activité nouvellement créée.

![](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Vidéo de formation : Utilisation des audiences ![Badge du tutoriel](/help/assets/tutorial.png)

Cette vidéo comprend des informations sur l’utilisation des audiences.

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Utilisation d’audiences à des fins de création passive de rapports dans une activité
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)
