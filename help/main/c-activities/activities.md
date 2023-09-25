---
keywords: liste des activités;activités;activité;types d’activité;modifier l’activité;actions d’activité;attribut d’activité;filtre de liste des activités;limites des activités;personnalisation;personnalisation
description: Découvrez comment les activités dans Adobe [!DNL Target] vous permet de personnaliser le contenu pour des audiences spécifiques et de tester des conceptions de page.
title: Comment personnaliser le contenu et tester les conceptions de page avec [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 4b62017fe4dca61b5b05c7778f3a02cf446c17f7
workflow-type: tm+mt
source-wordcount: '2487'
ht-degree: 44%

---

# Activités

Les activités de [!DNL Adobe Target] vous permettent de personnaliser du contenu pour des audiences spécifiques et de tester des conceptions de page.

Vous pouvez par exemple concevoir une activité qui teste deux pages de destination distinctes : l’une qui met en évidence les informations sur les chaussures d’été pour femmes, l’autre qui met en évidence des vêtements d’été plus généraux. L’activité détermine les conditions qui contrôlent quand s’affiche chacune de ces pages d’entrée, ainsi que les mesures qui déterminent la page qui réussit le mieux. L’activité est configurée de manière à démarrer et à s’arrêter quand des conditions spécifiques sont remplies, par exemple entre des dates spécifiques, ou pour commencer quand elle est approuvée et se terminer quand elle est désactivée.

Planifiez soigneusement une activité lorsque vous la concevez. Déterminez le moment auquel l’activité doit débuter, ainsi que sa durée. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

## Liste des activités {#section_DE8E2DB30D534962A931EF8BB48240F5}

La liste des [!UICONTROL activités] est la vue par défaut lors de l’ouverture [!DNL Target]. Vous pouvez créer des activités à partir de cette page et gérer les activités existantes.

Vous pouvez également afficher la liste [!UICONTROL Activités] en cliquant sur l’onglet [!UICONTROL Activités] en haut de [!DNL Target] l’interface utilisateur.

>[!NOTE]
>
>L’illustration et le tableau ci-dessous présentent les fonctionnalités de l’interface utilisateur mise à jour de la liste des activités actuellement en version bêta, qui sera publiée prochainement.


![Liste des activités](/help/main/c-activities/assets/activities-list-new.png)

La variable [!UICONTROL Activités] propose un aperçu de toutes les activités et vous permet d’effectuer diverses opérations :

| Élément | Description |
|--- |--- |
| Rail de navigation à gauche | Basculer entre vos activités enregistrées ou actives et en échec ou [activités préliminaires](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Afficher les filtres] icon<P>![Icône Afficher les filtres](/help/main/c-activities/assets/show-filters-icon.png) | Pour accéder aux filtres, cliquez sur le bouton **[!UICONTROL Afficher les filtres]** en haut de la liste.<P>Pour plus d’informations, voir [Application de filtres à la liste des activités](#filters) ci-dessous |
| Zone Rechercher | Recherchez rapidement une activité ou réduisez le nombre d’activités affichées dans la variable [!UICONTROL Activité] liste. Vous pouvez effectuer une recherche par [!UICONTROL Nom], [!UICONTROL URL], ou [!UICONTROL ID]. |
| [!UICONTROL Créer une activité] | Créez une activité. Pour plus d’informations sur la création des différents types d’activité, voir : <ul><li>[Création d’un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Création d’une activité d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Création d’une activité de ciblage automatique](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Créez une activité de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Création d’une activité de ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Création d’un test multivarié](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Création d’une activité Recommendations](/help/main/c-recommendations/recommendations.md)</li></ul>Pour plus d’informations sur chaque type, voir [Types d’activité](#types) ci-dessous |
| [!UICONTROL Créer un lien d’aperçu mobile]<P>![Plus de menu d’actions](/help/main/c-activities/assets/icon-create-mobile-link.png) | Utilisation [liens d’aperçu mobile](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=fr) pour vérifier simplement et de manière exhaustive la qualité des activités des applications mobiles.<P>Cliquez sur le bouton **Autres options** (points de suspension alignés verticalement), sélectionnez l’icône **Créer un lien d’aperçu mobile**, puis sélectionnez les activités que vous souhaitez tester sur mobile. |
| Personnalisation du tableau<P>![Icône Personnaliser le tableau](/help/main/c-activities/assets/icon-customize-table.png) | Modifier les colonnes affichées dans la variable [!UICONTROL Activité] en cliquant sur la **[!UICONTROL Personnalisation du tableau]** en haut à droite du tableau, puis en sélectionnant ou en désélectionnant les colonnes de votre choix.<P>Les modifications sont appliquées à votre compte et restent actives même après la déconnexion de [!DNL Target]. |
| Cases à cocher des opérations en bloc | Effectuez des opérations en bloc sur toutes les activités ou sur les activités sélectionnées.<P>Pour obtenir la liste des actions disponibles (en fonction de vos autorisations et de l’état de l’activité), voir [Exécution d’actions rapides](#quick-actions) ci-dessous |
| [!UICONTROL Type] | Type d’activité. La variable [!UICONTROL Type] permet d’identifier rapidement chaque activité par type. <ul><li>AB-M : manuel [!UICONTROL Test A/B]</li><li>AB-AA : [!UICONTROL Affectation automatique]</li><li>AB-AT : [!UICONTROL Ciblage automatique]</li><li>AP : [!UICONTROL Automated Personalization]</li><li>XT : [!UICONTROL Ciblage d’expérience]</li><li>MVT : [!UICONTROL Test multivarié]</li><li>REC : [!UICONTROL Recommendations]</li></ul>Pour plus d’informations sur chaque type, voir [Types d’activité](#types) ci-dessous |
| [!UICONTROL Nom] | Nom de l’activité. Cliquez sur le nom d’une activité pour afficher le rapport [!UICONTROL Présentation] page. <P>Cliquez sur le bouton **[!UICONTROL Informations rapides]** en regard de chaque nom d’activité pour afficher plus d’informations sur cette activité dans une carte contextuelle.<p>Cliquez sur le bouton **[!UICONTROL Autres actions]** icône (points de suspension horizontaux) en regard de chaque nom d’activité pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité. Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’activité) : [!UICONTROL Modifier], [!UICONTROL Activer], [!UICONTROL Désactiver], [!UICONTROL Copier], [!UICONTROL Supprimer], et [!UICONTROL Archiver]. Pour plus d’informations sur chaque action, voir [Exécution d’actions rapides](#quick-actions) ci-dessous<P>Cliquez sur l’en-tête du tableau pour trier la liste par ordre alphabétique croissant ou décroissant par nom. |
| [!UICONTROL État] | L’état d’une activité peut être l’un des suivants :<ul><li>**En cours** : l’activité est en cours d’exécution.</li><li>**Version préliminaire**: la configuration de l’activité a commencé, mais elle se trouve dans [mode brouillon](/help/main/c-activities/edit-activity.md) et n’est pas encore prêt à s’exécuter.</li><li>**Planifiée** : l’activité est prête à être activée aux heure et date spécifiées.</li><li>**Inactive** : l’activité a été interrompue ou désactivée.</li><li>**Synchronisation**[!DNL Target] : l’activité a été enregistrée et synchronisée sur le réseau de diffusion </li><li>**Terminé**: la date et l’heure de fin spécifiées de l’activité ont été atteintes et l’activité n’est plus en cours de diffusion.</li><li>**Archivé** : l’activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>**Remarque :**[!DNL Target] Lorsque vous réalisez certaines actions, par exemple lorsque vous activez une activité hors de l’interface utilisateur à l’aide des méthodes de l’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager jusqu’à l’interface utilisateur.[!DNL Target] |
| [!UICONTROL Dernière mise à jour] | Date et heure de la dernière mise à jour de l’activité, et par qui.<P>Cliquez sur l’en-tête du tableau pour trier la liste par date, par ordre croissant ou décroissant. |
| [!UICONTROL Priorité] | Priorité de l’activité.<P>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.<P>Selon votre [paramètres](/help/main/administrating-target/reporting.md), la variable [!DNL Target] Interface utilisateur et options pour [!UICONTROL Priorité] varient. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999. |
| [!UICONTROL Propriété] | Affiche [la propriété](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de l’activité.<P>Les autorisations des utilisateurs d’Enterprise sont [Target Premium](/help/main/c-intro/intro.md#premium) fonction . |
| [!UICONTROL Effet élévateur estimé dans les recettes] | Indique l’effet élévateur estimé dans les recettes si 100 % de l’audience consulte l’expérience gagnante.<P>Cette valeur est calculée à l’aide de la formule suivante :<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Ce chiffre est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la virgule (par exemple, 1,6M, 60K, 900, 8,5K, 205K).<P>Cette colonne indique « --- » pour les activités dont les données ne sont pas suffisantes pour déterminer un contenu performant ou qui ne disposent pas d’une estimation de coût.<P>Voir [Estimation de l’effet élévateur dans les recettes](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) pour plus d’informations. |
| [!UICONTROL Source] | Affiche l’emplacement de création de l’activité : [!DNL Adobe Target], [API ADOBE TARGET](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html), ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Emplacement] | L’URL de l’activité identifie l’emplacement d’affichage de l’activité. Cette colonne vous permet d’identifier rapidement une activité et de déterminer si une activité est déjà en cours d’exécution sur une page spécifique.<P>Si une activité s’exécute sur plusieurs URL, un lien indique le nombre d’URL supplémentaires utilisées. Cliquez sur le lien pour afficher la liste complète des URL pour cette activité.<P>Vous pouvez effectuer des recherches en fonction de l’URL. Utilisez la liste déroulante en regard de la zone de recherche et sélectionnez [!UICONTROL URL]. |
| Auteur | Nom de la personne qui a créé l’activité. |
| [!UICONTROL Méthode de prise de décision] | Méthode de prise de décision utilisée dans chaque activité : [Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr) ou [Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## Types d’activités {#types}

[!DNL Target] comprend plusieurs types d’activité. Le tableau suivant présente un aperçu de chaque type d’activité avec des liens pour vous aider à en savoir plus. Pour mieux choisir le meilleur type d’activité à vos fins, nous avons également créé le [guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Le test A/B compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie. |
| [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Affectation automatique], type de test A/B, identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant afin d’augmenter les conversions pendant que le test continue à s’exécuter et à apprendre. |
| [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | Le ciblage automatique, type de test A/B, utilise l’apprentissage automatique avancé pour identifier plusieurs expériences hautement performantes définies par des responsables du marketing. Il diffuse l’expérience la plus personnalisée à chaque visiteur selon le profil de chaque client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions. |
| [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compare des combinaisons d’offres d’éléments d’une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique, et identifie l’élément qui impacte le plus le succès de l’activité. |
| [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) | Le [!UICONTROL ciblage d’expérience] (XT) diffuse un contenu à une audience spécifique selon un ensemble de règles et de critères définis par les spécialistes marketing. |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) associe des offres ou des messages et utilise l’apprentissage automatique avancé pour faire correspondre différentes variations à chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions. |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Une recommandation détermine la manière dont un produit est proposé au visiteur d’un site web, en fonction des activités de ce visiteur sur le site.<P>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Vous pouvez également encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant des vidéos similaires à celles qu’ils visionnent, à l’aide de l’algorithme &quot;Les personnes qui ont consulté ceci ont consulté cela&quot;.<P>**REMARQUE**: vous pouvez également inclure des recommandations dans la variable [!UICONTROL Test A/B], [!UICONTROL Affectation automatique], [!UICONTROL Ciblage automatique], et [!UICONTROL Ciblage d’expérience] (XT). Pour plus d’informations, consultez [Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium). |

## Application de filtres à la liste des activités {#filters}

Pour accéder aux filtres, cliquez sur le bouton **[!UICONTROL Afficher les filtres]** en haut de la liste.

![Options de filtre](/help/main/c-activities/assets/show-filters-options.png)

Le menu permet de filtrer les activités selon les attributs suivants : |Attribut|Détails| | — | — | |[!UICONTROL Type]|Filtrer par [type d&#39;activité](#types).| |[!UICONTROL État]|Filtrez par état d’activité.| |[!UICONTROL Source de création de rapports]|Filtrez par source de création de rapports.<ul><li>[Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md): affiche les activités qui utilisent [!UICONTROL Analytics pour Target] (A4T) comme source des rapports.</li><li>[Cible](/help/main/c-reports/reports.md): affiche les activités qui utilisent [!DNL Target] comme source des rapports.</li></ul>| |[!UICONTROL Compositeur d’expérience]|Filtre selon lequel le compositeur d’expérience a été utilisé lors de la création de l’activité :<ul><li>[Visuel](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): affiche les activités qui ont été créées à l’aide de la variable [!UICONTROL Compositeur d’expérience visuelle] (VEC).</li><li>[Basé sur un formulaire](/help/main/c-experiences/form-experience-composer.md): affiche les activités qui ont été créées à l’aide du [!UICONTROL Compositeur d’expérience d’après les formulaires].</li></ul>| |[!UICONTROL Type de mesure]|Filtrer par [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md) a été sélectionné lors de la création de l’activité.<ul><li>Conversion</li><li>Recettes</li><li>Engagement</li></ul>| |[!UICONTROL Méthode de prise de décision]|Filtrer selon la méthode de prise de décision utilisée dans chaque activité<ul><li>[Côté serveur](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr): affiche les activités qui utilisent la prise de décision côté serveur.</li><li>[Côté client](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): affiche les activités qui utilisent la prise de décision côté client.</li></ul>| |[!UICONTROL Source de l’activité]|Filtrez selon la source de l’activité utilisée pour créer chaque activité.<ul><li>[!DNL Adobe Target]</li><li>[API ADOBE TARGET](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=fr)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[Services mobiles Adobe](https://developer.adobe.com/client-sdks/documentation/)</li></ul>| |[!UICONTROL Propriété]|Filtrez par la variable [property](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans laquelle l’activité a été créée.|

## Exécution d’actions rapides {#quick-actions}

Cliquez sur le bouton **[!UICONTROL Autres actions]** icône (points de suspension horizontaux) en regard de chaque nom d’activité pour ouvrir un menu vous permettant d’exécuter des actions rapides sur une activité.

![Options d’actions rapides](/help/main/c-activities/assets/quick-actions.png)

Les actions suivantes sont disponibles (en fonction de vos autorisations et de l’état de l’activité) :

| Action | Description |
| --- | --- |
| [!UICONTROL Modifier] | Permet de modifier une activité. Il est possible de modifier n’importe quelle activité.<P>Pour plus d’informations sur les différentes méthodes de modification des activités, voir [Modification d’une activité ou enregistrement en tant que brouillon](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Désactiver] | Permet d’arrêter une activité activée ou programmée. Une activité désactivée peut être réactivée ou archivée.<P>Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur fera encore partie de cette activité après la réactivation s’il s’y trouvait avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Activer] | Lancez une activité inactive ou une activité prête à être activée. |
| [!UICONTROL Archiver] | Envoie l’activité vers l’archive. Par défaut, les activités archivées n’apparaissent plus dans le [!UICONTROL Activités] liste. Pour les voir, modifiez le filtre de la liste des activités pour inclure les activités archivées. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.<P>Si vous désactivez ou archivez une activité, puis que vous la réactivez plus tard, un visiteur continuera à faire partie de cette activité après la réactivation s’il se trouvait dans cette activité avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| [!UICONTROL Copier] | Permet de copier une activité. Il est possible de copier n’importe quelle activité. La copie d’une activité permet d’en créer une autre dotée du même nom auquel est ajouté le mot « Copie ». Par exemple, la copie d’un test appelé « Offres de navigateur » porte le nom « Copie Offres de navigateur ».<P>Les offres visuelles sont copiées avec l’activité. Vous pouvez modifier les offres en toute sécurité dans la copie sans que cela ait d’incidence sur l’activité d’origine. La seule exception concerne les offres et les images sauvegardées dans le dossier Contenu/Ressources. |
| [!UICONTROL Supprimer] | Permet de supprimer un brouillon d’activité ou une activité.<P>**REMARQUE :** les activités supprimées le sont définitivement. À moins d’être sûr que vous n’aurez plus besoin de cette activité, utilisez la variable [!UICONTROL Archiver] action. Vous pouvez ensuite réactiver l’activité si nécessaire. |

## Considérations

Notez les détails suivants sur la variable [!UICONTROL Activité] list :

* Les activités archivées et terminées n’apparaissent pas dans la liste des [!UICONTROL activités]. Pour visualiser ces activités, filtrez-les à l’aide du [Icône Filtres](#filters) en haut de la liste.
* Lorsqu’une activité créée à l’origine dans [!DNL Target Classic] est désactivé ou supprimé, il est supprimé de [!DNL Target Standard/Premium]. Les activités supprimées créées à l’origine [!DNL Target Classic] ne sont pas envoyées dans le dossier [!UICONTROL Archives] dans [!DNL Target Standard/Premium]. La fonctionnalité du dossier Archives s’applique uniquement aux activités créées dans [!DNL Target Standard/Premium].
* Tous les types d’activités autres que [!UICONTROL Personnalisation automatisée] (AP), [!UICONTROL Allocation automatique], et [!UICONTROL Cible automatique] vous donnent le choix d’utiliser [!DNL Target] ou [!DNL Adobe Analytics] en tant que source de données. [!UICONTROL AP], [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] *utilisent* toujours [!DNL Target] les données.
* Les activités sont disponibles pour différents canaux :

   * sites web et mobiles ;
   * écrans et appareils connectés à Internet, y compris kiosques et guichets automatiques ;
   * messagerie électronique et autres canaux d’acquisition ou sites partenaires ;
   * applications mobiles ;
   * partout où vous pouvez diffuser du contenu balisé.

## Limites  {#section_049D4684403A4E07B998067EB8E9BE56}

Chaque activité Target comporte les limites de contenu suivantes :

| Élément | Limite |
|--- |--- |
| Sélecteurs uniques | 300 si un sélecteur est répété dans une autre expérience, il est compté une fois. Cependant, s’il est répété dans la même expérience, il est compté à nouveau. |
| Offres dans chaque expérience | 350 |
| Sélecteurs de suivi des clics dans les mesures | 50 |
| Mbox dans les mesures | 50 |
| Audiences et emplacements | 50 combinaisons d’audiences et d’emplacements (mbox) ne doivent pas dépasser 50. |

L’activité ne peut pas être enregistrée si vous dépassez l’une de ces limites.

L’augmentation du nombre de ces éléments dans votre activité augmente également le temps nécessaire pour synchroniser l’activité sur l’ensemble des [!DNL Target].

Pour les limites supplémentaires du V[!UICONTROL Compositeur d’expérience visuelle] VEC, voir [Limites du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributs importés dans [!DNL Target] pour les activités mises à jour en dehors de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si des activités ont été créées dans [!DNL Target] sont mises à jour en dehors de [!DNL Target] (par exemple, via l’API), les attributs d’activité suivants sont réimportés dans [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority`, et `marketingCloudMetadata(remoteModifiedBy)`.

Cette tâche d’importation s’exécute à l’ouverture de la page des activités, avec un délai maximal de dix minutes.

## Vidéos de formation {#section_BE80D13A2E81460C885F902010E1AD87}

La vidéo suivante contient des informations supplémentaires sur les concepts abordés dans cet article.

### Types d’activité (9:03)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

