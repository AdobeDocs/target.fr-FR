---
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
description: Informations sur les problèmes connus de cette version d’Adobe Target. Inclut également des informations sur les problèmes résolus.
title: Problèmes connus et problèmes résolus dans Adobe Target
feature: known issues
uuid: f8e8e057-1842-4922-ab7f-4d5441048573
translation-type: tm+mt
source-git-commit: 72ea4544313bcfd1d39c1a4ce63bb41fcad699c5
workflow-type: tm+mt
source-wordcount: '3793'
ht-degree: 80%

---


# Problèmes connus et problèmes résolus {#known-issues-and-resolved-issues}

Informations sur les problèmes connus de cette version de Target. Inclut également des informations sur les problèmes résolus.

>[!NOTE]
>
>Les numéros entre parenthèses sont réservés à une utilisation interne par Adobe.

## Problèmes connus {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

Les sections suivantes répertorient les problèmes connus de [!DNL Target] :

### Diffusion de page {#page-delivery}

Si vous ajoutez une règle de modèle, telle que l’URL contient (/checkout, /cart) dans la [diffusion de page](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md), des espaces supplémentaires sont prédéfinis dans vos règles. Il s’agit d’un problème cosmétique qui n’affecte pas la création de la définition de l’audience et la diffusion de l’offre. (TGT-35920)

### Liens de prévisualisation QA

Les liens d’aperçu de l’AQ des activités pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. Une nouvelle tentative avec les liens d’aperçu doit fonctionner. Archivez les activités enregistrées qui ne sont plus activement utilisées pour empêcher ce problème de se produire. (TNT-37294)

### Mode QA pour les activités Recommendations

Un problème connu empêche la prévisualisation si les critères utilisés dans l’activité sont basés sur un élément ou sur une catégorie. (TNT-37455)

### Offres de redirection {#redirect}

Les problèmes suivants sont des problèmes connus des offres de redirection :

* Dans certains cas, un nombre limité de clients ont signalé des degrés de variation de trafic supérieurs lors de l’utilisation d’une offre de redirection dans les activités configurées avec Analytics pour Target (A4T). Les ingénieurs Adobe travaillent actuellement sur ce problème.
* Dans les mises en œuvre d’at.js, les activités de redirection peuvent provoquer l’entrée dans une boucle de l’URL d’aperçu (la distribution de l’offre se répète). Vous pouvez utiliser le [mode Assurance qualité](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) au lieu d’effectuer l’aperçu et la vérification de la qualité. Ce problème n’a aucun impact sur la distribution réelle de l’offre. (TGT-23019)

### Annulation du chargement d’une page dans le VEC {#cancel}

* Le problème connu suivant existe actuellement lors de l’annulation du chargement d’une activité de [!UICONTROL test A/B] ou de [!UICONTROL ciblage d’expérience] dans le VEC qui contient une URL de redirection.

   Dans la première étape du workflow guidé en trois parties à l’intérieur du VEC, lorsque vous annulez le chargement de la page, le panneau [!UICONTROL Modifications] du VEC s’affiche et le modèle de redirection vers une URL est appliqué à l’expérience (par exemple « Expérience B »). Lorsque vous passez aux étapes deux ou trois puis que vous revenez à la première étape, la situation suivante se produit.

   Sur « Expérience B », par défaut, le modèle de chargement de site web annulé est rendu et le panneau [!UICONTROL Modifications] est accessible, ce qui ne devrait pas être le cas, car cette expérience a été appliquée à un modèle de redirection vers une URL. Le modèle de redirection vers l’URL doit s’afficher.

   Pour afficher l’état correct de l’expérience dans le VEC :

   Si vous passez à une autre expérience, puis revenez à « Expérience B », [!DNL Target] affiche le modèle de redirection vers l’URL appliqué à cette expérience et le panneau [!UICONTROL Modifications] n’est pas accessible. (TGT-32138)

* Pour les sites web d’applications monopages, l’annulation du chargement ne permet pas de modifier les actions dans le panneau [!UICONTROL Modifications].

### Recommandations

