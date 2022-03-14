---
keywords: qa;aperçu;signet d’applet;liens d’aperçu
description: Découvrez comment utiliser l’Adobe [!DNL Target] signet d’applet AQ à forcer [!DNL Target] pour vous libérer du mode AQ.
title: Comment utiliser le signet d’applet AQ d’activité ?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 27%

---

# Signet d’applet de l’AQ d’activité

Informations relatives à l’utilisation de la variable [!DNL Target] signet d’applet AQ à forcer [!DNL Target] pour vous libérer du mode AQ.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l’aide ou la recherche de votre navigateur sur Internet pour obtenir des instructions spécifiques.

## signet d’applet AQ d’activité pour at.js 1.*x*

Le [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md) étant attractif, une fois que vous avez navigué sur un site web en mode AQ, la session doit expirer ou doit vous libérer du mode AQ pour pouvoir afficher votre site comme un visiteur type. [!DNL Target][!DNL Target] Utilisation de l’AQ [!DNL Target] signet d’applet pour vous libérer du mode AQ.

Pour utiliser la variable [!DNL Target] signet d’applet AQ, créez un signet d’applet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils des signets de votre navigateur :

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

Vous pouvez également vous libérer manuellement du mode AQ en chargeant une page de votre site avec l’événement `at_preview_token` avec une valeur vide.

Par exemple :

`https://www.mysite.com/?at_preview_token=`

## signet d’applet AQ d’activité pour at.js 2.*x*

Contrairement à at.js 1.*x*, at.js 2.*x* ne prend pas en charge les cookies tiers et le mode AQ n’est attractif que pour le domaine propriétaire (au moyen d’un cookie propriétaire défini par at.js). Par conséquent, dans at.js 2.*x*, la session du mode AQ est gérée uniquement côté client et aucun cookie du mode AQ n’est envoyé à Target.

Pour utiliser la variable [!DNL Target] signet d’applet AQ, créez un signet d’applet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils des signets de votre navigateur :

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

## Utilisation du signet d’applet AQ d’activité

Cliquez sur le signet d’applet dans la barre d’outils de votre navigateur.
