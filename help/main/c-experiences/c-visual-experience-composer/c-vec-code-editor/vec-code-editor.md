---
keywords: sélecteur css;code personnalisé;éditeur de code;éditeur d’expérience Web Mobile
description: Découvrez comment utiliser le panneau Modifications dans Adobe [!DNL Target] pour afficher les modifications de page et ajouter des modifications supplémentaires (sélecteur CSS, mbox et code personnalisé).
title: Quelles modifications puis-je apporter à ma page ?
feature: Visual Experience Composer (VEC)
exl-id: 23456a4b-9457-4f05-989e-a7c39ce17cc2
TQID: 'https://experienceleague.adobe.com/sOgNlejLNcnSwKf46-AHRXTLkM5Y6laB7QMLu5oYBUU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2194'
ht-degree: 22%
---
# Prise en main des modifications {#vec-code-editor}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment afficher, modifier, supprimer et ajouter des modifications dans le panneau **[!UICONTROL Modifications]** du [!UICONTROL compositeur d’expérience visuelle] (VEC) et comment utiliser le code personnalisé.

>[!ENDSHADEBOX]

Le panneau **[!UICONTROL Modifications]** dans [!DNL Adobe Target] affiche toutes les modifications apportées à la page dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) et autorise des modifications supplémentaires en cliquant sur chaque élément de la page et [en sélectionnant une action](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md). Chaque modification apparaît comme une action ou un élément distinct dans la liste **[!UICONTROL Modifications]**. Vous pouvez également ajouter des modifications directement, avec l’un des types suivants : sélecteur CSS, mbox et code personnalisé.

## Présentation des modifications {#modifications-overview}

La page **[!UICONTROL Modifications]** apporte de petites modifications au sélecteur que [!DNL Target] choisit lorsque le compositeur d’expérience visuelle configure la manière dont le contenu est diffusé. Le contenu ou un attribut HTML peut être modifié. Vous pouvez également modifier le code pour créer l’équivalent d’une offre HTML dans une mbox.

![Compositeur d’expérience visuelle avec le panneau Modifications à droite, répertoriant les actions de l’expérience B](../assets/vec_modif_1.png)

La page **[!UICONTROL Modifications]** peut être utilisée pour :

* Afficher une action effectuée dans le compositeur visuel.

  ![Panneau Modifications répertoriant trois actions : Définir HTML, Modifier la couleur d’arrière-plan et Définir HTML](assets/codeeditor_viewchange.png)

