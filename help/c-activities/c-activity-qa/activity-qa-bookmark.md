---
description: Informations pour vous aider à utiliser le signet d’applet AQ de Target pour forcer Target à vous libérer du mode AQ.
keywords: qa;aperçu;signet d'applet;liens d’aperçu
seo-description: Informations pour vous aider à utiliser le signet d’applet AQ de Target pour forcer Target à vous libérer du mode AQ.
seo-title: Signet d’applet de l’AQ d’activité
solution: Target
title: Signet d’applet de l’AQ d’activité
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Signet d’applet de l’AQ d’activité{#activity-qa-bookmarklet}

Informations pour vous aider à utiliser le signet d’applet AQ de Target pour forcer Target à vous libérer du mode AQ.

Le [mode AQ](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) étant attractif, une fois que vous avez navigué sur un site web en mode AQ, la session Target doit expirer ou Target doit vous libérer du mode AQ pour pouvoir afficher votre site comme un visiteur type. Utilisez le signet d’applet AQ de Target pour vous libérer du mode AQ.

Pour utiliser le signet d’applet AQ Target, créez un signet d’applet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils des signets de votre navigateur :

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

Le signet d’applet doit ensuite apparaître dans la barre d’outils pour être réutilisé.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l’aide ou la recherche de votre navigateur sur Internet pour obtenir des instructions spécifiques.

Vous pouvez également quitter manuellement le mode AQ en chargeant une page de votre site avec le paramètre `at_preview_token` doté d’une valeur vide (par exemple, `https://www.mysite.com/?at_preview_token=`).
