---
description: Les activités vous permettent de tester les conceptions de page et de cibler du contenu vers des audiences spécifiques.
keywords: liste des activités;activités;activité;types d’activités;modifier l’activité;actions d’activités;attribut d’activité;filtre de la liste des activités;limites des activités
seo-description: Les activités dans Adobe Target vous permettent de tester des conceptions de page et de cibler du contenu vers des audiences spécifiques.
seo-title: Activités dans Adobe Target
solution: Target
title: Espaces de travail
topic: Standard
uuid: 89dca5b4-c23d-4dfa-8f13-f1b05c7ab22c
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Activités{#activities}

Les activités vous permettent de tester les conceptions de page et de cibler du contenu vers des audiences spécifiques. Une activité détermine les expériences qu’un visiteur de site peut rencontrer.

Vous pouvez, par exemple, concevoir une activité qui teste deux pages d&#39;entrée différentes, une qui met en évidence les informations sur les chaussures d&#39;été pour femmes, ainsi qu&#39;une autre page d&#39;entrée qui met en évidence des éléments d&#39;été plus généraux. L’activité détermine les conditions qui contrôlent quand s’affiche chacune de ces pages d’entrée, ainsi que les mesures qui déterminent la page qui réussit le mieux. L’activité est configurée de manière à démarrer et à s’arrêter quand des conditions spécifiques sont remplies, par exemple entre des dates spécifiques, ou pour commencer quand elle est approuvée et se terminer quand elle est désactivée.

Planifiez soigneusement une activité lorsque vous la concevez. Déterminez quand elle doit commencer et combien de temps elle doit durer. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

## Types d’activités

Target comprend plusieurs types d&#39;activité. Le tableau suivant présente un aperçu de chaque type d&#39;activité avec des liens pour vous aider à en savoir plus. Pour mieux choisir le meilleur type d&#39;activité à vos fins, nous avons également créé le guide des activités [Adobe Target](/help/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [Test A/B](/help/c-activities/t-test-ab/test-ab.md) | Le test A/B compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie.<br>**Remarque :** Vous pouvez désormais inclure [des recommandations dans les activités de test A/B](/help/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/c-intro/intro.md#premium). |
| [affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | L’affectation automatique identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant afin d’augmenter les conversions pendant que le test se poursuit et apprend.<br>**Remarque :** Vous pouvez désormais inclure [des recommandations dans les activités d&#39;affectation automatique](/help/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert que vous disposiez d&#39;une fonctionnalité tthis pour disposer d&#39;une licence [Target Premium](/help/c-intro/intro.md#premium). |
| [Ciblage automatique TargetTarget](/help/c-activities/auto-target-to-optimize.md)<br>![Premium](/help/assets/premium.png) | Le ciblage automatique met à profit l’apprentissage automatique avancé pour identifier plusieurs expériences hautes performances définies par des responsables du marketing et diffuse l’expérience la plus personnalisée à chaque visiteur selon son profil client et le comportement des visiteurs précédents dotés de profils similaires afin de personnaliser le contenu et de générer des conversions.<br>**Remarque :** Vous pouvez désormais inclure [des recommandations dans les activités Ciblage automatique](/help/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert que vous disposiez d&#39;une fonctionnalité de configuration [Target Premium](/help/c-intro/intro.md#premium). |
| [Utilisation des données Analytics](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A 4 T) | Vous pouvez configurer une activité pour utiliser [!DNL Adobe Analytics] en tant que source de création de rapports. Ce type d’activité requiert que vous liiez votre compte [!DNL Adobe Experience Cloud] avec [!DNL Analytics] et [!DNL Target]. |
| [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Le test multivarié (MVT) compare des combinaisons d’offres d’éléments sur une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique. Il identifie l’élément qui impacte le plus le succès de l’activité. |
| [Ciblage d’expérience](/help/c-activities/t-experience-target/experience-target.md) | Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.<br>**Remarque :** Vous pouvez désormais inclure [des recommandations dans les activités de ciblage d&#39;expérience](/help/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/c-intro/intro.md#premium). |
| [Personnalisation automatisée de Target](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Premium](/help/assets/premium.png) | Automated Personalization (AP) associe des offres ou des messages et utilise l’apprentissage automatique avancé pour mettre en correspondance différentes variations avec chaque visiteur selon leur profil client spécifique afin de personnaliser le contenu et de générer des conversions. |
| [Recommendationstarget](/help/c-recommendations/recommendations.md)<br>![Premium](/help/assets/premium.png) | Une recommandation détermine comment un produit est proposé à l’utilisateur d’un site web, en fonction de ses activités sur le site.<br>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Ou, vous souhaitez peut-être encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant une vidéo similaire à celle qu’ils regardent, à l’aide de l’algorithme « Les personnes qui ont regardé cette vidéo ont également regardé ».<br>**Remarque :** Vous pouvez désormais inclure des recommandations dans le test A/B (y compris l&#39;affectation automatique et le ciblage automatique) et les activités de ciblage d&#39;expérience (XT). Voir [Recommandations en tant qu&#39;offre](/help/c-recommendations/recommendations-as-an-offer.md). |

## Liste des activités {#section_DE8E2DB30D534962A931EF8BB48240F5}

La liste [!UICONTROL des activités] est la vue par défaut lors de l&#39;ouverture [!DNL Target]. Vous pouvez créer de nouvelles activités à partir de cette page et gérer les activités existantes.

Vous pouvez également afficher la liste [!UICONTROL Activités] en cliquant sur l&#39;onglet [!UICONTROL Activités] en haut de [!DNL Target] l&#39;interface utilisateur.

![Liste des activités](/help/c-activities/assets/activities-list.png)

La liste Activités donne une vue d’ensemble de toutes les activités:

| Élément | Description |
|--- |--- |
| Type | Type d’activité, tel que A/B ou MVT. |
| Nom | Nom de l’activité. |
| URL | L’URL apparaît en texte plus clair en dessous du nom.<br>L’URL de l’activité identifie l’emplacement d’affichage de l’activité. Vous pouvez ainsi identifier rapidement une activité et déterminer si une page spécifique comporte déjà un test en cours d’exécution.<br>Si un test s’exécute sur plusieurs URL, un lien affiche le nombre d’URL supplémentaires utilisées. Cliquez sur le lien pour afficher la liste complète des URL pour cette activité.<br>Vous pouvez effectuer des recherches en fonction de l’URL. Utilisez la liste déroulante en regard de la zone de recherche et sélectionnez [!UICONTROL Rechercher une URL]. |
| État | L’état d’une activité peut être l’un des suivants :<ul><li>**En cours** : l’activité est en cours d’exécution.</li><li>**Version préliminaire** : la configuration de l’activité a commencé, mais celle-ci n’est pas encore prête à être activée.</li><li>**Planifiée** : l’activité est prête à être activée aux heure et date spécifiées.</li><li>**Inactive** : l’activité a été interrompue ou désactivée.</li><li>**Synchronisation**: l’activité a été enregistrée et synchronisée sur le réseau de diffusion Target.</li><li>**Fin**: la date et l’heure de fin spécifiées de l’activité sont atteintes et l’activité n’est plus en cours de diffusion.</li><li>**Archivé**: l’activité a été archivée. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.</li></ul>**Remarque :** Lorsque vous réalisez certaines actions, par exemple lorsque vous activez une activité hors de l’interface utilisateur à l’aide des méthodes de l’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager jusqu’à l’interface utilisateur. |
| Source | Affiche l’emplacement où l’activité a été créée :<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager  (AEM)</li><li>Adobe Mobile Services (AMS)</li></ul> |
| Propriété | Affiche [la propriété](/help/administrating-target/c-user-management/property-channel/property-channel.md) de l&#39;activité. |
| Effet élévateur estimé dans les recettes | Indique l’effet élévateur estimé dans les recettes si 100 % de l’audience consulte l’expérience gagnante.<br>Calculé en utilisant la formule suivante :<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>le chiffre obtenu est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la décimale. Par exemple : $1.6M, $60K, $900, $8.5K, $205K<br> Cette colonne indique « --- » pour les activités dont les données ne sont pas suffisantes pour déterminer un contenu performant ou qui ne disposent pas d’une estimation de coût.Pour plus d’informations, <br>voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Dernière mise à jour | Date de la dernière mise à jour de l’activité et personne ayant effectué cette mise à jour. |

Pointez sur une activité pour afficher les actions disponibles,

![Actions de survol Liste des activités](/help/c-activities/assets/activities_list_hover.png)

Les actions suivantes sont disponibles (selon vos autorisations) :

| Action | Description |
| --- | --- |
| Modifier  | Permet de modifier une activité. Il est possible de modifier n’importe quelle activité.<br>Pour plus d’informations sur les différentes méthodes de modification des activités, voir [Modification d’une activité ou enregistrement en tant que brouillon](/help/c-activities/edit-activity.md). |
| Désactiver | Permet d’arrêter une activité activée ou programmée. Une campagne désactivée peut être réactivée ou archivée<br>. Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur continuera à faire partie de cette activité après la réactivation s’il y était avant sa désactivation ou son archivage. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| Activer | Permet de démarrer une activité inactive ou prête à être activée. |
| Archiver | Envoie l’activité vers l’archive. Par défaut, les activités archivées n’apparaissent plus dans la liste des activités. Pour les voir, modifiez le filtre de la liste des activités pour inclure les activités archivées. Vous pouvez activer une activité archivée pour l’utiliser à nouveau.<br>Si vous désactivez ou archivez une activité et que vous la réactivez plus tard, un visiteur fera encore partie de cette activité après la réactivation s’il s’y trouvait avant qu’elle ne soit désactivée ou archivée. Toute mesure de conversion enregistrée pendant la période entre les deux événements ne sera pas attribuée à cette activité. |
| Copier  | Permet de copier une activité. Il est possible de copier n’importe quelle activité. La copie d’une activité permet d’en créer une autre dotée du même nom auquel est ajouté le mot « Copie ». Par exemple, la copie d’un test appelé « Offres de navigateur » porte le nom « Copie Offres de navigateur ».<br>Les offres visuelles sont copiées avec l’activité. Vous pouvez modifier les offres en toute sécurité dans la copie sans que cela ait d’incidence sur l’activité d’origine. La seule exception concerne les offres et les images sauvegardées dans le dossier Contenu/Ressources. |
| Supprimer | Permet de supprimer un brouillon d’activité ou une activité prête. Les activités supprimées le sont définitivement. |

Remarques à propos de la liste des activités :

* Les activités archivées et terminées n’apparaissent pas dans la liste des [!UICONTROL activités]. Pour voir ces activités, filtrez-les en utilisant les paramètres de filtrage avancés dans le rail gauche.
* Dès qu’une activité créée à l’origine dans [!DNL Target Classic] est désactivée ou supprimée, elle est également supprimée de [!DNL Target Standard/Premium]. Les activités supprimées créées à l’origine [!DNL Target Classic] ne sont pas envoyées dans le dossier [!UICONTROL Archives] dans [!DNL Target Standard/Premium]. La fonctionnalité du dossier Archives s’applique uniquement aux activités créées dans [!DNL Target Standard/Premium].
* Tous les types d’activités autres que [!UICONTROL Personnalisation automatisée] (AP), [!UICONTROL Allocation automatique], et [!UICONTROL Cible automatique] vous donnent le choix d’utiliser [!DNL Target] ou [!DNL Adobe Analytics] en tant que source de données. [!UICONTROL AP], [!UICONTROL Affectation automatique]et [!UICONTROL Ciblage automatique] *utilisent* toujours [!DNL Target] les données.
* Les activités sont disponibles pour différents canaux :

   * sites web et mobiles ;
   * écrans et appareils connectés à Internet, y compris kiosques et guichets automatiques ;
   * messagerie électronique et autres canaux d’acquisition ou sites partenaires ;
   * applications mobiles ;
   * partout où vous pouvez diffuser du contenu balisé.

## Tri et filtrage de la liste des activités {#section_41DAD479FFF740E2BB67BF4825955670}

Par défaut, la liste est triée par date de dernière modification de l’activité. La date la plus récente apparaît en haut de la liste. Cependant, il existe plusieurs options de filtrage qui vous permettent de personnaliser la liste afin d’afficher les activités qui vous intéressent.

### Rechercher {#search-heading}

Utilisez le champ de recherche pour rechercher des activités qui correspondent à vos critères de recherche.

![Recherche d&#39;activités](/help/c-activities/assets/activities_search_new.png)

Le champ de recherche comprend un menu déroulant pour vous aider à cibler votre recherche en spécifiant l’un des filtres de recherche suivants :  [!UICONTROL Nom de l’activité] et [!UICONTROL URL].

### Filtres de la liste des activités

Vous pouvez choisir les activités qui apparaissent dans la liste des activités en sélectionnant des filtres de liste.

![Filtrage des activités par type](/help/c-activities/assets/activities_filters_new.png)

Vous pouvez filtrer le contenu selon les options suivantes : Dans chaque activité, si aucune valeur n’est sélectionnée, la valeur par défaut est Tous.

| Catégorie de filtre | Filtre |
|--- |--- |
| Type | Test A/B : [Manuel](/help/c-activities/t-test-ab/test-ab.md), [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)et [Ciblage automatique](/help/c-activities/auto-target-to-optimize.md).<br>[Custom personalizationtarget](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>[](/help/c-activities/t-experience-target/experience-target.md)<br>[targetingtestrecommandations testetingmultivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[](/help/c-recommendations/recommendations.md) |
| État | En direct<br>Brouillon<br>Programmé<br>Inactif<br>Synchronisation<br>Terminé<br>Archivé |
| Source de création de rapports | Targetanalytics<br> |
| Compositeur d’expérience | Visuel<br>D’après les formulaires |
| Type de mesure | Conversion<br>Recettes<br>Engagement |
| Source d’activité | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### Tri par attribut d&#39;activité

Cliquez sur l’un des titres suivants pour trier les activités par ordre croissant ou décroissant selon le titre sélectionné.

* Nom de l’activité
* Type d’activité

![Ordre croissant des activités](/help/c-activities/assets/activities_list_ascending.png)

## Conseils et astuces {#section_F77F30A246A14B538D9363B7F3639F97}

Tirez le meilleur parti d’Adobe Target en en apprenant davantage sur les différentes fonctionnalités et découvrez pourquoi vous devriez les essayer. La fonctionnalité Conseils et astuces fournit des liens vers des vidéos, des cas d’utilisation, des blogs, de la documentation et bien plus encore.

La fonctionnalité Conseils et astuces s’affiche régulièrement sur la page Liste des activités. Après avoir lu ou fermé un conseil, cette fonctionnalité ne s’affiche plus avant qu’un nouveau conseil soit disponible. Vous avez la possibilité de désactiver l’affichage des conseils en cliquant sur l’icône Aide, puis sur [!UICONTROL Désactiver le conseil du jour].

![Désactiver la pointe du jour](/help/c-activities/assets/tip-disable-new.png)

## Limites {#section_049D4684403A4E07B998067EB8E9BE56}

Chaque activité Target comporte les limites de contenu suivantes :

| Élément | Limite |
|--- |--- |
| Sélecteurs uniques | 300 si un sélecteur est répété dans une autre expérience, il est compté une fois. Cependant, s’il est répété dans la même expérience, il est compté à nouveau. |
| Offres dans chaque expérience | 350 |
| Sélecteurs de suivi des clics dans les mesures | 50 |
| Mbox dans les mesures | 50 |
| Audiences et emplacements | Il ne peut pas y avoir plus de 50 combinaisons d’audiences et d’emplacements (mbox). |

L&#39;activité ne peut pas être enregistrée si vous dépassez l&#39;une de ces limites.

L’augmentation du nombre de ces éléments dans votre activité entraîne l’augmentation du temps nécessaire pour synchroniser l’activité avec Target.

Pour des limites supplémentaires du compositeur d’expérience visuelle, voir [Limites du compositeur d’expérience visuelle](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Attributs importés dans Target pour les activités mises à jour en dehors de Target {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si des activités créées dans [!DNL Target] sont mises à jour en dehors de [!DNL Target] (par exemple, via Adobe I/O), les attributs d’activité suivants sont réimportés dans [!DNL Target] :

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

La tâche d’importation s’exécute lors de l’affichage de la page des activités, avec un retard maximal de dix minutes. (KB-1526)

## Vidéos de formation {#section_BE80D13A2E81460C885F902010E1AD87}

Les vidéos suivantes contiennent davantage d&#39;informations sur les concepts abordés dans cet article.

### Types d’activité (9:03)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Gestion des activités (5:55)

Cette vidéo explique comment utiliser la liste des activités pour gérer les activités.

* Définition du terme *activité*
* Recherche d’activités dans la liste des activités
* Modification, désactivation, copie et suppression d’activités

>[!VIDEO](https://video.tv.adobe.com/v/18550)
