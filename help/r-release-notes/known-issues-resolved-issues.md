---
keywords: problèmes connus;problèmes résolus;notes de mise à jour;bogues;problèmes;correctifs
description: Obtenez des informations sur les problèmes connus d’Adobe Target, y compris des solutions pour y remédier. Une fois les problèmes résolus, ils sont déplacés dans la section Résolus.
title: Où puis-je trouver des informations sur les problèmes connus et les problèmes résolus ?
feature: Release Notes
exl-id: 6eb854f7-ed46-4673-afeb-0b44970598cd
source-git-commit: a7854c30ac1ed5212a0f56f188bc83aa564814dc
workflow-type: ht
source-wordcount: '4738'
ht-degree: 100%

---

# Problèmes connus et problèmes résolus

Informations sur les problèmes connus d’[!DNL Adobe Target]. Inclut également des informations sur les problèmes résolus.

>[!NOTE]
>
>Les numéros entre parenthèses sont réservés à une utilisation interne par Adobe.

## Problèmes connus {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

Les sections suivantes répertorient les problèmes connus de [!DNL Target] :

### Compositeur d’expérience visuelle (VEC) chargeant des sites web avec Service Workers

Il existe actuellement certaines limitations lorsqu’on essaie d’utiliser le VEC (compositeur d’expérience visuelle) pour ouvrir un site web qui utilise [Service Workers](https://developer.mozilla.org/fr/docs/Web/API/Service_Worker_API){target=_blank} (SW).

Un SW est une technologie web qui peut être utilisée pour intercepter les requêtes du domaine sur lequel il est installé par une page web. Le SW survit à la visite de la page et s’active lors de visites ultérieures. Le SW décide quelles requêtes passent et lesquelles sont interceptées puis diffusées à partir d’un cache.

Le SW peut contrôler le caching. Il peut mettre en cache la page web elle-même, les ressources statiques telles que les requêtes JS, CSS, IMG, AJAX, leur contenu et leurs en-têtes de réponse, y compris les éléments que notre [extension d’assistance du VEC de Target](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) tente de supprimer, comme X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) ou Set-Cookie.

Malheureusement, les API des extensions Chrome qui interceptent les requêtes web ne reçoivent pas les requêtes qui ont été interceptées et traitées par un SW. Par conséquent, l’extension ne peut pas corriger les en-têtes et les cookies si la requête de page web a été diffusée à partir d’un cache par un SW, car la page web ne se charge pas dans le VEC en raison des en-têtes X-Frame-Options ou CSP qui ont également été mis en cache.

Pour contourner ce problème, vous pouvez désactiver Service Workers dans l’onglet Chrome Developer Tools > Application, puis activer la case à cocher « Contourner pour le réseau » sous la section Service Workers. (KB-2006)

### Distribution du trafic des activités d’affectation automatique à l’aide d’A4T {#aa-a4t}

Dans certains cas, la distribution du trafic des activités d’[!UICONTROL Affectation automatique] à l’aide d’[!UICONTROL Analytics for Target] (A4T) peut différer de ce qui doit se produire en fonction du taux de conversion signalé de chaque expérience. Cela se produit plus souvent pour les activités qui présentent une forte proportion de trafic lié à des visiteurs récurrents. Les clients concernés seront informés des activités affectées.

Jusqu’à ce que ce problème soit résolu, utilisez l’[!UICONTROL Affectation automatique] avec le compte rendu des performances [!DNL Target] standard. Vous pouvez également utiliser des tests A/B standard avec le compte rendu des performances [!DNL Analytics] comme alternative à l’[!UICONTROL Affectation automatique] avec le compte rendu des performances [!DNL Analytics]. (TOP-131)

### Mesures Analytics for Adobe Target (A4T) pour les activités d’affectation automatique et de ciblage automatique.

L’interface utilisateur de [!DNL Target] permet aux utilisateurs de sélectionner des mesures d’engagement et de chiffres d’affaires non prises en charge en tant que mesure d’objectif principale pour l’optimisation des activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique]. Les mesures de conversion sont prises en charge. Les mesures d’engagement et de chiffre d’affaires ne sont *pas* prises en charge. Si vous sélectionnez des mesures d’engagement ou d’objectif de chiffre d’affaires, aucun modèle d’optimisation n’est généré.

