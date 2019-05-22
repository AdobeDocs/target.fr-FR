---
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.
keywords: Notes de mise à jour, version préliminaire
seo-description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
seo-title: Notes de mise à jour de Target (actualisées)
solution: Target
title: Notes de mise à jour de Target (actualisées)
topic: Recommandations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e59b5f8fea0c0e1e79477764f6f870a50ee0bba4

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.

## Annonces

Avis importants :

* Le 20 février 2019, l&#39;infrastructure Adobe Target a été mise à niveau dans les régions EMEA, Japon et APAC afin de ne plus collecter les données à partir de la fin - utilisateurs disposant d&#39;anciens appareils ou de navigateurs Web qui ne prennent pas en charge TLS 1.1 ou une version ultérieure. Cette même mise à niveau est prévue pour la région Amérique du Nord pour **le 1 er avril 2019**. La migration vers TLS 1.2 améliore la sécurité. Il est important d&#39;examiner les détails et de planifier les modifications avec votre équipe informatique pour une transition fluide. Pour plus d&#39;informations, voir [Modifications du chiffrement TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] et [!DNL Adobe Marketing Cloud] ne prendront plus en charge Microsoft Internet Explorer 11 à partir de mars 2019. Cette modification a uniquement une incidence sur la création [!DNL Target]. Elle n’a aucun impact sur la diffusion d’expérience. Veuillez passer à Microsoft Edge ou à un autre navigateur. Pour plus d’informations, voir [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## [!DNL Target] Standard/Premium 19.5.1 (21 mai 2019) {#tgt-19-5-1}

Cette version inclut les fonctionnalités, modifications et améliorations suivantes :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

### Mises à jour des fonctionnalités

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle pour les applications monopages (Compositeur d&#39;expérience visuelle) | Le SPA VEC (compositeur d’expérience visuelle) a été amélioré comme suit afin que vous puissiez travailler plus vite et plus efficacement :<ul><li>Le fait de cliquer sur une action dans l&#39;application d&#39;une seule page met en évidence l&#39;élément sur le site où cette action sera appliquée. Chaque action du compositeur d&#39;expérience visuelle créée sous une vue comporte quatre icônes correspondantes : Informations, modification, déplacement et suppression. La nouvelle fonctionnalité Déplacer de cette version permet de déplacer l&#39;action vers un événement de chargement de page ou tout autre affichage existant dans le panneau Modifications. (TGT-33746)</li><li>Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans VEC, ou même si la page ne parvient pas à se charger complètement (par exemple, si un code personnalisé n’est plus fonctionnel). Les actions qu’il n’est pas possible de modifier avant le chargement complet du site sont désactivées dans l’interface utilisateur de Target. (TGT-33851 et TGT-34149)</li></ul>Pour plus d’informations, reportez-vous au [Compositeur d’expérience visuelle pour application d’une seule page (SPA)](/help/c-experiences/spa-visual-experience-composer.md). |

### Améliorations, correctifs et modifications

* Les icônes de la barre d’outils s’affichent correctement après l’annulation du chargement d’une page dans le compositeur d’expérience visuelle. Si des actions spécifiques ne peuvent être effectuées qu’après le chargement complet de la page, les icônes de la barre d’outils associée sont désactivées. (TGT-33811)

## Compositeur d&#39;expérience visuelle d&#39;applications mobiles (14 mai 2019) {mobile-vec}

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d&#39;expérience visuelle d&#39;applications mobiles (VEC) | Le compositeur d&#39;expérience visuelle Mobile vous permet de créer des activités et de personnaliser le contenu sur les applications mobiles natives d&#39;une manière-elle-vous-même sans dépendances de développement continues et cycles de publication d&#39;application.<br>Pour plus d’informations, voir:<ul><li>[Compositeur d’expérience visuelle pour application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configuration du suivi des clics dans le VEC Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vidéo : Compositeur d&#39;expérience visuelle d&#39;applications mobiles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d&#39;informations, voir [Notes de mise à jour d&#39;Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d&#39;autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |