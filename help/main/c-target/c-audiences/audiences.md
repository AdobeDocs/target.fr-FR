---
keywords: audience;règles d’audience;créer une audience;création d’une audience;audience ciblée;audience avec création de rapports;audience avec rapport;segment;paramètres de profil personnalisés;définition de l’audience;liste d’audiences
description: Découvrez comment utiliser les audiences dans [!DNL Adobe Target].
title: Comment utiliser la liste d’audiences ?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 28%

---

# Créer des audiences

Audiences dans [!DNL Adobe Target] déterminer qui voit le contenu et les expériences dans une activité ciblée ;

Les audiences sont utilisées partout où le ciblage est disponible. Lors du ciblage d’une activité, vous disposez des options suivantes :

* Sélectionnez une audience réutilisable à partir du [!UICONTROL Audiences] list
* [Création d’une audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) et le cibler
* [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) pour créer une audience ad hoc

Vous pouvez également utiliser les données d’audience collectées par [!DNL Adobe Analytics] pour le ciblage et la personnalisation en temps réel dans [!DNL Target] et autres [!DNL Adobe Experience Cloud] applications. Voir [Audiences Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) dans le *Composants de l’interface centrale Experience Cloud* guide.

Il existe deux types d’audiences dans [!DNL Target]:

* **Ciblage des audiences :** Utilisé pour diffuser du contenu différent à différents types de visiteurs.
* **Audiences avec création de rapports :** Permet de déterminer comment différents types de visiteurs répondent au même contenu afin que vous puissiez analyser les résultats de vos tests.

   Dans [!DNL Target], vous pouvez configurer les audiences avec création de rapports seulement si vous utilisez [!DNL Target] comme source des rapports. Si vous utilisez [ Adobe Analytics comme source des rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), vous devez configurer les audiences avec création de rapports dans [!DNL Analytics].

## Utilisez la variable [!UICONTROL Audiences] list {#use-list}

Pour accéder à la liste des [!UICONTROL audiences], cliquez sur **[!UICONTROL Audiences]** dans la barre de menu supérieure :

![Liste Audiences](assets/audiences_list.png)