Pour obtenir une liste des mesures d’objectif prises et non prises en charge, consultez [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). (TNT-38409)

### Le compositeur d’expérience amélioré (EEC) ne prend pas en charge les requêtes PUT.

Un problème avec le compositeur d’expérience amélioré l’empêche actuellement de prendre en charge les requêtes PUT et génère une erreur de temporisation 504. (TGT-41493)

### Les noms des segments [!DNL Adobe Experience Platform] ne sʼaffichent pas dans le rapport [!UICONTROL Attributs importants].

Les noms des segments [!DNL Adobe Experience Platform] ne sʼaffichent pas dans le rapport [!UICONTROL Attributs importants] pour les activités [!UICONTROL Automated Personalization] (AP) et de [!UICONTROL ciblage automatique] (Auto-Target, AT). (TOP-3813)

### Lʼarchivage des activités de [!UICONTROL ciblage automatique] peut entraîner des problèmes de synchronisation.

La tentative dʼarchivage des activités de [!UICONTROL ciblage automatique] inactives peut entraîner des problèmes de synchronisation. Tant que ce problème nʼest pas résolu, nʼarchivez pas les activités de [!UICONTROL ciblage automatique]. Laissez-les à lʼétat [!UICONTROL Inactif]. (TGT-40885)

### Diffusion de page {#page-delivery}

Si vous ajoutez une règle de modèle, telle que l’URL contient (/checkout, /cart) dans la [diffusion de page](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md), des espaces supplémentaires sont prédéfinis dans vos règles. Ces espaces supplémentaires sont cosmétiques et n’affectent pas la création de définitions d’audiences ni la diffusion d’offres. (TGT-35920)

### Liens d’aperçu de l’AQ

Les liens d’aperçu de l’AQ des activités pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. Réessayez les liens d’aperçu. Archivez les activités enregistrées qui ne sont plus utilisées activement pour empêcher ce problème de se produire. (TNT-37294)

### Mode AQ pour les activités Recommendations

Un problème connu empêche l’aperçu si le critère utilisé dans l’activité est basé sur un élément ou une catégorie. (TNT-37455)

### Offres de redirection {#redirect}

Les problèmes suivants sont des problèmes connus des offres de redirection :

* Un nombre limité de clients ont signalé des degrés de variation de trafic supérieurs lors de l’utilisation d’offres de redirection dans les activités configurées avec Analytics for Target (A4T).
* Dans les mises en œuvre d’at.js, les activités de redirection peuvent provoquer l’entrée dans une boucle de l’URL d’aperçu (la distribution de l’offre se répète). Vous pouvez utiliser le [mode Assurance qualité](/help/c-activities/c-activity-qa/activity-qa.md) au lieu d’effectuer l’aperçu et la vérification de la qualité. Ce problème n’a aucun impact sur la distribution réelle de l’offre. (TGT-23019)

### Annulation du chargement d’une page dans le compositeur d’expérience visuelle (VEC) {#cancel}

* Le problème connu suivant existe actuellement lors de l’annulation du chargement d’une activité de [!UICONTROL test A/B] ou de [!UICONTROL ciblage d’expérience] dans le VEC qui contient une URL de redirection.

   Dans la première étape du workflow guidé, lorsque vous annulez le chargement de la page, le panneau [!UICONTROL Modifications] du VEC s’affiche et le modèle de redirection vers une URL est appliqué à l’expérience (par exemple, « Expérience B »). Lorsque vous passez aux étapes deux ou trois puis que vous revenez à la première étape, la situation suivante se produit.

   Sur « Expérience B », par défaut, le modèle de chargement de site web annulé est rendu et le panneau [!UICONTROL Modifications] est accessible, ce qui ne devrait pas être le cas, car cette expérience a été appliquée à un modèle de redirection vers une URL. Le modèle de redirection vers l’URL doit s’afficher.

   Pour afficher l’état correct de l’expérience dans le VEC :

   Si vous passez à une autre expérience, puis revenez à « Expérience B », [!DNL Target] affiche le modèle de redirection vers l’URL appliqué à cette expérience et le panneau [!UICONTROL Modifications] n’est pas accessible. (TGT-32138)

