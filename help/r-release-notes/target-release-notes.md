---
description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir de Target.
keywords: notes de mise à jour
seo-description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir d’Adobe Target
seo-title: Adobe Target release notes (prerelease)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 6 juin 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions.  Pour afficher des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être identiques ou différer selon le timing des versions.
>
>Les numéros de problème entre parenthèses sont utilisés pour [!DNL Adobe] une utilisation interne.

## Target Standard/Premium 19.6.1 (25 juin 2019) {#tgt-19-6-1}

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

### Compositeur d’expérience visuelle (VEC)

* **Nouvelles options du menu** Compositeur d&#39;expérience visuelle : Lorsque vous cliquez sur un élément de page dans le compositeur d&#39;expérience visuelle, un menu affiche les options disponibles pour ce type d&#39;élément.

   * **Styles &gt; Arrière-plan**: Vous pouvez maintenant utiliser [!UICONTROL l&#39;option Styles &gt; Arrière-plan] pour modifier l&#39;image d&#39;arrière-plan et la couleur de l&#39;élément sélectionné. (TGT-15001)

   * **[!UICONTROL Remplacer par &gt; HTML]et[!UICONTROL Remplacer par &gt; Fragment d&#39;expérience]**: Lorsque vous cliquez sur une image puis sur [!UICONTROL Remplacer par], deux nouvelles options s&#39;affichent :

      * **HTML**: Vous pouvez remplacer une image par HTML pour vous donner le contrôle total de l&#39;élément sans avoir à sélectionner l&#39;élément parent pour accéder à l&#39;option HTML.
      * **Fragment d&#39;expérience**: Vous pouvez remplacer une image par un fragment [d&#39;expérience Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) pour insérer rapidement des éléments créés dans AEM dans les activités Target. (TGT-34097)

* **Améliorations du suivi des clics**: Nous avons amélioré le processus de configuration du suivi des clics dans le compositeur d&#39;expérience visuelle et le compositeur d&#39;applications de page unique (VEC).

   * Lors de la sélection d&#39;éléments à utiliser dans le suivi des clics, les noms de tous les éléments disponibles s&#39;affichent dans le panneau Modifications sur le côté droit, ce qui facilite et facilite la sélection des éléments souhaités.
   * La page [!UICONTROL Objectifs et paramètres] du workflow d&#39;activité guidée en trois parties affiche un nombre représentant le nombre d&#39;éléments sélectionnés pour le suivi des clics. Vous pouvez pointer sur ce nombre pour afficher les noms de tous les éléments sélectionnés. (TGT-33878)

### Compositeur d&#39;expérience visuelle

* **Processus guidé**: Un nouveau processus guidé vous aide à comprendre comment les paramètres de la règle de livraison de page doivent être configurés pour exécuter et exécuter une activité avec succès pour votre application de page unique. (TGT-33718)

* **Modifications de clone**: Vous pouvez maintenant définir une modification à l&#39;aide du compositeur d&#39;expérience visuelle, puis cloner cette modification pour l&#39;utiliser dans d&#39;autres vues de votre application de page unique. (TGT-33882)

### Compositeur d&#39;expérience visuelle mobile

* **Plusieurs versions d&#39;applications**: Vous pouvez désormais créer des activités pour plusieurs versions de votre application mobile. Vous gagnez ainsi du temps et des efforts lorsque les versions sont similaires et que vous n&#39;avez pas besoin de modifier significativement l&#39;interface utilisateur de l&#39;application. (TGT-34231)

### Badge de personnalisation automatisée (AP) et de ciblage ![automatique Premium](/help/assets/premium.png)

* **Expérience spécifique comme contrôle**: Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d&#39;une activité de personnalisation automatisée ou de ciblage automatique. Cette fonctionnalité vous permet d&#39;acheminer le trafic de contrôle entier vers une expérience spécifique, en fonction du pourcentage d&#39;affectation du trafic configuré dans l&#39;activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle. L&#39;option de contrôle actuelle (expériences servies de manière aléatoire) restera disponible. (TGT-32801 et TGT-26572)

### Autres améliorations, correctifs et modifications

* La `<BODY>` balise s&#39;affiche désormais dans le chemin DOM qui s&#39;affiche au bas du compositeur d&#39;expérience visuelle lorsque vous cliquez sur un élément de la page, ce qui vous permet d&#39;agir sur `<BODY>` la balise. (TGT-33736)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d&#39;autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
