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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.

## Annonces

Avis importants :

* Le 20 février 2019, l&#39;infrastructure Adobe Target a été mise à niveau dans les régions EMEA, Japon et APAC afin de ne plus collecter les données à partir de la fin - utilisateurs disposant d&#39;anciens appareils ou de navigateurs Web qui ne prennent pas en charge TLS 1.1 ou une version ultérieure. Cette même mise à niveau est prévue pour la région Amérique du Nord pour **le 1 er avril 2019**. La migration vers TLS 1.2 améliore la sécurité. Il est important d&#39;examiner les détails et de planifier les modifications avec votre équipe informatique pour une transition fluide. Pour plus d&#39;informations, voir [Modifications du chiffrement TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] et [!DNL Adobe Marketing Cloud] ne prendront plus en charge Microsoft Internet Explorer 11 à partir de mars 2019. Cette modification a uniquement une incidence sur la création [!DNL Target]. Elle n’a aucun impact sur la diffusion d’expérience. Veuillez passer à Microsoft Edge ou à un autre navigateur. Pour plus d’informations, voir [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Compositeur d&#39;expérience visuelle d&#39;applications mobiles (14 mai 2019) {mobile-vec}

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d&#39;expérience visuelle d&#39;applications mobiles (VEC) | Le compositeur d&#39;expérience visuelle Mobile vous permet de créer des activités et de personnaliser le contenu sur les applications mobiles natives d&#39;une manière-elle-vous-même sans dépendances de développement continues et cycles de publication d&#39;application.<br>Pour plus d’informations, voir:<ul><li>[Compositeur d’expérience visuelle pour application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configuration du suivi des clics dans le VEC Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium 19.4.2 (30 avril 2019) {#release-19-4-2}

Cette version comprend les fonctionnalités, modifications et améliorations suivantes :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

### Mises à jour des fonctionnalités

| Fonction/amélioration | Description |
| --- | --- |
| [!UICONTROL Compositeur d’expérience visuelle] | Le [!UICONTROL compositeur] d&#39;expérience visuelle comprend les améliorations suivantes afin de rendre votre travail plus rapide et plus efficace :<ul><li>La fonction Chemin DOM est désormais disponible lorsque vous définissez le suivi des clics.<br>Pour plus d&#39;informations, voir [Suivi des clics](/help/c-activities/r-success-metrics/click-tracking.md#considerations).</li><li>Utilisez le panneau Styles pour afficher ou modifier la valeur des styles existants pour l&#39;élément sélectionné. Vous pouvez également ajouter d&#39;autres styles.<br>Pour accéder au panneau Styles, cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, puis cliquez [!UICONTROL sur Edition] &gt; [!UICONTROL Styles].<br>Le panneau Styles s&#39;affiche sur le côté droit du compositeur d&#39;expérience visuelle. Le panneau contient une liste de styles qui vous permet de modifier ou d&#39;ajouter à l&#39;élément sélectionné. Un éditeur CSS en temps réel permet d&#39;afficher les modifications et d&#39;ajouter des styles si vous maîtrisez l&#39;utilisation de feuilles de style en cascade (CSS) ou si vous recevez du code de votre développeur.<br>Pour plus d&#39;informations, voir [Styles](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) dans *Options du compositeur d&#39;expérience visuelle*.</li><li>L&#39;éditeur de texte enrichi prend désormais en charge les éléments HTML 5 imbriqués.<br>Les spécifications HTML 5 permettent de créer de nouvelles combinaisons de balises pour l&#39;imbrication. La version précédente de l&#39;éditeur de texte enrichi ne prenait pas en charge la nouvelle imbrication de balises comme autorisé par la spécification HTML 5. Par conséquent, tout élément imbriqué sélectionné dans le compositeur d&#39;expérience visuelle n&#39;a pas été correctement géré, ce qui a entraîné des modifications HTML indésirables. (TGT -33618)<br>Pour plus d&#39;informations, voir [Modification de texte/code HTML](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html) dans *les options du compositeur d&#39;expérience visuelle*.</li> |

### Améliorations, correctifs et modifications

* Nous avons amélioré le flux de travail lorsque vous supprimez des ressources à l’aide du compositeur d’expérience visuelle. Les fichiers supprimés sont désormais supprimés de la bibliothèque [!UICONTROL Offres] et de [!DNL Scene7] (le cas échéant). Les ressources supprimées ne s’affichent plus dans les résultats de la recherche. (TGT-31981)
* Vous pouvez désormais supprimer des dossiers de fichiers même s&#39;ils contiennent des images (dossiers non vides). (TGT-33265)

   Auparavant, vous ne pouviez pas supprimer un dossier vide dans la bibliothèque des offres d&#39;image Target ([!UICONTROL Offres] &gt; [!UICONTROL Offres images]). Vous obtiendriez un dossier « N&#39;est pas vide !  » » lorsque vous essayez de supprimer le dossier de l&#39;interface utilisateur. Grâce à cette fonctionnalité, nous ajoutons la fonctionnalité permettant d&#39;effectuer la suppression de dossiers pour supprimer un dossier entier contenant un nombre indéfini de fichiers et sous-dossiers à l&#39;intérieur. Cette fonctionnalité est également disponible dans l&#39;interface utilisateur de Target dans l&#39;interface utilisateur d&#39;Adobe Experience Cloud Assets.

   * Les dossiers non vides dans la bibliothèque d&#39;offres d&#39;image peuvent être supprimés. Si toutes les images du dossier ne sont pas référencées dans une activité, le dossier entier et son contenu sont supprimés. Si certaines images du dossier sont référencées dans une activité, toutes les images non référencées sont supprimées, mais les images et dossiers référencés contenant ces images sont conservés.
   * Le rendu des offres image dans le sélecteur d&#39;images est plus rapide et plus efficace.
   Pour plus d&#39;informations, voir [Utilisation du contenu dans la bibliothèque](/help/c-experiences/c-manage-content/assets-working.md). (TGT-32897)

* Nous avons amélioré le rendu des offres d’images dans le sélecteur de ressources. L’affichage et la sélection d’une image sont désormais plus rapides et plus efficaces. (TGT-32897)
* Nous avons amélioré la gestion des redirections vers les URL lorsque vous annulez le chargement d’une page dans le compositeur d’expérience visuelle. (TGT-33815)
* Après avoir sélectionné une collection [!UICONTROL de recommandations] dans le sélecteur Collections, vous devez maintenant cliquer sur [!UICONTROL le] bouton Enregistrer. Ce flux de travail est cohérent avec les autres flux de travail dans [!DNL Target]. (TGT-33205)
* Correction d&#39;un problème en raison duquel un petit ensemble de rapports sur les connaissances renvoyait 0 % des taux de conversion au lieu des taux de conversion réels. (TNT-32125)

## [!DNL Target] Standard/Premium 19.4.1 (15 avril 2019) {#release-19-4-1}

Cette version est une version de maintenance et inclut les modifications suivantes :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

* Mise à jour [!DNL Adobe Experience Cloud] de l&#39;interface utilisateur pour refléter les modifications de marque et de produit. (TGT-33546, TGT-33272 et TGT-33331)

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