* Pour les sites web d’applications monopages, l’annulation du chargement ne permet pas de modifier les actions dans le panneau [!UICONTROL Modifications].

### Recommendations

Les problèmes suivants sont des problèmes connus des activités [!UICONTROL Recommendations] :

* Lors de la copie d’une activité [!UICONTROL Recommendations] avec une promotion principale, toute modification de l’activité dupliquée affecte également l’activité originale, et inversement. (TGT-39155)

   Solutions temporaires :

   * Désactiver les promotions d’activité
   * Dupliquer l’activité
   * Activer à nouveau les promotions dans chaque activité

* Lorsque [!DNL Target] renvoie une offre JSON avec getOffer(), il la renvoie avec le type JSON. Cependant, si vous renvoyez une conception Recommandations JSON, elle est renvoyée avec le type HTML.
* Les entités sont correctement expirées après 60 jours de non réception des mises à jour par flux ou API ; toutefois, les entités expirées ne sont pas supprimées de l’index de recherche de catalogue après expiration. (IRI-857)
* Les incrustations « Informations d’utilisation » pour les critères et les conceptions ne reflètent pas leur utilisation dans les activités A/B et de ciblage d’expérience. (TGT-34331)
* Les offres Recommendations dans les activités A/B et de ciblage d’expérience ne présentent pas de prévisualisation visuelle de la barre d’état de Recommendations. (TGT-33426)
* Les collections, exclusions, critères et conceptions créés par le biais de l’API ne sont pas visibles dans l’interface utilisateur de Target et ne peuvent être modifiés que par le biais de l’API. De même, si vous créez l’un de ces éléments dans l’interface utilisateur de Target et que vous le modifiez ultérieurement par le biais de l’API, ces modifications ne sont pas répercutées dans l’interface utilisateur de Target. Les éléments modifiés par le biais de l’API doivent continuer à l’être par ce même biais afin d’éviter toute perte de modifications. (TGT-35777)
* Les activités Recommendations créées par l’intermédiaire de l’API peuvent être visualisées dans l’interface utilisateur, mais ne peuvent être modifiées qu’au moyen de l’API.
* L’état du flux Critères personnalisés affiché dans la vue Liste (carte) de critères est actualisé toutes les dix minutes et peut parfois être obsolète de plus de dix minutes dans de rares circonstances. L’état affiché dans la vue Modification des Critères personnalisés est récupéré en temps réel et est constamment à jour. (TGT-35896, TGT-36173)
* Les cartes de critère et de conception n’indiquent pas le nombre correct d’activités dans lesquelles ils sont utilisés. Si le critère ou la conception est utilisé dans une activité A/B, la carte peut indiquer de manière erronée qu’ils ne sont pas utilisés, alors qu’ils le sont bien dans l’activité. (TGT-36621, TGT-37217)

### Activités de test multivarié (MVT)

Dans une activité de test multivarié, le gagnant affiché dans le tableau et dans le graphique n’est pas le même lors de la vérification des mesures. Cette situation se produit lorsqu’un utilisateur bascule de la vue récapitulative à la vue graphique, puis revient à la vue récapitulative, modifie une mesure, puis bascule en vue graphique. Lorsque ce problème se produit, la vue récapitulative affiche toujours le gagnant correct. Si l’utilisateur ne passe jamais à la vue graphique entre les vues récapitulatives, la vue graphique affiche le gagnant correct.

### at.js {#atjs}

Les problèmes suivants sont des problèmes connus d’at.js :

* En utilisant les versions d’at.js antérieures à la version 2.2.0, le suivi des clics ne signale pas les conversions dans Analytics for Target (A4T) si le code Adobe Analytics n’est pas présent sur les éléments de page (tels que les boutons). Un correctif a été introduit pour ce problème dans at.js 2.2.0. [Veuillez effectuer la mise à niveau vers la dernière version d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) si vous rencontrez ce problème.
* Si vous créez une expérience sans modification à l’aide d’at.js 2.1.1 ou d’une version antérieure (par exemple, une expérience par défaut), elle peut ne pas être comptabilisée dans les rapports, Analytics for Target (A4T), Adobe Analytics ou Google Analytics. En outre, le module ttMeta risque de ne pas fonctionner correctement.

   Pour pallier ce problème, utilisez un espace blanc dans le contenu de l’expérience. (TNT-33366)

   >[!NOTE]
   >
   >Un correctif pour ce problème a été inclus dans at.js 2.2.0. Effectuez la mise à niveau vers la [dernière version ou at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) ou utilisez la solution mentionnée ci-dessus uniquement pour les versions d’at.js antérieures à la version 2.2.0.

