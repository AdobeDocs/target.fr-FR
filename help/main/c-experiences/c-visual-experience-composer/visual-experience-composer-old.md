---
keywords: compositeur d’expérience visuelle;vec;wysiwyg
description: Découvrez les principes de base de l’utilisation du compositeur d’expérience visuelle (VEC) dans Adobe Target. Le compositeur d’expérience visuelle est un éditeur WYSIWYG qui vous permet de créer facilement des expériences personnalisées.
title: Comment utiliser le compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 73%

---

# Compositeur d’expérience visuelle (VEC)

Informations sur l’utilisation du [!UICONTROL Visual Experience Composer] (VEC) dans [!DNL Adobe Target].

Le compositeur d’expérience visuelle est une interface utilisateur de WYSIWYG qui vous permet de créer et de tester facilement des expériences et des offres personnalisées dans le contexte du site. Vous pouvez créer des expériences et des offres pour les activités Target en faisant glisser, en permutant et en modifiant la mise en page et le contenu d’une page Web (ou d’une offre) ou d’une page Web mobile.

Le compositeur d’expérience visuelle constitue l’une des principales fonctionnalités d’ [!DNL Adobe Target]. Le VEC permet aux marketeurs et aux concepteurs de créer et de modifier du contenu à l’aide d’une interface visuelle. Il est possible d’effectuer la plupart des choix de conception sans modifier directement le code. Il est également possible de modifier le code HTML et JavaScript à l’aide des options d’édition du compositeur.

Dans l’onglet **[!UICONTROL Administration]** de Target > **[!UICONTROL Visual Experience Composer]** , vous pouvez saisir l’URL du compositeur d’expérience visuelle par défaut.

