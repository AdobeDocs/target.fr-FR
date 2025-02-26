---
keywords: qa;aperçu;signet d’applet;liens d’aperçu
description: Découvrez comment utiliser le signet Adobe [!DNL Target] QA pour forcer  [!DNL Target]  à quitter le mode assurance qualité.
title: Comment utiliser le signet d’applet de l’AQ d’activité ?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 4b5111c00384fdc73eaadbf0eec22ac6c2784a22
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 13%

---

# Signet d’applet de l’AQ d’activité

Informations destinées à vous aider à utiliser le signet d’assurance qualité [!DNL Target] pour forcer [!DNL Target] à quitter le mode assurance qualité.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l’aide ou la recherche de votre navigateur sur Internet pour obtenir des instructions spécifiques.

## Signet d’applet de l’AQ d’activité pour at.js 1.*x*

Étant donné que le [mode assurance qualité](/help/main/c-activities/c-activity-qa/activity-qa.md) est contigu, après avoir parcouru un site web en mode assurance qualité, votre session [!DNL Target] doit expirer ou vous devez être libéré [!DNL Target] du mode assurance qualité avant de pouvoir afficher votre site comme un visiteur standard. Utilisez le signet d’[!DNL Target] de l’assurance qualité pour vous forcer à quitter le mode assurance qualité.

Pour utiliser le signet d’assurance qualité [!DNL Target], créez un signet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils des signets de votre navigateur :

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

Vous pouvez également vous forcer manuellement à quitter le mode AQ en chargeant une page de votre site avec le paramètre `at_preview_token` avec une valeur vide.

Par exemple :

`https://www.mysite.com/?at_preview_token=`

## Signet d’applet de l’AQ d’activité pour at.js 2.*x*

À la différence d’at.js 1.*x*, at.js 2.*x* ne prend pas en charge les cookies tiers et le mode QA n’est actif que pour le domaine propriétaire (au moyen d’un cookie propriétaire défini par at.js). Ainsi, dans at.js 2.*x*, la session en mode QA est gérée uniquement côté client et aucun cookie en mode QA n’est envoyé à Target.

Pour utiliser le signet d’assurance qualité [!DNL Target], créez un signet contenant le code JavaScript suivant et ajoutez-le à la barre d’outils des signets de votre navigateur :

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## Utiliser le signet d’AQ d’activité

Cliquez sur le signet dans la barre d’outils du navigateur.