Le [!UICONTROL Audiences] contient les audiences que vous pouvez utiliser dans vos activités. Utilisez la variable [!UICONTROL Audiences] pour créer, modifier, dupliquer, copier ou combiner des audiences. La liste présente également la source dans laquelle l’audience a été créée:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >Le [!DNL Adobe Experience Platform] La source est disponible pour tous les [!DNL Target] clients utilisant la variable [SDK Web Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}. Audiences disponibles à partir de [!DNL Adobe Experience Platform] peut être utilisé tel quel ou [combiné avec les audiences existantes](/help/main/c-target/combining-multiple-audiences.md).
   >
   >Les utilisateurs doivent disposer des [!UICONTROL Approbateur] ou au-dessus de l’état [!DNL Target] pour configurer [!DNL Target] [!UICONTROL Destinations] cartes dans AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
   >
   >Pour plus d’informations, voir [Utilisation des audiences de Adobe Experience Platform](#aep).

Audiences prédéfinies, telles que &quot;[!UICONTROL Nouveaux visiteurs]&quot; et &quot;[!UICONTROL Visiteurs récurrents]&quot; ne peut pas être renommé.

Lorsque vous utilisez des audiences qui ont été créées à l’origine dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], [!DNL Target] vous alerte si vous référencez une audience dans [!DNL Target] activités qui ont été supprimées ultérieurement dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Si une audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], une icône d’avertissement dans les [!UICONTROL Audience] et le sélecteur d’audience s’affiche. Une info-bulle dans la variable [!DNL Target] L’interface utilisateur indique également que l’audience a été supprimée dans [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Si vous tentez de combiner plusieurs audiences, parmi lesquelles une audience supprimée, ou si vous venez d’enregistrer une activité faisant référence à une audience supprimée, un message d’avertissement apparaît.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. Lors de la création d’une audience, faites glisser les attributs à utiliser pour cibler votre activité dans la fenêtre du créateur d’audiences. Si l’attribut souhaité ne s’affiche pas, l’attribut n’a pas été déclenché par une mbox. D’autres paramètres mbox personnalisés sont disponibles dans la liste déroulante [!UICONTROL Paramètres personnalisés].

Utilisez la variable [!UICONTROL Filtres] pour filtrer les [!UICONTROL Audiences] liste par source : [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud], et [!DNL Adobe Experience Platform].

![Option Filtres dans la [!UICONTROL Audiences] list](assets/filters.png)

Utilisez la variable [!UICONTROL Recherche d’audiences] pour rechercher votre [!UICONTROL Audiences] liste. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste d’[!UICONTROL audiences] par nom d’audience ou par date de dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Affichage des définitions d’audience {#section_11B9C4A777E14D36BA1E925021945780}

Vous pouvez afficher les détails de la définition de l’audience sur une carte contextuelle à différents endroits dans la variable [!DNL Target] Interface utilisateur sans ouvrir l’audience. Cette fonctionnalité s’applique aux audiences créées dans [!DNL Target Standard/Premium] et audiences importées depuis [!DNL Target Classic] ou créé via l’API.

Par exemple, la carte de définition de l’audience suivante est accessible en cliquant sur le [!UICONTROL Afficher les détails] pour l’audience souhaitée :

![Activités > Définition d’audience](assets/audience_definition_list.png)

Pour accéder à la carte de définition de l’audience suivante, cliquez sur le bouton [!UICONTROL Afficher les détails] sur l’icône d’une activité. [!UICONTROL Présentation] page :

![Activités > Définition d’audience](assets/view-details-activity-overview.png)

La carte de définition de l’audience indique le type, la source et les attributs de l’audience. Cliquez sur **[!UICONTROL Afficher les détails complets]** pour afficher d’autres activités qui font référence à cette audience, le cas échéant. Si vous affichez une carte de définition d’audience à partir d’une activité [!UICONTROL Présentation] page, cliquez sur **[!UICONTROL Utilisation de l’audience]**.

Les informations d’utilisation de l’audience peuvent vous aider à éviter tout impact accidentel sur d’autres activités lors de la modification des audiences. Informations incluses [!UICONTROL Activités en direct], [!UICONTROL Activités inactives], [!UICONTROL Activités archivées], et [!UICONTROL Synchronisation des activités]. Cette fonctionnalité est disponible pour toutes les audiences (audiences de bibliothèque et [les audiences d’activité uniques](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si une audience est [combiné avec une autre audience](/help/main/c-target/combining-multiple-audiences.md) et l’audience combinée est utilisée pour créer une activité. les informations d’utilisation des deux audiences répertorient cette activité nouvellement créée.

![](assets/audience_definition_list_usage.png)

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

## Utilisation d’audiences provenant de [!DNL Adobe Experience Platform] {#aep}

Les audiences créées dans [!DNL Adobe Experience Platform] fournissent des données client plus riches, qui conduisent de facto à une personnalisation ayant plus dʼimpact. Le [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank} (RTCDP), basé sur [!DNL Adobe Experience Platform], aide les entreprises à rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise. Ce processus vous permet de créer des profils client qui peuvent être utilisés pour offrir des expériences client personnalisées sur tous les canaux et appareils en temps réel.

En connectant [!DNL Target] à [!DNL Real-time Customer Data Platform], les clients peuvent enrichir leur personnalisation web en déverrouillant de nouveaux segments, auparavant inaccessibles pour [!DNL Target], afin d’activer la personnalisation en temps réel, à la milliseconde, sur la première page de visite d’un client sur le web. Utiliser les audiences créées dans [!DNL Adobe Experience Platform] vous permet d’étendre les points de données disponibles pour une personnalisation plus riche.

Cette intégration permet de déverrouiller les cas d’utilisation clés avec la plateforme RTCDP :

* Personnalisation Même page / Accès suivant
* Personnalisation des nouveaux utilisateurs / utilisateurs inconnus

Les principales fonctionnalités sont les suivantes :

* Intégration de Target direct avec RTCDP/[!DNL Adobe Experience Platform] sur l’Edge (suppression de la dépendance sur [!DNL Audience Core services] - AAM)
* [!UICONTROL Target Edge Destinations Card] avec application de la gouvernance
* Segmentation Edge et profil Edge avec profil unifié

Pour plus d’informations, voir les rubriques suivantes :

* [Notes de mise à jour des destinations](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} dans la variable *Notes de mise à jour de Adobe Experience Platform*
* [Configuration des destinations de personnalisation pour la personnalisation de la même page et de la page suivante](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} dans la variable *Présentation des destinations* guide.
* [Connexion à la personnalisation personnalisée](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} dans la variable *Présentation des destinations* guide
* [Connexion Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} dans la variable *Présentation des destinations* guide
* [Configuration des destinations de personnalisation pour les cas pratiques de personnalisation de la même page et de la page suivante](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} dans la variable *Présentation des destinations* guide

### Informations supplémentaires

Tenez compte des informations suivantes lors de l’utilisation d’audiences provenant de [!DNL Adobe Experience Platform]:

#### Cas d’utilisation de la personnalisation

Le tableau suivant indique quel type de cas d’utilisation de personnalisation (session suivante ou même page) est disponible lors de l’utilisation de la variable [!DNL Adobe Experience Platform Web SDK] plutôt que d’utiliser at.js :

| Mise en œuvre | Solutions/Cas d’utilisation activé |
| --- | --- |
| at.js | **Solutions**:<ul><li>[!DNL Adobe Audience Manager] (AAM) et [!DNL Target]</li><li>[!DNL RTCDP] (Premium ou Ultimate) et [!DNL Target]</li><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul>**Cas d’utilisation**:<ul><li>Personnalisation de la prochaine session</li></ul> |
| [!DNL Platform Web SDK] ou [!DNL AEP Server-Side API] | **Solutions**:<ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul>**Cas pratique**:<ul><li>Personnalisation de la prochaine session</li><li>Personnalisation de la même page via Edge</li><li>Gouvernance appliquée lors du partage de segments</li></ul>**Solutions**:<ul><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul>**Cas pratique**:<ul><li>Personnalisation de la prochaine session</li><ul><li>[!DNL AAM] segments</li><li>Segments tiers via [!DNL AAM]</li></ul><li>Personnalisation de la même page via Edge</li><ul><li>[!DNL RTCDP] segments</li><li>Gouvernance appliquée lors du partage de segments</li></ul> |
| Mix of [!UICONTROL at.js] et [!DNL Platform Web SDK] | **Solutions**:<ul><li>[!DNL RTCDP] (tout SKU) et [!DNL Target]</li></ul>**Cas pratique**:<ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li></ul><li>Personnalisation de la même page</li><ul><li>Pour toutes les pages avec [!DNL Platform Web SDK]</li></ul></ul>**Solutions**:<ul><li>[!DNL RTCDP] (toute SKU), [!DNL AAM], et [!DNL Target]</li></ul>**Cas pratique**:<ul><li>Personnalisation de la prochaine session</li><ul><li>Pour toutes les pages avec [!UICONTROL at.js]</li><li>[!DNL AAM] segments</li><li>Segments tiers via [!DNL AAM]</li></ul> |

#### Temps d’évaluation des segments

Le tableau suivant indique le temps d’évaluation des segments pour les événements provenant de différents scénarios d’implémentation :

| Scénario | Segment Edge (évaluation en millisecondes) | Segment de diffusion en continu (évaluation par minute) | Évaluation de segments par lots |
| --- | --- | --- | --- |
| Événements/données provenant de [!DNL Adobe Experience Platform] SDK | Oui | Oui | S.O. |
| Événements de [!UICONTROL at.js] | Non | Oui | S.O. |
| Événements de [!DNL Target Mobile] SDK | Non | Oui | S.O. |
| Événements de chargement par lots | Non | Non | Oui |
| Événements des données hors ligne (flux) | Non | Oui | Oui |

### Vidéo : Personnalisation des accès suivants avec la plateforme de données clients en temps réel et [!DNL Adobe Target]{#RTCDP}

Découvrez comment personnaliser lors de l’accès suivant avec [!DNL Real-time Customer Data Platform] et [!DNL Adobe Target]. Le [!DNL Adobe Target] destination dans [!DNL Real-time CDP] vous permet d’utiliser des [!DNL Experience Platform] segments dans [!DNL Adobe Target] pour une même page et une personnalisation de la page suivante avec prise en charge de la gouvernance et de la confidentialité.

Pour plus d’informations, voir [Personnalisation à l’accès suivant avec la plateforme de données clients en temps réel et Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} dans la variable *Tutorials de plateforme* guide.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog et vidéo Adobe Target :

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] et [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## Vidéo de formation : Utilisation des audiences ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comprend des informations sur l’utilisation des audiences.

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Utilisation d’audiences à des fins de création passive de rapports dans une activité
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)