![Paramètres d’URL de VEC par défaut](/help/main/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

Cette URL détermine votre point de départ lors de l’ouverture de VEC. Si vous ne saisissez pas d’URL par défaut, vous commencez par une page vide, puis vous spécifiez une URL.

>[!NOTE]
>
>Certains navigateurs tels que Firefox peuvent empêcher l’affichage d’une page dans VEC si celle-ci comporte du contenu mixte (une page non sécurisée d’un site sécurisé, par exemple). Si votre page ne s’affiche pas, cliquez sur l’icône en regard de l’URL dans la barre d’adresse du navigateur, puis cliquez sur **[!UICONTROL Disable protection on this page]**. Ce problème n’a aucun impact sur l’affichage de vos pages pour les visiteurs du site.

Le contenu dans un iframe sur la page ne peut pas être modifié dans VEC. Pour modifier du contenu dans un iframe, assurez-vous que le document iframe est activé pour Target, puis chargez cette URL d’iframe dans VEC.

Vous pouvez utiliser les menus déroulants se trouvant dans la partie supérieure de la page pour afficher votre page telle qu’elle apparaîtrait aux différentes audiences ou avec différentes expériences. Vous pouvez attribuer un nom à chaque expérience dans la deuxième liste déroulante. Par exemple, si vous testez l’emplacement du lien Accueil dans la barre de navigation, vous pouvez nommer une expérience pour laquelle le lien Accueil s’affiche tout d’abord comme « lien Accueil » pour faciliter l’identification des expériences dans la liste.

>[!NOTE]
>
>Remarque : Les modifications apportées à la structure d’une page qui affectent les emplacements utilisés dans une activité créée sur cette page peuvent créer des problèmes avec l’édition des expériences. Si un emplacement a été modifié en dehors de VEC, Target peut ne pas être en mesure de trouver l’emplacement où le contenu a été modifié.

Lorsque vous déplacez votre pointeur dans la page, une zone contextuelle le suit, mettant en surbrillance les éléments de la page.

![Mise en surbrillance de VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Cliquez sur l’icône **[!UICONTROL Overlays]** pour modifier l’affichage de la mise en surbrillance. Par exemple, vous pouvez choisir de mettre uniquement en surbrillance les images, les liens, les mbox régionales, les modifications ou JavaScript. Vous pouvez modifier la couleur du surlignage. Vous pouvez également spécifier une couleur de surbrillance et un type de remplissage à utiliser pour différents types d’éléments.

![Modification des paramètres de Recouvrement](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Cliquez sur un élément en surbrillance pour accéder à un menu d’options disponibles pour ce type d’élément. Par exemple, vous pouvez cliquer sur une image et sélectionner **[!UICONTROL Edit > Text/HTML]** pour modifier le texte, ou cliquer sur un bouton et modifier la couleur d’arrière-plan. Vous pouvez utiliser les boutons situés dans la partie supérieure gauche de la page pour activer ou désactiver les recouvrements.

Vous pouvez également cliquer sur **[!UICONTROL Browse]**, puis accéder à une page disponible sur la page principale, telle qu’une page d’expédition ou un panier, et tester les modifications sur cette page. Vous pouvez également accéder aux éléments de la page qui sont disponibles lorsque vous passez le curseur tels que les menus des fenêtres déroulantes et les mini-paniers. Lorsque vous avez terminé de naviguer vers la page, cliquez sur **[!UICONTROL Compose]** pour modifier l’expérience. Par exemple, vous souhaitez peut-être modifier la conception d’une liste déroulante de panier d’achat ou d’un carrousel d’images.

>[!NOTE]
>
>Si un état de survol dépend de JavaScript, assurez-vous que **[!UICONTROL Disable JavaScript]** n’est pas sélectionné. JavaScript doit être activé pour modifier des éléments JavaScript.

Pour obtenir des informations sur les options disponibles dans le compositeur d’expérience visuelle, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Vous pouvez effectuer certaines modifications sur une page pendant le chargement de la page (ou même si la page ne parvient pas à se charger complètement), ou vous pouvez annuler le chargement des pages dans VEC. Pour obtenir plus d’informations, voir :

* [Modifiez une page pendant ou après son chargement](#loading)
* [Annulation du chargement d’une page dans le VEC](#cancel-loading)

## Modifiez une page pendant ou après son chargement {#loading}

Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans VEC, ou même si la page ne parvient pas à se charger complètement (par exemple, si un code personnalisé n’est plus fonctionnel).

Raisons pour lesquelles vous pouvez accéder à une page ou la modifier pendant qu’elle est chargée dans VEC ou bien si elle ne parvient pas à se charger complètement :

* Vous souhaitez apporter une modification simple à une page, par exemple pour ajouter du code personnalisé ou modifier le nom d’une expérience
* Vous souhaitez copier du code personnalisé existant dans une page qui n’est plus accessible
* Vous savez qu’une page ne se charge pas dans VEC, mais vous souhaitez effectuer des modifications simples.

Lors du chargement de la page (ou après l’échec du chargement), le panneau [!UICONTROL Experiences], le panneau [!UICONTROL Modifications] et les paramètres en haut de l’expérience (Recouvrements, Modifications, Configuration, etc.) sont tous accessibles.

L’illustration suivante montre que vous pouvez insérer du code personnalisé ou effectuer d’autres actions pendant le chargement de la page :

![Chargement de page](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Annulation du chargement d’une page dans le VEC {#cancel-loading}

Vous pouvez annuler le chargement d’une page dans VEC pour déverrouiller la modification de l’activité sans attendre le chargement de la page. Cette fonctionnalité permet d’économiser du temps et d’effectuer des modifications ou d’insérer du code personnalisé plus efficacement sans attendre le chargement de la page dans VEC.

Voici quelques raisons pour lesquelles vous souhaitez annuler le chargement des pages dans VEC :

* Vous souhaitez apporter des modifications mineures aux modifications existantes
* Vous souhaitez supprimer une ou plusieurs modifications existantes
* Vous souhaitez insérer ou modifier du code personnalisé
* Vous avez saisi par erreur une URL erronée pour la page
* Vous souhaitez activer ou désactiver JavaScript avant de charger la page dans VEC
* Vous souhaitez ajouter d’autres règles de test de modèle aux critères de diffusion de page
* Vous souhaitez remplacer le basculement de compositeur d’expérience amélioré global (EEC) lors du chargement d’une page via EEC ou iframe-only peut varier d’une page à l’autre.

Après avoir annulé le chargement des pages dans VEC, vous pouvez basculer entre les expériences de l’activité sans attendre le chargement de la page. Pour afficher à nouveau la page dans le compositeur d’expérience visuelle, vous devez cliquer sur le bouton **[!UICONTROL Reload]** .

>[!IMPORTANT]
>
>Gardez à l’esprit que lorsque le code personnalisé ou toute modification est effectué, vous devez vous assurer que le codage ou les modifications sont effectués correctement en choisissant d’annuler le chargement dans VEC. Assurez-vous d’effectuer un contrôle qualité adéquat pour vous assurer que votre code personnalisé et toute autre modification sont diffusés comme prévu.

Pour annuler le chargement d’une page dans le VEC, cliquez sur le bouton **[!UICONTROL Cancel Loading]** pendant le chargement de la page. La page ne se charge pas dans VEC pour cette activité durant la session de modification en cours.

![Bouton Annuler le chargement](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

Pour continuer à gérer les expériences dans l’activité en cours ou ajouter de nouvelles modifications, vous devez cliquer sur le bouton **[!UICONTROL Reload]** .

![Bouton Recharger](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Compositeur d’expérience visuelle (1 de 2) (7:17) ![Badge de tutoriel](/help/main/assets/tutorial.png)

* Modification du contenu d’une page
* Modification de la mise en page d’une page

>[!VIDEO](https://video.tv.adobe.com/v/29229?captions=fre_fr)

### Compositeur d’expérience visuelle (2 de 2) (7:29) ![Badge de tutoriel](/help/main/assets/tutorial.png)

* Attribution d’un nouveau nom à une expérience et duplication d’une expérience
* Création d’une expérience de redirection
* Ciblage d’une activité sur une URL unique ou un groupe d’URL
* Création d’une activité multipage
* Prévisualisation et création d’expérience pour des sites web réactifs
* Utilisation de superposition pour mettre en avant des types d’éléments

>[!VIDEO](https://video.tv.adobe.com/v/30142?captions=fre_fr)

### Office Hours : Compositeur d’expérience visuelle ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo est un enregistrement des « [Heures de bureau](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7) », une initiative lancée par l’équipe d’assistance clientèle d’Adobe.

* Fonctionnement du VEC
* Comment éviter les problèmes courants liés au VEC
* Solutions de contournement utilisables avec le VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)
