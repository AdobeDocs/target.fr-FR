---
description: Ciblez les visiteurs qui se trouvent sur une page spécifique ou qui possèdent un paramètre de mbox spécifique.
keywords: pages du site;pages du site target;ciblage;page actuelle;cibler la page actuelle;page précédente;cibler la page précédente;page d’entrée;cibler la page d’entrée;mbox;cibler la mbox
seo-description: Vous pouvez cibler les visiteurs qui se trouvent sur une page spécifique ou qui disposent d’un paramètre de mbox spécifique à l’aide d’Adobe Target.
seo-title: Pages de site dans Adobe Target
solution: Target
title: Pages du site
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: d47772b35e371af4b6484ff59209de1c8482b712

---


# Pages du site{#site-pages}

Vous pouvez cibler les visiteurs qui se trouvent sur une page spécifique ou qui disposent d’un paramètre de mbox spécifique.

>[!NOTE]
>
>Les types de pages et les opérateurs de comparaison du site des audiences correspondent désormais aux types et aux opérateurs de comparaison de Target Classic. Vous pouvez également créer des audiences des pages du site en utilisant votre propre « paramètre de requête défini par l’utilisateur » ou « en-tête défini par l’utilisateur ».

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** &gt; **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Cliquez sur **[!UICONTROL Ajouter une règle]** &gt; **[!UICONTROL Pages du site]**.

   ![Audience par pages du site](assets/target_site_pages.png)

1. Cliquez sur **[!UICONTROL Sélectionner]**, puis sélectionnez l’une des options suivantes :

   * **Page en cours :** page sur laquelle se trouve actuellement l’utilisateur, à savoir la page contenant une mbox de l’activité. Si le ciblage est effectué au niveau de l’activité, il peut s’agir d’une page avec une mbox utilisée pour définir les conditions d’entrée ou d’une page qui affiche du contenu. Si le ciblage est basé sur l’expérience, la page active est la page dans laquelle se trouve la mbox d’affichage. Dans le cas du ciblage de mesures de succès ou de conversion, il s’agit de la page dans laquelle sont les mbox.
   * **Page précédente :** page sur laquelle se trouvait l’utilisateur avant de cliquer sur la page en cours. (L’utilisateur doit cliquer de la page précédente vers la page active pour activer le suivi de la page. La page précédente n’est pas suivie si l’utilisateur saisit une nouvelle URL dans son navigateur.) Le contenu réel de cette page dépend de la conception de votre site. Ainsi, si la page active affiche des informations sur un produit spécifique, il est possible que la page précédente soit une page de catégorie dans laquelle le visiteur a sélectionné ce produit (telle qu’une page présentant plusieurs appareils photo d’un certain type) ou la page d’accueil renvoyant à la dernière page.
   * **Page d’entrée :** première page que voit l’utilisateur lorsqu’il accède à votre site. Par exemple, si le visiteur clique sur un lien Google menant à une page de catégorie, la page de catégorie devient la page d’entrée. Si le lien mène à la page d’accueil, cette dernière est la page d’entrée. La page d’entrée est mémorisée pour toute la session du visiteur. Vous pouvez encore affiner le ciblage au sein du site en fonction de la page d’entrée du visiteur dans cette session.

      >[!NOTE]
      >
      >L’objet `landing.url` est réinitialisé au changement d’un sous-domaine ou au remplacement d’URL directe.

   * **Mbox :** mbox sur laquelle vous axez le ciblage. Si vous souhaitez, par exemple, comptabiliser les commandes dont le montant total est supérieur ou égal à 100 €, vous pouvez transmettre l’argument `orderTotal` en tant que paramètre de mbox avec le ciblage spécifié ici.
   * **Domaine :** domaine complet de la page. Lors de la spécification d’un domaine, la bonne pratique consiste à utiliser « contains ». Par exemple, « Domain equals facebook.com » n’acceptera ni `m.facebook.com` ni `www.facebook.com`. En revanche, « Domain contains facebook.com » acceptera toutes les variantes de facebook.com.
   * **Requête :** contenu de l’URL après le premier point d’interrogation (?).

      `foo.html?e0a72cb2a2c7`

1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Vous pouvez également créer des audiences des pages du site en utilisant votre propre « paramètre de requête défini par l’utilisateur » ou « en-tête défini par l’utilisateur ».

Utilisez un :

* paramètre de requête si la règle sélectionnée par l’utilisateur est Page actuelle, Page d’entrée ou Page précédente ;
* en-tête si la règle sélectionnée par l’utilisateur est un en-tête HTTP ;

comme illustré ci-dessous :

![](assets/site_pages.png)

## Résolution des problèmes {#ts}

* Pour que les audiences de la page d’entrée fonctionnent correctement, le paramètre `mboxReferrer` mbox doit être défini pour les requêtes. La bibliothèque JavaScript at.js récupère `mboxReferrer` de la page en utilisant `document.referrer`.

   Si ces paramètres ne sont pas correctement configurés, un visiteur peut quitter une activité après avoir accédé à une page suivante. Si, par exemple, `document.referrer` est utilisé sur la page d’entrée mais pas sur les pages suivantes, [!DNL Target] il n’est pas garanti que le visiteur reste dans l’activité.

   Si vous rencontrez cette situation, effectuez l’une des actions suivantes :

   * Assurez-vous que votre site Web se charge `document.referrer` correctement.
   * Transmettez les paramètres [de](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) mbox [!DNL Target] à utiliser à des fins de ciblage.
   * Utilisez une activité [de test](/help/c-activities/t-test-ab/test-ab.md) A/B au lieu d’une activité de page d’entrée. Les activités de test A/B ne changent pas d’expériences pour le même visiteur.
   * Utilisez plutôt un profil [de](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) visiteur.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=fre_fr)
