---
description: Informations détaillées sur les modifications apportées à chaque version d’at.js.
keywords: versions d’at.js, versions du fichier at.js
seo-description: Informations détaillées sur les modifications apportées à chaque version d’at.js.
seo-title: Informations détaillées sur les versions du fichier at.js
solution: Target
subtopic: Prise en main
title: Informations détaillées sur les versions du fichier at.js
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Informations détaillées sur les versions du fichier at.js {#at-js-version-details}

Informations détaillées sur les modifications apportées à chaque version de la Bibliothèque JavaScript at.js [!DNL Adobe Target].

>[!IMPORTANT]
>
>L’équipe Target gère deux versions seulement d’[!DNL at.js] : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour [!DNL at.js] si nécessaire pour vous assurer que vous utilisez une version prise en charge.

## at. js version 2.1.0 (3 juin 2019)

Cette version comprend les fonctionnalités et améliorations suivantes :

* **Prise en charge de la souscription Adobe**: Adobe Souscription est un moyen de simplifier les intégrations des solutions Adobe avec les plateformes de gestion des autorisations. Pour plus d’informations sur la fonctionnalité Adobe Opt-in, voir [Confidentialité et protection générale des données (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **Compatibilité CSP standard**: at. js n&#39;utilise plus eval () pour exécuter JavaScript.

* **Journalisation des analyses côté client**: Donnez aux clients un contrôle total sur la manière d&#39;envoyer des données d&#39;analyse à Adobe Analytics, que ce soit côté client ou côté serveur.

   For more information, see [Client-side Analytics logging](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) in *Before you implement*.

* **Envoyer des notifications**: Permet aux développeurs d&#39;envoyer des notifications lorsqu&#39;une expérience est générée par leur code au lieu d&#39;utiliser `applyOffer()` ou `applyOffers()`.

   For more information, see [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **Taille d&#39;at. js réduite de ~ 24 %**: La taille d&#39;at. js est réduite de ~ 24 %. La taille de fichier plus petite améliore les performances de chargement des pages et réduit le temps de téléchargement du fichier at. js sur la page.

## at.js version 2.0.1 (19 mars 2019)

Cette version de maintenance comprend les améliorations et correctifs suivants :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

* Correction d’une condition de concurrence dans le code d’interrogation DOM qui provoquait des exceptions JavaScript pour certains clients. (TNT-31869)
* Les notifications de rendu des vues ont été découplées des gestionnaires d’événements de suivi des clics. Initialement, Target n’envoyait pas de notifications si les gestionnaires d’événements de clic appartenant à une vue rendue ne pouvaient pas être attachés. Target envoie désormais une notification de vue même si les éléments de clic sont introuvables. (TNT-31969)
* Correction d’un problème en raison duquel le drapeau de redirection d’événement request-succeeded était toujours défini sur true. (TNT-31907)
* Correction d’un problème en raison duquel l’action de réorganisation du VEC était enregistrée comme succès, même lorsque des éléments étaient manquants. (TNT-31924)
* Correction d’un problème en raison duquel les notifications pour certains clients ne contenaient pas le jeton de propriété Permissions d’entreprise. (TNT-31999)

## at.js version 1.7.1 (19 mars 2019)

Cette version est une version de maintenance et inclut les modifications suivantes :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

* Correction d’une condition de concurrence dans le code d’interrogation DOM qui provoquait des exceptions JavaScript pour certains clients. (TNT-31869)

## at.js version 2.0.0 {#at-js-200}

at.js 2 propose des ensembles de fonctionnalités enrichies qui permettent à votre entreprise d’exécuter la personnalisation sur les technologies côté client de génération suivante. Cette nouvelle version vise à mettre à niveau at.js afin d’établir des interactions harmonieuses avec les applications monopages (SPA).

Voici quelques avantages de l’utilisation d’at.js 2.x qui ne sont pas disponibles dans les versions précédentes :

* Capacité à mettre en cache toutes les offres au chargement de la page afin de passer de plusieurs appels au serveur à un seul.
* Améliorez considérablement les expériences des utilisateurs finaux sur votre site. Les offres s’affichent immédiatement via le cache sans temps de latence que les appels serveur traditionnels imposent.
* Une simple ligne de code et une configuration unique des développeurs permettent aux marketeurs de créer et d’exécuter des activités A/B et d’expérience sur vos applications monopages via le compositeur d’expérience visuelle.

at.js 2.x introduit les nouvelles fonctions suivantes :

* getOffers()
* applyOffers()
* triggerView()

Les fonctions suivantes ont été abandonnées à l’introduction de la version at.js 2.x :

* mboxCreate()
* mboxDefine
* registerExtension()

Pour plus d’informations, voir [Mise à niveau d’at.js 1.x vers at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) et [Fonctions at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>
>If you require Adobe Opt-in support for the [General Data Protection Regulation](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR), you must currently use at.js 1.7.0 or at.js 2.1.0.

## at.js version 1.7.0 {#at-js-170}

at.js 1.7.0 prend en charge Adobe Opt-in. Adobe Opt-in est un moyen de simplifier les intégrations des solutions Adobe avec les plateformes de gestion des autorisations.

Pour plus d’informations sur Adobe Opt-in, voir [Confidentialité et Règlement général sur la protection des données](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR).

Cette version corrige également le problème selon lequel Target remplace les paramètres d’URL de redirection par les paramètres provenant de l’URL de redirection.

>[! REMARQUE]
>
>If you require Adobe Opt-in support for GDPR, you must currently use at.js 1.7.0 or 2.1.0.<br>For a list of all versions, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## at.js version 1.6.4 {#at-js-164}

at.js 1.6.4 est une version de maintenance qui résout le problème suivant :

* Correction d’un manifeste de conditions de concurrence dans Microsoft Internet Explorer 11 responsable de l’application d’offres dupliquées.

## at.js version 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

La version 1.6.3 d’at.js comprend les correctifs et améliorations suivants :

* Les sélecteurs sont désormais dotés d’une séquence d’échappement CSS s’ils contiennent des ID ou des classes CSS commençant par un chiffre, deux traits d’union ou un trait d’union suivi d’un chiffre (par exemple #-123). (TNT-31061)
* Correction d’un problème apparu avec at.js 1.6.2, selon lequel les offres du VEC issues d’activités différentes qui s’appliquaient au même sélecteur CSS ne respectaient pas la priorité de l’activité. (TNT-31052)
* Correction d’un problème impliquant des promesses non prises en charge nativement par le délai d’expiration d’une promesse. (TNT-30974)
* Les problèmes sont désormais correctement capturés et signalés par l’événement de rendu de contenu. Auparavant, il était possible que l’exécution de JavaScript soit signalée comme réussie, même si ce n’était pas le cas. (TNT-30599)

## at.js version 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

Il s’agit d’une version de maintenance qui résout le problème suivant :

* Correction d’un problème entraînant la présence d’une boucle asynchrone infinie sur les sites de certains clients.

>[!IMPORTANT]
>
>En outre, l’ensemble des améliorations et correctifs présents dans les versions 1.6.1 et 1.6.0 d’at.js le sont également dans la version 1.6.2. Ces deux anciennes versions ne sont désormais plus disponibles au téléchargement. Nous vous recommandons de mettre at.js à niveau vers la version 1.6.2 si vous utilisez les versions 1.6.1 ou 1.6.0

Voici les améliorations et les correctifs apportés dans la version 1.6.1 d’at.js :

* Résolution d’un problème dans at.js 1.6.0, qui causait la duplication des expériences de recommandations dans Microsoft Internet Explorer 11. (TNT-30593)
* at.js fait désormais en sorte que la logique de remplacement des serveurs Edge vérifie l’existence d’un cookie de cluster Edge, pour éviter que le nombre de serveurs Edge soit différent si un utilisateur change de serveur pendant une session. (TNT-30563)
* Résolution d’un problème empêchant at.js d’exécuter les actions suivantes, lorsqu’il y avait un code Javascript non valide dans le contenu HTML. at.js enregistre désormais l’erreur et effectue sans problème les autres actions. (TNT-30546)
* Changements effectués, de manière à ce qu’une exception soit faite quand une page de redirection est de nouveau admissible pour une activité de redirection. (TNT-30532)
* Résolution d’un problème empêchant le délai correct d’attente de la requête de se propager à partir de la requête de l’API getOffer(). (TNT-30498)
* Résolution d’un problème empêchant at.js 1.6.0 d’enregistrer les cookies lors de l’utilisation du protocole du fichier. (TNT-30454)
* Résolution d’un problème empêchant l’affichage des redirections normalement remises avec les expériences lors de l’utilisation d’Analytics for Target (A4T). (TNT-30444)
* Résolution d’un problème entraînant le masquage de la page une fois l’appel Target réussi. (TNT-30358)

Voici les améliorations et les correctifs apportés dans la version 1.6.0 d’at.js :

* Prise en charge automatique des offres redirigées dans l’intégration d’Analytics for Target (A4T). Suppression de la méthode de contournement côté client. (TNT-30247)
* Acheminement Edge côté client désormais activé par défaut. (TNT-30261)
* Résolution d’un problème de rendu des actions du compositeur d’expérience visuelle lors de la présence de dépendances entre les actions. (TNT-30248)

## at.js version 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js version 1.5.0 est désormais disponible.

* Les détails de l’événement `at-request-succeeded` contiennent l’indicateur de redirection. Cet indicateur peut être utilisé pour déterminer si la page sera redirigée vers une URL différente. Si vous souhaitez connaître l’URL, abonnez-vous à `at-content-rendering-redirect`. (TNT-29834)
* Résolution d’un problème qui faisait échouer `window.targetGlobalSettings.enabled` avec une exception d’exécution s’il était défini sur false. (TNT-29829)
* Résolution d’un problème qui faisait échouer la page lors du chargement dans le compositeur d’expérience visuelle (VEC) en cas d’utilisation de code personnalisé pour déclencher une demande mbox globale et à l’aide du masquage des corps. (TNT-29795)
* Ajout de la prise en charge de `screenOrientation`, `devicePixelRatio` et `webGLRenderer`. Ces nouveaux paramètres de demande de Target sont utilisés pour la détection de l’iPhone X et d’autres appareils modernes. Pour plus d’informations, voir [Mobile](../../c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89). (TNT-29781)
* Résolution du problème où le conseil d’emplacement d’Adobe Audience Manager (AAM) n’était pas toujours envoyé. (TNT-29695)
* Pour les navigateurs qui le prennent en charge, at.js 1.5.0 passe à MutationObserver pour l’interrogation du sélecteur. Les versions antérieures à at.js 1.0.0 utilisaient un polyfill MutationObserver, qui s’avérait problématique. Pour éviter les problèmes de polyfill, la version 1.5.0 utilise le pseudo code suivant afin de choisir le mécanisme de planification à utiliser :

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js version 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js version 1.3.0 est désormais disponible.

* Les nouveaux événements suivants sont disponibles afin de faciliter les activités de traçage, de débogage et de personnalisation de l’interaction avec at.js :

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT
   Pour plus d’informations, voir [Événements personnalisés de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md).

* Vous pouvez augmenter une requête at.js au moyen de paramètres complémentaires issus des fournisseurs de données. Les fournisseurs de données doivent être ajoutés à `window.targetGlobalSettings` sous la `dataProviders key`.

   Pour plus d’informations, voir [Fournisseurs de données](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

* Les requêtes at.js font désormais appel à GET, mais permutent sur le mode POST lorsque la taille de l’URL dépasse 2 048 caractères. Une nouvelle propriété nommée `urlSizeLimit` vous permet d’augmenter la taille limite si nécessaire. Cette modification permet à Target d’aligner at.js avec AppMeasurement, qui utilise la même technique.
* Target applique désormais la clé `mbox` dans la fonction `adobe.target.applyOffer(options)`. Cette clé était obligatoire par le passé, mais Target force désormais son application de manière à garantir sa validation et l’utilisation correcte de la fonction par les clients.
* La fonctionnalité de suivi des événements et des clients a été améliorée dans at.js. at.js utilise `navigator.sendBeacon()` pour envoyer les données de suivi d’événement et revient en mode XHR synchrone lorsque `navigator.sendBeacon()` n’est pas pris en charge. Cette solution de secours concerne principalement Internet Explorer 10 et 11, ainsi que certaines versions de Safari. Safari comprendra une prise en charge supplémentaire de `navigator.sendBeacon()` dans la prochaine version d’iOS 11.3.
* at.js peut désormais assurer le rendu des offres même lorsqu’une page est ouverte dans les onglets d’arrière-plan. Certains clients Target ont signalé qu’en cas de désactivation de `requestAnimationFrame()`, un problème de goulet d’étranglement se produisait dans le navigateur pour les onglets d’arrière-plan.
* Cette version apporte de nombreuses améliorations de performances, y compris des piles d’appels plus courtes lors de l’inspection d’un profil CPU Chrome.
* at.js 1.3.0 ne prend plus en charge la diffusion de contenu sur Microsoft Internet Explorer 9. Pour obtenir la liste des navigateurs pris en charge, voir [Navigateurs pris en charge](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100). Dorénavant, toutes les requêtes sont exécutées via `XMLHttpRequest` avec prise en charge de CORS sans requêtes JSONP. Cette modification améliore considérablement la sécurité.

## at.js version 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

La version 1.2.3 de [!DNL at.js] est désormais disponible.

* Ajoute une prise en charge des offres JSON. Les offres JSON sont uniquement prises en charge dans les activités créées dans le compositeur d’expérience d’après les formulaires. À l’heure actuelle, les offres JSON peuvent uniquement être utilisées par le biais d’appels d’API directs. Voir [Création d’offres JSON](../../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D).

## at.js version 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

La version 1.2.2 de [!DNL at.js] est désormais disponible.

* Correction d’un problème qui provoquait le renvoi d’une erreur JavaScript lors du chargement de la bibliothèque Target sur une page en mode QUIRKS. (TNT-28312)
* Correction d’un problème en raison duquel le suivi des clics de Target rompait les appels de collecte de données Analytics. (TNT-28261)
* Correction d’un problème causant l’échec de `getOffer() params` lorsque `targetPageParams()` renvoie une chaîne vide. (TNT-28359)
* Correction d’un problème relatif à la génération des ID de session lors de l’utilisation du paramètre x uniquement. (TNT-28361)

## at.js version 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

La version 1.2.1 de [!DNL at.js] est désormais disponible.

* Correction d’un problème en raison duquel le suivi des clics sur un lien avec target=&quot;_blank&quot; empêchait Target d’ouvrir le lien dans un nouvel onglet.

## at.js version 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] version 1.2 est désormais disponible sous la forme d’une version de maintenance contenant principalement des correctifs de bogues.

* Correction d’un problème qui empêchait les actions par défaut pour des cas spéciaux de suivi des clics. (TNT-28089)
* Correction d’un problème selon lequel le suivi des clics sur un lien avec `target="_blank"` empêchait Target d’ouvrir le lien dans un nouvel onglet. (TNT-28072)
* Les adresses IP peuvent être utilisées comme domaine de cookie. (TNT-28002)
* Correction d’un problème qui provoquait un scintillement des offres de redirection dotées d’une mbox globale ou de mbox régionales. (TNT-27978)
* Correction d’un problème en raison duquel la configuration des activités de ciblage d’expérience échouait dans le compositeur d’expérience visuelle en basculant du mode Parcourir au mode Composer. (TNT-27942)
* Correction de la gestion incorrecte des classes de style de scintillement pour les éléments de suivi des clics. (TNT-27896)
* Correction d’un problème en raison duquel les paramètres des mbox globales se mélangeaient à l’ensemble des paramètres de mbox. (TNT-27846)
* Apport de modifications pour garantir que Handlebars, Mustache et d’autres bibliothèques de création de modèles côté client sont correctement gérés par [!DNL at.js]. (TNT-27831)
* Apport de modifications pour garantir que `sdidParamExpiry` est correctement initialisé et transféré à l’API visiteur. Il s’agit d’une régression qui a été ajoutée à `at.js 1.1.0`. Les versions précédentes d’[!DNL at.js] ne sont pas affectées. Cela affecte uniquement les clients utilisant les offres de redirection et A4T. (TNT-27791)
* Apport de modifications pour garantir que `SCRIPT` est exécuté quel que soit l’attribut type utilisé. (TNT-27865)

## at.js version 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**Date :** 2 août 2017

Les améliorations et correctifs suivants sont inclus dans la version 1.1 de [!DNL at.js] :

* Ajout de la gestion des jetons de réponse. Pour plus d’informations, voir [Jetons de réponse](../../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).
* Correction d’un problème de sorte que `document.currentScript polyfill` n’interfère plus avec Angular 1.X.
* Apport de modifications permettant de garantir que le suivi des clics n’interfère pas avec la propriété Visibilité. Les éléments de suivi des clics sont marqués par la classe CSS `at-element-click-tracking` au lieu de `at-element-marker`.

## at.js version 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**Date :** 7 juillet 2017

Les améliorations et correctifs suivants sont inclus dans la version 1.0 d’at.js :

* Prise en charge du chargement d’at.js de manière asynchrone pour des chargements de page plus rapides.
* Prise en charge du pré-masquage du contenu de la page lors du chargement de manière asynchrone d’at.js.
* Amélioration des messages d’erreur lorsque la diffusion du contenu est désactivée.
* Amélioration des performances lors de la diffusion de plusieurs activités.
* Prise en charge du compresseur YUI.
* Création de rapports de bogue/d’erreur pour les événements personnalisés au cours de la diffusion des activités.
* Correction de problèmes de performances dans Microsoft Internet Explorer 11.
* Correction de la fonction `getOffer()` () qui produisait une erreur sur certains sites web.
* Chargement de la bibliothèque Target de manière asynchrone. Pour plus d’informations, consultez [la section Questions fréquentes d’at.js](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## at.js version 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**Date :** 22 mai 2017

Les améliorations et correctifs suivants sont inclus dans la version 0.9.7 de [!DNL at.js] :

* Correction d’un problème lié à une clé de ressource qui manquait dans les actions `insertAfter` et `insertBefore` dans le compositeur d’expérience visuelle. Ces problèmes étaient liés à la migration d’offres visuelles vers des modèles d’offres.

## at.js version 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**Date :** 13 avril 2017

Les améliorations et correctifs suivants sont inclus dans la version 0.9.6 de [!DNL at.js] :

* Prise en charge de l’offre de redirection pour A4T. Après avoir téléchargé et installé la version 0.9.6 d’[!DNL at.js], vous pouvez utiliser les offres de redirection dans les activités qui utilisent [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Target] (A4T). Outre la version 0.9.6 d’[!DNL at.js], d’autres exigences doivent être respectées pour pouvoir utiliser les offres de redirection et A4T dans la mise en œuvre. Pour en savoir plus et obtenir d’autres informations importantes, voir [FAQ sur les offres de redirection (A4T)](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Avant la version 0.9.6 d’[!DNL at.js], lorsque l’API visiteur était présente sur la page et que le paramètre `visitorApiTimeout` était trop agressif, ne pouvait pas s’exécuter quand aucune donnée MCID n’était envoyée dans la demande [!DNL Target]Target. Il pouvait en résulter certains problèmes, par exemple des accès désassemblés dans [!DNL Analytics] lors de l’utilisation d’A4T.

   Ce comportement a été modifié dans [!DNL at.js] 0.9.6 : même si `visitorApiTimeout` est défini à 1 ms, par exemple, Target tente de collecter le SDID, les données des serveurs de suivi et les identifiants client et les envoie dans la demande Target.

* Ajout du paramètre `selectorsPollingTimeout`. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Le format de la réponse de `getOffer()` a été modifié. Pour plus d’informations, voir [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* Ajout de la journalisation de la console pour les déclarations `<!DOCTYPE>` non prises en charge.
* Correction d’un problème en raison duquel les modules externes de [!DNL Target Classic] n’étaient pas correctement appliqués lorsque plusieurs offres par défaut étaient diffusées à une seule mbox. (TGT-22664) Pour plus d’informations, voir [Modules externes](https://marketing.adobe.com/resources/help/en_US/tnt/help/t_Using_Plug-Ins.html) dans la documentation d’Adobe Target Classic.
* Amélioration du paramètre de cookie pour les domaines de niveau supérieur à deux lettres afin de s’assurer que le cookie de mbox est correctement défini pour ces domaines (par exemple, [!DNL test.no],[!DNL autodrives.ca], etc.).
* L’algorithme d’extraction du domaine de premier niveau devant être utilisé lors de l’enregistrement des cookies a été modifié dans la version 0.9.6 d’at.js. En raison de cette modification, les cookies ne peuvent pas être enregistrés dans des adresses utilisant le protocole IP. La plupart du temps, les adresses IP sont utilisées à des fins de test mais, comme solutions de contournement, vous pouvez utiliser les entrées DNS ou ajuster le fichier des hôtes sur une box locale.
* Correction de la gestion des actions de déplacement et de réorganisation lorsque les propriétés sont des valeurs de chaîne au lieu d’entiers.

## at.js version 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**Date :** 19 janvier 2017

* Dans un souci de respect des exigences d’attribution de nom des mbox utilisant mbox.js, les noms de mbox peuvent maintenant contenir des caractères spéciaux, y compris des esperluettes ( &amp; ).

   Pour obtenir une liste des caractères spéciaux autorisés, voir [Configurations at.js](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812).

* Ajout du paramètre `secureOnly`, qui indique si at.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. Il s’agit d’un paramètre avancé défini par défaut sur false ; il peut être remplacé au moyen de `targetGlobalSettings`.
* L’option [!UICONTROL Prise en charge du navigateur hérité] est proposée dans les versions 0.9.3 et antérieures d’at.js. Elle a été supprimée de la version 0.9.4 d’at.js.

## at.js version 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**Date :** 10 octobre 2016.

* Veille au déclenchement des appels de mbox dans Microsoft Internet Explorer 11 lorsque les navigateurs hérités sont désactivés dans les paramètres d’at.js.
* Veille à ce que le contenu par défaut s’affiche en cas de problème lié à une offre dynamique distante (si l’URL est incorrecte et renvoie une erreur 404, par exemple).
* Veille à ce que les éléments soient rapidement affichés lorsque les sélecteurs de suivi des clics du compositeur d’expériences visuelles sont introuvables dans le modèle DOM.

## at.js version 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**Date :** 21 septembre 2016.

* Ajout d’un paramètre `optoutEnabled` pour activer ou désactiver le service d’exclusion du graphique de périphérique. Si ce paramètre est défini sur `true` et que le visiteur a choisi de ne pas autoriser le suivi, son navigateur n’effectuera aucun appel de mbox. Le graphique de périphérique est actuellement en version bêta. Ce paramètre est défini sur `false` par défaut, mais doit être défini sur `true` si vous utilisez le graphique de périphérique. Une option similaire est incluse dans la version 61 de mbox.js.
* Ajout de la prise en charge de `CustomEvent` pour le mécanisme de notification. Avant, le mécanisme de notification d’événement d’at.js ne pouvait pas être utilisé avec les API du modèle DOM standard telles que `document.addEventListener()`. Désormais, vous pouvez utiliser `document.addEventListener()` pour vous inscrire aux événements at.js, tels que les événements de requête et les événements de rendu de contenu.
* Résolution d’un problème lié aux offres créées dans le compositeur d’expérience visuelle. Avant cette version, Target masquait les sélecteurs et les affichait uniquement lorsqu’ils correspondaient tous. Dans at.js 0.9.2, Target affiche les sélecteurs dès qu’ils correspondent.

## at.js version 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**Date :** 14 juillet 2016.

* Fournit à at.js un délai d’attente pour le service d’identification des visiteurs, qui est indépendant du délai d’attente du service en lui-même.
* Résout le problème de la version 0.9.0 qui affectait les implémentations utilisant at.js dans certaines pages et mbox.js dans d’autres.
* Si vous utilisez Adobe Analytics comme source des rapports de votre activité, vous ne devez pas spécifier de serveur de suivi durant la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## at.js version 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Version de Target :** 16.6.1

**Date :** 23 juin 2016

* Corrige un problème d’écran blanc lors de l’utilisation d’offres du compositeur d’expérience visuelle. Les utilisateurs qui utilisent la bibliothèque [!DNL at.js] doivent effectuer une mise à niveau vers cette nouvelle version.
* Nouvelle API `registerExtension`.

   Cette nouvelle API permet aux développeurs d’avoir accès à certains modules jQuery utilisés dans [!DNL at.js] pour développer des extensions (ou modules externes) pour la bibliothèque. Ce changement a quelques répercussions. Il affecte uniquement les utilisateurs qui utilisent les fonctions suivantes :

   * L’API `getSettings()` a été supprimée, mais la même fonctionnalité est disponible avec `registerExtension()`.
   * L’API `getTracking()` a été supprimée, mais la même fonctionnalité est disponible avec `registerExtension()`.

   * Les extensions existantes (notamment les extensions AngularJS) doivent être mises à jour pour utiliser l’approche `registerExtension()`.

* Nouvelle API de notification d’at.js.

   Ce système de notification a pour objectif de fournir davantage d’informations sur ce qu’[!DNL at.js] fait sur la page et quand il y a des problèmes. Un problème courant rencontré avec le compositeur d’expérience visuelle est qu’une version IT modifie la page, un sélecteur du compositeur d’expérience visuelle se brise et le test cesse de fournir le contenu correctement. L’un des objectifs de ce système de notification est de rendre ce problème visible sur la page de manière à ce que les développeurs puissent accéder à ces informations, les transmettre à un système, comme [!DNL Adobe Analytics], et envoyer des alertes aux exploitants les informant que leur test est interrompu.

* Nouvelle méthode d’API `targetGlobalSettings()`.

   Vous pouvez remplacer les paramètres de la bibliothèque at.js au lieu de configurer les paramètres dans l’interface utilisateur de [!DNL Target Standard/Premium UI] ou utiliser des API REST.

## at.js version 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**Date :** 5 mai 2016.

Il s’agit de la première version officielle de la bibliothèque [!DNL at.js].

[!DNL at.js] est une nouvelle bibliothèque d’implémentation pour [!DNL Target] qui a été conçue pour les implémentations web classiques et les applications d’une seule page.

[!DNL at.js] remplace [!DNL mbox.js] pour les implémentations [!DNL Adobe Target].

>[!NOTE]
>
>Bien que [!DNL at.js] remplace [!DNL mbox.js], mbox.js reste prise en charge. Pour la plupart des utilisateurs, [!DNL at.js] offre des avantages par rapport à [!DNL mbox.js]. Vous avez du temps pour tester la bibliothèque [!DNL at.js] et pour modifier l’implémentation sur vos pages.

Autres avantages : [!DNL at.js] réduit les délais de chargement des pages pour les implémentations web, renforce la sécurité et offre des options d’implémentation optimisées pour les applications d’une seule page.

[!DNL at.js] contient les composants qui étaient inclus dans [!DNL target.js]. Il n’y a donc plus d’appel à [!DNL target.js].

Lors de l’implémentation de la bibliothèque [!DNL at.js], souvenez-vous des points suivants :

* Les versions d’Internet Explorer antérieures à la version 8 ne sont pas prises en charge.
* Une implémentation asynchrone signifie que les intégrations héritées telles que le module externe [!DNL Test&Target] vers [!DNL SiteCatalyst] risquent de ne pas fonctionner.
* Les modules externes de [!DNL Target] qui référencent des objets et des méthodes de [!DNL mbox.js] ne sont pas pris en charge.
* Tous les appels à [!DNL Target] sont effectués via XMLHTTPRequest et le contenu est renvoyé via JSON.
