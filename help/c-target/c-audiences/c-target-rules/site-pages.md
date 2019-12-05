---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;http header
description: Vous pouvez cibler les visiteurs qui se trouvent sur une page spécifique de votre site.
title: Pages de site dans Adobe Target
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: 758ebad09d0e2ff267ee219519e63d6528b83491

---


# Pages du site{#site-pages}

Vous pouvez cibler les visiteurs qui se trouvent sur une page spécifique de votre site.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** &gt; **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Cliquez sur **[!UICONTROL Ajouter une règle]** &gt; **[!UICONTROL Pages du site]**.

   ![Audience par pages du site](assets/target_site_pages.png)

1. Cliquez sur la liste **[!UICONTROL déroulante Sélectionner]** , sélectionnez l’une des options suivantes, puis configurez la règle selon vos besoins.

   Les options disponibles et les évaluateurs dans les listes déroulantes suivantes de la règle varient selon l’option choisie. L’illustration suivante présente les options disponibles si vous sélectionnez Page active :

   ![Page actuelle](/help/c-target/c-audiences/c-target-rules/assets/current-page.png)

   Les options suivantes sont disponibles dans la liste déroulante initiale lorsque vous sélectionnez [!UICONTROL Sélectionner].

   * **** Page active : Page sur laquelle se trouve actuellement l’utilisateur.

      Les options suivantes sont disponibles dans la deuxième liste déroulante si vous choisissez cette option :

      * URL
      * Domaine
      * Requête
      * Sous-domaine
      * Domaine de niveau supérieur
      * Chemin d’accès
      * Fragment de hachage (#)
   * **Page précédente :** page sur laquelle se trouvait l’utilisateur avant de cliquer sur la page en cours. (L’utilisateur doit cliquer de la page précédente vers la page active pour activer le suivi de la page. La page précédente n’est pas suivie si l’utilisateur saisit une nouvelle URL dans son navigateur.) Le contenu réel de cette page dépend de la conception de votre site. Ainsi, si la page active affiche des informations sur un produit spécifique, il est possible que la page précédente soit une page de catégorie dans laquelle le visiteur a sélectionné ce produit (telle qu’une page présentant plusieurs appareils photo d’un certain type) ou la page d’accueil renvoyant à la dernière page.

      Les options suivantes sont disponibles dans la deuxième liste déroulante si vous choisissez cette option :

      * URL
      * Domaine
      * Requête
      * Sous-domaine
      * Domaine de niveau supérieur
      * Chemin d’accès
   * **Page d’entrée :** première page que voit l’utilisateur lorsqu’il accède à votre site. Par exemple, si le visiteur clique sur un lien Google menant à une page de catégorie, la page de catégorie devient la page d’entrée. Si le lien mène à la page d’accueil, cette dernière est la page d’entrée. La page d’entrée est mémorisée pour toute la session du visiteur. Vous pouvez encore affiner le ciblage au sein du site en fonction de la page d’entrée du visiteur dans cette session.

      Les options suivantes sont disponibles dans la deuxième liste déroulante si vous choisissez cette option :

      * URL
      * Domaine
      * Requête
      * Sous-domaine
      * Domaine de niveau supérieur
      * Chemin d’accès
      * Fragment de hachage (#)
      >[!NOTE]
      >
      >L’objet `landing.url` est réinitialisé au changement d’un sous-domaine ou au remplacement d’URL directe.

   * **** En-tête HTTP : Cette option évalue les informations contenues dans l’en-tête HTTP de la requête Target. Par exemple, si l’en-tête HTTP contient des informations sur la langue, vous pouvez créer une règle qui contient la `Accept-Language: es` condition de ciblage des visiteurs qui accèdent à la page en espagnol.

      Les options suivantes sont disponibles dans la deuxième liste déroulante si vous choisissez cette option :

      * Accept
      * Accept-Charset
      * Accept-Encoding
      * Accept-Language
      * Autorisation
      * Cache-Control
      * Connexion
      * Content-Length
      * Content-MDS
      * Content-Type
      * Date
      * Attendre
      * De
      * Hôte
      * Si-Correspondance
      * If-Modified-Since
      * Si-Aucun-Correspondance
      * Si-Range
      * Si-Non-Modifié-Depuis
      * Max-Forwards
      * Pragma
      * Proxy-Authorization
      * Période 
      * Referer
      * TE
      * Mise à niveau
      * User-Agent
      * Via
      * Avertissement
   Si vous sélectionnez Page [!UICONTROL active], Page précédente ou Page [!UICONTROL d’entrée, les options][!UICONTROL Domaine et Requête sont disponibles. ] Tenez compte des points suivants lorsque vous choisissez ces options :

   * **Domaine :** domaine complet de la page. Lors de la spécification d’un domaine, la bonne pratique consiste à utiliser « contains ». Par exemple, « Domain equals facebook.com » n’acceptera ni `m.facebook.com` ni `www.facebook.com`. En revanche, « Domain contains facebook.com » acceptera toutes les variantes de facebook.com.
   * **Requête :** contenu de l’URL après le premier point d’interrogation (?).

      `foo.html?e0a72cb2a2c7`





1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Vous pouvez également créer des audiences des pages du site en utilisant votre propre « paramètre de requête défini par l’utilisateur » ou « en-tête défini par l’utilisateur ».

Utilisez un :

* paramètre de requête si la règle sélectionnée par l’utilisateur est Page actuelle, Page d’entrée ou Page précédente ;
* En-tête si la règle sélectionnée par l’utilisateur est un en-tête HTTP.

comme illustré ci-dessous :

![](assets/site_pages.png)

## Résolution des problèmes {#ts}

* Pour que les audiences de la page d’entrée fonctionnent correctement, les requêtes doivent avoir le `mboxReferrer` paramètre défini (pour l’API de remise, le `context.address.referringUrl` paramètre) que la bibliothèque JavaScript at.js utilise à partir de la page à l’aide de l’ `document.referrer` attribut. Cet `HTMLDocument` attribut renvoie l’URI de la page à partir de laquelle l’utilisateur a navigué. La valeur de cet attribut est une chaîne vide lorsque l’utilisateur accède directement à la page (pas par le biais d’un lien, mais, par exemple, via un signet).

   Si ce comportement ne correspond pas à vos besoins, effectuez l’une des actions suivantes :

   * Transmettez les paramètres [de](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) mbox [!DNL Target] à utiliser à des fins de ciblage.
   * Utilisez une activité [de test](/help/c-activities/t-test-ab/test-ab.md) A/B au lieu d’une activité de page d’entrée. Les activités de test A/B ne changent pas d’expériences pour le même visiteur.
   * Utilisez plutôt un profil [de](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) visiteur.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=fre_fr)
