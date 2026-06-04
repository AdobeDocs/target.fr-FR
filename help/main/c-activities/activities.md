---
keywords: liste des activités;activités;activité;types d’activités;modifier l’activité;actions d’activité;attribut d’activité;filtre de liste d’activités;limitations d’activité;personnaliser;personnalisation
description: Personnalisez le contenu et testez les conceptions de page pour des audiences spécifiques avec des activités  [!DNL Adobe Target] .
title: Comment personnaliser du contenu et tester des conceptions de page avec  [!DNL Target] ?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
TQID: https://experienceleague.adobe.com/q3-Z8r2eEWTISBkZBBJTJ8XarLi-lTa2qsqj961hhEQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2633
ht-degree: 25%

---

# Présentation des activités

Personnalisez le contenu et testez les conceptions de page pour des audiences spécifiques avec des activités [!DNL Adobe Target].

Vous pouvez par exemple concevoir une activité qui teste deux pages de destination distinctes : l’une qui met en évidence les informations sur les chaussures d’été pour femmes, l’autre qui met en évidence des vêtements d’été plus généraux. L’activité détermine les conditions qui contrôlent l’affichage de chacune de ces pages de destination et les mesures qui déterminent quelle page a le plus de succès. L’activité est configurée pour démarrer et se terminer lorsque des conditions spécifiques sont remplies, par exemple entre des dates spécifiques. Vous pouvez également choisir de démarrer l’activité lorsqu’elle est approuvée et de la terminer lorsqu’elle est désactivée.

Planifiez soigneusement une activité lorsque vous la concevez. Déterminez le moment auquel l’activité doit débuter, ainsi que sa durée. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

## Liste des activités {#section_DE8E2DB30D534962A931EF8BB48240F5}

La liste [!UICONTROL Activités] est la vue par défaut lorsque vous ouvrez [!DNL Target]. Vous pouvez créer des activités à partir de cette page et gérer les activités existantes.

Vous pouvez également afficher la liste [!UICONTROL Activités] en cliquant sur l’onglet [!UICONTROL Activités] dans la partie supérieure de l’interface utilisateur de [!DNL Target].

La liste [!UICONTROL Activités] donne un aperçu de toutes les activités de votre implémentation [!DNL Target] et vous permet d’effectuer différentes actions.

Le tableau suivant vous aide à comprendre divers éléments de la liste [!UICONTROL Activités] dans l’interface utilisateur de [!DNL Target] :

