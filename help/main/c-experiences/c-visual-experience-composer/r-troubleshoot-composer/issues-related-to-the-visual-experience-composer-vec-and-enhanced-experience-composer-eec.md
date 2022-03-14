---
keywords: Ciblage;compositeur d’expérience visuelle;liste autorisée;liste autorisée;liste autorisée;liste autorisée;compositeur d’expérience visuelle avancé;vec;dépannage du compositeur d’expérience visuelle;dépannage;eec;compositeur d’expérience avancé;tls;tls 1.2
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans l’Adobe [!DNL Target] compositeur d’expérience visuelle (VEC) et le compositeur d’expérience avancé (EEC) sous certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé ?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 53%

---

# Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé

Des problèmes d’affichage et d’autres problèmes surviennent parfois dans la variable [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) et la variable [!UICONTROL Compositeur d’expérience avancé] (CEE) sous certaines conditions.

## Comment les politiques dʼapplication des cookies SameSite de Google Chrome influencent-elles le VEC et l’EEC ? {#samesite}

Gardez à l’esprit les modifications qui affectent le compositeur d’expérience visuelle et le compositeur d’expérience avancé lors de l’utilisation des versions Chrome suivantes :

>[!NOTE]
>
>La modification suivante affecte les trois mises à jour décrites ci-dessous :
>
> * Will *not* être en mesure d’utiliser le compositeur d’expérience visuelle sans l’extension d’assistance du compositeur d’expérience visuelle installée et activée pour les pages protégées par mot de passe de vos sites. Les cookies de connexion à votre site sont considérés comme des cookies tiers et ne sont pas envoyés avec des demandes de connexion dans l’éditeur du VEC en mode de navigation. La seule exception concerne les cookies de connexion à votre site qui contiennent déjà la variable `SameSite=None` et `Secure` ensemble d’attributs.


**Chrome 94 (21 septembre 2021)**: Avec les modifications prévues pour la version 94 de Chrome (21 septembre 2021), la modification suivante a un impact sur tous les utilisateurs possédant des versions de navigateur Chrome 94+ :

* Indicateur de ligne de commande `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` sera supprimé.

**Chrome 91 (25 mai 2021)**: Avec les modifications mises en oeuvre pour la version 91 de Chrome (25 mai 2021), la modification suivante a un impact sur tous les utilisateurs possédant des versions de navigateur Chrome 91+ :

* Les drapeaux `#same-site-by-default-cookies` et `#cookies-without-same-site-must-be-secure` ont été supprimés de `chrome://flags`. Ce comportement est désormais activé par défaut.

**Chrome 80 (août 2020)**: Avec les modifications mises en oeuvre en août 2020, tous les utilisateurs disposant des versions de navigateur Chrome 80+ :

* Will *not* être en mesure de télécharger [!DNL Target] bibliothèques lors de la modification d’une activité (lorsqu’elles ne se trouvent pas déjà sur le site). Cela est dû au fait que l’appel de téléchargement est effectué depuis le domaine client vers un [!DNL Adobe] et est rejeté comme non authentifié.
* Le compositeur d’expérience avancé *not* pour tous les utilisateurs, car il n’est pas en mesure de définir l’attribut SameSite pour les cookies sur `adobemc.com domain`. Sans cet attribut, le navigateur rejette ces cookies, ce qui entraîne l’échec du compositeur d’expérience avancé.

### Déterminer les cookies bloqués

Pour déterminer les cookies qui sont bloqués en raison des stratégies d’application des cookies SameSite, utilisez les outils de développement dans Chrome.

1. Pour accéder aux outils de développement, lorsque vous affichez le VEC dans Chrome, cliquez sur le bouton **[!UICONTROL ellipse]** dans le coin supérieur droit de Chrome > **[!UICONTROL Autres outils]** > **[!UICONTROL Outils de développement]**.
1. Cliquez sur le bouton **[!UICONTROL Réseau]** > puis recherchez les cookies bloqués.

   >[!NOTE]
   >
   >Utilisez la variable **[!UICONTROL Comporte des cookies bloqués]** pour faciliter la recherche des cookies bloqués.

   L’illustration suivante présente un cookie bloqué :

   ![Outils de développement > Onglet Réseau présentant un cookie bloqué](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] Extension d’assistance VEC

