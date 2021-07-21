---
keywords: Ciblage;compositeur d’expérience visuelle;liste autorisée;liste autorisée;liste autorisée;liste autorisée;compositeur d’expérience visuelle avancé;vec;dépannage du compositeur d’expérience visuelle;dépannage;eec;compositeur d’expérience avancé;tls;tls 1.2
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans le compositeur d’expérience visuelle (VEC) et le compositeur d’expérience avancé dans l’Adobe  [!DNL Target] sous certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé ?
feature: Compositeur d’expérience visuelle (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 1da930f2dfe13fc7710da000f0d13d6aacd223b1
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 49%

---

# Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé

Dans certains cas, des problèmes d’affichage et d’autres problèmes se produisent parfois dans le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] (compositeur d’expérience visuelle) et le [!UICONTROL compositeur d’expérience avancé] (compositeur d’expérience avancé).

## Comment les stratégies d’application des cookies SameSite de Google Chrome affectent-elles le compositeur d’expérience visuelle et le compositeur d’expérience avancé ? {#samesite}

Gardez à l’esprit les modifications qui affectent le compositeur d’expérience visuelle et le compositeur d’expérience avancé lors de l’utilisation des versions Chrome suivantes :

**Chrome 94 (21 septembre 2021)** : Avec les modifications prévues pour la version 94 de Chrome (21 septembre 2021), la modification suivante a un impact sur tous les utilisateurs possédant des versions de navigateur Chrome 94+ :

* L’indicateur de ligne de commande `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` sera supprimé.

**Chrome 91 (25 mai 2021)** : Avec les modifications mises en oeuvre pour la version 91 de Chrome (25 mai 2021), la modification suivante a un impact sur tous les utilisateurs possédant des versions de navigateur Chrome 91+ :

* Les indicateurs `#same-site-by-default-cookies` et `#cookies-without-same-site-must-be-secure` ont été supprimés de `chrome://flags`. Ce comportement est désormais activé par défaut.

**Chrome 80 (août 2020)** : Avec les modifications mises en oeuvre en août 2020, tous les utilisateurs disposant des versions de navigateur Chrome 80+ :

* *not* pourra-t-il utiliser le VEC (avec ou sans l’extension d’assistance du VEC installée et activée) dans les pages protégées par mot de passe de leurs sites. Les cookies de connexion à votre site sont considérés comme des cookies tiers et sont envoyés avec la demande de connexion. La seule exception concerne lorsque le paramètre SameSite est déjà défini sur &quot;none&quot; pour le cookie de connexion à votre site.
* *not* pourra-t-il télécharger des bibliothèques [!DNL Target] lors de la modification d’une activité (lorsqu’elles ne se trouvent pas déjà sur le site) ? En effet, l’appel de téléchargement est effectué depuis le domaine client vers un domaine d’Adobe sécurisé et est rejeté comme non authentifié.
* Le compositeur d’expérience avancé a0/>not *fonction pour tous les utilisateurs, car il ne peut pas définir l’attribut SameSite pour les cookies sur `adobemc.com domain`.* Sans cet attribut, le navigateur rejette ces cookies, ce qui entraîne l’échec du compositeur d’expérience avancé.

### Déterminer les cookies bloqués

Pour déterminer les cookies qui sont bloqués en raison des stratégies d’application des cookies SameSite, utilisez les outils de développement dans Chrome.

