---
keywords: qa;preview;bookmarklet;preview links
description: Informations destinées à vous aider à utiliser le signet d’applet AQ d’Adobe Target pour forcer la Cible à vous libérer du mode AQ.
title: Signet d'applet d'assurance qualité Activité pour Adobe Target
feature: qa
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# Signet d’applet de l’AQ d’activité{#activity-qa-bookmarklet}

Informations destinées à vous aider à utiliser le signet d’applet [!DNL Target] AQ pour forcer [!DNL Target] à vous libérer du mode AQ.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l’aide ou la recherche de votre navigateur sur Internet pour obtenir des instructions spécifiques.

## Signet d’Activité de contrôle qualité pour at.js 1.*x*

Le [mode AQ](/help/c-activities/c-activity-qa/activity-qa.md) étant attractif, une fois que vous avez navigué sur un site web en mode AQ, la session doit expirer ou doit vous libérer du mode AQ pour pouvoir afficher votre site comme un visiteur type. [!DNL Target][!DNL Target] Utilisez le signet d’applet [!DNL Target] QA pour vous forcer à quitter le mode AQ.

Pour utiliser le signet d’applet [!DNL Target] QA, créez un signet d’applet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils Signets de votre navigateur :

```javascript
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

Vous pouvez également vous forcer manuellement à quitter le mode de contrôle qualité en chargeant une page de votre site avec le paramètre `at_preview_token` avec une valeur vide.

Par exemple :

`https://www.mysite.com/?at_preview_token=`

## Signet d’Activité de contrôle qualité pour at.js 2.*x*

Contrairement à at.js 1.*x*, at.js 2.** xne prend pas en charge les cookies tiers et le mode AQ reste uniquement attractive pour le domaine propriétaire (au moyen d’un cookie propriétaire défini par at.js). Ainsi, dans at.js 2.*x*, la session du mode AQ est gérée uniquement côté client et aucun cookie du mode AQ n’est envoyé à la Cible.

Pour utiliser le signet d’applet [!DNL Target] QA, créez un signet d’applet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils Signets de votre navigateur :

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## Utilisation du signet d’applet Contrôle qualité de l’Activité

Cliquez sur le signet d’applet dans la barre d’outils du navigateur.

