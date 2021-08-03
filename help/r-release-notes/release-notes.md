---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Notes de mise à jour
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7badceff58e00f8406d24621534d24ea4067a224
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 88%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK et la bibliothèque JavaScript (at.js) de Target et d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js afin dʼéviter tout problème potentiel avec vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## API de diffusion Target (3 août 2021)

Cette version contient les améliorations suivantes :

* La limite des paramètres de mbox a été augmentée à 100 paramètres. La limite précédente était de 50 paramètres. (TNT-41717)
* La limite pour `categoryId` a été augmentée à 256 caractères. La limite précédente était de 128 caractères.
* Les [!DNL Adobe Audience Manager] (AAM) détails suivants ont été ajoutés à l’API de diffusion :

   * UUID AAM : Identifiant d’AAM interne utilisé pour identifier de manière unique un utilisateur.
   * dataPartnerId : L’identifiant d’un partenaire de données.
   * dataPartnerUserId : Identifiant utilisateur fourni par un partenaire de données.

   Auparavant, l’API de diffusion incluait uniquement `dcsLocationHint` et `blob`. (TNT-41644)

## at.js 2.6.0 (16 juillet 2021)

* Ajout d’un attribut sécurisé aux cookies chaque fois que les paramètres at.js `secureOnly` sont définis sur `true`.
* Des jetons de réponse sont désormais disponibles lors de l’utilisation de `triggerView()`.
* Correction d’un problème relatif à l’événement `CONTENT_RENDERING_NO_OFFERS`. Désormais, cet événement est correctement déclenché lorsque [!DNL Target] ne renvoie aucun contenu.
* Les informations détaillées des mesures de clics [!DNL Anlytics for Target] (A4T) sont correctement renvoyées lors de l’utilisation de requêtes `prefetch`.
* La génération de l’UUID n’utilise plus `Math.random()`, mais repose sur `window.crypto`.
* L’expiration du cookie `sessionId` est correctement étendue à chaque appel réseau.
* L’initialisation de l’affichage du cache des [!UICONTROL Applications à page unique] (SPA) est désormais correctement gérée et respecte les paramètres `viewsEnable`.

## [!DNL Target Standard/Premium] 21.6.1 (30 juin 2021)

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes : Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| [!UICONTROL Analytics for Target] (A4T) | Désormais, cliquer sur le lien « [!UICONTROL Afficher dans Analytics] » sur la page [!UICONTROL Rapports] d’une activité qui utilise [!DNL Analytics] comme source de compte rendu des performances (A4T) ouvre [!DNL Analysis Workspace]. Auparavant, le lien ouvrait le compte rendu des performances [!DNL Analytics]. (TGT-36959) |

## SDK Python 1.0.0 (16 juin 2021)

Le nouveau SDK Python [!DNL Adobe Target] avec des fonctionnalités de prise de décision sur lʼappareil est désormais disponible. Cette dernière version renforce la suite [!DNL Target] de SDK côté serveur. Ces SDK permettent lʼintégration à [!DNL Target] et une rentabilisation plus rapide, dans la langue de votre choix. Les intégrations côté serveur deviennent de plus en plus populaires, car le marché évolue vers un monde sans cookies dans lequel les données propriétaires sont précieuses. Les SDK Target sont disponibles dans les langages de programmation les plus courants du marché (Python, Java, JavaScript, C# et .Net).

Pour plus dʼinformations, voir la [documentation du SDK Python](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk) dans le [guide des SDK Adobe Target](https://adobetarget-sdks.gitbook.io/docs/).

## ![Badge SDK Web Adobe Experience Platform](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] version 2.5.0 (1er juin 2021)

Cette version du [!DNL Platform Web SDK] prend en charge les éléments suivants :

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge des redirections avec [!UICONTROL Analytics for Target] (A4T) | Le SDK Web Platform prend désormais en charge les redirections [!DNL Target] lors de lʼutilisation dʼ[A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Pour plus dʼinformations, consultez la page sur la mise en œuvre dʼ[Analytics for  [!DNL Target] ](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
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
