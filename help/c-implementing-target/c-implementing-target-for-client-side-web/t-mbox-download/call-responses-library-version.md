---
description: La façon dont Target effectue des appels et y répond depuis la page dépend de la version de la bibliothèque de Target utilisée, de la présence de l’implémentation de l’identifiant visiteur Experience Cloud et de l’existence de l’identifiant visiteur.
title: Méthodes de page Target par version de bibliothèque mbox.js
feature: at.js
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 92%

---


# Méthodes de page Target par version de bibliothèque mbox.js{#target-page-methods-by-mbox-js-library-version}

La façon dont Target effectue des appels et y répond depuis la page dépend de la version de la bibliothèque de Target utilisée, de la présence de l’implémentation de l’identifiant visiteur Experience Cloud et de l’existence de l’identifiant visiteur.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Si vous utilisez [!DNL at.js], tous les appels sont effectués à l’aide de JSON. Cette page contient des informations détaillées sur les versions de la bibliothèque [!DNL mbox.js]. Les comportements décrits dans les scénarios ci-après ne s’appliquent pas à [!DNL at.js].

Cette section fournit des informations sur la façon dont chaque version de la bibliothèque [!DNL Target] répond à l’appel [!DNL Target] depuis votre page dans le cadre des scénarios suivants.

Selon votre implémentation et la version de la bibliothèque, il existe plusieurs types ou points de terminaison. Vous devez maîtriser chaque type pour comprendre comment [!DNL Target] répond aux appels dans chaque scénario.

| Type/point de terminaison | Méthode d’appel | Contenu de la réponse |
|--- |--- |--- |
| autocreate global mbox - synchrone | document.write pour effectuer l’appel | JavaScript sans document.write() |
| autocreate global mbox - asynchrone | createElement() pour ajouter l’appel au corps | JavaScript sans document.write() |
| standard | document.write pour effectuer l’appel | JavaScript avec document.write() |
| ajax | createElement() pour ajouter l’appel au corps | JavaScript sans document.write() |
| json | XMLHTTPrequest() pour effectuer l’appel | renvoie une réponse JSON |

>[!IMPORTANT]
>
>Pour tous les types à l’exception de standard, tous les codes personnalisés et les offres doivent être écrits pour prendre en charge un environnement ajax. Par exemple, si vous utilisez un JavaScript qui comprend `document.write()`, le script ne fonctionnera pas comme prévu.

## Aucune implémentation de l’identifiant visiteur {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

Si vous utilisez [!DNL Target Standard] ou [!DNL Premium] avec [!DNL mbox.js] et si vous avez activé la [!UICONTROL création de la mbox globale] pour votre compte, le type d’appel **autocreate global mbox** - synchrone est effectué et une réponse est renvoyée, indépendamment de la version de [!DNL mbox.js].

Si vous écrivez votre propre code personnalisé au lieu d’utiliser les actions du [!UICONTROL compositeur d’expérience visuelle], veillez à ce que le code soit adapté à un environnement ajax. Par exemple, si vous utilisez un JavaScript qui comprend `document.write()`, le script ne fonctionnera pas comme prévu.

>[!NOTE]
>
>Plusieurs appels de mbox ajax avec le même nom de mbox et des paramètres différents ne fonctionneront pas sur une même page. Seul le premier appel est effectué.

Si vous utilisez « création automatique de mbox globale » mais qu’il existe aussi des appels `mboxCreate` sur votre page (si vous implémentez par exemple [!DNL Target Standard] ou [!DNL Premium] sur une page qui utilisait auparavant une implémentation héritée), les appels de mbox globale sont effectués à l’aide du point de terminaison** autocreate global mbox - standard** et les appels `mboxCreate` sont réalisés à l’aide du point de terminaison **standard**. Le point de terminaison **standard** utilise `document.write()` pour effectuer l’appel et répondre. Le chargement de la page est bloqué, notamment la diffusion du contenu dans la réponse ajax, jusqu’à ce que toutes les informations soient téléchargées.

Si vous utilisez uniquement mboxCreate sur les pages créées à l’aide de [!DNL Target Classic], par exemple, la page fonctionne normalement.

| Méthode de création | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchrone | autocreate global mbox - synchrone | autocreate global mbox - synchrone | autocreate global mbox - synchrone |
| mboxCreate | standard | standard | standard | standard |

## Implémentation de l’identifiant visiteur présente sans aucun identifiant visiteur défini {#section_29888A119C7A4753AD287FC845AA63F4}

Si aucun identifiant visiteur n’a été défini, il n’existe pas de cookie visiteur [!DNL Experience Cloud] pour l’utilisateur. La page effectue un appel au service d’identification des visiteurs pour obtenir l’identifiant visiteur. attend que la réponse avec l’identifiant effectue l’appel[!DNL Target].

>[!NOTE]
>
>[!DNL Mbox.js] v58 est vivement recommandé pour s’assurer que l’identifiant visiteur est renvoyé avant le lancement de l’appel Target.

Si vous utilisez la version 57 de [!DNL mbox.js] dans ce scénario, tout fonctionne normalement s’il n’existe pas d’implémentation de l’identifiant visiteur, comme décrit dans le précédent scénario. À partir de la version 58 de [!DNL mbox.js], le service [!DNL Experience Cloud Visitor ID] renvoie un identifiant visiteur avant que les appels [!DNL Target] ne soient effectués. Cela permet que les données d’audience qui sont partagées à l’aide du service de base des profils et des audiences soient disponibles pour le premier appel [!DNL Target] dans la session du visiteur. Pour éviter le scintillement du contenu par défaut avant le renvoi du contenu du test, [!DNL Target] masque la `<BODY>` jusqu’au retour du service d’identifiant visiteur. Dans la version 58, `display:none` est utilisée pour masquer la page. Cela entraîne un problème relatif aux sites réactifs. C’est la raison pour laquelle la propriété `opacity:0` est utilisée à partir de la version 59 pour masquer le contenu.

| Méthode de création | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchrone | autocreate global mbox - asynchrone | autocreate global mbox - asynchrone | autocreate global mbox - asynchrone |
| mboxCreate | standard | ajax | ajax | ajax |

## Implémentation de l’identifiant visiteur présente et identifiant visiteur existant  {#section_9CD4AE4C8186425D886398BC3CE6C46D}

Si le cookie d’identifiant visiteur existe, [!DNL Target] n’a pas à effectuer d’appel au service d’identification des visiteurs. Dans ce cas, il n’est pas nécessaire d’attendre la réponse du service d’identification des visiteurs avant d’afficher le contenu. Dans les versions 57 à 59, le type **autocreate global mbox - synchrone** est utilisé. La page attend donc que l’appel à [!DNL Target] renvoie une réponse avant de continuer le chargement. Ainsi, aucun scintillement du contenu par défaut n’est visible. Dans la version 60, le type **global mbox - asynchrone** est utilisé pour s’assurer que [!DNL Target] attende la réponse du service d’exclusion [!DNL Experience Cloud]. Le service d’exclusion fait partie de la version Data Co-op publiée à l’automne 2016. Dans la mesure où tous les appels sont renvoyés à l’aide d’ajax, `document.write()` ne doit pas être utilisé avec la version 60 de [!DNL mbox.js].

| Méthode de création | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocreate global mbox | autocreate global mbox - synchrone | autocreate global mbox - synchrone | autocreate global mbox - synchrone | autocreate global mbox - asynchrone (pour prendre en charge de développement de la version de Data Co-op qui sera publiée à l’automne 2016) |
| mboxCreate | standard | standard | standard | ajax |