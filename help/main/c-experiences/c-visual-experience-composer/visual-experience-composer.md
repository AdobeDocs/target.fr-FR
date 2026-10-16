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
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL Compositeur d’expérience visuelle] (VEC)

Le [!UICONTROL compositeur d’expérience visuelle] (VEC) d’[!DNL Adobe Target] est un éditeur WYSIWYG qui permet de créer et de tester des expériences personnalisées directement sur des sites web et des pages web mobiles sans modifier le code.

Créez des expériences et des offres pour les activités de [!DNL Target] en faisant glisser et en déposant des éléments, en permutant le contenu et en modifiant les mises en page. Le compositeur fournit également des options de modification d’HTML et de JavaScript.

## Configuration requise du navigateur {#browser-requirements}

[!DNL Safari] est pris en charge pour l’interface [!DNL Adobe Target]. Vous pouvez créer des activités basées sur des formulaires dans [!DNL Safari] et utiliser toutes les fonctionnalités, à l’exception du VEC et du [!UICONTROL Enhanced Experience Composer] (EEC). Si vous ouvrez le compositeur d’expérience visuelle dans [!DNL Safari], un recouvrement vous invite à passer à [!DNL Google Chrome] pour modifier les expériences.

Les navigateurs tels que [!DNL Firefox] peuvent empêcher l’affichage dans le compositeur d’expérience visuelle des pages contenant du contenu mixte, par exemple une page non sécurisée au sein d’un site sécurisé. Si une page ne s’affiche pas, cliquez sur l’icône en regard de l’URL dans la barre d’adresse du navigateur, puis cliquez sur **[!UICONTROL Désactiver la protection sur cette page]**. Ce problème n’affecte pas l’affichage des pages pour les visiteurs du site.

## Ouvrir le compositeur d’expérience visuelle {#open-the-vec}

Pour définir la page qui s’ouvre par défaut dans le VEC, saisissez une URL par défaut [!UICONTROL Compositeur d’expérience visuelle] dans l’onglet [!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**.

Si vous ne définissez pas d’URL par défaut, le VEC s’ouvre avec une page vierge dans laquelle vous pouvez spécifier une URL.

![Mise en surbrillance de VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Modifier des expériences {#edit-experiences}

### Afficher et nommer les expériences {#view-and-name-experiences}

Utilisez les onglets du rail [!UICONTROL Expériences] pour afficher la manière dont votre page s’affiche pour différentes audiences ou avec différentes expériences. Attribuez un nom explicite à chaque expérience pour en faciliter l’identification dans la liste.

Par exemple, lors du test de la position du lien Accueil dans votre barre de navigation, nommez l’expérience dans laquelle il apparaît en premier « Lien d’accueil en premier ».

![&#x200B; Renommer une expérience dans le rail Expériences &#x200B;](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### Sélection et modification d’éléments {#select-and-modify-elements}

Déplacez le curseur sur la page pour mettre en surbrillance des éléments individuels avec une zone contextuelle.

Cliquez sur un élément en surbrillance pour afficher les options d’édition de ce type d’élément. Par exemple, sélectionnez une image et cliquez sur **[!UICONTROL Modifier la source de l’image]** pour la remplacer, ou sélectionnez un bouton pour modifier la couleur de son texte.

![Options d&#39;édition pour un élément sélectionné](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

Vous ne pouvez pas modifier le contenu dans un iframe incorporé dans la page. Pour modifier ce contenu, assurez-vous que le document iframe est compatible avec le [!DNL Target], puis chargez l’URL iframe directement dans le VEC.

Les modifications apportées à la structure de la page en dehors du compositeur d’expérience visuelle peuvent affecter les emplacements utilisés par une activité. Si ces emplacements changent, [!DNL Target] ne pourrez peut-être pas trouver les éléments que vous avez modifiés, ce qui peut entraîner des problèmes lors de la modification d’expériences.

### Parcourir et concevoir {#browse-and-design}

Cliquez sur **[!UICONTROL Parcourir]** pour accéder à une page accessible à partir de la page active, telle qu’une page d’expédition ou un panier, et y tester les modifications.

![Mode de navigation dans le compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

En mode de navigation, vous pouvez également accéder aux éléments qui apparaissent au survol, tels que les menus déroulants et les mini-paniers. Lorsque vous atteignez la page ou l’élément à modifier, cliquez sur **[!UICONTROL Conception]** pour modifier l’expérience.

Si un état de survol dépend de JavaScript, assurez-vous que l’option **[!UICONTROL Désactiver JavaScript]** n’est pas sélectionnée. JavaScript doit être activé pour modifier les éléments qui en dépendent.

Pour plus d’informations sur les options de modification disponibles, voir [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

## Gérer le chargement des pages {#manage-page-loading}

Certaines options de modification restent disponibles lors du chargement d’une page ou après son échec. Vous pouvez également annuler le chargement de la page pour accéder à ces options sans attendre.

### Modifiez une page pendant ou après son chargement {#loading}

Vous pouvez apporter certaines modifications avant qu’une page ne finisse de se charger dans le VEC ou après son échec, par exemple, parce que le code personnalisé ne fonctionne plus.

Utilisez les options de modification disponibles pour :

* Apportez des modifications simples, telles que l’ajout de code personnalisé ou le changement de nom d’une expérience
* Copiez le code personnalisé existant d’une page qui n’est plus accessible.
* Apportez des modifications simples à une page qui ne peut pas se charger dans le compositeur d’expérience visuelle.

Les options [!UICONTROL Expériences] rail, [!UICONTROL Composants] rail et [!UICONTROL Configurer] restent accessibles pendant ou après le chargement de la page.

### Annulation du chargement d’une page dans le VEC {#cancel-loading}

Annulez le chargement de la page dans le VEC pour modifier l’activité sans attendre que le chargement de la page soit terminé.

L’annulation du chargement de la page est utile lorsque vous devez :

* Apporter des modifications mineures aux modifications existantes
* Supprimer une ou plusieurs modifications existantes
* Insertion ou modification de code personnalisé
* Corriger une URL de page saisie de manière incorrecte
* Activer ou désactiver JavaScript avant de charger la page dans le compositeur d’expérience visuelle
* Ajoutez des règles de test de modèle aux critères [!UICONTROL Diffusion de page]
* Remplacez le bouton global [!UICONTROL Enhanced Experience Composer] (EEC) lors du chargement d’une page via EEC ou en mode iframe uniquement

Après l’annulation du chargement de la page, vous pouvez basculer entre les expériences de l’activité sans attendre que la page se charge. Cliquez sur **[!UICONTROL Recharger]** pour afficher à nouveau la page dans le compositeur d’expérience visuelle.

>[!IMPORTANT]
>
>Si vous modifiez du code personnalisé ou apportez d’autres modifications après l’annulation du chargement de la page, effectuez des tests d’assurance qualité (QA) pour vérifier que vos modifications sont correctement appliquées.

Pour arrêter le chargement de la page, cliquez sur **[!UICONTROL Annuler le chargement]** pendant le chargement de la page. La page reste déchargée pour cette activité au cours de la session de modification en cours, sauf si vous la rechargez.

Cliquez sur **[!UICONTROL Recharger]** pour reprendre la gestion des expériences dans l’activité en cours ou ajouter de nouvelles modifications.
