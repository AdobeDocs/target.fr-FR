---
keywords: Ciblage;compositeur d’expérience visuelle;liste blanche;liste blanche;;liste autorisée;compositeur d’expérience visuelle amélioré;vec;dépannage du compositeur d’expérience visuelle;dépannage;eec;compositeur d’expérience amélioré;tls;tls 1.2
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans le [!DNL Target] [!UICONTROL compositeur d’expérience visuelle] (VEC) et le [!UICONTROL compositeur d’expérience amélioré] (EEC) sous certaines conditions.
title: Comment résoudre les problèmes liés au [!UICONTROL compositeur d’expérience visuelle] et au [!UICONTROL compositeur d’expérience amélioré] ?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: 'https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 13%
---
# Résolution des problèmes liés au [!DNL Adobe Target] [!UICONTROL compositeur d’expérience visuelle] et au [!UICONTROL compositeur d’expérience amélioré] {#vec-eec-issues}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment résoudre les problèmes qui affectent le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) et le **[!UICONTROL compositeur d’expérience amélioré]** (EEC).

>[!ENDSHADEBOX]

Des problèmes d’affichage et d’autres problèmes surviennent parfois dans le [!DNL Target] **[!UICONTROL compositeur d’expérience visuelle]** (VEC) et le **[!UICONTROL compositeur d’expérience amélioré]** (EEC) sous certaines conditions. Les éléments suivants décrivent les problèmes qui affectent les deux compositeurs et comment les résoudre.

## Navigateur et sécurité

### Politiques de cookie Google Chrome samesite {#samesite}

Les politiques d’application des cookies SameSite de [!DNL Google Chrome] affectent le VEC et l’EEC dans les versions suivantes.

>[!NOTE]
>
>La modification suivante s’applique aux trois versions. Le compositeur d’expérience visuelle ne peut pas être utilisé sur les pages du site protégées par mot de passe à moins que l’[extension d’assistance du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) ne soit installée et activée. Les cookies de connexion du site sont considérés comme des cookies tiers. Ils ne sont donc pas envoyés avec des demandes de connexion dans l’éditeur du compositeur d’expérience visuelle en mode **[!UICONTROL Parcourir]**. La seule exception est lorsque les attributs `SameSite=None` et `Secure` sont déjà définis pour les cookies de connexion.

* **Chrome 94 (21 septembre 2021) :** pour tous les utilisateurs disposant de Chrome 94 et versions ultérieures, l’indicateur de ligne de commande `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` a été supprimé.
* **Chrome 91 (25 mai 2021) :** Pour tous les utilisateurs disposant de Chrome 91 et versions ultérieures, les indicateurs `#same-site-by-default-cookies` et `#cookies-without-same-site-must-be-secure` ont été supprimés de `chrome://flags`. Ce comportement est désormais activé par défaut.
* **Chrome 80 (août 2020) :** pour tous les utilisateurs disposant de Chrome 80 et versions ultérieures :

  * [!DNL Target] bibliothèques ne peuvent pas être téléchargées lorsqu’une activité est modifiée si elles ne se trouvent pas déjà sur le site. L&#39;appel de téléchargement est effectué du domaine client vers un domaine [!DNL Adobe] sécurisé et est rejeté comme non authentifié.
  * L’EEC ne fonctionne pas, car il ne peut pas définir l’attribut SameSite pour les cookies sur le domaine `adobemc.com`. Sans cet attribut, le navigateur rejette ces cookies, ce qui entraîne l’échec de l’EEC.

+++ Détermination des cookies bloqués

Pour déterminer les cookies bloqués par les politiques d’application des cookies SameSite, utilisez le [!DNL Developer Tools] dans [!DNL Chrome].

1. Lors de l’affichage du compositeur d’expérience visuelle dans [!DNL Chrome], cliquez sur l’icône **[!UICONTROL points de suspension]** en haut à droite de Chrome > **[!UICONTROL Plus d’outils]** > **[!UICONTROL Outils de développement]**.
1. Cliquez sur l&#39;onglet **[!UICONTROL Réseau]**, puis recherchez les cookies bloqués.

   >[!NOTE]
   >
   >Utilisez la case à cocher **[!UICONTROL A bloqué les cookies]** pour faciliter la recherche des cookies bloqués.

+++

+++ Les en-têtes de la politique de sécurité du contenu (CSP) bloquent les bibliothèques [!DNL Target] sur le site web

Si les en-têtes CSP du site web bloquent les bibliothèques [!DNL Target], le site web se charge mais la modification est empêchée. Assurez-vous que les bibliothèques [!DNL Target] ne sont pas bloquées.

>[!NOTE]
>
>En plus des informations suivantes, l’extension de navigateur [Assistant du compositeur d’expérience visuelle d’Adobe Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) pour [!DNL Google Chrome] peut être utilisée.

![Console du navigateur affichant une requête bloquée pour target.js avec le message indiquant que la directive de la politique de sécurité du contenu a été enfreinte](assets/cps_headers.png)

Pour pallier ce problème, configurez une règle [!DNL Requestly] pour supprimer les en-têtes CSP, comme illustré ci-dessous.

