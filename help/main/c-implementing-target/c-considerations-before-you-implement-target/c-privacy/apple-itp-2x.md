---
keywords: apple;ITP;prévention du suivi intelligent;experience cloud id;ecid;itp
description: En savoir plus sur Adobe [!DNL Target] et l’impact de l’initiative ITP (Intelligent Tracking Prevention) d’Apple, qui vise à protéger la confidentialité des utilisateurs de Safari.
title: Comment [!DNL Target] Gérer la prise en charge d’Apple ITP ?
feature: Privacy & Security
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 38%

---

# ITP (Intelligent Tracking Prevention) 2.x d’Apple

ITP (Intelligent Tracking Prevention) est une initiative d’Apple pour protéger la confidentialité des utilisateurs de Safari. La première version d’ITP, qui date de 2017, concernait l’utilisation des cookies tiers. En fait, Apple bloquait entièrement les cookies tiers, ce qui gênait les entreprises technologiques et marketing, car ceux-ci servent généralement au suivi des visiteurs et à la collecte des données des visiteurs. Maintenant, Apple souhaite limiter l’utilisation des cookies propriétaires dans Safari.

Ces versions d’ITP comprennent les restrictions suivantes :

| Version | Détails |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Limite à sept jours le délai d’expiration des cookies côté client qui sont placés sur le navigateur à l’aide de l’API `document.cookie`.<br>Publié le 21 février 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Réduit de façon drastique la limite de délai d’expiration de sept jours à un jour.<br>Publié le 24 avril 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Suppression de plusieurs solutions, telles que l’utilisation de localStorage ou de JavaScript. `Document.referrer property`.<br>Publié le 23 septembre 2019.<br>Fonctionnalité de défense avec cloaking CNAME sur ITP sortie dans Safari 14, macOS Big Sur, Catalina, Mojave, iOS 14 et iPadOS 14. Tous les cookies créés par une réponse HTTP sécurisée CNAME tiers expireront dans sept jours.<br>Annoncé le 12 novembre 2020. |

## Quel est l&#39;impact pour moi en tant qu&#39;Adobe ? [!DNL Target] client ? {#impact}

[!DNL Target] fournit des bibliothèques JavaScript que vous pouvez déployer sur vos pages afin que [!DNL Target] puisse effectuer une personnalisation en temps réel pour vos visiteurs. Il existe trois bibliothèques JavaScript Target at.js 1.x, at.js 2.x qui placent le côté client [!DNL Target] des cookies sur les navigateurs de vos visiteurs via la variable `document.cookie` API. Par conséquent, [!DNL Target] les cookies sont affectés par ITP 2.1, 2.2 et 2.3 d’Apple et expirent après sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3).

Incidences d’Apple ITP 2.x [!DNL Target] dans les domaines suivants :

| Impact | Détails |
| --- | --- |
| Augmentation éventuelle du nombre de visiteurs uniques | Étant donné que la fenêtre d’expiration est définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), vous pouvez constater une augmentation des visiteurs uniques provenant des navigateurs Safari. Si vos visiteurs reviennent sur votre domaine au bout de sept jours (ITP 2.1) ou un jour (ITP 2.2 et ITP 2.3), [!DNL Target] est forcé de placer une nouvelle [!DNL Target] sur votre domaine à la place du cookie expiré. Le nouveau cookie [!DNL Target] convertit un utilisateur en nouveau visiteur unique, même s’il s’agit d’un même utilisateur. |
| Diminution des périodes de recherche pour les activités [!DNL Target] | La période de recherche des profils de visiteur des activités [!DNL Target]peut être réduite pour la prise de décision. Les cookies [!DNL Target] sont utilisés pour identifier un visiteur et stocker les attributs de profil utilisateur en vue de la personnalisation. Étant donné que [!DNL Target] les cookies peuvent avoir expiré sur Safari après sept jours (ITP 2.1) ou un jour (ITP 2.2 et 2.3), les données de profil utilisateur qui ont été liées à la purge [!DNL Target] ne peut pas être utilisé pour la prise de décision. |
| Scripts de profil basés sur 3rdPartyID | La fenêtre d’expiration étant définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), [scripts de profil](/help/main/c-target/c-visitor-profile/profile-parameters.md) sur la base du cookie 3rdPartyID, cessera de fonctionner lors de l’expiration. |
| URL d’AQ/d’aperçu des périphériques iOS | La fenêtre d’expiration étant définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), [URL d’assurance qualité/d’aperçu](/help/main/c-activities/c-activity-qa/activity-qa.md) cessera de fonctionner lors de l’expiration, car les URL sont basées sur le cookie 3rdPartyID . |

## Mon implémentation actuelle de [!DNL Target] est-elle impactée ?

Si vous utilisez la bibliothèque d’ID d’Experience Cloud (ECID) en plus de la variable [!DNL Target] Dans la bibliothèque JavaScript, votre mise en oeuvre sera impactée comme indiqué dans cet article : [Impact d’ITP 2.1 sur les clients Adobe Experience Cloud et Experience Platform de Safari](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).
