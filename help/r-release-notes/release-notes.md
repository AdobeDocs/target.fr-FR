---
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.
keywords: Notes de mise à jour, version préliminaire
seo-description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
seo-title: Notes de mise à jour d'Adobe Target (en cours)
solution: Target
title: Notes de mise à jour de Target (actualisées)
topic: Recommandations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51f52bb40a0af4dac63236d46e6d6f0286cbb877

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.

## Annonces

**31 juillet 2019**

[!UICONTROL Les autorisations d'entreprise] permettent [!DNL Target] aux clients d'utiliser une seule organisation, mais la divisent en espaces de travail pour différentes équipes ou différents processus. La fonction [!UICONTROL Autorisations] d'entreprise facilite la mise à l'échelle efficace des programmes d'optimisation entre équipes. Bien que cette fonctionnalité soit disponible dans [!DNL Target] l'interface utilisateur, les API d'administration lacaient la prise en charge correspondante jusqu'à [!DNL Target] la version de février 2019. Adobe a mis à jour les API d'administration afin que vous puissiez utiliser le compte d'intégration pour accéder à tous les espaces de travail créés dans votre organisation. Ainsi, bien qu'auparavant, les API d'administration étaient limitées à l'espace de travail par défaut, la mise à jour de février 2019 autorisait l'accès à tous les espaces de travail avec [!UICONTROL accès aux approbateurs] .

Avec la prochaine version [!DNL Target] de septembre 2019, [!UICONTROL les permissions] d'entreprise offrent aux clients les commandes d'accès suivantes :

* Vous pouvez choisir les espaces de travail auxquels l'intégration peut être appliquée.
* Vous pouvez appliquer un rôle à l'intégration d'Adobe I/S : [!UICONTROL Approbateur], [!UICONTROL Éditeur]ou [!UICONTROL Observateur].

**Action requise**: Les clients qui exploitent actuellement des API pour les opérations CRUD sur des ressources (activités, audiences, offres et création de rapports) sur tous les espaces de travail doivent accorder à leur intégration d'E/S existante Adobe l'accès à tous les espaces de travail avec le rôle souhaité. Avant la version de septembre, toutes les intégrations utilisées à l'aide [!UICONTROL d'un] accès Approbateur, quel que soit le rôle sélectionné dans [!UICONTROL la liste déroulante Rôle] du produit. Avec la prochaine version, vous pouvez désormais sélectionner un rôle.

Cette action doit être effectuée pendant le mois **d'août 2019**. Après la sortie [!DNL Target] de la version de septembre 2019, les commandes d'accès activeront et vous constaterez l'accès à l'espace de travail par défaut, si c'est comme vous le souhaitez actuellement. Il n'existe aucune conséquence négative pour la définition des rôles d'intégration à l'avance.

Pour obtenir des instructions pas à pas et plus d'informations, voir [Octroi d'intégrations d'E/S Adobe aux espaces de travail et attribution de rôles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Mobile VEC SDK ios 2.1.0 &amp; Android 1.1.0 (7 août 2019)

Cette version du SDK Mobile VEC comprend les améliorations et correctifs suivants :

(Les numéros de problèmes entre parenthèses sont réservés à une utilisation interne par Adobe.)

* Ajout de la prise en charge de la fonction Aperçu pour les activités visuelles sur un périphérique mobile. (TGT-27875)
* Correction d'un problème qui provoquait une violation Apple Standard en raison de `UIImagePickerController` l'utilisation.
* Suppression de la dépendance GSON du SDK Android. (TGT-31710)
* Correction d'un problème en raison duquel l'offre de remise n'était pas réinitialisée au moment de la création. (TGT-35270)

## Target Standard/Premium 19.7.1 (24 juillet 2019) {#tgt-19-7-1}

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

(Les numéros de problèmes entre parenthèses sont réservés à une utilisation interne par Adobe.)

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle pour application mobile | Un nouveau panneau Modifications s'affiche dans le compositeur d'expérience visuelle Mobile, qui affiche les éléments que vous avez configurés pour le suivi des clics. (TGT -31741)<br> Reportez-vous [à la section Configuration du suivi des clics dans l'application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Badgerecommendations](/help/assets/premium.png)<br>dans les activités de test A/B et de ciblage d'expérience (XT) | L'état d'offre de recommandations (algorithme) s'affiche sur la page Aperçu pour les tests A/B et les activités de ciblage d'expérience contenant des offres Recommendations. Les états incluent : Résultats prêts, Résultats non prêts et Échec du flux. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Prise en charge de suivi interdomaines pour at. js 2.0 + via la bibliothèque Experience Cloud ID (ECID) | Auparavant, le suivi inter-domaines n'était pas pris en charge dans at. js 2.*x*. Avec cette version, les utilisateurs qui utilisent at. js 2.0 ou version ultérieure peuvent désormais utiliser le suivi inter-domaines via la bibliothèque ECID. La bibliothèque ECID doit être installée sur la page conjointement avec at. js 2.0 ou version ultérieure pour que le suivi inter-domaines fonctionne. [La bibliothèque Experience Cloud ID 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) doit être utilisée.<br>Voir [Prise en charge du suivi inter-domaines dans at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain). |
| Prise en charge de Target pour ITP 2.1 et ITP 2.2 d'Apple via la bibliothèque d'Experience Cloud ID (ECID) 4.3 | Aujourd'hui, les clients Target peuvent réduire les ITP 2.1 et ITP 2.2 Apple en exploitant le programme de certification CNAME d'Adobe.<br>Avec cette version, Target introduit une intégration transparente avec la bibliothèque ECID 4.3, qui utilise un cookie côté serveur pour atténuer ITP 2.1 et ITP 2.2. Il est vivement recommandé aux clients Target de déployer [la bibliothèque ECID 4.3 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) conjointement avec la bibliothèque JavaScript de Target pour atténuer les futures versions ITP. La bibliothèque ECID continue à déployer les améliorations qui offrent une solution fiable aux stratégies de cookies qui évoluent constamment par les navigateurs.<br>Voir [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md). |

**Améliorations, correctifs et modifications**

* Correction d'un problème qui empêchait l'effacement des valeurs d'exclusion dans les activités de recommandations lors de l'ajout de valeurs en double. (TGT-34996)
* Vous pouvez désormais supprimer une conception dans une activité de recommandations de la page Ciblage (étape 2 du workflow assisté en trois parties). Notez que pour supprimer une conception, plusieurs conceptions doivent être sélectionnées. (TGT-35118)
* Correction d'un problème qui empêchait le chargement correct des cartes de critères personnalisés pour certains clients dans l'interface utilisateur de Target ou pour être modifiables. (TGT-35170)

## at. js version 2.1.1 (24 juillet 2019)

Cette version de at. js est une version de maintenance et comprend les améliorations et correctifs suivants :

(Les numéros de problèmes entre parenthèses sont réservés à une utilisation interne par Adobe.)

* Correction d'un problème en raison duquel plusieurs balises se déclenchaient lors de l'utilisation de la mesure Suivi des clics dans la page Objectifs et paramètres du compositeur d'expérience visuelle. (TNT-32812)
* Correction d'un problème qui empêchait `triggerView()` le rendu des offres plusieurs fois. (TNT-32780)
* Correction d'un problème en raison `triggerView()` duquel la demande contenait des informations de Marketing Cloud ID (MCID). (TNT-32776)
* Correction d'un problème qui empêchait la `triggerView()` notification de se déclencher même s'il n'y avait aucune vue enregistrée. (TNT-32614)
* Correction d'un problème qui provoquait une erreur en raison de l'utilisation de decodeuricomponent qui provoquait des problèmes lorsque l'URL contenait un paramètre de chaîne de requête incorrect. (TNT-32710)
* L'indicateur de balise est maintenant défini sur « true » dans le contexte des demandes de livraison envoyées via l' `Navigator.sendBeacon()` API. (TNT-32683)
* Correction d'un problème qui empêchait l'affichage des offres Recommendations sur les sites Web pour certains clients. Les clients peuvent voir le contenu de l'offre dans l'appel de l'API de livraison, mais l'offre n'a pas été appliquée sur le site Web. (TNT-32680)
* Correction d'un problème en raison duquel le suivi des clics sur plusieurs expériences ne fonctionnait pas comme prévu. (TNT-32644)
* Correction d'un problème qui empêchait at. js d'appliquer la seconde mesure après l'échec du rendu de la première mesure. (TNT-32628)
* Correction d'un problème lors de la transmission `mboxThirdPartyId` à l'aide de `targetPageParams` la fonction en raison duquel la charge utile de la requête n'était pas présente dans les paramètres de requête ou dans la charge utile de requête. (TNT-32613)
* Correction d'un problème en raison duquel les réponses de notification et de clic étaient bloquées dans les navigateurs Chromium (y compris Google Chrome). (TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d'informations, voir [Notes de mise à jour d'Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
