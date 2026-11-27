---
keywords: compositeur d’expérience visuelle;vec;wysiwyg
description: Découvrez les principes de base de l’utilisation du compositeur d’expérience visuelle (VEC) dans Adobe Target. Le compositeur d’expérience visuelle est un éditeur WYSIWYG qui vous permet de créer facilement des expériences personnalisées.
title: Comment utiliser le compositeur d’expérience visuelle (VEC) ?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%
---
# Prise en main du [!UICONTROL compositeur d’expérience visuelle] {#vec-overview}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment ouvrir le [!UICONTROL compositeur d’expérience visuelle] (VEC), modifier des expériences et gérer le chargement des pages.

>[!ENDSHADEBOX]

Le [!UICONTROL compositeur d’expérience visuelle] (VEC) de [!DNL Adobe Target] est un éditeur WYSIWYG qui permet de créer et de tester des expériences personnalisées directement sur des sites web et des pages web mobiles, sans modifier le code.

Les expériences et offres pour les activités [!DNL Target] sont créées en faisant glisser et en déposant des éléments, en permutant le contenu et en modifiant les mises en page. Le compositeur fournit également des options de modification d’HTML et de JavaScript.

## Configuration requise du navigateur {#browser-requirements}

[!DNL Safari] est pris en charge pour l’interface [!DNL Adobe Target]. Les activités basées sur des formulaires peuvent être créées dans [!DNL Safari] avec toutes les fonctionnalités, à l’exception du compositeur d’expérience visuelle et du [!UICONTROL compositeur d’expérience amélioré] (EEC). Si le compositeur d’expérience visuelle est ouvert dans [!DNL Safari], un recouvrement invite l’utilisateur à passer à [!DNL Google Chrome] pour modifier les expériences.

Les navigateurs tels que [!DNL Firefox] peuvent empêcher l’affichage dans le VEC des pages contenant du contenu mixte, par exemple une page non sécurisée au sein d’un site sécurisé. Si une page ne s&#39;affiche pas, cliquez sur l&#39;icône en regard de l&#39;URL dans la barre d&#39;adresse du navigateur, puis cliquez sur **[!UICONTROL Désactiver la protection sur cette page]**. Ce problème n’affecte pas l’affichage des pages pour les visiteurs du site.

## Ouvrir le compositeur d’expérience visuelle {#open-the-vec}