Les problèmes suivants sont des problèmes connus des activités de recommandations :

* Les entités sont correctement expirées après 60 jours de non réception des mises à jour par flux ou API ; toutefois, les entités expirées ne sont pas supprimées de l’index de recherche de catalogue après expiration. (IRI-857)
* Les incrustations « Informations d’utilisation » pour les critères et les conceptions ne reflètent pas leur utilisation dans les activités A/B et de ciblage d’expérience (TGT-34331)
* Les recommandations d’offres dans les activités A/B et de ciblage d’expérience ne présentent pas de prévisualisation visuelle de la barre d’état Recommandations (TGT-33426)
* Les collections, exclusions, critères et conceptions créés par le biais de l’API ne sont pas visibles dans l’interface utilisateur Target et ne peuvent être modifiés que par le biais de l’API. (TGT-35777)
* Les activités de recommandations créées par l’intermédiaire de l’API peuvent être visualisées dans l’interface utilisateur, mais ne peuvent être modifiées qu’au moyen de l’API.
* L’état du flux Critères personnalisés affiché dans la vue Liste (carte) de critères est actualisé toutes les dix minutes et peut parfois être obsolète de plus de dix minutes dans de rares circonstances. L’état affiché dans la vue Modification des Critères personnalisés est récupéré en temps réel et est constamment à jour. (TGT-35896, TGT-36173)

### Activités de test multivarié (MVT)

Dans une activité de test multivarié, les gagnants affichés dans le tableau et le graphique ne sont pas cohérents lors de la vérification des mesures. Cette situation se produit lorsqu’un utilisateur bascule de la vue récapitulative à la vue graphique, puis revient à la vue récapitulative, modifie une mesure, puis bascule en vue graphique. Lorsque ce problème se produit, la vue récapitulative affiche toujours le gagnant correct. Si l’utilisateur ne passe jamais à la vue graphique entre les vues récapitulatives, la vue graphique affiche le gagnant correct.

### at.js {#atjs}

Les problèmes suivants sont des problèmes connus d’at.js :

* En utilisant les versions d’at.js antérieures à la version 2.2.0, le suivi des clics ne signale pas les conversions dans Analytics for Target (A4T) si le code Adobe Analytics n’est pas présent sur les éléments de page (tels que les boutons). Un correctif a été introduit pour ce problème dans at.js 2.2.0. [Veuillez effectuer la mise à niveau vers la dernière version d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) si vous rencontrez ce problème.
* Si vous créez une expérience sans modification à l’aide d’at.js 2.1.1 ou d’une version antérieure (par exemple, une expérience par défaut), elle peut ne pas être comptabilisée dans les rapports, Analytics for Target (A4T), Adobe Analytics ou Google Analytics. En outre, le module [ttMeta](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md) risque de ne pas fonctionner correctement.

   Pour pallier ce problème, utilisez un espace blanc dans le contenu de l’expérience. (TNT-33366)

   >[!NOTE]
   >
   >Un correctif pour ce problème a été inclus dans at.js 2.2.0. Vous devez effectuer la mise à niveau vers la [dernière version ou at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) ou utiliser la solution mentionnée ci-dessus uniquement pour les versions d’at.js antérieures à la version 2.2.0.

* Lorsqu’une page est chargée dans le compositeur d’expérience visuelle, Target doit déterminer si le paramètre de mbox globale est activé ou désactivé et si entityID ou categoryID est présent à l’emplacement où l’utilisateur tente d’appliquer la recommandation dans le compositeur d’expérience visuelle. Sur la base de ces informations, la liste des critères est filtrée. La liste par défaut comporte des algorithmes filtrés, mais la [case à cocher Compatible](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) permet d’afficher la liste complète des algorithmes.

   Lorsque vous utilisez at.js, la case à cocher Compatible est masquée. Vous ne pouvez donc pas voir les algorithmes incompatibles.

   Ce problème s’applique uniquement aux activités de recommandations qui utilisent le compositeur d’expérience visuelle.

   **Solution** : désactivez l’option [!UICONTROL Filtrer les critères incompatibles] dans [!UICONTROL Recommandations > Paramètres]. Après avoir désactivé ce paramètre, tous les critères (compatibles et incompatibles) s’affichent dans le sélecteur de critères. (TGT-25949)

