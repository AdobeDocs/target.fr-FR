---
description: Informations sur l’utilisation du compositeur d’expérience visuelle (VEC).
seo-description: Informations sur l’utilisation du compositeur d’expérience visuelle (VEC) dans Adobe Target.
seo-title: Compositeur d’expérience visuelle (VEC) Adobe Target
title: Compositeur d’expérience visuelle (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# Compositeur d’expérience visuelle{#visual-experience-composer-vec}

Informations sur l’utilisation du compositeur d’expérience visuelle (VEC).

Le compositeur d&#39;expérience visuelle est l&#39;une des principales caractéristiques de [!DNL Adobe Target]. Le compositeur d&#39;expérience visuelle est un éditeur qui permet aux spécialistes du marketing et aux concepteurs de créer et de modifier du contenu à l&#39;aide d&#39;une interface visuelle. Il est possible d’effectuer la plupart des choix de conception sans modifier directement le code. Il est également possible de modifier le code HTML et JavaScript à l’aide des options d’édition du compositeur.

Dans Target, sous l’onglet **[!UICONTROL Configuration]** &gt; **[!UICONTROL Préférences]**, vous pouvez saisir l’URL du compositeur d’expérience visuelle par défaut.

![Paramètres d&#39;URL du compositeur d&#39;expérience visuelle par défaut](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

Cette URL détermine l&#39;emplacement où vous commencez lorsque vous ouvrez le compositeur d&#39;expérience visuelle. Si vous ne saisissez pas d’URL par défaut, vous commencez par une page vide, puis vous spécifiez une URL.

>[!NOTE]
>
>Certains navigateurs, tels que Firefox, peuvent empêcher l&#39;affichage d&#39;une page dans le compositeur d&#39;expérience visuelle si la page contient du contenu mixte (par exemple, une page non sécurisée sur un site sécurisé). Si votre page ne s&#39;affiche pas, cliquez sur l&#39;icône en regard de l&#39;URL dans la barre d&#39;adresses du navigateur et cliquez sur **[!UICONTROL Désactiver la protection de cette page]**. Ce problème n’a aucun impact sur l’affichage de vos pages pour les visiteurs du site.

Le contenu d&#39;un iframe sur la page ne peut pas être modifié dans le compositeur d&#39;expérience visuelle. Pour modifier le contenu dans un iframe, assurez-vous que le document iframe est compatible Target, puis chargez cette URL d&#39;iframe dans le compositeur d&#39;expérience visuelle.

Vous pouvez utiliser les menus déroulants se trouvant dans la partie supérieure de la page pour afficher votre page telle qu’elle apparaîtrait aux différentes audiences ou avec différentes expériences. Vous pouvez attribuer un nom à chaque expérience dans la deuxième liste déroulante. Par exemple, si vous testez l’emplacement du lien Accueil dans la barre de navigation, vous pouvez nommer une expérience pour laquelle le lien Accueil s’affiche tout d’abord comme « lien Accueil » pour faciliter l’identification des expériences dans la liste.

>[!NOTE]
>
>Remarque : Les modifications apportées à la structure d’une page qui affectent les emplacements utilisés dans une activité créée sur cette page peuvent créer des problèmes avec l’édition des expériences. Si un emplacement a été modifié en dehors du compositeur d&#39;expérience visuelle, Target peut ne pas trouver l&#39;emplacement de modification du contenu.

Lorsque vous déplacez votre pointeur dans la page, une zone contextuelle le suit, mettant en surbrillance les éléments de la page.

![Mise en surbrillance du compositeur d&#39;expérience visuelle](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Cliquez sur l&#39;icône **[!UICONTROL Overlays]** pour modifier la manière dont la mise en surbrillance s&#39;affiche. Par exemple, vous pouvez choisir de mettre uniquement en surbrillance les images, les liens, les mbox régionales, les modifications ou JavaScript. Vous pouvez modifier la couleur du surlignage. Vous pouvez également spécifier une couleur de surbrillance et un type de remplissage à utiliser pour différents types d’éléments.

![Modification des paramètres d&#39;incrustation](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Cliquez sur un élément surligné pour un menu d&#39;options disponibles pour ce type d&#39;élément. Par exemple, vous pouvez cliquer sur une image et choisir **[!UICONTROL Edition &gt; Texte/Code HTML]** pour modifier le texte ou cliquer sur un bouton et modifier la couleur d&#39;arrière-plan. Vous pouvez utiliser les boutons situés dans la partie supérieure gauche de la page pour activer ou désactiver les recouvrements.

Vous pouvez également cliquer sur **[!UICONTROL Parcourir]**, puis accéder à une page qui est disponible depuis la page principale, telle la page d’expédition ou le panier d’achat, et tester les modifications sur cette page. Vous pouvez également accéder aux éléments de la page qui sont disponibles lorsque vous passez le curseur tels que les menus des fenêtres déroulantes et les mini-paniers. Lorsque vous avez terminé de parcourir la page, cliquez sur **[!UICONTROL Composer]pour modifier l’expérience.** Par exemple, vous souhaitez peut-être modifier la conception d’une liste déroulante de panier d’achat ou d’un carrousel d’images.

>[!NOTE]
>
>Remarque : Si un état sensitif dépend de JavaScript, assurez-vous que l’option **[!UICONTROL Désactiver JavaScript]** n’est pas sélectionnée. JavaScript doit être activé pour modifier des éléments JavaScript.

Pour plus d&#39;informations sur les options disponibles dans le compositeur d&#39;expérience visuelle, voir [Options du compositeur d&#39;expérience visuelle](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Vous pouvez effectuer certaines modifications sur une page pendant le chargement de la page (ou après le chargement de la page), ou vous pouvez annuler le chargement des pages dans le compositeur d&#39;expérience visuelle. Pour obtenir plus d’informations, voir :

* [Modifier une page pendant le chargement de la page ou après le chargement de la page](#loading)
* [Annulation du chargement d&#39;une page dans le compositeur d&#39;expérience visuelle](#cancel-loading)

## Modifier une page pendant le chargement de la page ou après le chargement de la page {#loading}

Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans VEC, ou même si la page ne parvient pas à se charger complètement (par exemple, si un code personnalisé n’est plus fonctionnel).

Raisons pour lesquelles vous pouvez accéder à une page ou la modifier pendant qu&#39;elle est chargée dans le compositeur d&#39;expérience visuelle ou après son chargement :

* Vous souhaitez apporter une modification simple à une page, par exemple pour ajouter du code personnalisé ou modifier le nom d&#39;une expérience
* Vous souhaitez copier le code personnalisé existant d&#39;une page qui n&#39;est plus accessible
* Vous savez qu&#39;une page ne se charge pas dans le compositeur d&#39;expérience visuelle, mais vous souhaitez effectuer des modifications simples.

Pendant le chargement de la page (ou après son chargement), le panneau [!UICONTROL Expériences] , [!UICONTROL le] panneau Modifications et les paramètres en haut de l&#39;expérience (Overlays, Modifications, Configurer, etc.) sont tous accessibles.

L&#39;illustration suivante montre que vous pouvez insérer du code personnalisé ou effectuer d&#39;autres actions pendant le chargement de la page :

![Chargement de page](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Annulation du chargement d&#39;une page dans le compositeur d&#39;expérience visuelle {#cancel-loading}

Vous pouvez annuler le chargement d&#39;une page dans le compositeur d&#39;expérience visuelle pour déverrouiller la modification de l&#39;activité sans attendre le chargement de la page. Cette fonctionnalité permet d&#39;économiser du temps et d&#39;effectuer des modifications ou d&#39;insérer du code personnalisé plus efficacement sans attendre le chargement de la page dans le compositeur d&#39;expérience visuelle.

Voici quelques raisons pour lesquelles vous souhaitez annuler le chargement des pages dans le compositeur d&#39;expérience visuelle :

* Vous souhaitez apporter des modifications mineures aux modifications existantes
* Vous souhaitez supprimer une ou plusieurs modifications existantes.
* Vous souhaitez insérer ou modifier du code personnalisé
* Vous avez saisi par erreur une URL erronée pour la page.
* Vous souhaitez activer ou désactiver JavaScript avant de charger la page dans le compositeur d&#39;expérience visuelle
* Vous souhaitez ajouter d&#39;autres règles de test de modèle aux critères de diffusion de page
* Vous souhaitez remplacer le basculement de compositeur d&#39;expérience amélioré global (EEC) lors du chargement d&#39;une page via la norme EEC ou iframe-only peut varier d&#39;une page à l&#39;autre.

Après avoir annulé le chargement des pages dans le compositeur d&#39;expérience visuelle, vous pouvez basculer entre les expériences de l&#39;activité sans attendre le chargement de la page. Pour afficher à nouveau la page du compositeur d&#39;expérience visuelle, vous devez cliquer sur le **[!UICONTOL bouton Actualiser]** .

>[!IMPORTANT]
>
>Gardez à l&#39;esprit que lorsque le code personnalisé ou toute modification est effectué, vous devez vous assurer que le codage ou les modifications sont effectués correctement en choisissant d&#39;annuler le chargement dans le compositeur d&#39;expérience visuelle. Assurez-vous d&#39;effectuer un contrôle qualité adéquat pour vous assurer que votre code personnalisé et toute autre modification sont diffusés comme prévu.

Pour annuler le chargement d&#39;une page dans le compositeur d&#39;expérience visuelle, cliquez sur le **[!UICONTROL bouton Annuler le chargement]** pendant le chargement de la page. La page ne se charge pas dans le compositeur d&#39;expérience visuelle pour cette activité durant la session de modification en cours.

![Bouton Annuler le chargement](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

Pour continuer la gestion des expériences dans l&#39;activité actuelle ou pour ajouter de nouvelles modifications, vous devez cliquer sur le bouton **[!UICONTROL Actualiser]** .

![Bouton Recharger](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>Il existe actuellement un problème connu avec cette fonctionnalité qui sera corrigé dans la prochaine version. Pour plus d&#39;informations, voir « Annuler le chargement d&#39;une page dans le compositeur d&#39;expérience visuelle » sur les [problèmes connus et la page Problèmes](/help/r-release-notes/known-issues-resolved-issues.md#cancel) résolus.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d&#39;informations sur les concepts abordés dans cet article.

### Compositeur d’expérience visuelle (7:17)

La vidéo ci-après fournit des informations sur l’utilisation des options du compositeur d’expérience visuelle.

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Compositeur d’expérience visuelle (1 de 2) (07:17)

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Compositeur d’expérience visuelle (2 de 2) (07:29)

* Attribution d’un nouveau nom à une expérience et duplication d’une expérience
* Création d’une expérience de redirection
* Ciblage d’une activité sur une URL unique ou un groupe d’URL
* Création d’une activité multipage
* Prévisualisation et création d’expérience pour des sites web réactifs
* Utilisation de superposition pour mettre en avant des types d’éléments

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Heures de bureau : compositeur d’expérience visuelle

Cette vidéo est un enregistrement des « [Heures de bureau](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Fonctionnement du VEC
* Comment éviter les problèmes courants liés au VEC
* Solutions de contournement utilisables avec le VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)