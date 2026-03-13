---
keywords: compositeur d’expérience visuelle;vec;wysiwyg
description: Découvrez les principes de base de l’utilisation du compositeur d’expérience visuelle (VEC) dans Adobe Target. Le compositeur d’expérience visuelle est un éditeur WYSIWYG qui vous permet de créer facilement des expériences personnalisées.
title: Comment utiliser le compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: f984f2db3ccfb02629ddfd4f3c5f957256bd9f6a
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 43%

---

# [!UICONTROL Visual Experience Composer] (VEC)

L’éditeur [!UICONTROL Visual Experience Composer] (VEC) dans [!DNL Adobe Target] est un éditeur WYSIWYG qui permet aux clients de créer et de tester des expériences personnalisées directement sur leurs sites Web ou pages Web mobiles sans avoir besoin de modifier le code.

>[!NOTE]
>
>La version [!DNL Target Standard/Premium] 25.2.1 (17 février 2025) incluait une version mise à jour de la CVE. Pour plus d&#39;informations sur la façon dont la CVE mise à jour diffère de la version précédente, voir [Modifications de Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md). Pour obtenir une vue d&#39;ensemble des différentes options dans la mise à jour VEC, consultez [Options de Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

Le VEC vous permet de créer et de tester facilement des expériences et des offres personnalisées dans le contexte du site. Vous pouvez créer des expériences et des offres pour les activités [!DNL Target] en faisant glisser et en déposant, en échangeant et en modifiant la mise en page et le contenu d&#39;une page web (ou offre) ou d&#39;une page web mobile.

Le compositeur d’expérience visuelle constitue l’une des principales fonctionnalités d’ [!DNL Target]. Le VEC permet aux marketeurs et aux concepteurs de créer et de modifier du contenu à l’aide d’une interface visuelle. Il est possible d’effectuer la plupart des choix de conception sans modifier directement le code. Il est également possible de modifier le code HTML et JavaScript à l’aide des options d’édition du compositeur.

