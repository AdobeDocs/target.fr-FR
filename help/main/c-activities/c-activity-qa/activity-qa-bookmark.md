---
keywords: qa;aperçu;signet d’applet;liens d’aperçu
description: Découvrez comment utiliser le signet d’assurance qualité [!DNL Target] d’Adobe pour forcer [!DNL Target] à vous libérer du mode assurance qualité.
title: Comment utiliser le signet d’applet de l’AQ d’activité ?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%
---
# Signet d’applet de l’AQ d’activité {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser le signet d’assurance qualité [!DNL Target] pour quitter le mode **[!UICONTROL Assurance qualité de l’activité]** et afficher votre site comme un visiteur type.

>[!ENDSHADEBOX]

Après avoir parcouru un site web en mode [QA](/help/main/c-activities/c-activity-qa/activity-qa.md), le mode QA persiste sur plusieurs pages jusqu’à l’expiration de votre session [!DNL Target]. Un signet est un signet de navigateur qui exécute JavaScript. Le signet d’assurance qualité [!DNL Target] force [!DNL Target] à vous libérer du mode assurance qualité, de sorte que vous n’ayez pas à attendre l’expiration de la session. Utilisez la version qui correspond à la version at.js déployée sur votre site.

>[!NOTE]
>
>Le processus de création d’un signet d’applet varie en fonction du type et de la version du navigateur. Consultez l&#39;aide de votre navigateur ou recherchez des instructions spécifiques sur Internet.

## Signet d’applet de l’AQ d’activité pour at.js 1.*x*

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

Vous pouvez également vous forcer manuellement à quitter le mode AQ en chargeant une page de votre site avec le paramètre `at_preview_token` défini sur une valeur vide. Par exemple :

`https://www.mysite.com/?at_preview_token=`

## Signet d’applet de l’AQ d’activité pour at.js 2.*x*

Contrairement à at.js 1.*x*, at.js 2.*x* ne prend pas en charge les cookies tiers. Le mode assurance qualité ne persiste que pour le domaine propriétaire, au moyen d’un cookie propriétaire défini par at.js. Par conséquent, la session en mode QA est gérée uniquement du côté client et aucun cookie en mode QA n&#39;est envoyé à [!DNL Target].

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

Après avoir ajouté le signet correspondant à votre version at.js à votre navigateur, utilisez-le chaque fois que vous souhaitez quitter le mode assurance qualité :

1. Ouvrez n’importe quelle page de votre site lorsque vous êtes en mode AQ.
1. Cliquez sur le signet dans la barre d’outils des signets de votre navigateur.
1. Chargez une page de votre site. [!DNL Target] sort la session du mode AQ et le site s’affiche comme pour un visiteur type.
