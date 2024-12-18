---
keywords: liste des activités;activités;activité;types d’activité;modifier l’activité;actions d’activité;attribut d’activité;filtre de liste des activités;limites des activités;personnalisation;personnalisation
description: Personnalisez le contenu et testez des conceptions de page pour des audiences spécifiques avec des activités  [!DNL Adobe Target] .
title: Comment personnaliser le contenu et tester les conceptions de page avec [!DNL Target] ?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 1e23c1170475869e2798e23551d63575031502b4
workflow-type: tm+mt
source-wordcount: '2313'
ht-degree: 26%

---

# Présentation des activités

Personnalisez le contenu et testez des conceptions de page pour des audiences spécifiques avec des activités [!DNL Adobe Target].

Vous pouvez par exemple concevoir une activité qui teste deux pages de destination distinctes : l’une qui met en évidence les informations sur les chaussures d’été pour femmes, l’autre qui met en évidence des vêtements d’été plus généraux. L’activité détermine les conditions qui contrôlent le moment où s’affiche chacune de ces pages d’entrée, ainsi que les mesures qui déterminent la page la plus performante. L’activité est configurée pour commencer et se terminer lorsque des conditions spécifiques sont remplies, par exemple entre des dates spécifiques. Vous pouvez également choisir de démarrer lorsque l’activité est approuvée et de se terminer lorsqu’elle est désactivée.

Planifiez soigneusement une activité lorsque vous la concevez. Déterminez le moment auquel l’activité doit débuter, ainsi que sa durée. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

## Liste des activités {#section_DE8E2DB30D534962A931EF8BB48240F5}

La liste [!UICONTROL Activities] est la vue par défaut lorsque vous ouvrez [!DNL Target]. Vous pouvez créer des activités à partir de cette page et gérer les activités existantes.

Vous pouvez également afficher la liste [!UICONTROL Activities] en cliquant sur l’onglet [!UICONTROL Activities] en haut de l’interface utilisateur de [!DNL Target].

![Liste des activités](/help/main/c-activities/assets/activities-list-new.png)

La liste [!UICONTROL Activities] fournit un aperçu de toutes les activités de votre implémentation [!DNL Target] et vous permet d’effectuer diverses actions.

Le tableau suivant vous aide à comprendre les différents éléments de la liste [!UICONTROL Activities] dans l’interface utilisateur de [!DNL Target] :

