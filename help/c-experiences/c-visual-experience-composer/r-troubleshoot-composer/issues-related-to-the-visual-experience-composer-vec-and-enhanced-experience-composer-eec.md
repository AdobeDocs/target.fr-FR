---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: Dans certaines circonstances, des problèmes d’affichage se produisent parfois dans le compositeur d’expérience visuelle et le compositeur d’expérience avancé.
title: Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé
feature: vec
uuid: 93f646d9-fcbc-43f0-9f84-0ce8e486ff7f
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 98%

---


# Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé{#troubleshooting-issues-related-to-the-visual-experience-composer-and-enhanced-experience-composer}

Dans certaines circonstances, des problèmes d’affichage se produisent parfois dans le compositeur d’expérience visuelle et le compositeur d’expérience avancé.

## Target prend-il en charge les iframes à plusieurs niveaux ?

Target ne prend pas en charge les iFrames à plusieurs niveaux. Si votre site Web charge un iFrame qui possède un iframe enfant, les bibliothèques Target (at.js et mbox.js) interagissent avec l’iFrame parent uniquement. Les bibliothèques Target n’interagissent pas avec l’iFrame enfant.

Pour pallier ce problème, vous pouvez ajouter une page dans l’expérience avec l’URL de l’iFrame enfant.

## Lorsque je tente de modifier une page, tout ce que je vois est un compteur au lieu de ma page. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_313001039F79446DB28C70D932AF5F58}

Cela se produit si l’URL comporte un caractère #. Pour corriger le problème, passez en mode Parcourir dans le compositeur d’expérience visuelle, puis repassez en mode Composer. Le compteur doit disparaître et la page doit se charger.

## Les en-têtes CSP (Content Security Policy, stratégie de sécurité du contenu) bloquent les bibliothèques Target sur mon site web. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_89A30C7A213D43BFA0822E66B482B803}

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

## Le compositeur d’expérience visuelle et le compositeur d’expérience avancé semblent rompus et ne s’initialisent pas lors de la réédition d’une activité enregistrée. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Si le site web a été modifié en dehors du compositeur d’expérience visuelle une fois l’expérience définie, les sélecteurs sur lesquels des actions ont été entreprises antérieurement sont introuvables lorsque l’activité est ouverte pour réédition. La page apparaît rompue et aucun avertissement ne s’affiche.

## Le compositeur d’expérience visuelle ou le compositeur d’expérience avancé n’affiche pas mes bannières tournantes ni le contenu comportant du code JavaScript. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_8B5BE6EB050B42D6A14A054724C41330}

Le compositeur d’expérience visuelle bloque par défaut les éléments JavaScript. Vous pouvez utiliser ces éléments si vous désactivez JavaScript dans les paramètres du compositeur d’expérience visuelle. Selon la configuration du site, il est possible que certains éléments continuent à s’afficher incorrectement ou ne soient pas disponibles.

## Échec du chargement de mon fichier target.js hébergé lors des chargements consécutifs de la page. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_87F6418C2CD142A7B4D1E7037935F81F}

Ce problème survient quand les clients ont une version de mbox.js antérieure à la version 57 (c.-à-d. version 56 ou antérieure).

Nous recommandons à tous les utilisateurs du compositeur d’expérience visuelle de mettre à niveau la [dernière version de mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) ou d’effectuer au moins la mise à niveau vers la version 57. Vous devez également envisager [d’effectuer la transition vers at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

## Lorsque je modifie un élément sur la page, plusieurs éléments changent également. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_309188ACF34942989BE473F63C5710AF}

Si un même ID d’élément DOM est utilisé pour plusieurs éléments de la page, la modification d’un de ces éléments entraîne celle de tous les éléments dotés de cet ID. Pour éviter ce problème, un seul ID doit être utilisé sur chaque page. Il s’agit d’une bonne pratique HTML standard. Pour plus d’informations, consultez les [Scénarios de modification de page](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Je ne peux pas modifier des expériences sur un site avec des iFrames. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_9FE266B964314F2EB75604B4D7047200}

Ce problème peut être résolu en activant le compositeur d’expérience avancé. Click **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**, then select the check box that enables the Enhanced Experience Composer. Le compositeur d’expérience avancé utilise un serveur proxy géré par Adobe pour charger votre page pour modification. Il permet de modifier des sites avec des iFrames ainsi que des sites et des pages pour lesquels vous n’avez pas encore ajouté de code Adobe Target. Les activités ne sont pas diffusées sur le site tant que le code n’a pas été ajouté. Certains sites ne peuvent pas se charger via le compositeur d’expérience avancé, auquel cas vous pouvez décocher cette option afin de charger le compositeur d’expérience visuelle au moyen d’une iFrame. []

>[!NOTE]
>
>Vos pages hébergées localement ou non accessibles hors de votre réseau ne sont pas accessibles au serveur proxy d’Adobe et ne peuvent pas être ouvertes dans l’EEC. Ces pages peuvent inclure des URL d’évaluation, des URL d’essais d’acceptation par l’utilisateur (EAU) ou des pages hébergées localement.

## Je souhaite configurer des tests sur des pages pour lesquelles l’implémentation mbox/cible n’a pas encore été faite. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Voir « Je ne peux pas modifier des expériences sur un site avec des iFrames » ci-dessus.

## Les styles de texte gras et italique appliqués avec Modifier le texte/l’HTML ou Modifier le texte/code HTML ne s’affichent pas sur ma page. Il arrive que le texte disparaisse après l’application de ces changements de style. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_7A71D6DF41084C58B34C18701E8774E5}

Si vous utilisez **[!UICONTROL Modifier le texte/l’HTML]** dans le compositeur d’expérience visuelle pour des activités A/B ou de ciblage d’expérience ou **[!UICONTROL Modifier le texte/code HTML]** pour des activités d’Automated Personalization ou de test multivarié pour mettre le texte en gras ou en italique, ces styles ne seront peut-être pas appliqués sur la page ou le texte disparaîtra peut-être de la page dans le compositeur d’expérience visuelle. En effet, la façon dont l’éditeur de texte enrichi applique ces styles peut interférer avec le balisage du site.

Si vous rencontrez ce problème :

1. Cliquez sur le bouton **[!UICONTROL HTML]** dans l’éditeur de texte enrichi pour entrer dans le mode de modification du code source.
1. Identifiez les éléments de texte auxquels vous avez appliqué un style.

   * Pour le texte en gras, remplacez les éléments `<strong>`&lt; > par `<b>`.

   * Pour le texte en italique, remplacez les éléments `<em>` par `<i>`.

## La permutation d’image apparaît rompue dans le compositeur d’expérience visuelle ou le compositeur d’expérience avancé pour les activités d’Automated Personalization. (Compositeur d’expérience visuelle et compositeur d’expérience avancé) {#section_88AABFDFE6A3420299B0D508B12A3994}

L’ajout d’une offre d’image à un emplacement occupe l’ensemble de l’espace de l’image d’origine dans le compositeur d’expérience visuelle ou le compositeur d’expérience avancé. Lors de la diffusion, l’image n’est pas développée et est affichée en l’état, ce qui n’a aucun impact sur la diffusion.
