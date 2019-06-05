---
description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir de Target.
keywords: notes de mise à jour
seo-description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir d’Adobe Target
seo-title: Notes de mise à jour de Target (préliminaires)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: b601e6cfa4061387352378271aa2c2e966584e40

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 28er mai 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer. Pour afficher des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être identiques ou différer selon le timing des versions.

## Target Standard/Premium 19.6.1 (25 juin 2019) {#tgt-19-6-1}

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle (VEC) | Lorsque vous cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, un menu affiche les options disponibles pour ce type d&#39;élément. <ul><li>Vous pouvez désormais utiliser [!DNL Styles > Background] l&#39;option permettant de modifier l&#39;image d&#39;arrière-plan et la couleur de l&#39;élément sélectionné. (TGT-15001)</li><li>Lorsque vous cliquez sur une image puis sur, [!DNL Replace With]deux nouvelles options s&#39;affichent : [!DNL HTML] et [le fragment d&#39;expérience](/help/c-experiences/c-manage-content/aem-experience-fragments.md).<br> Le remplacement d&#39;une image par HTML vous permet de contrôler totalement l&#39;élément sans avoir à sélectionner l&#39;élément parent pour accéder à l&#39;option HTML.<br>Les fragments d&#39;expérience vous permettent d&#39;insérer rapidement des éléments créés dans Adobe Experience Manager (AEM) dans les actionites Target. (TGT-34097)</li></ul> |
| Compositeur d&#39;expérience visuelle (VEC) d&#39;une seule page | <ul><li>Un nouveau processus guidé vous aide à comprendre comment les paramètres de la règle de livraison de page doivent être configurés pour exécuter et exécuter une activité avec succès pour votre application de page unique. (TGT-33718)</li><li>Vous pouvez maintenant définir une modification à l&#39;aide du compositeur d&#39;expérience visuelle, puis cloner cette modification pour l&#39;utiliser dans d&#39;autres vues de votre application de page unique. (TGT-33882)</li><li>Nous avons amélioré le processus de configuration du suivi des clics dans le compositeur d&#39;expérience visuelle.<br>Lors de la sélection d&#39;éléments à utiliser dans le suivi des clics, les noms de tous les éléments disponibles s&#39;affichent dans le panneau Modifications sur le côté droit, ce qui facilite et facilite la sélection des éléments souhaités.<br>La [!DNL Goals & Settings] page du workflow d&#39;activité guidée en trois parties affiche un nombre représentant le nombre d&#39;éléments sélectionnés pour le suivi des clics. Vous pouvez pointer sur ce nombre pour afficher les noms de tous les éléments sélectionnés. (TGT-33878) </li></ul> |
| Compositeur d&#39;expérience visuelle mobile (VEC) | <ul><li>Vous pouvez désormais créer des activités pour plusieurs versions de votre application mobile. Vous gagnez ainsi du temps et des efforts lorsque les versions sont très similaires et que vous n&#39;avez pas besoin de modifier significativement l&#39;interface utilisateur de l&#39;application. (TGT-34231)</li></ul> |
| ![Principales activités de](/help/assets/premium.png)<br>personnalisation automatisée (AP) et de ciblage automatique : expérience comme contrôle | <ul><li>Vous pouvez sélectionner une expérience à utiliser en tant que contrôle lors de la création d’une activité de PA ou de ciblage automatique. Cette fonctionnalité vous permet d’acheminer tout le trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’allocation de trafic configuré dans l’activité. Vous pouvez ensuite évaluer les performances des livraisons personnalisées par rapport à l’expérience de contrôle. (TGT-32801 et TGT-26572)</li></ul> |

### Améliorations, correctifs et modifications

* La `<BODY>` balise s&#39;affiche désormais dans le chemin DOM qui s&#39;affiche au bas du compositeur d&#39;expérience visuelle lorsque vous cliquez sur un élément de la page, ce qui vous permet d&#39;agir sur `<BODY>` la balise. (TGT-33736)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d&#39;autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
