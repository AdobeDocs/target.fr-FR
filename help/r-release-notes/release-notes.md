---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 95fdb1dcee873f7a414a3aecdc363fca2b621c01
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 100%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js afin dʼéviter tout problème potentiel avec vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## at.js 2.6.1 (16 août 2021)

* Correction de bug « Aucun artefact mis en cache disponible pour le mode hybride » lors de l’utilisation de la prise de décision sur l’appareil.

## SDK node.js 2.2.0 [!DNL Target] (11 août 2021)

* Ajout de la collecte de données de télémétrie du SDK
* Génération de code OpenAPI du client de l’API de diffusion automatisée

Pour plus d’informations à ce sujet et sur les versions précédentes, reportez-vous au [Journal des modifications](https://github.com/adobe/target-nodejs-sdk/blob/main/CHANGELOG.md) dans la [documentation du SDK node.js de Target](https://github.com/adobe/target-nodejs-sdk) sur Github.

## [!DNL Target Standard/Premium] 21.8.1 (10 août 2021)

Cette version de maintenance offre de nombreuses améliorations du serveur principal, notamment la modification suivante destinée aux clients :

* Correction d’un problème en raison duquel les rapports d’activités de [!UICONTROL Personnalisation automatique] créées dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] référençaient des offres supprimées dans les rapports. Ce problème entraînait l’affichage du message d’erreur suivant : « Problème lors de la récupération des données de ce rapport. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-41028)

## [!DNL Target Delivery API] (3 août 2021)

Les améliorations suivantes ont été apportées à cette version :

* La limite des paramètres de mbox a été augmentée à 100 paramètres. Auparavant, les paramètres étaient limités à 50. (TNT-41717)
* La limite pour `categoryId` a augmenté, passant à 256 caractères. Auparavant, la limite était de 128 caractères.
* Les détails [!DNL Adobe Audience Manager] (AAM) suivants ont été ajoutés à l’API de diffusion :

   * UUID AAM : ID AAM interne utilisé pour identifier un utilisateur de manière unique.
   * dataPartnerId : ID d’un partenaire de données.
   * dataPartnerUserId : ID utilisateur fourni par un partenaire de données.

   Auparavant, l’API de diffusion incluait uniquement `dcsLocationHint` et `blob`. (TNT-41644)

## at.js 2.6.0 (27 juillet 2021)

* Ajout d’un attribut sécurisé aux cookies chaque fois que les paramètres at.js `secureOnly` sont définis sur `true`.
* Des jetons de réponse sont désormais disponibles lors de l’utilisation de `triggerView()`.
* Correction d’un problème relatif à l’événement `CONTENT_RENDERING_NO_OFFERS`. Désormais, cet événement est correctement déclenché lorsque [!DNL Target] ne renvoie aucun contenu.
* Les informations détaillées des mesures de clics [!DNL Analytics for Target] (A4T) sont correctement renvoyées lors de l’utilisation de requêtes `prefetch`.
* La génération de l’UUID n’utilise plus `Math.random()`, mais repose sur `window.crypto`.
* L’expiration du cookie `sessionId` est correctement étendue à chaque appel réseau.
* L’initialisation de l’affichage du cache des [!UICONTROL Applications à page unique] (SPA) est désormais correctement gérée et respecte les paramètres `viewsEnable`.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