* Lorsqu’une page est chargée dans le compositeur d’expérience visuelle, Target doit déterminer si le paramètre de mbox globale est activé ou désactivé et si entityID ou categoryID est présent à l’emplacement où l’utilisateur tente d’appliquer la recommandation dans le compositeur d’expérience visuelle. Sur la base de ces informations, la liste des critères est filtrée. La liste par défaut comporte des algorithmes filtrés, mais la [case à cocher Compatible](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) permet d’afficher la liste complète des algorithmes.

   Lorsque vous utilisez at.js, la case à cocher Compatible est masquée. Vous ne pouvez donc pas voir les algorithmes incompatibles.

   Ce problème s’applique uniquement aux activités Recommendations qui utilisent le compositeur d’expérience visuelle.

   **Solution** : désactivez l’option [!UICONTROL Filtrer les critères incompatibles] dans [!UICONTROL Recommendations > Paramètres]. Après avoir désactivé ce paramètre, tous les critères (compatibles et incompatibles) s’affichent dans le sélecteur de critères. (TGT-25949)

* Les mbox ne se déclenchent pas sur les navigateurs Microsoft Explorer 11 après la mise à niveau vers at.js version 1.0 en raison de l’interaction entre at.js et l’API visiteur 2.2.0. Ce problème affecte les versions 0.9.6 et ultérieures d’at.js. (TNT-27600)
* at.js peut ne pas fonctionner avec les applications Cordova/Hybrid, puisqu’elles ne prennent pour l’instant pas en charge les cookies propriétaires. (TNT-26166)

   **Solution** : configurez at.js avec l’option « x-only » activée et transmettez `mboxThirdPartyId` dans les appels pour la gestion des utilisateurs.

### Mesures de succès

Les mesures de succès avec l’option avancée « Comment sera incrémenté le décompte ? » définie sur « À chaque impression » ou « À chaque impression (actualisations de page exclues) » ne peuvent pas être utilisées en tant que mesure de succès dont dépend une autre mesure.

Lorsqu’une mesure de succès est définie pour incrémenter à chaque impression, Target comptabilise à nouveau le visiteur à chaque fois qu’il visite cette mesure de succès. Target remet ensuite la mesure de succès « appartenance » à 0 pour pouvoir effectuer le décompte à nouveau à la prochaine impression. Par conséquent, si une autre mesure nécessite que cette mesure ait été vue au préalable, Target ne reconnait jamais que l’utilisateur a vu la première mesure.

### Analytics for [!DNL Target] (A4T)

