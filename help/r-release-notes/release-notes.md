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
source-git-commit: ce1758df44740213a2d9011ee43f84cb52f6a29d

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium.

## Annonces

Avis importants :

* Le 20 février 2019, l’infrastructure Adobe Target a été mise à niveau dans les régions EMEA, Japon et Asie-Pacifique afin de ne plus collecter les données d’utilisateurs finaux disposant d’anciens appareils ou de navigateurs Web qui ne prennent pas en charge TLS 1.1 ou une version ultérieure. Cette même mise à niveau est prévue pour la région Amérique du Nord pour **le 1er avril 2019**. La migration vers TLS 1.2 améliore la sécurité. Il est important que vous passiez en revue les détails et que vous planifiiez les changements avec votre équipe informatique pour une transition en douceur. Pour plus d’informations, voir [Modifications du chiffrement TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* [!DNL Target] et [!DNL Adobe Marketing Cloud] ne prendront plus en charge Microsoft Internet Explorer 11 à partir de mars 2019. Cette modification a uniquement une incidence sur la création [!DNL Target]. Elle n’a aucun impact sur la diffusion d’expérience. Veuillez passer à Microsoft Edge ou à un autre navigateur. Pour plus d’informations, voir [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Target Standard/Premium 19.6.1 (26 juin 2019)

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

(Les numéros de problèmes entre parenthèses sont réservés à une utilisation interne par Adobe.)

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle (VEC) | **Nouvelles options du menu** Compositeur d&#39;expérience visuelle : Lorsque vous cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, un menu affiche les options disponibles pour ce type d&#39;élément.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**Améliorations du suivi des clics**: Nous avons amélioré le processus de configuration du suivi des clics dans le compositeur d&#39;expérience visuelle et le compositeur d&#39;applications de page unique (VEC).<ul><li>Lors de la sélection d&#39;éléments à utiliser dans le suivi des clics, les noms de tous les éléments disponibles s&#39;affichent dans le panneau Modifications sur le côté droit, ce qui facilite et facilite la sélection des éléments souhaités.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Vous pouvez pointer sur ce nombre pour afficher les noms de tous les éléments sélectionnés. (TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| Compositeur d’expérience visuelle pour les applications monopages (SPA VEC) | **Processus guidé**: Un nouveau processus guidé vous aide à comprendre comment les paramètres de la règle de livraison de page doivent être configurés pour exécuter et exécuter une activité avec succès pour votre application de page unique. (TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**Modifications de clone**: Vous pouvez maintenant définir une modification à l&#39;aide du compositeur d&#39;expérience visuelle, puis cloner cette modification pour l&#39;utiliser dans d&#39;autres vues de votre application de page unique. (TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Compositeur d’expérience visuelle mobile | **Plusieurs versions d&#39;applications**: Vous pouvez désormais créer des activités pour plusieurs versions de votre application mobile. Vous gagnez ainsi du temps et des efforts lorsque les versions sont similaires et que vous n&#39;avez pas besoin de modifier significativement l&#39;interface utilisateur de l&#39;application. (TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Badge](/help/assets/premium.png) Premium de personnalisation automatisée et ciblage automatique | **Expérience spécifique comme contrôle**: Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d&#39;une activité de personnalisation automatisée ou de ciblage automatique. Cette fonctionnalité vous permet d&#39;acheminer le trafic de contrôle entier vers une expérience spécifique, en fonction du pourcentage d&#39;affectation du trafic configuré dans l&#39;activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle. L&#39;option de contrôle actuelle (expériences servies de manière aléatoire) restera disponible. (TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**Rapports sur la personnalisation des connaissances**: Le nommage convivial des marketeurs pour les attributs lorsqu&#39;un visiteur voit un élément de contenu spécifique à un emplacement spécifique fournit des informations plus significatives. (TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![Badge Premium](/help/assets/premium.png) Recommendations | Vous pouvez utiliser le bouton de basculement Recommander des articles précédemment achetés lors de la création de la logique Éléments récemment consultés. (TGT-34030)<br>Pour plus d&#39;informations, voir Éléments [récemment consultés](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) dans « Création de critères ».  » » |
| Stratégies de cookie Google Chrome samesite | Google a récemment annoncé qu&#39;à compter de Chrome 76, qui est découpé pour une version du 30 juillet 2019, les développeurs doivent spécifier explicitement quels cookies peuvent fonctionner sur plusieurs sites Web et quels cookies peuvent suivre les utilisateurs.<br>Tandis que le secteur fait des progrès pour créer un Web plus sécurisé pour les consommateurs, Target s&#39;engage à fournir des expériences personnalisées lors de la réunion et à dépasser les attentes en matière de confidentialité des visiteurs.<br>Voir [Stratégies de cookie Google Chrome samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md). |

## at. js version 2.1.0 (3 juin 2019)

Nous sommes ravis d&#39;annoncer les fonctionnalités fascinantes suivantes dans at. js 2.1.0 :

| Fonction/amélioration | Description |
| --- | --- |
| Prise en charge de la souscription Adobe | Adobe Opt-in est un moyen de simplifier les intégrations des solutions Adobe avec les plateformes de gestion des autorisations.<br>Pour plus d’informations sur la fonctionnalité Adobe Opt-in, voir [Confidentialité et protection générale des données (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Compatibilité CSP standard | at. js n&#39;utilise plus eval () pour exécuter JavaScript. |
| Consignation des analyses côté client | Donne aux clients un contrôle total sur la manière d&#39;envoyer des données d&#39;analyse à Adobe Analytics, que ce soit côté client ou côté serveur.<br>Pour plus d&#39;informations, voir [Connexion Analytics côté client](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) avant *de procéder à l&#39;implémentation*. |
| Envoi de notifications | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>Pour plus d&#39;informations, voir [adobe. target. sendnotifications (options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md). |
| Taille de fichier réduite | La taille d&#39;at. js est réduite de ~ 24 %. La taille de fichier plus petite améliore les performances de chargement des pages et réduit le temps de téléchargement du fichier at. js sur la page. |
| Mises à jour de la documentation d&#39;at. js | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

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
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |