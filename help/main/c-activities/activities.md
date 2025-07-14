---
keywords: liste des activités;activités;activité;types d’activités;modifier l’activité;actions d’activité;attribut d’activité;filtre de liste d’activités;limitations d’activité;personnaliser;personnalisation
description: Personnalisez le contenu et testez les conceptions de page pour des audiences spécifiques avec des activités  [!DNL Adobe Target] .
title: Comment personnaliser du contenu et tester des conceptions de page avec  [!DNL Target] ?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 5012c2b849d6b415f08fcaa3be85508637e30481
workflow-type: tm+mt
source-wordcount: '2292'
ht-degree: 25%

---

# Présentation des activités

Personnalisez le contenu et testez les conceptions de page pour des audiences spécifiques avec des activités [!DNL Adobe Target].

Vous pouvez par exemple concevoir une activité qui teste deux pages de destination distinctes : l’une qui met en évidence les informations sur les chaussures d’été pour femmes, l’autre qui met en évidence des vêtements d’été plus généraux. L’activité détermine les conditions qui contrôlent l’affichage de chacune de ces pages de destination et les mesures qui déterminent quelle page a le plus de succès. L’activité est configurée pour démarrer et se terminer lorsque des conditions spécifiques sont remplies, par exemple entre des dates spécifiques. Vous pouvez également choisir de démarrer l’activité lorsqu’elle est approuvée et de la terminer lorsqu’elle est désactivée.

Planifiez soigneusement une activité lorsque vous la concevez. Déterminez le moment auquel l’activité doit débuter, ainsi que sa durée. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

## Liste des activités {#section_DE8E2DB30D534962A931EF8BB48240F5}

La liste [!UICONTROL Activities] est la vue par défaut lorsque vous ouvrez [!DNL Target]. Vous pouvez créer des activités à partir de cette page et gérer les activités existantes.

Vous pouvez également afficher la liste des [!UICONTROL Activities] en cliquant sur l’onglet [!UICONTROL Activities] dans la partie supérieure de l’interface utilisateur de [!DNL Target].

La liste [!UICONTROL Activities] fournit un aperçu de toutes les activités de votre implémentation [!DNL Target] et vous permet d’effectuer diverses actions.

Le tableau suivant vous aide à comprendre divers éléments de la liste [!UICONTROL Activities] dans l’interface utilisateur de [!DNL Target] :

| Élément | Description |
|--- |--- |
| Icône [!UICONTROL Show filters]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Show Filters]** située en haut de la liste pour filtrer les activités par [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Source], [!UICONTROL Activity Source] et [!UICONTROL Properties].<P>Les filtres que vous configurez sont persistants tout au long de la session en cours.<P>Pour plus d’informations, voir [Appliquer des filtres à la liste de [!UICONTROL Activities]](#filters) ci-dessous. |
| Champs de recherche | Trouvez rapidement une activité ou réduisez le nombre d’activités affichées dans la liste [!UICONTROL Activity]. Vous pouvez effectuer une recherche par [!UICONTROL Activity Name], [!UICONTROL URL] ou [!UICONTROL ID] à l’aide de la liste déroulante.<P>Les options de recherche que vous configurez sont persistantes dans la session en cours. |
| [!UICONTROL Create Activity] | Créez une activité.<P>Pour plus d’informations sur la création des différents types d’activités, voir : <ul><li>[Création d’une activité [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Création d’une activité [!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Création d’une activité [!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Création d’une activité [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Création d’une activité [!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Créer une activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Créer une [!UICONTROL Recommendations] activité](/help/main/c-recommendations/recommendations.md)</li></ul>Pour plus d’informations sur chaque type, consultez la section [Types d’activités](#types) ci-dessous. |
| [!UICONTROL Create mobile preview link]<P>![Menu Autres actions](/help/main/assets/icons/MoreVertical.svg) | Utilisez les [liens d’aperçu mobile](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview) pour effectuer un contrôle qualité de bout en bout facile pour les activités d’applications mobiles.<P>Cliquez sur l’icône **Plus d’options**, sélectionnez le lien **Créer un aperçu mobile**, puis choisissez les activités à tester sur mobile. |
| Personnaliser le tableau<P>![icône Personnaliser le tableau](/help/main/assets/icons/ColumnSetting.svg) | Modifiez les colonnes à afficher dans la liste [!UICONTROL Activity] en cliquant sur l’icône **[!UICONTROL Customize Table]** en haut à droite de la page, puis en sélectionnant ou en désélectionnant les colonnes de votre choix.<P>Les modifications sont appliquées à votre compte et restent actives même après votre déconnexion de [!DNL Target]. |
| Cases à cocher des opérations en bloc<P>![ Icône Opérations en bloc ](/help/main/assets/icons/Rectangle.svg) | Effectuer des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et du statut de l’activité), reportez-vous à la section [Exécuter des actions rapides](#quick-actions) ci-dessous. |
| [!UICONTROL Type] | Type d’activité. La colonne [!UICONTROL Type] permet d&#39;identifier rapidement chaque activité par type. <ul><li>**AB-M** : [!UICONTROL A/B Test] manuelle</li><li>**AB-AA** : [!UICONTROL Auto-Allocate]</li><li>**AB-AT** : [!UICONTROL Auto-Target]</li><li>**AP** : [!UICONTROL Automated Personalization]</li><li>**XT** : [!UICONTROL Experience Targeting]</li><li>**MVT** : [!UICONTROL Multivariate Test]</li><li>**REC** : [!UICONTROL Recommendations]</li></ul>Pour plus d’informations sur chaque type, consultez la section [Types d’activités](#types) ci-dessous. |
| [!UICONTROL Name] | Nom de l’activité. Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![icône d’informations rapides](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’activité pour afficher plus d’informations sur cette activité dans une carte pop-up, y compris les [!UICONTROL Activity ID], [!UICONTROL Activity Objective], [!UICONTROL Activity Location], [!UICONTROL Goal] et [!UICONTROL Status].<P>Cliquez sur l’icône **[!UICONTROL More actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’activité pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l’activité) : [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] et [!UICONTROL Archive].<P>Pour plus d’informations sur chaque action, consultez [Exécution d’actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Status] | L’état d’une activité peut être l’un des suivants :<ul><li>**[!UICONTROL Live]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Scheduled]** : l’activité est prête à être activée à la date et à l’heure de début spécifiées.</li><li>**[!UICONTROL Inactive]** : l&#39;activité a été mise en pause ou désactivée.</li><li>**[!UICONTROL Ended]** : la date et l&#39;heure de fin spécifiées de l&#39;activité ont été atteintes et l&#39;activité n&#39;est plus diffusée.</li><li>**[!UICONTROL Archived]** : l&#39;activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>**Remarque** : lorsque vous effectuez certaines actions, telles que l’activation d’une activité en dehors de l’interface utilisateur de [!DNL Target] à l’aide de méthodes d’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager vers l’interface utilisateur de [!DNL Target]. |
| [!UICONTROL Last Updated] | Date et heure de la dernière mise à jour de l’activité, et par qui.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre croissant ou décroissant de date. |
| [!UICONTROL Priority] | Priorité de l’activité.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Selon vos [paramètres](/help/main/administrating-target/reporting.md), l’interface utilisateur [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou activer les priorités affinées de 0 à 999.<P>Pour plus d’informations sur les paramètres de priorité, voir [Priorité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) sous *Paramètres d’activité* dans *Objectifs et paramètres*. |
| [!UICONTROL Property] | Affiche [la propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de l’activité.<P>Les autorisations des utilisateurs d&#39;entreprise sont une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Estimated Lift in Revenue] | Indique l’effet élévateur estimé dans les recettes si 100 % de l’audience consulte l’expérience gagnante.<P>Cette valeur est calculée à l’aide de la formule suivante :<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Ce chiffre est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la virgule (par exemple, 1,6M, 60K, 900, 8,5K, 205K).<P>Cette colonne indique « --- » pour les activités dont les données ne sont pas suffisantes pour déterminer un contenu performant ou qui ne disposent pas d’une estimation de coût.<P>Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations. |
| [!UICONTROL Source] | Indique l’emplacement de création de l’activité : [!DNL Adobe Target], [API Adobe Target](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr) ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Author] | Nom de la personne qui a créé l’activité. |
| [!UICONTROL Decisioning Method] | La méthode de prise de décision utilisée dans chaque activité : [côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) ou [côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## Types d’activités {#types}

[!DNL Target] inclut plusieurs types d’activités. Le tableau suivant présente un aperçu de chaque type d’activité avec des liens pour vous aider à en savoir plus. Pour vous aider à choisir le type d’activité le mieux adapté à vos besoins, utilisez le [Guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Les tests A/B comparent plusieurs versions du contenu de votre site web afin de déterminer celle qui améliore le mieux vos conversions au cours d’une période de test prédéfinie. |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], un type de test A/B, identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement davantage de trafic au gagnant pour augmenter les conversions pendant que le test continue à s’exécuter et à apprendre. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | Le ciblage automatique, un type de test A/B, utilise le machine learning avancé pour identifier plusieurs expériences hautement performantes définies par des spécialistes marketing. Il fournit l’expérience la plus personnalisée à chaque visiteur selon le profil individuel du client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compare les combinaisons d’offres dans les éléments d’une page afin de déterminer la combinaison la plus performante pour une audience spécifique. Il identifie l’élément qui impacte le plus la réussite de l’activité. |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT) diffuse du contenu à une audience spécifique en fonction d’un ensemble de règles et de critères définis par les responsables marketing. |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) combine des offres ou des messages et utilise le machine learning avancé pour faire correspondre différentes variations à chaque visiteur en fonction de son profil client individuel, afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Une recommandation détermine la manière dont un produit est suggéré à un visiteur ou une visiteuse du site web, en fonction de ses activités sur le site.<P>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Vous pouvez également encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant des vidéos similaires à la vidéo qu’ils regardent, à l’aide de l’algorithme « Les personnes qui ont vu ceci a vu cela ».<P>**REMARQUE** : vous pouvez également inclure des recommandations dans les activités [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Experience Targeting] (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium). |

## Application de filtres à la liste des Activités {#filters}

Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Show Filters]** ( ![icône Afficher les filtres](/help/main/assets/icons/Filter.svg) ) en haut de la liste.

Le menu permet de filtrer les activités selon les attributs suivants :

| Attribut | Détails |
| --- | --- |
| [!UICONTROL Type] | Filtrez par [ type d’activité ](#types). |
| [!UICONTROL Status] | Filtrez par statut d’activité.<ul><li>**[!UICONTROL Live]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Scheduled]** : l’activité est prête à être activée à la date et à l’heure de début spécifiées.</li><li>**[!UICONTROL Inactive]** : l&#39;activité a été mise en pause ou désactivée.</li><li>**[!UICONTROL Ended]** : la date et l&#39;heure de fin spécifiées de l&#39;activité ont été atteintes et l&#39;activité n&#39;est plus diffusée.</li><li>**[!UICONTROL Archived]** : l&#39;activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>Pour plus d’informations sur les statuts [!UICONTROL Save as Draft] et [!UICONTROL Syncing] obsolètes, reportez-vous à la remarque ci-dessous de ce tableau. |
| [!UICONTROL Reporting Source] | Filtrez par source de création de rapports.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) : affichage des activités qui utilisent [!UICONTROL Analytics for Target] (A4T) comme source de création de rapports.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md) : affichage des activités qui utilisent [!DNL Target] comme source de création de rapports.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) : affichage des activités qui utilisent [!DNL Adobe Customer Analytics] comme source de création de rapports.</li></ul> |
| [!UICONTROL Experience Composer] | Filtre selon lequel le compositeur d’expérience a été utilisé lors de la création de l’activité :<ul><li>[Visuel](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) : affiche les activités créées à l’aide du [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md) : affiche les activités créées à l’aide de l’[!UICONTROL Form-Based Experience Composer].</li></ul> |
| [!UICONTROL Metrics Type] | Filtre selon lequel la [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) a été choisie lors de la création de l’activité.<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | Filtrez selon la méthode de prise de décision utilisée dans chaque activité.<ul><li>[Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) : affichez les activités qui utilisent la prise de décision côté serveur.</li><li>[Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html) : affichez les activités qui utilisent la prise de décision côté client.</li></ul> |
| [!UICONTROL Activity Source] | Filtrez par source d’activité utilisée pour créer chaque activité.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=fr)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | Filtrez par la [propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans laquelle l’activité a été créée. |


>[!NOTE]
>
>**Mise à jour des états d’activité dans l’interface utilisateur mise à jour** : avec les dernières mises à jour de l’interface utilisateur, les états [!UICONTROL Save as Draft] et [!UICONTROL Syncing] ne sont plus disponibles. En effet, toutes les créations et modifications d’activités ont désormais lieu directement dans le système de diffusion [!DNL Target] principal, à l’aide de la couche GraphQL, ce qui simplifie et rend plus efficace le processus.
>
>Auparavant, les activités étaient d’abord enregistrées dans le système frontal [!DNL Target], puis synchronisées dans le système de diffusion [!DNL Target] principal, qui nécessitait ces états intermédiaires. Comme ce n&#39;est plus le cas, ces États ont été supprimés.
>
>[!DNL Adobe] comprend que certains clients ont indiqué être intéressés par la fonctionnalité [!UICONTROL Save as Draft]. Nous apprécions ces commentaires, mais cette fonctionnalité n’est actuellement pas prise en charge.

## Exécution d’actions rapides {#quick-actions}

Cliquez sur l’icône **[!UICONTROL More actions]** ( ![menu Autres actions](/help/main/assets/icons/MoreVertical.svg) ) en regard de chaque nom d’activité pour ouvrir un menu qui vous permet d’effectuer des actions rapides sur une activité.

Les actions suivantes sont disponibles (en fonction de vos autorisations et du statut de l’activité) :

| Action | Description |
| --- | --- |
| [!UICONTROL Edit] | Permet de modifier une activité. Il est possible de modifier n’importe quelle activité.<P>Pour plus d’informations sur les différentes manières de modifier les activités, voir [Modifier une activité ou enregistrer en tant que brouillon](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Permet d’arrêter une activité activée ou programmée. Une activité désactivée peut être réactivée ou archivée.<P>Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur fera encore partie de cette activité après la réactivation s’il s’y trouvait avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Activate] | Démarrez une activité inactive ou une activité prête à être activée. |
| [!UICONTROL Archive] | Envoie l’activité vers l’archive. Par défaut, les activités archivées n’apparaissent plus dans la liste [!UICONTROL Activities]. Modifiez le filtre de la liste de [!UICONTROL Activities] afin d’inclure les activités archivées pour les afficher. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.<P>Si vous désactivez ou archivez une activité, puis la réactivez ultérieurement, un visiteur continuera à faire partie de cette activité après la réactivation s’il se trouvait dans cette activité avant que celle-ci ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Copy] | Permet de copier une activité. Il est possible de copier n’importe quelle activité. La copie d’une activité permet d’en créer une autre dotée du même nom auquel est ajouté le mot « Copie ». Par exemple, la copie d’un test appelé « Offres de navigateur » porte le nom « Copie Offres de navigateur ».<P>Les offres visuelles sont copiées avec l’activité. Vous pouvez modifier les offres en toute sécurité dans la copie sans que cela ait d’incidence sur l’activité d’origine. La seule exception concerne les offres et les images sauvegardées dans le dossier Contenu/Ressources. |
| [!UICONTROL Delete] | Permet de supprimer un brouillon d’activité ou une activité.<P>**REMARQUE :** les activités supprimées le sont définitivement. Utilisez l’action [!UICONTROL Archive], sauf si vous êtes sûr de ne plus jamais avoir besoin de cette activité. Vous pouvez ensuite réactiver l’activité si nécessaire. |

## Considérations

Notez les détails suivants concernant la liste [!UICONTROL Activity] :

* Les activités [!UICONTROL Archived] et [!UICONTROL Ended] n’apparaissent pas dans la liste [!UICONTROL Activities]. Pour afficher ces activités, filtrez-les à l’aide de l’icône [Filtres](#filters) ( ![Afficher l’icône Filtres](/help/main/assets/icons/Filter.svg) ) en haut de la liste.
* Lorsqu’une activité créée à l’origine dans [!DNL Target Classic] est désactivée ou supprimée, elle est supprimée de [!DNL Target Standard/Premium]. Les activités supprimées créées à l’origine dans [!DNL Target Classic] ne sont pas envoyées au dossier [!UICONTROL Archive] dans [!DNL Target Standard/Premium]. La fonctionnalité du dossier Archives s’applique uniquement aux activités créées dans [!DNL Target Standard/Premium].
* Tous les types d’activité autres que [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] vous donnent le choix d’utiliser [!DNL Target] ou [!DNL Adobe Analytics] comme source de données. [!UICONTROL Automated Personalization], [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] *toujours* utilisez des données [!DNL Target].
* Les activités sont disponibles pour différents canaux :

   * sites web et mobiles ;
   * écrans et appareils connectés à Internet, y compris kiosques et guichets automatiques ;
   * messagerie électronique et autres canaux d’acquisition ou sites partenaires ;
   * applications mobiles ;
   * partout où vous pouvez diffuser du contenu balisé.

## Limites  {#section_049D4684403A4E07B998067EB8E9BE56}

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

Pour connaître les limites supplémentaires du [!UICONTROL Visual Experience Composer] (VEC), voir [Limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributs importés dans [!DNL Target] pour les activités mises à jour en dehors de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si des activités créées dans [!DNL Target] sont mises à jour depuis l’extérieur de [!DNL Target] (par exemple, via l’API), les attributs d’activité suivants sont réimportés dans [!DNL Target] : `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` et `marketingCloudMetadata(remoteModifiedBy)`.

Cette tâche d’importation s’exécute à l’ouverture de la liste de [!UICONTROL Activities], avec un délai maximal de dix minutes.