1. Pour accéder aux outils de développement, lors de l’affichage du compositeur d’expérience visuelle dans Chrome, cliquez sur l’icône **[!UICONTROL points de suspension]** dans le coin supérieur droit de Chrome > **[!UICONTROL Autres outils]** > **[!UICONTROL Outils de développement]**.
1. Cliquez sur l’onglet **[!UICONTROL Réseau]** , puis recherchez les cookies bloqués.

   >[!NOTE]
   >
   >Cochez la case **[!UICONTROL Comporte des cookies bloqués]** pour faciliter la recherche des cookies bloqués.

   L’illustration suivante présente un cookie bloqué :

   ![Outils de développement > Onglet Réseau présentant un cookie bloqué](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### Extension d’assistance Google VEC

Adobe a envoyé une extension d’assistance du compositeur d’expérience visuelle mise à jour à Google Chrome Store. Cette extension remplace les attributs de cookie pour définir l’attribut `SameSite="none"`, si nécessaire. [L’extension mise à jour se trouve ici](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en). Pour plus d’informations sur l’installation et l’utilisation de l’extension d’assistance du compositeur d’expérience visuelle, voir [Extension d’assistance du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

Pour les cookies de votre propre site, vous devez spécifier les cookies par nom.

>[!NOTE]
>
>Cette approche ne convient que lorsque tous les cookies sont définis dans un seul domaine. L’assistant du VEC ne permet pas à [!DNL Target] de spécifier des cookies pour plusieurs domaines.

Faites basculer le curseur [!UICONTROL Cookie] sur l’emplacement actif, puis spécifiez le cookie par nom et le domaine du cookie. Le nom du cookie est &quot;mbox&quot; et le domaine du cookie correspond aux deuxième et dernier niveaux des domaines à partir desquels vous diffusez la mbox. Il s’agit d’un cookie propriétaire, puisqu’il est diffusé à partir du domaine de votre société. Exemple: `mycompany.com`. Pour plus d’informations, voir [Cookies Adobe Target](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html?lang=fr) dans le *Guide de l’utilisateur de l’interface Experience Cloud*.

![Bascule des cookies dans l’extension d’assistance de VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### Alternatives et solutions de contournement

Utilisez l’une des options suivantes pour vous assurer que VEC et compositeur d’expérience avancé continuent à fonctionner comme prévu :

* Téléchargez et utilisez l’ [extension d’assistance du VEC](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en) mise à jour.
* Utilisez le navigateur Mozilla Firefox. Firefox n’applique pas encore cette stratégie.
* Utilisez les indicateurs suivants pour exécuter Google Chrome à partir de la ligne de commande jusqu’au 21 septembre 2021. À compter du 21 septembre, votre site web ne fonctionnera plus dans le compositeur d’expérience visuelle. Si vous effectuez une mise à jour vers Chrome 94, vous devez générer manuellement des cookies avec `SameSite=none` et `Secure` sur vos sites web.

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## [!DNL Target] prend-il en charge les iframes à plusieurs niveaux ?

[!DNL Target] ne prend pas en charge les iFrames à plusieurs niveaux. Si votre site web charge un iframe qui possède un iframe enfant, at.js interagit uniquement avec l’iframe parent. [!DNL Target]Les bibliothèques n’interagissent pas avec l’iFrame enfant.

Pour pallier ce problème, vous pouvez ajouter une page dans l’expérience avec l’URL de l’iFrame enfant.

## Lorsque je tente de modifier une page, tout ce que je vois est un compteur au lieu de ma page. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_313001039F79446DB28C70D932AF5F58}

Cette situation peut se produire si l’URL contient un caractère #. Pour corriger le problème, passez en mode Parcourir dans le compositeur d’expérience visuelle, puis repassez en mode Composer. Le compteur doit disparaître et la page doit se charger.

## Les en-têtes CSP (Content Security Policy, stratégie de sécurité du contenu) bloquent les bibliothèques [!DNL Target] de mon site web. (Compositeur d’expérience visuelle et compositeur d’expérience avancé)  {#section_89A30C7A213D43BFA0822E66B482B803}

Si les en-têtes CSP de votre site web bloquent les bibliothèques Target, puis chargent le site web mais empêchent la modification, assurez-vous que les bibliothèques Target ne sont pas bloquées.

>[!NOTE]
>
>Outre les informations suivantes, vous pouvez utiliser l’[extension de navigateur Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) pour Google Chrome.

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

Si un même ID d’élément DOM est utilisé pour plusieurs éléments de la page, la modification d’un de ces éléments entraîne celle de tous les éléments dotés de cet ID. Pour éviter ce problème, un seul ID doit être utilisé sur chaque page. Cette pratique est une bonne pratique HTML standard. Pour plus d’informations, consultez les [Scénarios de modification de page](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

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