* Modifier une action existante. Accédez au menu avancé et sélectionnez **[!UICONTROL Modifier]**.

  ![Panneau Modifications avec l’icône Modifier mise en surbrillance en regard de la première action](assets/codeeditor_edit.png)

  Effectuez les modifications.

  ![Panneau Modifications avec l’action Définir HTML, l’#default_content Sélecteur d’éléments CSS et le champ Contenu](assets/codeeditor_changechange1.png)

* Supprimer une action existante. Accédez au menu avancé et sélectionnez **[!UICONTROL Supprimer la modification]**.

  ![Panneau Modifications avec l’icône Supprimer mise en surbrillance en regard de la première action](assets/codeditor_delete.png)

* Ajouter une nouvelle modification. Accédez au menu avancé **[!UICONTROL Modifications]** et sélectionnez **[!UICONTROL Ajouter une modification]**, puis spécifiez les modifications comme décrit dans [Ajouter des modifications](#add-modifications).

  ![Panneau Modifications avec le type de modification, le sélecteur d’éléments CSS, le type d’action et les champs de contenu](assets/codeeditor_new.png)

## Ajouter des modifications {#add-modifications}

Les modifications sont ajoutées à partir du panneau **[!UICONTROL Modifications]** pour l’expérience sélectionnée dans le compositeur d’expérience visuelle.

1. Pour afficher les **[!UICONTROL modifications]**, cliquez sur **[!UICONTROL Afficher les modifications]**.

   ![Icône Modifications mise en surbrillance dans la barre d’outils du compositeur d’expérience visuelle](assets/codeeditor_icon_big.png)

   Pour ouvrir le panneau **[!UICONTROL Modifications]** dans le compositeur d’expérience d’après les formulaires, créez ou modifiez une offre HTML. Pour plus d’informations, voir [Compositeur d’expérience basé sur un formulaire](/help/main/c-experiences/form-experience-composer.md).

1. Pour ajouter une modification :

   * Si aucune modification précédente n’a été apportée à l’expérience, cliquez sur **[!UICONTROL Ajouter une modification]** dans le panneau **[!UICONTROL Modifications]**.
   * S’il existe des modifications précédentes pour l’expérience, accédez au menu avancé **[!UICONTROL Modifications]** et sélectionnez **[!UICONTROL Ajouter une modification]**.

   Le panneau **[!UICONTROL Modifications]** affiche :

   ![Compositeur d’expérience visuelle avec le panneau Modifications ouvert sur la droite, affichant le type de modification, le sélecteur d’éléments CSS, le type d’action et les champs de contenu](assets/codeeditor_page_mods_add.png)

1. Dans la liste déroulante **[!UICONTROL Type de modification]**, choisissez le type souhaité :

   | Type de modification | Détails |
   |--- |--- |
   | Sélecteur CSS | Dans la zone **[!UICONTROL Sélecteur d’élément CSS]**, spécifiez l’élément CSS à modifier, sélectionnez un type d’action (**[!UICONTROL Définir le contenu]** ou **[!UICONTROL Définir l’attribut]**), puis renseignez les informations requises et le contenu souhaité. |
   | Mbox | Spécifiez le nom de la mbox et le contenu souhaité. |
   | Code personnalisé | Spécifiez un nom facultatif, sélectionnez ou désélectionnez la case à cocher **[!UICONTROL Ajouter du code dans la section `<HEAD>`]**, selon vos besoins, puis ajoutez le code personnalisé. Pour plus d&#39;informations, voir [Code personnalisé](#custom-code). |

   >[!NOTE]
   >
   >Les mbox ne sont plus prises en charge dans le VEC dans les pages qui utilisent at.js 2.*x*. Pour pallier ce problème :
   >
   >* Si vous utilisez at.js 2.*x*, ajoutez une modification de sélecteur CSS au lieu d’une modification de mbox, puis ajoutez le contenu sur le sélecteur utilisé par la mbox.
   >* Utiliser des activités basées sur des formulaires (fonctionne avec les mbox et at.js 1.*x* et at.js 2.*x*).
   >* Utilisez at.js 1.*x* dans le VEC.

1. Ajoutez d’autres modifications si nécessaire.

## Code personnalisé {#custom-code}

Le code personnalisé offre une interface non visuelle pour afficher, modifier ou ajouter de nouvelles actions dans le VEC, le compositeur d’expérience d’après les formulaires et l’éditeur d’offres HTML. Le panneau fournit une vue du code d’une expérience, afin de créer des expériences plus complexes, d’affiner les expériences existantes et de résoudre les problèmes.

Le code personnalisé est destiné aux utilisateurs avancés à l’aise avec HTML, JavaScript et CSS. L’affichage du code peut aider à ajuster ou affiner les modifications, ou résoudre des problèmes de sélecteur. Vous pouvez également l’utiliser pour ajouter un nouveau code personnalisé et des actions. Vous pouvez ajouter plusieurs codes personnalisés et chacun d’eux peut éventuellement être nommé.

![Panneau Modifications avec le type de modification Code personnalisé, le nom Couleur bleue, la case à cocher Ajouter du code dans la section head et le code](assets/codeeditor_custom.png)

Le code personnalisé se comporte comme suit :

* Lorsque **[!UICONTROL Ajouter du code dans la section `<HEAD>`]** est sélectionné, le code personnalisé est ajouté à la section `<head>` et son exécution n’attend pas les événements de chargement de corps ou de page. Ajoutez uniquement les éléments `<script>` et `<style>`. L’ajout de `<div>` balises et d’autres éléments peut entraîner l’affichage de `<head>` éléments restants dans `<body>`. Si at.js est utilisé, toutes les offres sont diffusées de manière asynchrone.
* Lorsque **[!UICONTROL Ajouter du code dans la section `<HEAD>`]** est désélectionné, le code personnalisé s’exécute immédiatement après la balise `<body>`. Encapsulez tout le code dans un seul `<div>` pour conserver la structure DOM. Si at.js est utilisé, toutes les offres sont diffusées de manière asynchrone.
* Si l’HTML pour `<BODY>` contient `<SCRIPT>` et `<DIV>`, alors `<DIV>` est ajouté à `<BODY>` et `<SCRIPT>` est exécuté dans `<HEAD>`. Un `<SCRIPT>` qui charge un fichier externe est également ajouté à `<HEAD>`.
* Les scripts sont exécutés de manière asynchrone. Cela signifie que `document.write` et les méthodes de script similaires ne peuvent pas être utilisés.
* Le code personnalisé est actuellement disponible pour les activités A/B et de ciblage d’expérience (XT) uniquement. Le code personnalisé est désactivé pour les superpositions et si une offre de redirection est appliquée.

Le code personnalisé prend en charge les cas d’utilisation suivants :

* Ajoutez des JavaScript, HTML ou CSS personnalisés à exécuter en haut de la page
* Afficher ou modifier le code généré par le compositeur d’expérience visuelle après avoir apporté des modifications
* Définition du contenu HTML pour un sélecteur (sélecteurs CSS uniquement)
* Définition d’un attribut sur un élément HTML
* Ajout du contenu d’offre à diffuser dans une mbox régionale
* Permutation sur DOM-ready, à l’aide de jQuery
* Permutation sur DOM-ready, sans jQuery (ne prend pas en charge Internet Explorer 8)
* Permutez avec l’interrogation DOM par le biais du plug-in « elementOnLoad »
* Redirection personnalisée

Le code personnalisé fournit :

* Des numéros de ligne pour une utilisation plus conviviale.
* Mise en surbrillance de la syntaxe pour éviter une syntaxe incorrecte pour les offres HTML.
* La possibilité de créer plusieurs codes personnalisés et de fournir un nom facultatif pour chacun d’eux. La création de plusieurs codes personnalisés facilite le débogage futur. Par exemple, au lieu de créer un code personnalisé unique pour accomplir plusieurs modifications, vous pouvez créer un code personnalisé distinct pour chaque modification, avec un nom explicite. Des codes personnalisés distincts rendent les modifications plus modulaires et faciles à gérer. Il n’est pas garanti que l’exécution de plusieurs codes personnalisés dans une activité se produise dans l’ordre dans lequel ils ont été créés.

Le panneau **[!UICONTROL Modifications]** divise l’écran entre le mode visuel et le mode code. Les deux modes restent synchronisés. Chaque modification apportée visuellement comporte une ligne correspondante dans l’affichage du code. De même, chaque modification validée dans l’affichage du code apparaît dans l’expérience visuelle. Cliquez sur une ligne dans l’affichage du code pour sélectionner l’élément correspondant dans la page visuelle.

Le code personnalisé prend en charge HTML, les scripts et les styles. Vous pouvez ajouter ou modifier tout code HTML ou script valide.

## Exemples de code personnalisé {#custom-code-examples}

Le panneau **[!UICONTROL Code personnalisé]** contient du code exécuté au début du chargement de la page. Le code JavaScript peut être exécuté dans la balise `<head>`. L&#39;exécution du code n&#39;attend pas que la balise `<body>` soit présente dans le DOM. Les sélecteurs pour les actions visuelles suivantes dépendent des éléments HTML ajoutés dans cet onglet.

Le panneau **[!UICONTROL Code personnalisé]** est généralement utilisé pour ajouter JavaScript ou CSS en haut de la page.

Utilisez l’onglet **[!UICONTROL Code personnalisé]** pour :

* Utiliser l’inline ou le lien JavaScript vers un fichier JavaScript

  Par exemple, pour modifier la couleur d’un élément :

  ```javascript
  <script type="text/javascript"> 
  document.getElementById("element_id").style.color = "blue"; 
  </script> 
  ```

* Configurer un inline ou un lien de style vers une feuille de style externe

  Par exemple, pour définir une classe pour un élément de superposition :

  ```html
  <style> 
  .overlay 
  { position: absolute; top:0; left: 0; right: 0; bottom: 0; background: red; } 
  </style> 
  ```

* Ajouter des extraits de code HTML pour définir de nouveaux éléments

  Par exemple, utilisez le fragment de code HTML suivant pour créer un recouvrement `<div>` qui utilise la classe CSS définie ci-dessus :

  ```html
  <div class="overlay"></div>
  ```

* Permutation sur DOM-ready, à l’aide de jQuery

  L&#39;exemple suivant suppose que jQuery est disponible sur le site web du client sur la page lorsque [!DNL Target] exécute les offres.

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  jQuery( document ).ready(function() { 
      jQuery("#default_content").html( "<span style='color:red'>Hello <strong>Again</strong></span>" ); 
      jQuery("#default_content").css("visibility","visible"); 
  }); 
  </script> 
  ```

* Permutation sur DOM-ready, sans jQuery (ne prend pas en charge Internet Explorer 8)

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  document.addEventListener("DOMContentLoaded", function(event) {  
      document.getElementById("default_content").innerHTML = "<span style='color:red'>Hello <strong>Again</strong></span>"; 
      document.getElementById("default_content").style.visibility="visible"; 
  }); 
  </script> 
  ```

* Redirection personnalisée qui transmet les paramètres existants, le paramètre `s_tnt` (pour l’ancienne intégration avec Analytics), le paramètre référent et la session mbox

  ```javascript
  <style type="text/css">body{display:none!important;}</style> 
  <script type="text/javascript"> 
   var qs='';window.location.search?qs=window.location.search+'&':qs='?'; 
   window.location.replace('//www.mywebsite.com/'+qs+'s_tnt=${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}&s_tntref='+encodeURIComponent(document.referrer)+'&mboxSession='+mboxFactoryDefault.getSessionId().getId()+''+window.location.hash+''); 
  </script> 
  ```

* Ajouter [!DNL Adobe Target] modèles d’expérience à utiliser dans le code personnalisé

  Les modèles d’expérience sont des exemples précodés avec des entrées configurables, utilisés pour exécuter des cas d’utilisation courants pour les spécialistes marketing. Ils sont fournis gratuitement aux développeurs et aux spécialistes du marketing comme point de départ pour exécuter des cas d’utilisation courants, par le biais du compositeur d’expérience visuelle ou du compositeur d’expérience d’après les formulaires. Les cas d’utilisation incluent les lightbox, les carrousels, les comptes à rebours, etc. Pour plus d’informations, consultez les [Modèles d’expérience](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/experience-templates.md).

## Bonnes pratiques relatives au code personnalisé {#custom-code-best-practices}

* **Enveloppez systématiquement le code personnalisé dans un élément.**

  Par exemple :

```html
<div id="custom-code"> 
// My Code goes here 
</div>
```

Si des modifications sont nécessaires, apportez-les dans ce conteneur. Si le code personnalisé n’est plus nécessaire, laissez ce conteneur vide, mais ne le supprimez pas. Cela permet de s’assurer que d’autres modifications de l’expérience ne sont pas affectées.

* **N’utilisez pas l’ID d’élément CDQID pour des modifications apportées à la page effectuées dans l’éditeur de code.**

  [!DNL Target] applique un nouvel ID d&#39;élément avec la valeur « CDQID » à tout élément de la page modifié par [!DNL Target]. Cet identifiant est appliqué par [!DNL Target]. Il ne doit donc pas être utilisé pour d’autres modifications ou ajustements dans l’éditeur de code.

* **N’effectuez pas d’actions `document.write` dans les scripts de code personnalisé.**

  Les scripts sont exécutés de manière asynchrone. Cela entraîne souvent l’affichage de `document.write` actions au mauvais endroit sur la page. Utiliser `document.write` dans des scripts créés avec du code personnalisé n’est pas recommandé.

* **Si un élément est créé puis modifié, ne supprimez pas l&#39;élément d&#39;origine.**

  Chaque modification crée un nouvel élément dans le panneau **[!UICONTROL Modifications]**. La deuxième action modifie l’élément 1. Ainsi, si l’élément 1 est supprimé, cette action ne peut plus rien modifier et la modification ne fonctionne plus. Voir [Dépannage du code personnalisé](#troubleshooting-custom-code) pour plus d’informations.

* **Soyez prudent lorsque vous utilisez la fonction de code personnalisé pour deux activités qui ciblent la même URL.**

  Lorsque la fonction de code personnalisé est utilisée pour deux activités qui ciblent la même URL, le JavaScript est injecté dans la page à partir des deux activités. [!DNL Target] détermine automatiquement l&#39;ordre du contenu diffusé. Assurez-vous que le code ne dépend pas de l’emplacement. L’auteur du code est chargé de s’assurer qu’il n’y a aucun conflit dans le code.

## Résolution des problèmes liés au code personnalisé {#troubleshooting-custom-code}

+++ Pourquoi le code personnalisé n’est-il pas exécuté lors de l’utilisation de `triggerView` ?

Les offres de code personnalisé dans le VEC ne sont pas rendues de nouveau lorsque `triggerView()` est appelé avec `{page: false}` comme option.

+++

+++ Que signifie l’avertissement indiquant qu’une action ne peut pas être appliquée en raison de modifications structurelles dans une page ?

Ce message indique que la structure de la page a changé depuis le dernier enregistrement de l’activité.

![Message d&#39;avertissement indiquant que la structure de la page a changé depuis le dernier enregistrement de l&#39;activité](assets/code_editor_2.png)

Les sélecteurs manquants peuvent être obtenus en utilisant le mode de navigation. Adobe recommande de supprimer puis de recréer chaque expérience pour s’assurer que le contenu s’affiche comme prévu, comme indiqué dans le message d’avertissement.

+++

+++ Que signifie l’avertissement « La suppression de cette action peut avoir un impact sur les actions suivantes » ?

Par exemple, deux actions peuvent avoir été entreprises :

* Ajout d’une classe à l’élément 1
* Modification du code HTML pour l’élément 1

Chaque modification crée un nouvel élément dans le panneau **[!UICONTROL Modifications]**. La deuxième action modifie l’élément 1. Par conséquent, si l’élément 1 est supprimé, la deuxième action n’a plus rien à modifier et la modification ne fonctionne plus.

En d’autres termes, si un élément est ajouté avec du texte et qu’il est ensuite modifié avec un texte différent dans une action distincte, le panneau **[!UICONTROL Modifications]** affiche les deux actions sous la forme d’éléments distincts. La modification de l’élément crée un nouvel élément qui modifie l’élément d’origine et contient le texte modifié. Si l’élément d’origine est ensuite supprimé, le texte modifié ne peut pas trouver l’élément qui a été modifié et ne s’affiche pas. Le deuxième élément reste dans la liste des éléments, mais il n’a aucune incidence sur la page, car l’élément qu’il modifie n’existe plus.

+++

+++ Pourquoi un élément créé avec `document.write` dans un script n’apparaît-il pas comme prévu ?

Les scripts sont exécutés de manière asynchrone. Cela entraîne souvent l’affichage de `document.write` actions au mauvais endroit sur la page. Adobe ne recommande pas d’utiliser `document.write` dans des scripts créés avec du code personnalisé.

+++

+++ Pourquoi le JavaScript affiche-t-il des erreurs dans le code personnalisé ?

Tout code JavaScript intégré non valide dans JavaScript affiche des erreurs dans le code personnalisé.

+++

+++ Pourquoi une modification du code personnalisé ne peut-elle pas être annulée ?

Actuellement, l’annulation n’est pas prise en charge pour les actions de modification et de suppression du panneau **[!UICONTROL Modifications]** et dans le code personnalisé. Annuler l’une de ces opérations pourrait rendre l’expérience dans le VEC incohérente par rapport aux actions visibles dans le code personnalisé. Toutefois, les actions du code personnalisé sont dans le bon état et il n’y a aucun impact sur la diffusion. Il s’agit d’un problème de l’interface utilisateur. Pour actualiser l’expérience, enregistrez-la et ouvrez-la à nouveau, ou passez à l’étape suivante et revenez. L’une ou l’autre de ces actions recharge l’expérience, de sorte qu’elle s’affiche comme prévu et est cohérente avec les actions du panneau **[!UICONTROL Modifications]**.

+++

+++ Pourquoi le code personnalisé ne produit-il pas les résultats attendus dans Internet Explorer 8 ?

[!DNL Target] ne prend plus en charge Internet Explorer 8.

+++