* Les mbox ne se déclenchent pas sur les navigateurs Microsoft Explorer 11 après la mise à niveau vers at.js version 1.0 en raison de l’interaction entre at.js et l’API visiteur 2.2.0. Ce problème affecte les versions 0.9.6 et ultérieures d’at.js. (TNT-27600)
* at.js peut ne pas fonctionner avec les applications Cordova/Hybrid, puisqu’elles ne prennent pour l’instant pas en charge les cookies propriétaires. (TNT-26166)

   **Solution** : configurez at.js avec l’option « x-only » activée et transmettez `mboxThirdPartyId` dans les appels pour la gestion des utilisateurs.

### Mesures de succès

Les mesures de succès avec l’option avancée « Comment sera incrémenté le décompte ? » définie sur « À chaque impression » ou « À chaque impression (actualisations de page exclues) » ne peuvent pas être utilisées en tant que mesure de succès dont une autre mesure dépend.

Lorsqu’une mesure de succès est définie pour être incrémentée à chaque impression, Target comptabilise à nouveau le visiteur à chaque fois que ce visiteur visite cette mesure de succès. Target remet ensuite la mesure de succès « appartenance » à 0 pour pouvoir effectuer le décompte à nouveau à la prochaine impression. Par conséquent, si une autre mesure nécessite que cette mesure ait été vue au préalable, Target ne reconnaîtra jamais que l’utilisateur a vu la première mesure.

### Analytics for Target (A4T)

Lors de l’utilisation des impressions et des conversions d’activité d’Cible dans Analysis Workspace, appliquez le modèle Attribution IQ &quot;Même touche&quot; aux mesures afin d’assurer un comptage précis. Pour appliquer un modèle [d’attribution](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)non défini par défaut, cliquez avec le bouton droit de la souris sur la mesure pour **modifier les paramètres de colonne > activez Utiliser un modèle d’attribution non défini par défaut > sélectionnez le modèle** Même touche. Si ce modèle n’est pas appliqué, les mesures sont surestimées.

Tous les packages Analytics actuels peuvent ajouter ce modèle avec Attribution IQ. Si vous n’avez pas accès à Attribution IQ, vous devez vous baser sur les données A4T dans les rapports et analyses.

### API de Target

Les clients ne peuvent pas effectuer d’opérations CRUD sur les activités d’affectation automatique via la version v3 de l’API d’activité A/B d’Adobe I/O.

### Ciblage GEO

Le 10 mai 2020, nous avons mis à jour nos fichiers de fournisseurs GEO, ce qui a introduit quelques incohérences. Par exemple, certaines valeurs contenant des virgules ont été ajoutées ; toutefois, les valeurs des audiences existantes n’avaient pas de virgule. Tous nos serveurs de diffusion n&#39;ont pas été affectés par ce changement. Par conséquent, les audiences qui utilisent ces valeurs n’ont peut-être pas qualifié tous les visiteurs corrects entre le 10 mai et le 22 juillet 2020.

### Offres d’image présentant l’étiquette &quot;Traitement&quot;

Les offres d’image de la page Offres conservent parfois l’étiquette &quot;traitement&quot; pendant plusieurs heures après le téléchargement des images. Dans la plupart des cas, il s’agit d’un problème lié à l’étiquette seulement : les offres d&#39;image peuvent toujours être utilisées dans les activités et être diffusées. Dans certains cas, cependant, une offre d’image peut ne pas être disponible pour l’action Remplacer le contenu > Image. Dans ce cas, vous devez télécharger à nouveau l’offre d’image et vérifier après quelques heures si l’offre d’image est disponible pour remplacement. (TGT-37458)

## Problèmes résolus {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

À mesure que les problèmes connus mentionnés ci-dessus seront résolus, ils seront déplacés dans les sections suivantes et des notes supplémentaires seront ajoutées, le cas échéant.