Pour définir la page qui s’ouvre par défaut dans le VEC, saisissez une URL de [!UICONTROL compositeur d’expérience visuelle] par défaut dans l’onglet [!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**. Si aucune URL par défaut n’est définie, le VEC s’ouvre avec une page vierge dans laquelle une URL peut être spécifiée.

![Page d’administration avec l’onglet Compositeur d’expérience visuelle mis en surbrillance, affichant l’URL par défaut, le compositeur d’expérience amélioré et les paramètres de chargement de contenu mixte](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Modifier des expériences {#edit-experiences}

### Afficher et nommer les expériences {#view-and-name-experiences}

Les onglets du rail **[!UICONTROL Expériences]** montrent comment la page s’affiche pour différentes audiences ou avec différentes expériences. Un nom explicite pour chaque expérience facilite son identification dans la liste. Par exemple, lors du test de la position du lien Accueil dans une barre de navigation, l’expérience dans laquelle il apparaît en premier peut être nommée « Lien d’accueil en premier ».

![La boîte de dialogue Renommer l’expérience commence par le lien Accueil, ouvert à partir de l’icône Renommer de l’expérience B](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### Sélection et modification d’éléments {#select-and-modify-elements}

Le déplacement du curseur sur la page met en surbrillance les éléments individuels avec une zone contextuelle. Cliquez sur un élément en surbrillance pour afficher les options d’édition de ce type d’élément. Par exemple, si vous sélectionnez une image et cliquez sur **[!UICONTROL Modifier l’offre d’image]** pour la remplacer, et si vous sélectionnez un bouton, sa couleur de texte peut être modifiée.

![Options d&#39;édition affichées au-dessus d&#39;une image sélectionnée](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

Le contenu d’un iframe incorporé dans la page ne peut pas être modifié. Pour modifier ce contenu, assurez-vous que le document iframe est activé pour [!DNL Target], puis chargez l’URL iframe directement dans le VEC.

Les modifications apportées à la structure de la page en dehors du compositeur d’expérience visuelle peuvent affecter les emplacements utilisés par une activité. Si ces emplacements changent, [!DNL Target] pourrait ne pas être en mesure de trouver les éléments qui ont été modifiés, ce qui peut entraîner des problèmes lors de la modification d’expériences.

### Parcourir et concevoir {#browse-and-design}

Cliquez sur **[!UICONTROL Parcourir]** pour accéder à une page accessible à partir de la page active, telle qu’une page d’expédition ou un panier, et y tester les modifications.

![Mode de navigation dans le VEC, avec le champ URL et les flèches Précédent et Suivant](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

En mode de navigation, les éléments qui apparaissent au survol, tels que les menus déroulants et les mini-paniers, sont également accessibles. Lorsque la page ou l’élément à modifier est atteint, cliquez sur **[!UICONTROL Conception]** pour modifier l’expérience.

Si un état de survol dépend de JavaScript, assurez-vous que l’option **[!UICONTROL Désactiver JavaScript]** n’est pas sélectionnée. JavaScript doit être activé pour modifier les éléments qui en dépendent.

Pour plus d’informations sur les options de modification disponibles, consultez les [options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

## Gérer le chargement des pages {#manage-page-loading}

Certaines options de modification restent disponibles lors du chargement d’une page ou après son échec. Le chargement de la page peut également être annulé pour accéder à ces options sans attendre.

### Modifiez une page pendant ou après son chargement {#loading}

Certaines modifications peuvent être apportées avant qu’une page ne finisse de se charger dans le VEC ou après son échec, par exemple parce que le code personnalisé ne fonctionne plus.

Les options de modification disponibles permettent ce qui suit :

* Apportez des modifications simples, telles que l’ajout de code personnalisé ou le changement de nom d’une expérience
* Copiez le code personnalisé existant d’une page qui n’est plus accessible.
* Apportez des modifications simples à une page qui ne peut pas se charger dans le compositeur d’expérience visuelle.

Le rail **[!UICONTROL Expériences]**, le rail **[!UICONTROL Composants]** et les options **[!UICONTROL Configurer]** restent accessibles pendant ou après le chargement de la page.

### Annulation du chargement d’une page dans le VEC {#cancel-loading}

L’annulation du chargement de la page dans le VEC permet de modifier l’activité sans attendre que le chargement de la page soit terminé. Cela s’avère utile pour :

* Apporter des modifications mineures aux modifications existantes
* Supprimer une ou plusieurs modifications existantes
* Insertion ou modification de code personnalisé
* Corriger une URL de page saisie de manière incorrecte
* Activer ou désactiver JavaScript avant de charger la page dans le compositeur d’expérience visuelle
* Ajoutez des règles de test de modèle aux critères de **[!UICONTROL Diffusion de page]**
* Remplacez le bouton (bascule) global [!UICONTROL Enhanced Experience Composer] (EEC) lors du chargement d’une page via EEC ou en mode iframe uniquement

Une fois le chargement de la page annulé, il est possible de basculer entre les expériences de l’activité sans attendre que la page se charge. Cliquez sur **[!UICONTROL Recharger]** pour afficher à nouveau la page dans le compositeur d’expérience visuelle.

>[!IMPORTANT]
>
>Si du code personnalisé est modifié ou si d’autres modifications sont apportées après l’annulation du chargement de la page, effectuez des tests d’assurance qualité (QA) pour vérifier que les modifications sont apportées comme prévu.

Pour arrêter le chargement de la page, cliquez sur **[!UICONTROL Annuler le chargement]** pendant le chargement de la page. La page reste déchargée pour cette activité pendant la session de modification en cours, sauf si elle est rechargée.

Cliquez sur **[!UICONTROL Recharger]** pour reprendre la gestion des expériences dans l’activité actuelle ou ajouter de nouvelles modifications.
