---
keywords: pages du site;pages du site cible;ciblage;page actuelle;page actuelle cible;page précédente;page précédente cible;page de destination;page de destination cible;en-tête http
description: Découvrez comment cibler les visiteurs et visiteuses qui se trouvent sur une page spécifique  [!DNL Adobe Target]  votre site à l’aide de .
title: Puis-je cibler les visiteurs en fonction des pages du site ?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 19%

---

# Pages du site

Vous pouvez cibler les visiteurs et visiteuses qui utilisent des [!DNL Adobe Target] et visiteuses qui accèdent à une page spécifique de votre site.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Faites glisser et déposez **[!UICONTROL Site Pages]** dans le volet du Créateur d’audiences.

   ![Audience par pages du site](assets/target_site_pages.png)

1. Cliquez sur la liste déroulante **[!UICONTROL Select]**, sélectionnez l’une des options suivantes, puis configurez la règle selon vos besoins.

   Les options et les évaluateurs disponibles dans les listes déroulantes suivantes de la règle varient en fonction de l’option choisie. L’illustration suivante présente les options disponibles si vous choisissez [!UICONTROL Current Page] :

   ![Page actuelle](assets/current-page.png)

   Les options suivantes sont disponibles dans la liste déroulante initiale lorsque vous choisissez [!UICONTROL Select].

   * **[!UICONTROL Current Page]:** page que l’utilisateur consulte.

     Si vous choisissez cette option, les options suivantes sont disponibles dans la deuxième liste déroulante :

      * [!UICONTROL URL] (Pour plus d’informations sur la manière dont [!DNL Target] évalue les URL, voir [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

   * **[!UICONTROL Previous Page]:** page que l’utilisateur a consultée avant de cliquer sur la page active. L’utilisateur doit cliquer de la page précédente à la page actuelle pour que la page soit suivie. La page précédente n’est pas suivie si l’utilisateur saisit une nouvelle URL dans le navigateur. Le contenu réel de cette page dépend de la conception de votre site. Par exemple, si la page en cours affiche des informations sur un produit spécifique, la page précédente peut être une page de catégorie sur laquelle le visiteur sélectionne l’élément spécifique. Par exemple, une page affichant plusieurs caméras d’un certain type, ou il peut s’agir de la page d’accueil qui mène à la dernière page.

     Si vous choisissez cette option, les options suivantes sont disponibles dans la deuxième liste déroulante :

      * [!UICONTROL URL] (pour plus d’informations sur la manière dont Target évalue les URL, voir [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]

   * **[!UICONTROL Landing Page]:** la page de destination est la première page que le visiteur voit lorsqu’il accède à votre site. Par exemple, si le visiteur clique sur un lien Google menant à une page de catégorie, la page de catégorie devient la page d’entrée. Si le lien mène à la page d’accueil, cette dernière est la page d’entrée. La page d’entrée est mémorisée pour toute la session du visiteur. Vous pouvez encore affiner le ciblage au sein du site en fonction de la page d’entrée du visiteur dans cette session.

     Si vous choisissez cette option, les options suivantes sont disponibles dans la deuxième liste déroulante :

      * [!UICONTROL URL] (pour plus d’informations sur la manière dont Target évalue les URL, voir [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domain]
      * [!UICONTROL Query]
      * [!UICONTROL Subdomain]
      * [!UICONTROL Top-Level Domain]
      * [!UICONTROL Path]
      * [!UICONTROL Hash (#) fragment]

     >[!NOTE]
     >
     >L’objet `landing.url` est réinitialisé au changement d’un sous-domaine ou au remplacement d’URL directe.

   * **[!UICONTROL HTTP Header]:** cette option évalue les informations contenues dans l’en-tête HTTP de la requête [!DNL Target]. Par exemple, si l’en-tête HTTP contient des informations de langue, vous pouvez créer une règle contenant la condition `Accept-Language: es` pour cibler les visiteurs et visiteuses qui accèdent à la page en espagnol.

     Si vous choisissez cette option, les options suivantes sont disponibles dans la deuxième liste déroulante :

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Authorization]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connection]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Expect]
      * [!UICONTROL From]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Range]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL Upgrade]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Warning]

   Si vous choisissez [!UICONTROL Current Page], [!UICONTROL Previous Page] ou [!UICONTROL Landing Page], les options [!UICONTROL Domain] et [!UICONTROL Query] sont disponibles. Tenez compte des points suivants lors du choix de ces options :

   * **Domaine :** domaine complet de la page. Lors de la spécification d’un domaine, la bonne pratique consiste à utiliser « contains ». Par exemple, « Domaine égal à facebook.com » n’accepte ni `m.facebook.com` ni `www.facebook.com`. « Le domaine contient facebook.com » accepte toute variante de facebook.com.
   * **Requête :** contenu de l’URL après le premier point d’interrogation (?).

     `foo.html?e0a72cb2a2c7`

1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Done]**.

Vous pouvez également créer des audiences des pages du site en utilisant votre propre « paramètre de requête défini par l’utilisateur » ou « en-tête défini par l’utilisateur ».

Utilisez un :

* Paramètre de requête si la règle sélectionnée par l’utilisateur est [!UICONTROL Current Page], [!UICONTROL Landing Page] ou [!UICONTROL Previous Page]
* En-tête si la règle sélectionnée par l’utilisateur est un en-tête HTTP

## Résolution des problèmes {#ts}

* Pour que les audiences de la page de destination fonctionnent correctement, le paramètre `mboxReferrer` doit être défini pour les requêtes (paramètre `context.address.referringUrl` pour l’API de diffusion) que la bibliothèque JavaScript at.js extrait de la page à l’aide de l’attribut `document.referrer` . Cet attribut `HTMLDocument` renvoie l’URI de la page à partir de laquelle l’utilisateur a navigué. La valeur de cet attribut est une chaîne vide lorsque l&#39;utilisateur accède directement à la page (non par un lien, mais par exemple via un signet).

  Si ce comportement ne correspond pas à vos exigences, envisagez d’effectuer l’une des actions suivantes :

   * Transmettez les [paramètres de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=fr){target=_blank} aux [!DNL Target] à utiliser à des fins de ciblage.
   * Utilisez une activité de test A/B [A/B](/help/main/c-activities/t-test-ab/test-ab.md) au lieu d’une activité de page de destination. Les activités de test A/B ne changent pas d’expérience pour le même visiteur.
   * Utilisez plutôt un [profil du visiteur](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md).

* Lors de l’utilisation d’évaluateurs « commence/se termine par » sur des chaînes contenant des virgules, ces chaînes sont évaluées sous la forme d’un tableau de valeurs, dans lequel chaque valeur séparée par des virgules est évaluée. Par exemple, si vous disposez de la valeur pour un en-tête : `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` il est éligible pour des conditions telles que :
   * commence par zh,
   * commence par en,
   * se termine par 0,7,
   * se termine par 0,8.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