Dans l’onglet [!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**, vous pouvez saisir l’URL [!UICONTROL Visual Experience Composer] par défaut.

Cette URL détermine votre point de départ lors de l’ouverture de VEC. Si vous ne saisissez pas d’URL par défaut, vous commencez avec une page vierge lorsque vous ouvrez l’éditeur, puis vous pouvez spécifier une URL.

![Mise en surbrillance de VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>Certains navigateurs, tels que [!DNL Firefox], peuvent bloquer l’affichage d’une page dans le compositeur d’expérience visuelle si la page contient du contenu mixte (par exemple, une page non sécurisée dans un site sécurisé). Si votre page ne s&#39;affiche pas, cliquez sur l&#39;icône en regard de l&#39;URL dans la barre d&#39;adresse du navigateur et cliquez sur **[!UICONTROL Disable protection on this page]**. Ce problème n’a aucun impact sur l’affichage de vos pages pour les visiteurs du site.

Le contenu dans un iframe sur la page ne peut pas être modifié dans VEC. Pour modifier le contenu d&#39;un iframe, assurez-vous que le document iframe est activé pour [!DNL Target], puis chargez cette URL iframe dans le VEC.

Vous pouvez utiliser les onglets du rail [!UICONTROL Experiences] pour afficher votre page telle qu&#39;elle apparaîtrait à différents publics ou avec différentes expériences. Vous pouvez fournir un nom pour chaque expérience. Par exemple, si vous testez l’emplacement du lien Accueil dans votre barre de navigation, vous pouvez nommer une expérience dans laquelle le lien Accueil apparaît en premier. Par exemple, « Home link » pour faciliter l’identification des expériences dans la liste.

>[!NOTE]
>
>Les modifications apportées à la structure d’une page qui affectent les emplacements utilisés dans une activité créée sur cette page peuvent entraîner des problèmes d’expérience de modification. Si un emplacement a été modifié en dehors du VEC, [!DNL Target] ne pourra peut-être pas trouver l&#39;emplacement où le contenu a été modifié.

Lorsque vous déplacez votre pointeur dans la page, une zone contextuelle le suit, mettant en surbrillance les éléments de la page.

<!--
Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)
-->

Cliquez sur un élément en surbrillance pour accéder à un menu d’options disponibles pour ce type d’élément. Par exemple, vous pouvez cliquer sur une image et sélectionner **[!UICONTROL Change Image]** pour la remplacer par une autre image. Ou cliquez sur un bouton et modifiez la couleur du texte.

Vous pouvez également cliquer sur **[!UICONTROL Browse]**, puis accéder à une page disponible sur la page principale, telle qu’une page d’expédition ou un panier, et tester les modifications sur cette page. Vous pouvez également accéder aux éléments de la page qui sont disponibles lorsque vous passez le curseur tels que les menus des fenêtres déroulantes et les mini-paniers. Lorsque vous avez terminé de naviguer vers la page, cliquez sur **[!UICONTROL Design]** pour modifier l&#39;expérience. Par exemple, vous souhaitez peut-être modifier la conception d’une liste déroulante de panier d’achat ou d’un carrousel d’images.

>[!NOTE]
>
>Si un état de survol dépend de JavaScript, assurez-vous que **[!UICONTROL Disable JavaScript]** n&#39;est pas sélectionné. JavaScript doit être activé pour modifier des éléments JavaScript.

Pour obtenir des informations sur les options disponibles dans le compositeur d’expérience visuelle, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Vous pouvez effectuer certaines modifications sur une page pendant le chargement de la page (ou même si la page ne parvient pas à se charger complètement), ou vous pouvez annuler le chargement des pages dans VEC. Pour obtenir plus d’informations, voir :

* [Modifier une page pendant son chargement ou après l’échec de son chargement](#loading)
* [Annuler le chargement d&#39;une page dans le VEC](#cancel-loading)

## Modifiez une page pendant ou après son chargement {#loading}

Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans VEC, ou même si la page ne parvient pas à se charger complètement (par exemple, si un code personnalisé n’est plus fonctionnel).

Raisons pour lesquelles vous pouvez accéder à une page ou la modifier pendant qu’elle est chargée dans VEC ou bien si elle ne parvient pas à se charger complètement :

* Vous souhaitez apporter une modification simple à une page, par exemple pour ajouter du code personnalisé ou modifier le nom d’une expérience
* Vous souhaitez copier du code personnalisé existant dans une page qui n’est plus accessible
* Vous savez qu’une page ne se charge pas dans VEC, mais vous souhaitez effectuer des modifications simples.

Pendant le chargement de la page (ou après l’échec du chargement), les options du rail [!UICONTROL Experiences], du rail [!UICONTROL Components] et de [!UICONTROL Configure] sont accessibles.

## Annuler le chargement d&#39;une page dans le VEC {#cancel-loading}

Vous pouvez annuler le chargement d’une page dans VEC pour déverrouiller la modification de l’activité sans attendre le chargement de la page. Cette fonctionnalité permet d’économiser du temps et d’effectuer des modifications ou d’insérer du code personnalisé plus efficacement sans attendre le chargement de la page dans VEC.

Voici quelques raisons pour lesquelles vous souhaitez annuler le chargement des pages dans VEC :

* Vous souhaitez apporter des modifications mineures aux modifications existantes
* Vous souhaitez supprimer une ou plusieurs modifications existantes
* Vous souhaitez insérer ou modifier du code personnalisé
* Vous avez saisi par erreur une URL erronée pour la page
* Vous souhaitez activer ou désactiver JavaScript avant de charger la page dans VEC
* Vous souhaitez ajouter d&#39;autres règles de test de modèles aux critères [!UICONTROL Page Delivery]
* Vous souhaitez remplacer le bouton (bascule) [!UICONTROL Enhanced Experience Composer] global (EEC) lors du chargement d’une page via EEC ou iframe-only

Si vous annulez le chargement de la page dans le VEC, vous pouvez basculer entre les expériences de l’activité sans attendre que la page se charge. Pour afficher à nouveau la page dans le compositeur d’expérience visuelle, vous devez cliquer sur le bouton **[!UICONTROL Reload]** .

>[!IMPORTANT]
>
>Gardez à l’esprit que lorsque le code personnalisé ou toute modification est effectué, vous devez vous assurer que le codage ou les modifications sont effectués correctement en choisissant d’annuler le chargement dans VEC. Assurez-vous d’effectuer un contrôle qualité adéquat pour vous assurer que votre code personnalisé et toute autre modification sont diffusés comme prévu.

Pour annuler le chargement d&#39;une page dans le VEC, cliquez sur le bouton **[!UICONTROL Cancel Loading]** pendant le chargement de la page. La page ne se charge pas dans VEC pour cette activité durant la session de modification en cours.

Pour continuer à gérer les expériences dans l&#39;activité actuelle ou pour ajouter de nouvelles modifications, vous devez cliquer sur le bouton **[!UICONTROL Reload]**.