| Élément | Description |
|--- |--- |
| Icône [!UICONTROL Afficher les filtres]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Afficher les filtres]** en haut de la liste pour filtrer les activités par [!UICONTROL Type], [!UICONTROL Statut], [!UICONTROL Source de création de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesures], [!UICONTROL Decisioning Source], [!UICONTROL Activity Source] et [!UICONTROL Properties].<P>Les filtres que vous configurez sont persistants tout au long de la session en cours.<P>Pour plus d’informations, voir [Appliquer des filtres à la liste [!UICONTROL Activités] ci-dessous](#filters). |
| Champs de recherche | Trouvez rapidement une activité ou réduisez le nombre d’activités affichées dans la liste [!UICONTROL Activité]. Vous pouvez effectuer une recherche par [!UICONTROL Nom de l’activité], [!UICONTROL URL] ou [!UICONTROL ID] à l’aide de la liste déroulante.<P>Les options de recherche que vous configurez sont persistantes dans la session en cours. |
| [!UICONTROL Créer une activité] | Créez une activité.<P>Pour plus d’informations sur la création des différents types d’activités, voir : <ul><li>[Créer une activité [!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Créer une activité [!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Création d’une activité de [!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Créer une activité [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Créer une activité [!UICONTROL Ciblage d’expérience]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Créer une activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Créer une activité [!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)</li></ul>Pour plus d’informations sur chaque type, consultez la section [Types d’activités](#types) ci-dessous. |
| [!UICONTROL Créer un lien d’aperçu mobile]<P>![Menu Autres actions](/help/main/assets/icons/MoreVertical.svg) | Utilisez les [liens d’aperçu mobile](https://experienceleague.adobe.com/fr/docs/target-dev/developer/mobile-apps/target-mobile-preview) pour effectuer un contrôle qualité de bout en bout facile pour les activités d’applications mobiles.<P>Cliquez sur l’icône **Plus d’options**, sélectionnez le lien **Créer un aperçu mobile**, puis choisissez les activités à tester sur mobile. |
| Personnaliser le tableau<P>![icône Personnaliser le tableau](/help/main/assets/icons/ColumnSetting.svg) | Modifiez les colonnes à afficher dans la liste [!UICONTROL Activité] en cliquant sur l’icône **[!UICONTROL Personnaliser le tableau]** en haut à droite de la page, puis en sélectionnant ou en désélectionnant les colonnes de votre choix.<P>Les modifications sont appliquées à votre compte et restent actives même après votre déconnexion de [!DNL Target]. |
| Cases à cocher des opérations en bloc<P>![&#x200B; Icône Opérations en bloc &#x200B;](/help/main/assets/icons/Rectangle.svg) | Effectuer des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et du statut de l’activité), reportez-vous à la section [Exécuter des actions rapides](#quick-actions) ci-dessous. |
| [!UICONTROL Type] | Type d’activité. La colonne [!UICONTROL Type] permet d&#39;identifier rapidement chaque activité par type. <ul><li>**AB-M** : essai manuel [!UICONTROL A/B]</li><li>**AB-AA** : [!UICONTROL &#x200B; Affectation automatique]</li><li>**AB-AT** : [!UICONTROL ciblage automatique]</li><li>**AP** : [!UICONTROL Automated Personalization]</li><li>**XT** : [!UICONTROL ciblage d’expérience]</li><li>**MVT** : [!UICONTROL test multivarié]</li><li>**REC** : [!UICONTROL Recommendations]</li></ul>Pour plus d’informations sur chaque type, consultez la section [Types d’activités](#types) ci-dessous. |
| [!UICONTROL Nom] | Nom de l’activité. Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’activité pour afficher plus d’informations sur cette activité dans une carte pop-up, y compris les [!UICONTROL ID d’activité], [!UICONTROL Objectif d’activité], [!UICONTROL Emplacement de l’activité], [!UICONTROL Goal] et [!UICONTROL Status].<P>Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’activité pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité. Les actions disponibles sont les suivantes (selon vos autorisations et le statut de l’activité) : [!UICONTROL Modifier], [!UICONTROL Activer], [!UICONTROL Désactiver], [!UICONTROL Copier], [!UICONTROL Supprimer] et [!UICONTROL Archiver].<P>Pour plus d’informations sur chaque action, consultez [Exécution d’actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL État] | L’état d’une activité peut être l’un des suivants :<ul><li>**[!UICONTROL En direct]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Planifié]** : l’activité est prête à être activée à la date et à l’heure de début spécifiées.</li><li>**[!UICONTROL Inactive]** : l’activité a été mise en pause ou désactivée.</li><li>**[!UICONTROL Terminé]** : la date et l’heure de fin spécifiées de l’activité ont été atteintes et l’activité n’est plus diffusée.</li><li>**[!UICONTROL Archivée]** : l&#39;activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>**Remarque** : lorsque vous effectuez certaines actions, telles que l’activation d’une activité en dehors de l’interface utilisateur de [!DNL Target] à l’aide de méthodes d’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager vers l’interface utilisateur de [!DNL Target]. |
| [!UICONTROL Dernière mise à jour &#x200B;] | Date et heure de la dernière mise à jour de l’activité, et par qui.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre croissant ou décroissant de date. |
| [!UICONTROL Priorité] | Priorité de l’activité.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Selon vos [paramètres](/help/main/administrating-target/reporting.md), l’interface utilisateur [!DNL Target] et les options de [!UICONTROL Priorité] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Faible], [!UICONTROL Medium] ou [!UICONTROL Élevé], ou activer des priorités affinées de 0 à 999.<P>Pour plus d’informations sur les paramètres de priorité, voir [Priorité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) sous *Paramètres d’activité* dans *Objectifs et paramètres*. |
| [!UICONTROL Propriété] | Affiche [la propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de l’activité.<P>Les autorisations des utilisateurs d&#39;entreprise sont une fonctionnalité de [&#128279;](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Effet élévateur estimé dans les revenus] | Indique l’effet élévateur estimé dans les recettes si 100 % de l’audience consulte l’expérience gagnante.<P>Cette valeur est calculée à l’aide de la formule suivante :<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Ce chiffre est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la virgule (par exemple, 1,6M, 60K, 900, 8,5K, 205K).<P>Cette colonne indique « --- » pour les activités dont les données ne sont pas suffisantes pour déterminer un contenu performant ou qui ne disposent pas d’une estimation de coût.<P>Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations. |
|  | Indique l’emplacement de création de l’activité : [!DNL Adobe Target], [API Adobe Target](https://experienceleague.adobe.com/fr/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr) ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Auteur] | Nom de la personne qui a créé l’activité. |
| [!UICONTROL &#x200B; Méthode de prise de décision &#x200B;] | La méthode de prise de décision utilisée dans chaque activité : [côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) ou [côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## Types d’activités {#types}

[!DNL Target] inclut plusieurs types d’activités. Le tableau suivant présente un aperçu de chaque type d’activité avec des liens pour vous aider à en savoir plus. Pour vous aider à choisir le type d’activité le mieux adapté à vos besoins, utilisez le [Guide des activités &#x200B;](/help/main/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [[!UICONTROL Test A/B]](/help/main/c-activities/t-test-ab/test-ab.md) | Les tests A/B comparent plusieurs versions du contenu de votre site web afin de déterminer celle qui améliore le mieux vos conversions au cours d’une période de test prédéfinie. |
| [[!UICONTROL Affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Affectation automatique], un type de test A/B, identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant pour augmenter les conversions pendant que le test continue à s’exécuter et à apprendre. |
| [[!UICONTROL ciblage automatique]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | Le ciblage automatique, un type de test A/B, utilise le machine learning avancé pour identifier plusieurs expériences hautement performantes définies par des spécialistes marketing. Il fournit l’expérience la plus personnalisée à chaque visiteur selon le profil individuel du client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Test multivarié]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) |  (MVT) compare les combinaisons d’offres dans les éléments d’une page afin de déterminer la combinaison la plus performante pour une audience spécifique et identifie l’élément qui impacte le plus le succès de l’activité. |
| [[!UICONTROL Ciblage d’expérience]](/help/main/c-activities/t-experience-target/experience-target.md) | Le [!UICONTROL ciblage d’expérience] (XT) diffuse du contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables marketing. |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) |  (AP) associe des offres ou des messages et utilise le machine learning avancé pour faire correspondre différentes variations à chaque visiteur en fonction de son profil client individuel, afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Recommandations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Une recommandation détermine la manière dont un produit est suggéré à un visiteur ou une visiteuse du site web, en fonction de ses activités sur le site.<P>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Vous pouvez également encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant des vidéos similaires à la vidéo qu’ils regardent, à l’aide de l’algorithme « Les personnes qui ont vu ceci a vu cela ».<P>**REMARQUE** : vous pouvez également inclure des recommandations dans les activités [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique] et [!UICONTROL Ciblage d’expérience] (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium). |

## Application de filtres à la liste des Activités {#filters}

Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Afficher les filtres]** ( ![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) ) en haut de la liste.

Le menu permet de filtrer les activités selon les attributs suivants :

| Attribut | Détails |
| --- | --- |
| [!UICONTROL Type] | Filtrez par [&#x200B; type d’activité &#x200B;](#types). |
| [!UICONTROL État] | Filtrez par statut d’activité.<ul><li>**[!UICONTROL En direct]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Planifié]** : l’activité est prête à être activée à la date et à l’heure de début spécifiées.</li><li>**[!UICONTROL Inactive]** : l’activité a été mise en pause ou désactivée.</li><li>**[!UICONTROL Terminé]** : la date et l’heure de fin spécifiées de l’activité ont été atteintes et l’activité n’est plus diffusée.</li><li>**[!UICONTROL Archivée]** : l&#39;activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>Consultez la remarque ci-dessous de ce tableau pour plus d’informations sur les statuts obsolètes [!UICONTROL Enregistrer en tant que brouillon] et [!UICONTROL Synchronisation]. |
| [!UICONTROL Reporting Source] | Filtrez par source de création de rapports.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) : affichage des activités qui utilisent [!UICONTROL Analytics for Target] (A4T) comme source de création de rapports.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md) : affichage des activités qui utilisent [!DNL Target] comme source de création de rapports.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) : affichage des activités qui utilisent [!DNL Adobe Customer Analytics] comme source de création de rapports.</li></ul> |
| [!UICONTROL compositeur d’expérience] | Filtre selon lequel le compositeur d’expérience a été utilisé lors de la création de l’activité :<ul><li>[Visuel](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) : affiche les activités créées à l’aide du [!UICONTROL Compositeur d’expérience visuelle] (VEC).</li><li>[Basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md) : affichez les activités créées à l’aide du [!UICONTROL Compositeur d’expérience d’après les formulaires].</li></ul> |
| [!UICONTROL Type de mesures] | Filtre selon lequel la [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) a été choisie lors de la création de l’activité.<ul><li>[!UICONTROL &#x200B; Conversion &#x200B;]</li><li>[!UICONTROL Recettes]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Utiliser une mesure Analytics]</lI></ul> |
| [!UICONTROL &#x200B; Méthode de prise de décision &#x200B;] | Filtrez selon la méthode de prise de décision utilisée dans chaque activité.<ul><li>[Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) : affichez les activités qui utilisent la prise de décision côté serveur.</li><li>[Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html) : affichez les activités qui utilisent la prise de décision côté client.</li></ul> |
| Source d’activité | Filtrez par source d’activité utilisée pour créer chaque activité.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=fr)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Propriété] | Filtrez par la [propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans laquelle l’activité a été créée. |


>[!NOTE]
>
>**Mise à jour des états d’activité dans l’interface utilisateur mise à jour** : avec les dernières mises à jour de l’interface utilisateur, les états [!UICONTROL Enregistrer en tant que brouillon] et [!UICONTROL Synchronisation] ne sont plus disponibles. En effet, toutes les créations et modifications d’activités ont désormais lieu directement dans le système de diffusion [!DNL Target] principal, à l’aide de la couche GraphQL, ce qui simplifie et rend plus efficace le processus.
>
>Auparavant, les activités étaient d’abord enregistrées dans le système frontal [!DNL Target], puis synchronisées dans le système de diffusion [!DNL Target] principal, qui nécessitait ces états intermédiaires. Comme ce n&#39;est plus le cas, ces États ont été supprimés.
>
>[!DNL Adobe] comprend que certains clients ont indiqué être intéressés par la fonctionnalité [!UICONTROL Enregistrer en tant que brouillon]. Nous apprécions ces commentaires, mais cette fonctionnalité n’est actuellement pas prise en charge.

## Exécution d’actions rapides {#quick-actions}

Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![menu Plus d’actions](/help/main/assets/icons/MoreVertical.svg) ) en regard de chaque nom d’activité pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité.

Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l’activité) :

| Action | Description |
| --- | --- |
| [!UICONTROL Modifier] | Permet de modifier une activité. Il est possible de modifier n’importe quelle activité.<P>Pour plus d’informations sur les différentes manières de modifier les activités, voir [Modifier une activité ou enregistrer en tant que brouillon](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Désactiver] | Permet d’arrêter une activité activée ou programmée. Une activité désactivée peut être réactivée ou archivée.<P>Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur fera encore partie de cette activité après la réactivation s’il s’y trouvait avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Activer] | Démarrez une activité inactive ou une activité prête à être activée. |
| [!UICONTROL Archiver] | Envoie l’activité vers l’archive. Par défaut, les activités archivées n’apparaissent plus dans la liste [!UICONTROL Activités]. Modifiez le filtre de la liste [!UICONTROL Activités] afin d’inclure les activités archivées pour les afficher. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.<P>Si vous désactivez ou archivez une activité, puis la réactivez ultérieurement, un visiteur continuera à faire partie de cette activité après la réactivation s’il se trouvait dans cette activité avant que celle-ci ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Copier] | Permet de copier une activité. Il est possible de copier n’importe quelle activité. La copie d’une activité permet d’en créer une autre dotée du même nom auquel est ajouté le mot « Copie ». Par exemple, la copie d’un test appelé « Offres de navigateur » porte le nom « Copie Offres de navigateur ».<P>Les offres visuelles sont copiées avec l’activité. Vous pouvez modifier les offres en toute sécurité dans la copie sans que cela ait d’incidence sur l’activité d’origine. La seule exception concerne les offres et les images sauvegardées dans le dossier Contenu/Ressources. |
| [!UICONTROL Supprimer] | Permet de supprimer un brouillon d’activité ou une activité.<P>**REMARQUE :** les activités supprimées le sont définitivement. Utilisez l’action [!UICONTROL Archiver] à moins que vous ne soyez certain de ne plus jamais avoir besoin de cette activité. Vous pouvez ensuite réactiver l’activité si nécessaire. |

## Considérations

Notez les détails suivants sur la liste [!UICONTROL Activité] :

* Les activités [!UICONTROL archivées] et [!UICONTROL terminées] n’apparaissent pas dans la liste [!UICONTROL Activités]. Pour afficher ces activités, filtrez-les à l’aide de l’icône [Filtres](#filters) ( ![Afficher l’icône Filtres](/help/main/assets/icons/Filter.svg) ) en haut de la liste.
* Lorsqu’une activité créée à l’origine dans [!DNL Target Classic] est désactivée ou supprimée, elle est supprimée de [!DNL Target Standard/Premium]. Les activités supprimées créées à l’origine dans [!DNL Target Classic] ne sont pas envoyées au dossier [!UICONTROL Archive] dans [!DNL Target Standard/Premium]. La fonctionnalité du dossier Archives s’applique uniquement aux activités créées dans [!DNL Target Standard/Premium].
* Tous les types d’activité autres que  (AP), [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] vous donnent le choix d’utiliser [!DNL Target] ou [!DNL Adobe Analytics] comme source de données. , [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] *toujours* utilisent les données [!DNL Target].
* Les activités sont disponibles pour différents canaux :

   * sites web et mobiles ;
   * écrans et appareils connectés à Internet, y compris kiosques et guichets automatiques ;
   * messagerie électronique et autres canaux d’acquisition ou sites partenaires ;
   * applications mobiles ;
   * partout où vous pouvez diffuser du contenu balisé.

## Limites {#section_049D4684403A4E07B998067EB8E9BE56}

Chaque activité [!DNL Target] présente les limitations de contenu suivantes :

| Élément | Limite |
|--- |--- |
| Sélecteurs uniques | 300 si un sélecteur est répété dans une autre expérience, il est comptabilisé une fois. Cependant, s’il est répété dans la même expérience, il est compté à nouveau. |
| Offres dans chaque expérience | 350 |
| Sélecteurs de suivi des clics dans les mesures | 50 |
| Mbox dans les mesures | 50 |
| Audiences et emplacements | Les combinaisons de 50 audiences et emplacements (mbox) ne doivent pas dépasser 50. |

L’activité ne peut pas être enregistrée si vous dépassez l’une de ces limites.

L’augmentation du nombre de ces éléments dans votre activité augmente également la durée nécessaire à la synchronisation de l’activité entre les [!DNL Target].

Pour connaître les limites supplémentaires du [!UICONTROL compositeur d’expérience visuelle] (VEC), voir [limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributs importés dans [!DNL Target] pour les activités mises à jour en dehors de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si des activités créées dans [!DNL Target] sont mises à jour depuis l’extérieur de [!DNL Target] (par exemple, via l’API), les attributs d’activité suivants sont réimportés dans [!DNL Target] : `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` et `marketingCloudMetadata(remoteModifiedBy)`.

Cette tâche d’importation s’exécute à l’ouverture de la liste [!UICONTROL Activités], avec un délai maximal de dix minutes.

