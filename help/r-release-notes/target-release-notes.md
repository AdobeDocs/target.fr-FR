---
description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir de Target.
keywords: notes de mise à jour
seo-description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir d’Adobe Target
seo-title: Notes de mise à jour d'Adobe Target (bêta)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: bc44fd95263e7f2ad22e556a07468c9d7ed3ba8c

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 25 juin 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, les fonctionnalités et d&#39;autres informations peuvent être modifiées sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1 (26 juin 2019) {#tgt-19-6-1}

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle (VEC) | **Nouvelles options du menu** Compositeur d&#39;expérience visuelle : Lorsque vous cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, un menu affiche les options disponibles pour ce type d&#39;élément.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**Améliorations du suivi des clics**: Nous avons amélioré le processus de configuration du suivi des clics dans le compositeur d&#39;expérience visuelle et le compositeur d&#39;applications de page unique (VEC).<ul><li>Lors de la sélection d&#39;éléments à utiliser dans le suivi des clics, les noms de tous les éléments disponibles s&#39;affichent dans le panneau Modifications sur le côté droit, ce qui facilite et facilite la sélection des éléments souhaités.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Vous pouvez pointer sur ce nombre pour afficher les noms de tous les éléments sélectionnés. (TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| Compositeur d’expérience visuelle pour les applications monopages (SPA VEC) | **Processus guidé**: Un nouveau processus guidé vous aide à comprendre comment les paramètres de la règle de livraison de page doivent être configurés pour exécuter et exécuter une activité avec succès pour votre application de page unique. (TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**Modifications de clone**: Vous pouvez maintenant définir une modification à l&#39;aide du compositeur d&#39;expérience visuelle, puis cloner cette modification pour l&#39;utiliser dans d&#39;autres vues de votre application de page unique. (TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Compositeur d’expérience visuelle mobile | **Plusieurs versions d&#39;applications**: Vous pouvez désormais créer des activités pour plusieurs versions de votre application mobile. Vous gagnez ainsi du temps et des efforts lorsque les versions sont similaires et que vous n&#39;avez pas besoin de modifier significativement l&#39;interface utilisateur de l&#39;application. (TGT-34231) |
| ![Badge](/help/assets/premium.png) Premium de personnalisation automatisée et ciblage automatique | **Expérience spécifique comme contrôle**: Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d&#39;une activité de personnalisation automatisée ou de ciblage automatique. Cette fonctionnalité vous permet d&#39;acheminer le trafic de contrôle entier vers une expérience spécifique, en fonction du pourcentage d&#39;affectation du trafic configuré dans l&#39;activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle. L&#39;option de contrôle actuelle (expériences servies de manière aléatoire) restera disponible. (TGT-32801 &amp; TGT-26572)<br>**Personalization Insights reports**: The marketer-friendly naming for attributes when a visitor sees a specific piece of content in a specific location provides more meaningful information. (TGT-33326 et TGT-34957) |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