| Élément | Description |
|--- |--- |
| Rail de navigation à gauche | Basculez entre vos activités enregistrées ou actives et les activités [préliminaires](/help/main/c-activities/edit-activity.md) ayant échoué ou ayant échoué. |
| Icône [!UICONTROL Show filters]<P>![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) | Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Show Filters]** située en haut de la liste pour filtrer les activités par [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Source], [!UICONTROL Activity Source] et [!UICONTROL Properties].<P>Pour plus d’informations, voir [Application de filtres à la [!UICONTROL Activities] liste](#filters) ci-dessous. |
| Champs de recherche | Recherchez rapidement une activité ou réduisez le nombre d’activités affichées dans la liste [!UICONTROL Activity]. Vous pouvez effectuer des recherches par [!UICONTROL Activity Name], [!UICONTROL URL] ou [!UICONTROL ID] à l’aide de la liste déroulante. |
| [!UICONTROL Create Activity] | Créez une activité.<P>Pour plus d’informations sur la création des différents types d’activité, voir : <ul><li>[Créer une activité [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Créer une activité [!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Créer une activité [!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Créer une activité [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Créer une activité [!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Créer une activité](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Créer une activité [!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)</li></ul>Pour plus d’informations sur chaque type, voir [Types d’activité](#types) ci-dessous. |
| [!UICONTROL Create mobile preview link]<P>![Menu Autres actions](/help/main/assets/icons/MoreVertical.svg) | Utilisez les [liens d’aperçu mobile](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview) pour effectuer un contrôle qualité de bout en bout simple pour les activités d’application mobile.<P>Cliquez sur l’icône **Plus d’options**, sélectionnez le **lien Créer un aperçu mobile**, puis choisissez les activités que vous souhaitez tester sur mobile. |
| Personnalisation du tableau<P>![Icône Personnaliser la table](/help/main/assets/icons/ColumnSetting.svg) | Modifiez les colonnes affichées dans la liste [!UICONTROL Activity] en cliquant sur l’icône **[!UICONTROL Customize Table]** dans le coin supérieur droit de la page, puis en sélectionnant ou en désélectionnant les colonnes de votre choix.<P>Les modifications sont appliquées à votre compte et restent actives même après la déconnexion de [!DNL Target]. |
| Cases à cocher des opérations en bloc<P>![Icône Opérations en bloc](/help/main/assets/icons/Rectangle.svg) | Effectuez des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et de l’état de l’activité), reportez-vous à la section [ Exécution d’actions rapides ](#quick-actions) ci-dessous. |
| [!UICONTROL Type] | Type d’activité. La colonne [!UICONTROL Type] vous permet d’identifier rapidement chaque activité par type. <ul><li>**AB-M** : manuel [!UICONTROL A/B Test]</li><li>**AB-AA** : [!UICONTROL Auto-Allocate]</li><li>**AB-AT** : [!UICONTROL Auto-Target]</li><li>**AP** : [!UICONTROL Automated Personalization]</li><li>**XT** : [!UICONTROL Experience Targeting]</li><li>**MVT** : [!UICONTROL Multivariate Test]</li><li>**REC** : [!UICONTROL Recommendations]</li></ul>Pour plus d’informations sur chaque type, voir [Types d’activité](#types) ci-dessous. |
| [!UICONTROL Name] | Nom de l’activité. Cliquez sur l’icône **[!UICONTROL Quick Info]** ( ![Icône Quick Info](/help/main/assets/icons/InfoOutline.svg) ) en regard de chaque nom d’activité pour afficher plus d’informations sur cette activité dans une carte contextuelle, y compris les [!UICONTROL Activity ID], [!UICONTROL Activity Objective], [!UICONTROL Activity Location], [!UICONTROL Goal] et [!UICONTROL Status].<P>Cliquez sur l’icône **[!UICONTROL More actions]** ( ![Icône Autres actions](/help/main/assets/icons/MoreSmallList.svg) ) en regard de chaque nom d’activité pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’activité) : [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] et [!UICONTROL Archive].<P>Pour plus d’informations sur chaque action, voir [Réaliser des actions rapides](#quick-actions) ci-dessous.<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL Status] | L’état d’une activité peut être l’un des suivants :<ul><li>**[!UICONTROL Live]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Draft]** : la configuration de l’activité a commencé, mais l’activité est en [mode préliminaire](/help/main/c-activities/edit-activity.md) et n’est pas encore prête à être exécutée.</li><li>**[!UICONTROL Scheduled]** : l’activité est prête à être activée aux heure et date spécifiées.</li><li>**[!UICONTROL Inactive]** : l’activité a été suspendue ou désactivée.</li><li>**[!UICONTROL Syncing]** : l’activité a été enregistrée et synchronisée sur le réseau de diffusion [!DNL Target].</li><li>**[!UICONTROL Ended]** : la date et l’heure de fin spécifiées de l’activité ont été atteintes et l’activité n’est plus en cours de diffusion.</li><li>**[!UICONTROL Archived]** : l’activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>**Remarque** : lorsque vous effectuez certaines actions, comme l’activation d’une activité en dehors de l’interface utilisateur de [!DNL Target] à l’aide de méthodes API, la mise à jour peut prendre jusqu’à dix minutes pour se propager à l’interface utilisateur de [!DNL Target]. |
| [!UICONTROL Last Updated] | Date et heure de la dernière mise à jour de l’activité, et par qui.<P>Cliquez sur l’en-tête du tableau pour trier la liste par date, par ordre croissant ou décroissant. |
| [!UICONTROL Priority] | Priorité de l’activité.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Selon vos [paramètres](/help/main/administrating-target/reporting.md), l’interface utilisateur de [!DNL Target] et les options de [!UICONTROL Priority] varient. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou vous pouvez activer les priorités affinées de 0 à 999.<P>Pour plus d’informations sur les paramètres de priorité, voir [Priorité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) sous *Paramètres d’activité* dans *Objectifs et paramètres*. |
| [!UICONTROL Property] | Affiche [la propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de l’activité.<P>Les autorisations des utilisateurs d’Enterprise sont une fonctionnalité [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Estimated Lift in Revenue] | Indique l’effet élévateur estimé dans les recettes si 100 % de l’audience consulte l’expérience gagnante.<P>Cette valeur est calculée à l’aide de la formule suivante :<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Ce chiffre est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la virgule (par exemple, 1,6M, 60K, 900, 8,5K, 205K).<P>Cette colonne indique « --- » pour les activités dont les données ne sont pas suffisantes pour déterminer un contenu performant ou qui ne disposent pas d’une estimation de coût.<P>Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations. |
| [!UICONTROL Source] | Affiche l’emplacement de création de l’activité : [!DNL Adobe Target], [API Adobe Target](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr) ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Location] | L’URL de l’activité identifie l’emplacement d’affichage de l’activité. Cette colonne vous permet d’identifier rapidement une activité et de déterminer si une activité est déjà en cours d’exécution sur une page spécifique.<P>Si une activité s’exécute sur plusieurs URL, un lien indique le nombre d’URL supplémentaires utilisées. Cliquez sur le lien pour afficher la liste complète des URL pour cette activité.<P>Vous pouvez effectuer des recherches en fonction de l’URL. Utilisez la liste déroulante en regard de la zone de recherche et sélectionnez [!UICONTROL URL]. |
| [!UICONTROL Author] | Nom de la personne qui a créé l’activité. |
| [!UICONTROL Decisioning Method] | La méthode de prise de décision utilisée dans chaque activité : [Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) ou [Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## Types d’activités {#types}

[!DNL Target] comprend plusieurs types d’activité. Le tableau suivant présente un aperçu de chaque type d’activité avec des liens pour vous aider à en savoir plus. Pour vous aider à mieux choisir le meilleur type d’activité à vos fins, utilisez le [Guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Le test A/B compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie. |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], type de test A/B, identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant afin d’augmenter les conversions pendant que le test se poursuit et apprend. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | Le ciblage automatique, type de test A/B, utilise l’apprentissage automatique avancé pour identifier plusieurs expériences hautement performantes définies par des responsables du marketing. Il diffuse l’expérience la plus personnalisée à chaque visiteur selon le profil de chaque client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compare des combinaisons d’offres d’éléments sur une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique. Il identifie l’élément qui impacte le plus le succès de l’activité. |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT) diffuse du contenu à une audience spécifique selon un ensemble de règles et de critères définis par le marketeur. |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) combine des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions. |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Une recommandation détermine la manière dont un produit est proposé au visiteur d’un site web, en fonction des activités de ce visiteur sur le site.<P>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Vous pouvez également encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant des vidéos similaires à celles qu’ils visionnent, à l’aide de l’algorithme &quot;Les personnes qui ont consulté ceci ont consulté cela&quot;.<P>**REMARQUE** : vous pouvez également inclure des recommandations dans les activités [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] et [!UICONTROL Experience Targeting] (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une [licence Target Premium](/help/main/c-intro/intro.md#premium). |

## Application de filtres à la liste des activités {#filters}

Accédez aux filtres en cliquant sur l’icône **[!UICONTROL Show Filters]** ( ![Icône Afficher les filtres](/help/main/assets/icons/Filter.svg) ) près du haut de la liste.

Le menu permet de filtrer les activités selon les attributs suivants :

| Attribut | Détails |
| --- | --- |
| [!UICONTROL Type] | Filtrez par [type d’activité](#types). |
| [!UICONTROL Status] | Filtrage par état d’activité.<ul><li>**[!UICONTROL Live]** : l’activité est en cours d’exécution.</li><li>**[!UICONTROL Draft]** : la configuration de l’activité a commencé, mais l’activité est en [mode préliminaire](/help/main/c-activities/edit-activity.md) et n’est pas encore prête à être exécutée.</li><li>**[!UICONTROL Scheduled]** : l’activité est prête à être activée aux heure et date spécifiées.</li><li>**[!UICONTROL Inactive]** : l’activité a été suspendue ou désactivée.</li><li>**[!UICONTROL Syncing]** : l’activité a été enregistrée et synchronisée sur le réseau de diffusion [!DNL Target].</li><li>**[!UICONTROL Ended]** : la date et l’heure de fin spécifiées de l’activité ont été atteintes et l’activité n’est plus en cours de diffusion.</li><li>**[!UICONTROL Archived]** : l’activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul> |
| [!UICONTROL Reporting Source] | Filtrez par source de création de rapports.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) : affiche les activités qui utilisent [!UICONTROL Analytics for Target] (A4T) comme source des rapports.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md) : affiche les activités qui utilisent [!DNL Target] comme source des rapports.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) : affiche les activités qui utilisent [!DNL Adobe Customer Analytics] comme source des rapports.</li></ul> |
| [!UICONTROL Experience Composer] | Filtre selon lequel le compositeur d’expérience a été utilisé lors de la création de l’activité :<ul><li>[Visuel](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) : affiche les activités créées à l’aide du [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Basé sur un formulaire](/help/main/c-experiences/form-experience-composer.md) : affiche les activités créées à l’aide de [!UICONTROL Form-Based Experience Composer].</li></ul> |
| [!UICONTROL Metrics Type] | Filtre par lequel la [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) a été sélectionnée lors de la création de l’activité.<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | Filtrez selon la méthode de prise de décision utilisée dans chaque activité.<ul><li>[Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) : affiche les activités qui utilisent la prise de décision côté serveur.</li><li>[Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html) : affiche les activités qui utilisent la prise de décision côté client.</li></ul> |
| [!UICONTROL Activity Source] | Filtrez selon la source de l&#39;activité utilisée pour créer chaque activité.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=fr)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=fr)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | Filtrez selon la [propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans laquelle l’activité a été créée. |

## Exécution d’actions rapides {#quick-actions}

Cliquez sur l’icône **[!UICONTROL More actions]** ( ![Menu Autres actions](/help/main/assets/icons/MoreVertical.svg) ) en regard de chaque nom d’activité pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité.

Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’activité) :

| Action | Description |
| --- | --- |
| [!UICONTROL Edit] | Permet de modifier une activité. Il est possible de modifier n’importe quelle activité.<P>Pour plus d’informations sur les différentes façons dont vous pouvez modifier les activités, voir [Modification d’une activité ou enregistrement en tant que brouillon](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Permet d’arrêter une activité activée ou programmée. Une activité désactivée peut être réactivée ou archivée.<P>Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur fera encore partie de cette activité après la réactivation s’il s’y trouvait avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Activate] | Lancez une activité inactive ou une activité prête à être activée. |
| [!UICONTROL Archive] | Envoie l’activité vers l’archive. Par défaut, les activités archivées n’apparaissent plus dans la liste [!UICONTROL Activities]. Modifiez le filtre de la liste [!UICONTROL Activities] afin d’inclure les activités archivées pour les afficher. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.<P>Si vous désactivez ou archivez une activité, puis que vous la réactivez plus tard, un visiteur continuera à faire partie de cette activité après la réactivation s’il se trouvait dans cette activité avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Copy] | Permet de copier une activité. Il est possible de copier n’importe quelle activité. La copie d’une activité permet d’en créer une autre dotée du même nom auquel est ajouté le mot « Copie ». Par exemple, la copie d’un test appelé « Offres de navigateur » porte le nom « Copie Offres de navigateur ».<P>Les offres visuelles sont copiées avec l’activité. Vous pouvez modifier les offres en toute sécurité dans la copie sans que cela ait d’incidence sur l’activité d’origine. La seule exception concerne les offres et les images sauvegardées dans le dossier Contenu/Ressources. |
| [!UICONTROL Delete] | Permet de supprimer un brouillon d’activité ou une activité.<P>**REMARQUE :** les activités supprimées le sont définitivement. À moins que vous ne soyez sûr que vous n’aurez plus besoin de cette activité, utilisez l’action [!UICONTROL Archive]. Vous pouvez ensuite réactiver l’activité si nécessaire. |

## Considérations

Notez les détails suivants sur la liste [!UICONTROL Activity] :

* Les activités [!UICONTROL Archived] et [!UICONTROL Ended] n’apparaissent pas dans la liste [!UICONTROL Activities]. Pour afficher ces activités, filtrez-les à l’aide de l’ [icône Filtres](#filters) ( ![icône Afficher les filtres](/help/main/assets/icons/Filter.svg) ) en haut de la liste.
* Lorsqu’une activité créée à l’origine dans [!DNL Target Classic] est désactivée ou supprimée, elle est supprimée de [!DNL Target Standard/Premium]. Les activités supprimées créées à l’origine dans [!DNL Target Classic] ne sont pas envoyées au dossier [!UICONTROL Archive] dans [!DNL Target Standard/Premium]. La fonctionnalité du dossier Archives s’applique uniquement aux activités créées dans [!DNL Target Standard/Premium].
* Tous les types d’activité autres que [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] vous donnent le choix d’utiliser [!DNL Target] ou [!DNL Adobe Analytics] comme source de données. [!UICONTROL Automated Personalization], [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target] ** utilisent toujours des données [!DNL Target].
* Les activités sont disponibles pour différents canaux :

   * sites web et mobiles ;
   * écrans et appareils connectés à Internet, y compris kiosques et guichets automatiques ;
   * messagerie électronique et autres canaux d’acquisition ou sites partenaires ;
   * applications mobiles ;
   * partout où vous pouvez diffuser du contenu balisé.

## Limites  {#section_049D4684403A4E07B998067EB8E9BE56}

Chaque activité [!DNL Target] présente les limites de contenu suivantes :

| Élément | Limite |
|--- |--- |
| Sélecteurs uniques | 300 si un sélecteur est répété dans une expérience différente, il est compté une fois. Cependant, s’il est répété dans la même expérience, il est compté à nouveau. |
| Offres dans chaque expérience | 350 |
| Sélecteurs de suivi des clics dans les mesures | 50 |
| Mbox dans les mesures | 50 |
| Audiences et emplacements | 50 combinaisons d’audiences et d’emplacements (mbox) ne doivent pas dépasser 50. |

L’activité ne peut pas être enregistrée si vous dépassez l’une de ces limites.

L’augmentation du nombre de ces éléments dans votre activité augmente également le temps nécessaire pour synchroniser l’activité sur [!DNL Target].

Pour obtenir des limites supplémentaires du [!UICONTROL Visual Experience Composer] (VEC), voir [Limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributs importés dans [!DNL Target] pour les activités mises à jour en dehors de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si les activités créées dans [!DNL Target] sont mises à jour en dehors de [!DNL Target] (par exemple, via l’API), les attributs d’activité suivants sont réimportés dans [!DNL Target] : `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` et `marketingCloudMetadata(remoteModifiedBy)`.

Cette tâche d’importation s’exécute à l’ouverture de la liste [!UICONTROL Activities], avec un délai maximal de dix minutes.