Lors de l’utilisation des impressions et des conversions d’activité de Target dans Analysis Workspace, appliquez le modèle Attribution IQ « Touche identique » aux mesures afin d’assurer un comptage précis. Pour appliquer un [modèle d’attribution autre que celui par défaut](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/column-row-settings/column-settings.html?lang=fr#cja-workspace), cliquez avec le bouton droit de la souris sur la mesure pour **modifier les paramètres de colonne, activez l’option Utiliser un modèle d’attribution autre que celui par défaut, puis sélectionnez le modèle Touche identique**. Si ce modèle n’est pas appliqué, les mesures sont surestimées.

Tous les packages Analytics actuels peuvent ajouter ce modèle avec Attribution IQ. Si vous n’avez pas accès à Attribution IQ, utilisez les données d’A4T dans Reports &amp; Analytics.

### API de Target

Les clients ne peuvent pas effectuer d’opérations CRUD sur les activités d’affectation automatique via la version v3 de l’API d’activité A/B d’Adobe I/O.

### Géociblage

Le 10 mai 2020, Adobe a mis à jour les fichiers de géociblage, ce qui a introduit quelques incohérences. Par exemple, certaines valeurs contenant des virgules ont été ajoutées alors que les valeurs des audiences existantes n’avaient pas de virgule. Ce changement n’a pas affecté tous les serveurs de diffusion d’Adobe. Par conséquent, les audiences qui utilisent ces valeurs pourraient ne pas avoir qualifié tous les bons visiteurs entre le 10 mai et le 22 juillet 2020.

### Reporting : données incohérentes dans le rapport .csv téléchargeable en comparaison avec le rapport affiché dans l’interface utilisateur de [!DNL Target]. {#csv}

Les rapports générés pour le téléchargement de fichiers .csv sont incohérents si l’activité utilise plusieurs mesures. Le rapport téléchargeable n’est généré qu’en fonction des paramètres du rapport et prend en compte la même valeur pour toute autre mesure utilisée.

La source de vérité est toujours le rapport affiché dans l’interface utilisateur de [!DNL Target].

## Problèmes résolus {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

Au fur et à mesure que les problèmes connus ci-dessus sont résolus, ils sont déplacés vers les sections suivantes. Si nécessaire, des notes supplémentaires sont ajoutées.

### Offres d’image présentant l’étiquette « Traitement »

Les offres d’image de la page Offres conservent parfois l’étiquette « Traitement » pendant plusieurs heures après le transfert des images. Dans la plupart des cas, il s’agit d’un problème lié seulement à l’étiquette : les offres d’image peuvent toujours être utilisées dans les activités et être diffusées. (MCUI-10264, TGT-37458)

Ce problème a été résolu pour la version Target Standard/Premium 20.10.1.

### Reporting Analytics for Adobe Target (A4T)

Les problèmes suivants liés à A4T ont été résolus :

* Un problème qui affectait les activités A4T utilisant une mesure d’objectif [!DNL Analytics], en raison duquel les rapports A4T affichaient un fractionnement de trafic inattendu ou des conversions artificiellement gonflées.

   Ce problème affectait la génération de rapports A4T dans les cas suivants :

   * L’activité a été créée ou enregistrée entre le 15 septembre et le 5 novembre 2020 (4 h PST), et
   * L’activité avait une mesure [!DNL Analytics] sélectionnée en tant que mesure d’objectif.

   [!DNL Target] répartit correctement le trafic pendant cette période. Cependant, une répartition 50/50 dans la configuration de l’activité peut apparaître, par exemple, comme une répartition 90/10 dans les rapports A4T.

   Pour les activités affectées, la répartition correcte du trafic est visible pour les nouveaux visiteurs de l’activité après le 5 novembre (4 h PST). Les nouvelles activités créées ou enregistrées après cette date rapportent correctement la répartition du trafic.

* Un problème qui affectait les activités A4T utilisant une mesure d’objectif [!DNL Target], en raison duquel les rapports A4T rapportaient des conversions faibles ou inexistantes.

   >[!NOTE]
   >
   >Ce problème affectait uniquement les rapports A4T. Il n’affectait pas la diffusion des activités.

   Ce problème affectait la génération de rapports A4T dans les cas suivants :

   * L’activité A4T était active entre le 22 septembre et le 11 novembre 2020 (14 h 30 PST), et
   * L’activité avait une mesure [!DNL Target] sélectionnée en tant que mesure d’objectif, et
   * Lorsqu’un visiteur atteint l’événement d’objectif de l’activité (par exemple [!UICONTROL A cliqué sur un élément]), une activité de priorité inférieure hors A4T correspondait également à l’événement de conversion. Cela peut se produire si l’activité hors A4T a été configurée avec la même mesure que l’activité A4T ou si elle a été configurée avec la mesure « n’importe quelle mbox ».

   Ce problème affectait les rapports des activités A4T qui étaient actives entre le 22 septembre et le 11 novembre 2020 (14 h 30 PST). Les rapports des activités A4T affectées affichent correctement les conversions en dehors de cette plage de dates. Les rapports des activités hors A4T n’ont pas été affectés.

Si vous avez d’autres questions, contactez votre responsable du service client ou [l’assistance clientèle d’Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). (CSO 20201110016)

### Rapports de ciblage automatique {#at-metrics}

Résolution d’un problème qui affectait les rapports de [!UICONTROL ciblage automatique] des utilisateurs d’[!DNL Adobe Target Premium] entre le 15 septembre à 14 h 30 (PDT) et le 6 octobre à 9 h 25 (PDT). Lors de l’affichage des rapports sur les mesures de conversion affectées (configurées à l’aide de l’option « [!UICONTROL A affiché une page] » ou « [!UICONTROL A cliqué sur mbox] »), les taux de conversion signalés sont incorrects. Aucun problème de diffusion n’est connu pour le moment.

Pour resynchroniser et corriger vos rapports :

1. Copiez et enregistrez les activités de [!UICONTROL ciblage automatique] affectées.
1. Activez les activités nouvellement enregistrées (si les activités affectées étaient actives).
1. Supprimez les activités (affectées) d’origine.

(TGT-38522, CSO 20201006007)

### Création de rapports {#conversions-audiences}

Les conversions s’incrémentent actuellement différemment selon l’audience utilisée.

Par exemple, pour le même visiteur, si le nombre de conversions est défini sur incrémenter « Une fois par participant : »

* Audience : la mesure « Tous les visiteurs qualifiés » pour les conversions au niveau de la visite s’incrémente une seule fois. Il s’agit du comportement attendu.
* Audience : la mesure « Nouveaux visiteurs » pour les conversions au niveau de la visite s’incrémente incorrectement, à chaque fois, au lieu de s’incrémenter une seule fois. Il ne s’agit pas du comportement attendu.

Si le nombre de conversions est défini sur incrémenter « À chaque impression : »

* Audience : la mesure « Tous les visiteurs qualifiés » pour les conversions au niveau du visiteur s’incrémente incorrectement une seule fois, au lieu de s’incrémenter à chaque fois. Il ne s’agit pas du comportement attendu.
* Audience : la mesure « Nouveaux visiteurs » pour les conversions au niveau du visiteur s’incrémente à chaque fois. Il s’agit du comportement attendu.

Notez que ce problème n’est lié qu’aux rapports [!DNL Target]. Le problème ne touche pas les rapports [!UICONTROL Analytics for Target] (A4T).

Ce problème a été résolu.

### Pages non chargées dans le compositeur d’expérience visuelle (VEC) ou le compositeur d’expérience avancé (CEE) lors de l’utilisation de Google Chrome version 80 ou ultérieure

Ce problème connu concerne la décision de Google de modifier le comportement par défaut des cookies sans l’attribut SameSite à partir de la version 80 de Chrome. Avant la modification de Chrome, tous les cookies par défaut sans l’attribut SameSite étaient définis sur « SameSite=None ». Désormais, ils sont définis sur « SameSite=Lax », ce qui modifie la manière dont les cookies sont envoyés sur les requêtes GET et POST. Consultez [Mises à jour SameSite](https://www.chromium.org/updates/same-site).

Pour plus d’informations et pour obtenir un correctif, consultez « Comment les politiques d’application des cookies SameSite récemment annoncées par Google Chrome influencent-elles le VEC et le CEE ? » dans [Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### Le rendu d’un rapport graphique pour une activité de ciblage automatique échoue lors de l’utilisation d’une expérience personnalisée comme contrôle.

Le rendu du rapport graphique d’une activité de ciblage automatique échoue pour les modes « différentiels » (effet élévateur moyen et effet élévateur quotidien) s’il n’existe aucune donnée (0 visite) dans une expérience. Cette situation peut se produire au début d’une activité si l’expérience de contrôle est définie sur personnalisée. Pour les autres modes (Moyenne cumulée en continue et ciblée, contrôle quotidien et ciblé, et Visites), il fonctionne correctement. Dès qu’il y a des données (visites non nulles), le rapport est rendu comme prévu.

Ce problème a été résolu avec la version Target 19.7.1.

### Implémentation : création automatique de mbox globales

Dans l’onglet Implémentation ([!UICONTROL Administration > Implémentation]), le champ [!UICONTROL Création automatique de mbox globale] a par défaut la valeur « false » pour un client nouvellement configuré.

Lorsqu’at.js est téléchargé pour la première fois après la configuration, le champ [!UICONTROL Création automatique de mbox globale] est défini sur « true » dans le fichier at.js téléchargé et sur le serveur principal de [!DNL Target], mais il continue de s’afficher en tant que « false » sur la page [!UICONTROL Implémentation] de l’interface utilisateur jusqu’à ce que la page soit actualisée (une fois la page actualisée, l’état est défini sur « true »).

at.js est téléchargé avec `global_mbox_autocreate = false` pour un client nouvellement configuré. Si mbox.js (aujourd’hui obsolète) est téléchargé en premier, global\_mbox\_autocreate est défini sur « true » et at.js est également téléchargé avec `global_mbox_autocreate = true`. (TGT-15929)

### Prise en charge des autorisations Enterprise dans les API [!DNL Target] {#api}

Les offres de code créées à partir de l’interface utilisateur de Target dans la bibliothèque d’offres peuvent s’afficher dans l’espace de travail par défaut si la liste des offres est extraite à l’aide des API GET. Ce problème sera corrigé lors de la première semaine de mars 2019. Une fois ce correctif mis en place, les offres de code s’affichent dans l’espace de travail approprié lorsqu’elles sont extraites d’API. Ce problème *n’affecte pas* les offres créées à partir d’API. Par exemple, les offres de code créées à partir d’API s’affichent dans l’espace de travail dans lequel elles ont été créées, qu’elles soient récupérées à l’aide d’API GET ou dans l’interface utilisateur de Target.

### Rapports et commandes extrêmes

Du 25 novembre 2019 au 26 avril 2020, un serveur Target a rencontré un problème qui a conduit à la comptabilisation de valeurs de commande extrêmes dans les mesures de rapports basées sur le chiffre d’affaires (AOV, RPV). Du 19 décembre 2019 au 23 avril 2020, un autre serveur a rencontré le même problème. Ce problème n’a pas affecté tous les serveurs ni tous les clients Target.

Vous n’avez *pas* été affecté si :

* Votre implémentation Target utilise différents serveurs.
* Vos rapports n’ont pas exclu les commandes extrêmes.
* Vous avez utilisé une mesure de conversion pour mesurer vos activités.
* Vos activités Target utilisent Analytics for Target (A4T).
* Vous vous trouvez dans la région Asie-Pacifique (APAC).

Pour déterminer si ce problème a eu un effet sur vos rapports Target, contactez l’[assistance clientèle](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB).

### Recommendations

* L’index de flux de Recommendations peut afficher la mention « En attente d’index » si les éléments du flux sont identiques à ceux de l’exécution précédente. L’ingestion du produit pour la diffusion n’est pas affectée. (RECS-6663)

   Ce problème a été résolu avec la version Target 19.4.2.

* Le traitement des flux de recommandations dure plus longtemps que prévu. (COR-2836)

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

### at.js {#at-js-2}

Les mbox ne se déclenchent pas sur les navigateurs Microsoft Explorer 11 après la mise à niveau vers at.js version 1.0 en raison de l’interaction entre at.js et l’API visiteur 2.2.0. Ce problème affecte les versions 0.9.6 et ultérieures d’at.js. (TNT-27600)

Ce problème a été résolu dans la version 2.3.0 ou ultérieure de l’API.

### Géo  ciblage

La recherche d’une chaîne contenant des caractères spéciaux (comme une espace ou une virgule) ne fonctionne pour l’instant pas lors de la création d’audiences avec le géociblage. Ce problème peut survenir lors de la création d’audiences basées sur des villes, des régions, des pays, etc. Par exemple, lors d’une recherche sur « New York », les résultats retournés peuvent ne pas être valides.

Ce problème a été résolu en novembre 2018.

### at.js {#at-js-3}

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

### Activité Recommendations utilisant une règle de promotion d’attribut

Lorsque vous modifiez ou copiez une activité Recommendations utilisant une règle de promotion d’attribut, l’erreur « Comprend des champs manquants » s’affiche lorsque vous cliquez sur Enregistrer.

Ce problème a été résolu dans la version 17.8.1.

### Recommandations de sauvegarde

Les recommandations de sauvegarde affichent par erreur la mention « Activé » sur les cartes des éléments récemment consultés dans l’interface utilisateur de Target. (TGT-29308)

Ce problème a été résolu dans la version 18.4.1 de sorte que « Désactivé » s’affiche.

### Activités de ciblage automatique et audiences avec création de rapports

Lorsque le nom d’une audience avec création de rapports utilisé dans une activité de ciblage automatique est modifié, les mises à jour supplémentaires à partir de Target pour cette activité peuvent échouer avec un message d’erreur.

Ce problème a été résolu avec la version Target 18.5.1 (22 mai 2018).

### at.js {#at-js-4}

L’algorithme d’extraction du domaine de premier niveau devant être utilisé lors de l’enregistrement des cookies a été modifié dans la version 0.9.6 d’at.js. En raison de cette modification, les cookies ne peuvent pas être enregistrés dans des adresses utilisant le protocole IP. La plupart du temps, les adresses IP sont utilisées à des fins de test. Pour contourner le problème, vous pouvez utiliser les entrées DNS, ajuster le fichier d’hôtes sur une zone locale ou utiliser la fonction at.js de targetGlobalSettings() pour insérer un extrait de code qui assurera la prise en charge d’adresses IP.

Ce problème a été résolu dans la version 1.2 d’at.js.

### Autorisations des utilisateurs Enterprise pour [!DNL Target] Premium

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

### at.js {#at-js-5}

Depuis la version 17.4.1 de Target (27 avril 2017), l’utilisation de l’action d’insertion d’une image dans le compositeur d’expérience visuelle empêche la diffusion du contenu de l’offre lors de l’utilisation de la bibliothèque at.js.

Un correctif relatif à ce problème a été ajouté à la version 0.9.7 d’at.js publiée le 22 mai 2017.

### Création de rapports : activités A/B et de ciblage d’expérience (XT)

Entre le 27 avril à 21h00 et le 5 mai à 6h00, heure de la côte Ouest des États-Unis, les activités A/B et XT créées ou modifiées avec des mesures utilisant l’action de conversion « A affiché une page » (qui n’étaient pas basées sur d’autres mesures) peuvent avoir enregistré des conversions de manière incorrecte. Ce problème est maintenant résolu. Cependant, la création de rapports relative à l’action de conversion « A affiché une page » pour ces activités pendant la période touchée peut ne pas être exacte et, malheureusement, ne peut pas être corrigée. Il est recommandé que, pour toute décision basée sur des actions de conversion « A affiché une page » pour ces activités, vous ne teniez compte que des données enregistrées avant ou après la période concernée.

Les données de création de rapports pour d’autres mesures peuvent toujours être utilisées car elles n’ont pas été affectées.

Ce problème a été corrigé dans Target 17.4.3.

### Offres : activités A/B et de ciblage d’expérience (XT)

La diffusion et la prévisualisation ont été affectées pour les offres des activités A/B et XT comportant au moins deux expériences et qui ont été créées ou modifiées à l’aide du compositeur d’expérience d’après les formulaires entre le vendredi 28 avril (21h, heure de la côte Ouest des États-Unis) et le lundi 1er mai (21h15, heure de la côte Ouest des États-Unis). Seules les offres comportant du contenu par défaut étaient affichées.

Ce problème a été corrigé dans Target 17.4.3.

### at.js {#at-js-6}

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

Ce problème a été corrigé après la publication de Recommendations (22 mars 2018). Après la publication de Recommendations, Target ignore les règles dynamiques basées sur l’entité si le paramètre entity.id n’est pas transmis dans la requête mbox.

### at.js  {#at-js-7}

Lorsque les utilisateurs essaient de télécharger at.js depuis la page relative aux détails de l’implémentation après la mise à jour des paramètres d’at.js, est téléchargé à la place d’at.js. (TGT-23069)

Ce problème a été corrigé dans la version 17.3.1 de Target (30 mars 2017).

### Règles d’exclusion globale

Il faut compter de 10 à 20 minutes pour que les règles d’exclusion globale se propagent à la périphérie pour Recommendations Premium. (RECS-5270)

Corrigé dans la version 17.2.2.0 de Recommendations (6 mars 2017).

### Reporting Analytics for Adobe Target (A4T)

Les rapports ne sont pas mis à jour quand la mesure de reporting est activée. Ce problème n’affecte que l’interface utilisateur. Ceci n’a aucun impact sur la collecte ou la distribution de données de création de rapports. (TGT-22970)

Ce problème a été corrigé dans la version 17.2.2.0 de Target (24 février 2017).

### Rapports CSV

Les rapports téléchargés ne tiennent pas compte du paramètre Exclure les commandes extrêmes. (TGT-21871)

Ce problème a été corrigé dans Target 17.2.1.0.