### Rapports de Cible automatique {#at-metrics}

Un problème a été résolu, affectant le rapports de Cible [!DNL Adobe Target Premium]  automatique des utilisateurs à partir du 15 septembre à 14h30. (HAP) au 6 octobre, de 9 h 25 (PDT). Lors de l’affichage de rapports pour les mesures de conversion affectées (configurées à l’aide de l’option [!UICONTROL Consulté une page]&quot; ou &quot;[!UICONTROL Cliqué sur la mbox]&quot;), les taux de conversion sont incorrectement signalés. Il n&#39;y a pas de problème de diffusion connu pour le moment.

Pour resynchroniser et corriger votre rapports :

1. Copiez et enregistrez les activités de Cible  automatique affectées.
1. Activez les activités nouvellement enregistrées (si les activités affectées étaient actives).
1. Supprimez les activités d’origine (affectées).

(TGT-38522, CSO 20201006007)

### Création de rapports {#conversions-audiences}

Les conversions s’incrémentent actuellement différemment selon l’audience utilisée.

Par exemple, pour le même visiteur, si le nombre de conversions est défini sur incrémenter &quot;Une fois par participant :&quot;

* Audience : &quot;Tous les Visiteurs qualifiés&quot; pour les conversions au niveau de la visite s’incrémentent une seule fois. Il s’agit du comportement attendu.
* Audience : Les nouveaux Visiteurs pour les conversions au niveau des visites s’incrémentent incorrectement à chaque fois, au lieu de s’incrémenter une seule fois. Il ne s&#39;agit pas du comportement attendu.

Si le nombre de conversions est défini sur incrémenter &quot;A chaque impression :&quot;

* Audience : &quot;Tous les Visiteurs qualifiés&quot; pour les conversions au niveau du visiteur s’incrémentent incorrectement une seule fois, au lieu de s’incrémenter à chaque fois. Il ne s&#39;agit pas du comportement attendu.
* Audience : Les &quot;nouveaux Visiteurs&quot; pour les conversions au niveau du visiteur sont incrémentés à chaque fois. Il s’agit du comportement attendu.

Notez que ce problème n&#39;est lié qu&#39;au [!DNL Target] rapports. Il ne s’agit pas d’un problème lors de l’utilisation du rapports [!UICONTROL Analytics pour la Cible] (A4T).

Ce problème a été résolu.

### Pages non chargées dans le compositeur d’expérience visuelle (VEC) ou le compositeur d’expérience amélioré (CEE) lors de l’utilisation de Google Chrome version 80+

