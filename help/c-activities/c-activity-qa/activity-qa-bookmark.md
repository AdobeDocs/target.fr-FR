---
keywords: qa;preview;bookmarklet;preview links
description: Informations destinées à vous aider à utiliser le signet d’applet AQ d’Adobe Target pour forcer la Cible à vous libérer du mode AQ.
title: Signet d'applet d'assurance qualité Activité pour Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: d858f17baff9a7d863be0888200800b3f0d0f301
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# Signet d’applet de l’AQ d’activité{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l’aide ou la recherche de votre navigateur sur Internet pour obtenir des instructions spécifiques.

## Signet d’Activité de contrôle qualité pour at.js 1.*x*

Le [mode AQ](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) étant attractif, une fois que vous avez navigué sur un site web en mode AQ, la session doit expirer ou doit vous libérer du mode AQ pour pouvoir afficher votre site comme un visiteur type. [!DNL Target][!DNL Target] Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

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

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

Par exemple :

`https://www.mysite.com/?at_preview_token=`

## Signet d’Activité de contrôle qualité pour at.js 2.*x*

Contrairement à at.js 1.*x*, at.js 2.*x* ne prend pas en charge les cookies tiers et le mode AQ n’est attractif que pour le domaine propriétaire (au moyen d’un cookie propriétaire défini par at.js). Ainsi, dans at.js 2.*x*, la session du mode AQ est gérée uniquement côté client et aucun cookie du mode AQ n’est envoyé à la Cible.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Max-Age=-99999999;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.location.href = url.substring(0, url.length - 1);
        }
    })();
```

## Utilisation du signet d’applet Contrôle qualité de l’Activité

Cliquez sur le signet d’applet dans la barre d’outils du navigateur.