À partir de la version 0.7.1, la variable [!DNL Adobe Target] L’extension de navigateur VEC Helper ajoute la valeur `SameSite=None` et `Secure` attributs à tous les cookies sur les réponses provenant de pages web modifiées dans le VEC lorsque le bouton &quot;Cookies&quot; est activé dans l’interface utilisateur de l’extension :

![Interface utilisateur de l’extension d’assistance d’Adobe Target VEC pour Adobe Target VEC Helper](assets/cookies-vec-helper.png)

### Alternatives et solutions de contournement

Utilisez l’une des options suivantes pour vous assurer que VEC et compositeur d’expérience avancé continuent à fonctionner comme prévu :

* Téléchargez et utilisez la mise à jour [Extension d’assistance VEC](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Utilisez le navigateur Mozilla Firefox. Firefox n’applique pas encore cette stratégie.
* Utilisez les indicateurs suivants pour exécuter Google Chrome à partir de la ligne de commande jusqu’au 21 septembre 2021. Après le 21 septembre, les fonctionnalités qui nécessitent des cookies ne fonctionneront plus dans le compositeur d’expérience visuelle, telles que les fenêtres de connexion ou de consentement pour les cookies. Si vous effectuez une mise à jour vers Chrome 94, vous devez générer manuellement des cookies avec `SameSite=none` et `Secure` sur vos sites web.

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## Does [!DNL Target] prendre en charge les iframes à plusieurs niveaux ?

[!DNL Target] ne prend pas en charge les iFrames à plusieurs niveaux. Si votre site web charge un iframe qui possède un iframe enfant, at.js interagit uniquement avec l’iframe parent. [!DNL Target]Les bibliothèques n’interagissent pas avec l’iFrame enfant.

Pour pallier ce problème, vous pouvez ajouter une page dans l’expérience avec l’URL de l’iFrame enfant.

## Lorsque je tente de modifier une page, tout ce que je vois est un compteur au lieu de ma page. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_313001039F79446DB28C70D932AF5F58}

Cette situation peut se produire si l’URL contient un caractère #. Pour corriger le problème, passez en mode Parcourir dans le compositeur d’expérience visuelle, puis repassez en mode Composer. Le compteur doit disparaître et la page doit se charger.

## Les en-têtes CSP (Content Security Policy, stratégie de sécurité du contenu) bloquent la variable [!DNL Target] bibliothèques sur mon site web. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_89A30C7A213D43BFA0822E66B482B803}

Si les en-têtes CSP de votre site web bloquent les bibliothèques Target, puis chargent le site web mais empêchent la modification, assurez-vous que les bibliothèques Target ne sont pas bloquées.

>[!NOTE]
>
>Outre les informations suivantes, vous pouvez utiliser l’[extension de navigateur Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) pour Google Chrome.

![](assets/cps_headers.png)

Pour contourner ce problème, vous pouvez configurer une règle Requestly permettant de supprimer les en-têtes CSP, comme indiqué ci-dessous :

![](assets/cps_headers_2.png)

Vous pouvez configurer une règle Requestly similaire pour tout en-tête qui empêche le chargement d’une ressource dans le compositeur d’expérience visuelle.

Pour Requestly, lorsque la suppression d’en-têtes est nécessaire, il convient d’effectuer l’une des opérations suivantes :

* Ajoutez des règles d’URL pour les URL que vous souhaitez ouvrir avec le compositeur d’expérience visuelle. Les en-têtes sont alors supprimés uniquement pour ces URL.
* Activez la règle lorsque vous effectuez une modification dans le compositeur d’expérience visuelle et désactivez la règle lorsque vous ne l’utilisez pas.

## Le compositeur d’expérience visuelle et le compositeur d’expérience avancé semblent rompus et ne s’initialisent pas lors de la réédition d’une activité enregistrée. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Si le site web a été modifié en dehors du compositeur d’expérience visuelle une fois l’expérience définie, les sélecteurs sur lesquels des actions ont été entreprises antérieurement sont introuvables lorsque l’activité est ouverte pour réédition. La page apparaît rompue et aucun avertissement ne s’affiche.

## Le compositeur d’expérience visuelle ou le compositeur d’expérience avancé n’affiche pas mes bannières tournantes ni le contenu comportant du code JavaScript. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_8B5BE6EB050B42D6A14A054724C41330}

Le compositeur d’expérience visuelle bloque par défaut les éléments JavaScript. Vous pouvez utiliser ces éléments si vous désactivez JavaScript dans les paramètres du compositeur d’expérience visuelle. Selon la configuration du site, il est possible que certains éléments continuent à s’afficher incorrectement ou ne soient pas disponibles.

## Lorsque je modifie un élément sur la page, plusieurs éléments changent également. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_309188ACF34942989BE473F63C5710AF}

Si un même ID d’élément DOM est utilisé pour plusieurs éléments de la page, la modification d’un de ces éléments entraîne celle de tous les éléments dotés de cet ID. Pour éviter ce problème, un seul ID doit être utilisé sur chaque page. Il s’agit d’une bonne pratique HTML standard. Pour plus d’informations, consultez les [Scénarios de modification de page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Je ne peux pas modifier des expériences sur un site avec des iFrames. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_9FE266B964314F2EB75604B4D7047200}

Ce problème peut être résolu en activant le compositeur d’expérience avancé. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**, puis cochez la case qui active le compositeur d’expérience avancé. Le compositeur d’expérience avancé utilise un serveur proxy géré par Adobe pour charger votre page pour modification. Ce proxy permet de modifier des sites avec des iFrames et d’effectuer des modifications sur des sites et des pages pour lesquels vous n’avez pas encore ajouté de code Adobe Target. Les activités ne sont pas diffusées sur le site tant que le code n’a pas été ajouté. Certains sites ne peuvent pas se charger via le compositeur d’expérience avancé, auquel cas vous pouvez décocher cette option afin de charger le compositeur d’expérience visuelle au moyen d’une iFrame.

>[!NOTE]
>
>Vos pages hébergées localement ou non accessibles hors de votre réseau ne sont pas accessibles au serveur proxy d’Adobe et ne peuvent pas être ouvertes dans l’EEC. Ces pages peuvent inclure des URL d’évaluation, des URL d’essais d’acceptation par l’utilisateur (EAU) ou des pages hébergées localement.

## Je souhaite configurer des tests sur des pages pour lesquelles l’implémentation mbox/cible n’a pas encore été faite. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_DE63BCCB5B124E10A71FA579B582A80A}

Voir « Je ne peux pas modifier des expériences sur un site avec des iFrames » ci-dessus.

## Les styles de texte gras et italique appliqués avec Modifier le texte/l’HTML ou Modifier le texte/code HTML ne s’affichent pas sur ma page. Il arrive que le texte disparaisse après l’application de ces changements de style. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_7A71D6DF41084C58B34C18701E8774E5}

Si vous utilisez **[!UICONTROL Modifier le texte/l’HTML]** dans le compositeur d’expérience visuelle pour des activités A/B ou de ciblage d’expérience ou **[!UICONTROL Modifier le texte/code HTML]** pour des activités d’Automated Personalization ou de test multivarié pour mettre le texte en gras ou en italique, ces styles ne seront peut-être pas appliqués sur la page ou le texte disparaîtra peut-être de la page dans le compositeur d’expérience visuelle. Cela se produit en raison de la manière dont l’éditeur de texte enrichi applique ces styles qui peuvent interférer avec le balisage du site web.

Si vous rencontrez ce problème :

1. Cliquez sur le bouton **[!UICONTROL HTML]** dans l’éditeur de texte enrichi pour entrer dans le mode de modification du code source.
1. Identifiez les éléments de texte auxquels vous avez appliqué un style.

   * Pour le texte en gras, remplacez les éléments `<strong>`&lt; > par `<b>`.

   * Pour le texte en italique, remplacez les éléments `<em>` par `<i>`.

## La permutation d’image apparaît rompue dans le compositeur d’expérience visuelle ou le compositeur d’expérience avancé pour les activités d’Automated Personalization. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_88AABFDFE6A3420299B0D508B12A3994}

L’ajout d’une offre d’image à un emplacement occupe l’ensemble de l’espace de l’image d’origine dans le compositeur d’expérience visuelle ou le compositeur d’expérience avancé. Lors de la diffusion, l’image n’est pas développée et est affichée en l’état, ce qui n’a aucun impact sur la diffusion.