![Boîte de dialogue de demande, Modifier les en-têtes dans la requête et la réponse HTTP, avec une règle nommée Content-Security-Policy qui supprime l&#39;en-tête Content-Security-Policy de la réponse](assets/cps_headers_2.png)

Une règle [!DNL Requestly] similaire peut être configurée pour tout en-tête qui entraîne le non chargement d’une ressource dans le VEC. Lorsque des en-têtes doivent être supprimés avec [!DNL Requestly], effectuez l’une des opérations suivantes :

* Ajoutez des règles d’URL pour que l’URL s’ouvre dans le VEC, de sorte que les en-têtes soient supprimés pour ces URL uniquement.
* Activez la règle lors de la modification dans le VEC et désactivez-la lorsque le VEC n’est pas en cours d’utilisation.

+++

+++ Les iframes à plusieurs niveaux ne sont pas pris en charge

[!DNL Target] ne prend pas en charge les iFrames à plusieurs niveaux. Si le site web charge un iframe qui a un iframe enfant, at.js interagit uniquement avec l’iframe parent. Les bibliothèques [!DNL Target] n’interagissent pas avec l’iframe enfant.

Pour pallier ce problème, ajoutez une page dans l’expérience avec l’URL de l’iframe enfant.

+++

+++ Les expériences ne peuvent pas être modifiées sur un site qui démolit des iFrames ou sur des pages sans l’implémentation [!DNL Target]

Activez le **[!UICONTROL compositeur d’expérience amélioré]** (EEC) pour résoudre ce problème. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Compositeur d’expérience visuelle]**, puis cochez la case qui active le **[!UICONTROL Compositeur d’expérience amélioré]**.

L’EEC utilise un proxy géré par [!DNL Adobe] pour charger la page à modifier. Ce proxy permet la modification sur les sites qui démolissent des iFrames, ainsi que sur les sites et les pages où le code [!DNL Adobe Target] n’a pas encore été ajouté. Les activités ne sont pas diffusées sur le site tant que le code n’a pas été ajouté. Certains sites peuvent ne pas charger via l’EEC. Dans ce cas, la désactivation de cette option charge la page via un iFrame.

>[!NOTE]
>
>Les pages hébergées localement et celles qui ne sont pas accessibles en dehors du réseau ne sont pas accessibles au serveur proxy [!DNL Adobe] et ne peuvent pas être ouvertes dans le CEE. Ces pages peuvent inclure des URL d’évaluation, des URL d’essais d’acceptation par l’utilisateur (EAU) ou des pages hébergées localement.

+++

## Chargement et affichage de la page

+++ Une double flèche s’affiche à la place de la page lorsqu’une page est modifiée

Cette situation peut se produire si l’URL contient un caractère #. Pour résoudre le problème, passez en mode **[!UICONTROL Parcourir]** dans le VEC ou l’EEC, puis revenez au mode **[!UICONTROL Composer]**. Le compteur doit disparaître et la page doit se charger.

+++

+++ Le compositeur d’expérience visuelle ou l’EEC semble endommagé ou ne s’initialise pas lorsqu’une activité enregistrée est de nouveau modifiée

Si le site web a été modifié en dehors du compositeur d’expérience visuelle après la définition de l’expérience, les sélecteurs sur lesquels des actions ont été entreprises précédemment sont introuvables lorsque l’activité est ouverte pour modification. La page apparaît rompue et aucun avertissement ne s’affiche.

+++

+++ Les bannières rotatives et tout autre contenu contenant du JavaScript ne s’affichent pas dans le VEC ou l’EEC

Par défaut, le compositeur d’expérience visuelle bloque les éléments JavaScript. La désactivation de JavaScript permet de travailler avec ces éléments. Selon la configuration du site, il est possible que certains éléments continuent à s’afficher incorrectement ou ne soient pas disponibles.

+++

+++ Pour les activités Automated Personalization, la permutation d’images apparaît endommagée dans le VEC ou l’EEC

L’ajout d’une offre d’image à un emplacement occupe l’ensemble de l’espace de l’image d’origine dans le compositeur d’expérience visuelle ou le compositeur d’expérience avancé. Lors de la diffusion, l’image n’est pas développée et est affichée en l’état, ce qui n’a aucun impact sur la diffusion.

+++

## Modification des résultats

+++ La modification d’un élément sur la page modifie plusieurs éléments

Si un même ID d’élément DOM est utilisé pour plusieurs éléments de la page, la modification d’un de ces éléments entraîne celle de tous les éléments dotés de cet ID. Pour éviter cela, utilisez un identifiant une seule fois sur chaque page. Il s’agit d’une bonne pratique HTML standard. Pour plus d&#39;informations, voir [Scénarios de modification de page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#vec-scenarios).

+++

+++ Les styles de texte en gras et en italique ne s’affichent pas ou le texte disparaît après l’application de Modifier le texte/Modifier HTML ou Modifier le texte/Modifier HTML

Lorsque l’option **[!UICONTROL Modifier le texte]**/**[!UICONTROL Modifier HTML]** est utilisée dans le VEC pour les activités **[!UICONTROL Test A/B]** ou **[!UICONTROL Ciblage d’expérience]**, ou **[!UICONTROL Modifier le texte]**/**[!UICONTROL Modifier HTML]** est utilisée pour les activités **[!UICONTROL Automated Personalization]** ou **[!UICONTROL Test multivarié]**, afin de rendre le texte en gras ou en italique, les styles peuvent ne pas être appliqués à la page ou le texte peut disparaître de la page dans le VEC. Cela se produit, car la manière dont l’éditeur de texte enrichi applique ces styles peut interférer avec le balisage du site web.

Si ce problème se produit :

1. Cliquez sur le bouton **[!UICONTROL HTML]** dans l’éditeur de texte enrichi pour entrer dans le mode de modification du code source.
1. Recherchez les éléments de texte stylisés.

   * Pour le texte en gras, remplacez les éléments `<strong>`&lt; > par `<b>`.
   * Pour le texte en italique, remplacez les éléments `<em>` par `<i>`.

+++