Ce problème connu concerne la décision de Google de modifier le comportement par défaut des cookies sans l’attribut MêmeSite à partir de Chrome version 80. Avant la modification de Chrome, tous les cookies par défaut sans l’attribut MêmeSite étaient définis sur &quot;SameSite=None&quot;. Désormais, il est défini sur &quot;SameSite=Lax&quot;, ce qui modifie la manière dont les cookies sont envoyés sur les demandes des GET et des POST. Voir Mises à jour [](https://www.chromium.org/updates/same-site)du même site.

Pour plus d’informations et pour obtenir un correctif, voir &quot;Quel est l’impact des politiques d’application des cookies récemment annoncées dans Google Chrome SameSite sur le compositeur d’expérience visuelle et la CEE ?&quot; in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### Le rendu d’un rapport graphique pour une activité de ciblage automatique échoue lors de l’utilisation d’une expérience personnalisée comme contrôle.

Le rendu du rapport graphique d’une activité de ciblage automatique échoue pour les modes « différentiels » (effet élévateur moyen et effet élévateur quotidien) s’il n’existe aucune donnée (0 visite) dans une expérience. Cette situation peut se produire au début d’une activité si l’expérience de contrôle est définie sur personnalisée. Pour les autres modes (Moyenne cumulée en continue et ciblée, contrôle quotidien et ciblé, et Visites), il fonctionne correctement. Dès qu’il y a des données (visites non nulles), le rapport est rendu comme prévu.

Ce problème a été résolu avec la version Target 19.7.1.

### mbox.js

La bibliothèque mbox.js ne prend pas en charge les langages de modèle côté client, tels que Handlebars et Mustache. La bibliothèque at.js *prend* en charge ces langages.

**Remarque :** La bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. Pour plus d’informations, voir [Migration vers at.js depuis mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Mise en œuvre : création automatique de mbox globales

On the Implementation tab ([!UICONTROL Administration > Implementation]) the [!UICONTROL Global Mbox Auto Create] field will be &quot;false&quot; by default for a newly provisioned tenant.

Lorsque mbox.js est téléchargé pour la première fois après la configuration, le champ [!UICONTROL Création auto. de mbox globale] est défini sur « true » dans le fichier mbox.js téléchargé et sur le serveur principal de [!DNL Target], mais il continue de s’afficher en tant que « false » sur la page [!UICONTROL Mise en œuvre] de l’interface utilisateur jusqu’à ce que la page soit actualisée (une fois la page actualisée, l’état est « true »).

at.js est téléchargé avec `global_mbox_autocreate = false` pour un client nouvellement configuré. Si mbox.js est téléchargé en premier, global\_mbox\_autocreate est défini sur « true » et at.js est également téléchargé avec `global_mbox_autocreate = true`. (TGT-15929)

### Prise en charge des autorisations d’Enterprise dans les API Target {#api}

Les offres de code créées à partir de l’interface utilisateur de Target dans la bibliothèque d’offres peuvent s’afficher dans l’espace de travail par défaut si la liste des offres est extraite à l’aide des API GET. Ce problème sera corrigé lors de la première semaine de mars 2019. Une fois ce correctif mis en place, les offres de code s’affichent dans l’espace de travail approprié lorsqu’elles sont extraites d’API. Ce problème *n’affecte pas* les offres créées à partir d’API. Par exemple, les offres de code créées à partir d’API s’affichent dans l’espace de travail dans lequel elles ont été créées, qu’elles soient récupérées à l’aide d’API GET ou dans l’interface utilisateur de Target.

### Rapports et commandes extrêmes

Du 25 novembre 2019 au 26 avril 2020, un serveur de Cible a rencontré un problème qui a conduit à la comptabilisation de valeurs de commande extrêmes dans les mesures de rapports basées sur les recettes (AOV, RPV). Du 19 décembre 2019 au 23 avril 2020, un autre serveur a connu le même problème. Ce problème n’affectait pas tous les serveurs de Cible ou tous les clients de la Cible.

Vous *n’avez pas* été affecté si :

* L’implémentation de votre Cible utilise différents serveurs.
* Vos rapports n’excluaient pas les commandes extrêmes.
* Vous avez utilisé une mesure de conversion pour mesurer vos activités.
* Vos activités de Cible utilisent Analytics pour la Cible (A4T).
* Vous vous trouvez dans la région Asie-Pacifique (APAC).

Pour déterminer si ce problème a eu un impact sur votre rapports de Cible, contactez le service à la [clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB).

### Recommandations

* L’index de flux de recommandations peut afficher la mention « En attente d’index » si les éléments du flux sont identiques à ceux de l’exécution précédente. L’ingestion du produit pour la diffusion n’est pas affectée. (RECS-6663)

   Ce problème a été résolu avec la version Target 19.4.2.

* Le traitement des flux de Recommandations dure plus longtemps que prévu. (COR-2836)

   Ce problème a été corrigé dans Target 16.10.1.

* L’interface utilisateur des flux de recommandations n’affiche pas le statut d’indexage correct. Les tâches principales fonctionnent normalement, mais l’interface utilisateur ne parvient pas à récupérer et à afficher l’état actuel.

   Ce problème a été résolu dans la version 17.10.1.

### Offres de redirection

Une situation de concurrence sur votre page peut entraîner la comptabilisation des pages vues sur la page originale et la page de redirection. Des mises à jour de l’implémentation d’at.js sont prévues au afin de s’assurer que cette situation de concurrence puisse être évitée.

Ce problème a été résolu dans at.js 1.6.3.

### Groupes d’exclusion

* Lorsque l’élimination automatique des doublons est appliquée après la création de groupes d’exclusion, le décompte du diagramme d’activité peut être incorrect dans l’interface utilisateur.
* Lorsqu’une activité existante dotée d’un groupe d’exclusion est modifiée, les inclusions manuelles risquent de ne pas être correctement reflétées dans l’interface utilisateur.

Ces problèmes ont été résolus.

### API de Target

La version v1 des API d’offre sur Adobe I/O traite toutes les offres créées par le biais de Target pour qu’elles soient dans l’espace de travail par défaut. (TTTEAM-41957)

Ce problème a été résolu.

### at.js

Les mbox ne se déclenchent pas sur les navigateurs Microsoft Explorer 11 après la mise à niveau vers at.js version 1.0 en raison de l’interaction entre at.js et l’API visiteur 2.2.0. Ce problème affecte les versions 0.9.6 et ultérieures d’at.js. (TNT-27600)

Ce problème a été résolu dans la version 2.3.0 d’at.js ou ultérieure.

### Géo  ciblage

La recherche d’une chaîne contenant des caractères spéciaux (comme une espace ou une virgule) ne fonctionne pour l’instant pas lors de la création d’audiences avec le géociblage. Ce problème peut survenir lors de la création d’audiences basées sur des villes, des régions, des pays, etc. Par exemple, lors d’une recherche sur « New York », les résultats retournés peuvent ne pas être valides.

Ce problème a été résolu en novembre 2018.

### at.js

Lors de l’utilisation d’at.js version 1.6.0, Analytics for Target (A4T) entraîne des redirections, sans qualifications d’activité.

Ce problème a été résolu dans la version 1.6.2 d’at.js.

### Espaces de travaildes activités et Suppression des activités avec une API

Les activités de l’espace de travail par défaut, supprimées à l’aide d’une API, s’affichent toujours dans l’interface utilisateur de Target. La solution est de supprimer l’ensemble des activités de l’espace de travail par défaut, à l’aide de l’interface utilisateur de Target. (TGT-31315)

Ce problème a été résolu le 25 octobre 2018

### Rapport au niveau de l’offre Automated Personalization (AP)

Lorsque vous cliquez sur l’expérience ciblée dans le rapport d’activité Automated Personalization (AP) pour voir le rapport au niveau de l’offre, cela vous renvoie zéro résultat, un message d’erreur ou une icône se met à tourner. (TNT-30695)

Ce problème a été résolu le 27 septembre 2018

### Éditeur de code

Lorsque vous rechargez le compositeur d’expérience visuelle à l’étape 1 du processus assisté en trois étapes, alors que vous utilisez l’éditeur de code dans Firefox ou Internet Explorer, le rendu de l’onglet Modifications est incorrect. Cependant, cela n’a aucune répercussion sur la fonctionnalité du compositeur d’expérience visuelle. (TGT-28730)

Ce problème a été résolu dans la version 18.9.1.

### Activité de recommandations utilisant une règle de promotion d’attribut

Lorsque vous modifiez ou copiez une activité de recommandations utilisant une règle de promotion d’attribut, l’erreur « Comprend des champs manquants » s’affiche lorsque vous cliquez sur Enregistrer.

Ce problème a été résolu dans la version 17.8.1.

### Recommandations de sauvegarde

Les recommandations de sauvegarde affichent par erreur la mention « Activé » sur les cartes des éléments récemment consultés dans l’interface utilisateur de Target. (TGT-29308)

Ce problème a été résolu dans la version 18.4.1 de sorte que « Désactivé » s’affiche.

### Activités de ciblage automatique et audiences avec création de rapports

Lorsque le nom d’une audience avec création de rapports utilisé dans une activité de ciblage automatique est modifié, les mises à jour supplémentaires à partir de Target pour cette activité peuvent échouer avec un message d’erreur.

Ce problème a été résolu avec la version Target 18.5.1 (22 mai 2018).

### at.js

L’algorithme d’extraction du domaine de premier niveau devant être utilisé lors de l’enregistrement des cookies a été modifié dans la version 0.9.6 d’at.js. En raison de cette modification, les cookies ne peuvent pas être enregistrés dans des adresses utilisant le protocole IP. La plupart du temps, les adresses IP sont utilisées à des fins de test. Pour contourner le problème, vous pouvez utiliser les entrées DNS, ajuster le fichier d’hôtes sur une zone locale ou utiliser la fonction at.js de targetGlobalSettings() pour insérer un extrait de code qui assurera la prise en charge d’adresses IP.

Ce problème a été résolu dans la version 1.2 d’at.js.

### Autorisations des utilisateurs d’Enterprise pour Target Premium

Dans le cadre de la migration des autorisations d’Enterprise, toute la gestion des utilisateurs Target Premium a été déplacée de l’interface utilisateur d’Adobe Target vers Adobe Admin Console.

À la suite de la migration, deux problèmes potentiels doivent être pris en compte :

* Les utilisateurs non administrateurs ont reçu un message électronique indiquant qu’ils ont désormais accès à Adobe Target. Cela indique que la migration est terminée pour votre organisation. Le message électronique peut être ignoré.
* Suite à la migration, il a été signalé que certains utilisateurs précédemment désactivés réapparaissent dans Adobe Admin Console. Cela pourrait poser problème à votre organisation si des utilisateurs désactivés dans Adobe Admin Console figuraient toujours dans la liste des utilisateurs de Target avant la migration. Il est recommandé aux administrateurs de vérifier la liste des utilisateurs dans Admin Console pour valider l’accès.

Ce problème a été corrigé le 30 août 2017.

### Création de l’activité

Un problème lié à la version 17.6.2 peut avoir affecté les activités créées et/ou mises à jour entre le 22 juin 2017 et le 29 juin 2017. Les activités comportant les éléments suivants ont été affectées :

* Toute expérience réorganisée dans le ciblage d’expérience (XT) peut être restaurée à l’ordre d’origine.
* Toutes les règles de segment locales à l’activité (non enregistrées dans une audience) peuvent avoir été perdues : audiences combinées, perfectionnements des emplacements et règles de mesure de succès.

Aucune autre activité n’a été affectée.

**Important :** Ce problème ne se résout pas automatiquement. Vous devez réenregistrer toute activité affectée pour résoudre le problème.

Ce problème a été corrigé le 29 juin 2017.

### Compositeur d’expérience d’après les formulaires

Les problèmes connus suivants ont été signalés lors de l’utilisation du compositeur d’expérience d’après les formulaires :

* Si vous utilisez le compositeur d’expérience d’après les formulaires avec une mbox autre que la mbox globale créée automatiquement (target-global-mbox), puis choisissez une mesure d’engagement comme mesure de succès, la mesure s’incrémente seulement sur les pages où la mbox est utilisée dans l’activité. Si, par exemple, la mbox est homepage\_mbox, la mesure Pages par visite correspond au nombre d’accès à homepage_mbox durant cette visite. (TGT-22789)
* Une exception JavaScript est générée lorsque vous supprimez une expérience d’une activité de ciblage d’expérience (XT) lors de l’utilisation du compositeur d’expérience d’après les formulaires à l’étape 1 du processus. (TGT-24366)

Le premier problème a été corrigé dans la version 17.3.1 de Target (mars 2017).

Le deuxième problème a été corrigé dans la version 17.6.1 de Target (juin 2017).

### at.js

Depuis la version 17.4.1 de Target (27 avril 2017), l’utilisation de l’action d’insertion d’une image dans le compositeur d’expérience visuelle empêche la diffusion du contenu de l’offre lors de l’utilisation de la bibliothèque at.js.

Un correctif relatif à ce problème a été ajouté à la version 0.9.7 d’at.js publiée le 22 mai 2017.

### Création de rapports : activités A/B et de ciblage d’expérience (XT)

Entre le 27 avril à 21h00 et le 5 mai à 6h00, heure de la côte Ouest des États-Unis, les activités A/B et XT créées ou modifiées avec des mesures utilisant l’action de conversion « A affiché une page » (qui n’étaient pas basées sur d’autres mesures) peuvent avoir enregistré des conversions de manière incorrecte. Ce problème est maintenant résolu. Cependant, la création de rapports relative à l’action de conversion « A affiché une page » pour ces activités pendant la période touchée peut ne pas être exacte et, malheureusement, ne peut pas être corrigée. Il est recommandé que, pour toute décision basée sur des actions de conversion « A affiché une page » pour ces activités, vous ne teniez compte que des données enregistrées avant ou après la période concernée.

Les données de création de rapports pour d’autres mesures peuvent toujours être utilisées car elles n’ont pas été affectées.

Ce problème a été corrigé dans Target 17.4.3.

### Offres : activités A/B et de ciblage d’expérience (XT)

La diffusion et la prévisualisation ont été affectées pour les offres des activités A/B et XT comportant au moins deux expériences et qui ont été créées ou modifiées à l’aide du compositeur d’expérience d’après les formulaires entre le vendredi 28 avril (21h, heure de la côte Ouest des États-Unis) et le lundi 1er mai (21h15, heure de la côte Ouest des États-Unis). Seules les offres comportant du contenu par défaut étaient affichées.

Ce problème a été corrigé dans Target 17.4.3.

### at.js

Les actions suivantes ont empêché la diffusion de l’offre lors de l’utilisation du compositeur d’expérience visuelle et d’at.js : déplacer et réorganiser.

Un correctif pour ce problème a été inclus dans la version 0.9.6 d’at.js.

### Rapports

La possibilité d’afficher plusieurs mesures dans un rapport, y compris dans la version de Target 17.3.1 (30 mars 2017) a été supprimée en raison d’un comportement inattendu. Cette fonction sera de nouveau disponible dans une prochaine version.

La possibilité d’afficher plusieurs mesures dans un rapport a été incluse dans la version 17.4.1 de Target (27 avril 2017).

### Offres

Les images supprimées de la bibliothèque d’offres (Offres > Offres d’images) restent visibles dans l’interface utilisateur. Dans une prochaine version, ces images supprimées ne s’afficheront plus. Dans l’intervalle, les images supprimées s’affichent dans l’interface utilisateur, mais sont identifiées comme supprimées. (TGT-23793)

Ce problème a été corrigé dans la version 17.4.1 de Target (27 avril 2017).

### Offres de redirection

Pour le critère Récemment consultés, les règles dynamiques basées sur les entités ne génèrent aucune recommandation si le paramètre entity.id n’est pas transmis dans la requête mbox. (RECS-6241)

Ce problème a été corrigé après la diffusion de Recommandations (22 mars 2018). Après la diffusion de Recommandations, Target ignore les règles dynamiques basées sur l’entité si le paramètre entity.id n’est pas transmis dans la requête mbox.

### at.js

Lorsque les utilisateurs essaient de télécharger at.js depuis la page « Détails de mise en œuvre » après avoir mis à jour les paramètres d’at.js, c’est mbox.js qui se télécharge, pas at.js. (TGT-23069)

Ce problème a été corrigé dans la version 17.3.1 de Target (30 mars 2017).

### Règles d’exclusion globale

Il faut compter de 10 à 20 minutes pour que les règles d’exclusion globale se propagent à la périphérie pour Recommendations Premium. (RECS-5270)

Corrigé dans la version 17.2.2.0 de Recommandations (6 mars 2017).

### Rapports Analytics for Target (A4T)

Les rapports ne sont pas mis à jour quand la mesure de création de rapports est activée. Il s’agit d’un problème de l’interface utilisateur. Ceci n’a aucun impact sur la collecte ou la distribution de données de création de rapports. (TGT-22970)

Ce problème a été corrigé dans la version 17.2.2.0 de Target (24 février 2017).

### Rapports CSV

Les rapports téléchargés ne tiennent pas compte du paramètre Exclure les commandes extrêmes. (TGT-21871)

Ce problème a été corrigé dans Target 17.2.1.0.
