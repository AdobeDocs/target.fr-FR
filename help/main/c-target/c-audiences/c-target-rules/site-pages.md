---
keywords: pages du site;cibler des pages du site;ciblage;page actuelle;cibler la page actuelle;page précédente;cibler la page précédente;page d’entrée;cibler une page d’entrée;en-tête http
description: Découvrez comment cibler les visiteurs à l’aide de [!DNL Adobe Target] qui se trouvent sur une page spécifique de votre site.
title: Puis-je cibler les visiteurs en fonction des pages du site ?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 26%

---

# Pages du site

Vous pouvez cibler les visiteurs qui utilisent [!DNL Adobe Target] qui accède à une page spécifique de votre site.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Glisser-déposer **[!UICONTROL Pages du site]** dans le volet audience builder.

   ![Audience par pages du site](assets/target_site_pages.png)

1. Cliquez sur le bouton **[!UICONTROL Sélectionner]** , sélectionnez l’une des options suivantes, puis configurez la règle selon vos besoins.

   Les options et évaluateurs disponibles dans les listes déroulantes suivantes de la règle varient selon l’option choisie. L’illustration suivante présente les options disponibles si vous choisissez [!UICONTROL Page en cours]:

   ![Page actuelle](assets/current-page.png)

   Les options suivantes sont disponibles dans la liste déroulante initiale lorsque vous choisissez [!UICONTROL Sélectionner].

   * **[!UICONTROL Page en cours]:** Page que l’utilisateur consulte.

      Si vous choisissez cette option, les options suivantes sont disponibles dans la seconde liste déroulante :

      * [!UICONTROL URL] (Pour plus d’informations sur la manière dont [!DNL Target] évalue les URL, voir [FAQ sur le ciblage et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domaine]
      * [!UICONTROL Requête]
      * [!UICONTROL Sous-domaine]
      * [!UICONTROL Domaine de niveau supérieur]
      * [!UICONTROL Video Analytics]
      * [!UICONTROL Fragment de hachage (#)]
   * **[!UICONTROL Page précédente]:** Page consultée par l’utilisateur avant de cliquer sur la page active. L’utilisateur doit cliquer de la page précédente vers la page active pour que la page soit suivie. La page précédente n’est pas suivie si l’utilisateur saisit une nouvelle URL dans son navigateur. Le contenu réel de cette page dépend de la conception de votre site. Par exemple, si la page active affiche des informations sur un produit spécifique, la page précédente peut être une page de catégorie dans laquelle le visiteur sélectionne l’article en question. Par exemple, une page qui affiche plusieurs appareils photo d’un certain type ou la page d’accueil qui mène à la dernière page.

      Si vous choisissez cette option, les options suivantes sont disponibles dans la seconde liste déroulante :

      * [!UICONTROL URL] (Pour plus d’informations sur la manière dont Target évalue les URL, voir [FAQ sur le ciblage et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domaine]
      * [!UICONTROL Requête]
      * [!UICONTROL Sous-domaine]
      * [!UICONTROL Domaine de niveau supérieur]
      * [!UICONTROL Video Analytics]
   * **Page d’entrée :** première page que voit l’utilisateur lorsqu’il accède à votre site. Par exemple, si le visiteur clique sur un lien Google menant à une page de catégorie, la page de catégorie devient la page d’entrée. Si le lien mène à la page d’accueil, cette dernière est la page d’entrée. La page d’entrée est mémorisée pour toute la session du visiteur. Vous pouvez encore affiner le ciblage au sein du site en fonction de la page d’entrée du visiteur dans cette session.

      Si vous choisissez cette option, les options suivantes sont disponibles dans la seconde liste déroulante :

      * [!UICONTROL URL] (Pour plus d’informations sur la manière dont Target évalue les URL, voir [FAQ sur le ciblage et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domaine]
      * [!UICONTROL Requête]
      * [!UICONTROL Sous-domaine]
      * [!UICONTROL Domaine de niveau supérieur]
      * [!UICONTROL Video Analytics]
      * [!UICONTROL Fragment de hachage (#)]

      >[!NOTE]
      >
      >L’objet `landing.url` est réinitialisé au changement d’un sous-domaine ou au remplacement d’URL directe.

   * **[!UICONTROL En-tête HTTP]:** Cette option évalue les informations dans l’en-tête HTTP de la variable [!DNL Target] requête. Par exemple, si l’en-tête HTTP contient des informations sur la langue, vous pouvez créer une règle contenant la variable `Accept-Language: es` pour cibler les visiteurs qui accèdent à la page en espagnol.

      Si vous choisissez cette option, les options suivantes sont disponibles dans la seconde liste déroulante :

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Autorisation]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL Connexion]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL Date]
      * [!UICONTROL Attente]
      * [!UICONTROL De]
      * [!UICONTROL Hôte]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Proxy-Authorization]
      * [!UICONTROL Période ]
      * [!UICONTROL Référent]
      * [!UICONTROL TE]
      * [!UICONTROL Mise à niveau]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Avertissement]

   Si vous choisissez [!UICONTROL Page en cours], [!UICONTROL Page précédente]ou [!UICONTROL Page d’entrée], la variable [!UICONTROL Domaine] et [!UICONTROL Requête] sont disponibles. Tenez compte des points suivants lors du choix de ces options :

   * **Domaine :** domaine complet de la page. Lors de la spécification d’un domaine, la bonne pratique consiste à utiliser « contains ». Par exemple, &quot;Domain equals facebook.com&quot; n’accepte pas `m.facebook.com` ou `www.facebook.com`. &quot;Le domaine contient facebook.com&quot; accepte toute variante de facebook.com.
   * **Requête :** contenu de l’URL après le premier point d’interrogation (?).

      `foo.html?e0a72cb2a2c7`





1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Terminé]**.

Vous pouvez également créer des audiences des pages du site en utilisant votre propre « paramètre de requête défini par l’utilisateur » ou « en-tête défini par l’utilisateur ».

Utilisez un :

* Paramètre de requête si la règle sélectionnée par l’utilisateur est [!UICONTROL Page en cours], [!UICONTROL Page d’entrée]ou [!UICONTROL Page précédente]
* En-tête si la règle sélectionnée par l’utilisateur est un en-tête HTTP

## Résolution des problèmes {#ts}

* Pour que les audiences de page d’entrée fonctionnent correctement, les requêtes doivent avoir la variable `mboxReferrer` paramètre défini (pour l’API de diffusion, le paramètre `context.address.referringUrl` ) que la bibliothèque JavaScript at.js extrait de la page à l’aide de la variable `document.referrer` attribut. Ceci `HTMLDocument` renvoie l’URI de la page à partir de laquelle l’utilisateur a navigué. La valeur de cet attribut est une chaîne vide lorsque l’utilisateur accède directement à la page (pas par le biais d’un lien, mais, par exemple, via un signet).

   Si ce comportement ne correspond pas à vos besoins, envisagez d’effectuer l’une des actions suivantes :

   * Pass [paramètres mbox](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/){target=_blank} à [!DNL Target] à utiliser à des fins de ciblage.
   * Utilisez une [Activité Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) plutôt qu&#39;une activité de landing page. Les activités de test A/B ne changent pas d’expériences pour un même visiteur.
   * Utilisez une [profil du visiteur](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) au lieu de .

* Lors de l’utilisation d’évaluateurs &quot;commence/se termine par&quot; sur des chaînes contenant des virgules, ces chaînes sont évaluées sous la forme d’un tableau de valeurs, dans lequel chaque valeur séparée par des virgules est évaluée. Par exemple, si vous avez la valeur d’un en-tête : `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` il remplit les conditions suivantes :
   * commence par zh,
   * commence par en,
   * se termine par 0,7,
   * se termine par 0,8.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
