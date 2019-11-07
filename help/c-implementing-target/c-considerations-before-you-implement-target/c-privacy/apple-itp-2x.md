---
keywords: apple;ITP;intelligent tracking prevention
description: Informations sur la prise en charge d’Adobe Target pour ITP 2.1 et ITP 2.2 d’Apple via la bibliothèque Experience Cloud ID (ECID) 4.3.
title: Adobe Target et prise en charge d’ITP d’Apple
subtopic: Prise en main
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ITP (Intelligent Tracking Prevention) 2.x d’Apple

ITP (Intelligent Tracking Prevention) est une initiative d’Apple pour protéger la confidentialité des utilisateurs de Safari. La première version d’ITP, qui date de 2017, concernait l’utilisation des cookies tiers. En fait, Apple bloquait entièrement les cookies tiers, ce qui gênait les entreprises technologiques et marketing, car ceux-ci servent généralement au suivi des visiteurs et à la collecte des données des visiteurs. Maintenant, Apple souhaite limiter l’utilisation des cookies propriétaires dans Safari.

Ces versions d’ITP comprennent les restrictions suivantes :

| Version | Détails |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Limite à sept jours le délai d’expiration des cookies côté client qui sont placés sur le navigateur à l’aide de l’API `document.cookie`.<br>Publié le 21 février 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Réduit de façon drastique la limite de délai d’expiration de sept jours à un jour.<br>Publié le 24 avril 2019. |

## Quel est l’impact pour moi, en tant que client Adobe Target ?

[!DNL Target] fournit des bibliothèques JavaScript que vous pouvez déployer sur vos pages afin que [!DNL Target] puisse effectuer une personnalisation en temps réel pour vos visiteurs. Il existe trois bibliothèques JavaScript Target ([at.js 1.*x* et at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) qui placent des cookies [!DNL Target] côté client sur les navigateurs des visiteurs via l’API `document.cookie`. ITP 2.1 et 2.2 d’Apple ont donc un impact sur les cookies [!DNL Target] qui arrivent à expiration après sept jours (avec ITP 2.1) et un jour (avec ITP 2.2).

ITP 2.1 et 2.2 ont un impact sur [!DNL Target] en ce qui concerne les aspects suivants :

| Impact | Détails |
| --- | --- |
| Augmentation éventuelle du nombre de visiteurs uniques | Étant donné que la fenêtre d’expiration est définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2), vous pouvez peut-être constater une augmentation des visiteurs uniques provenant des navigateurs Safari. Si les visiteurs accèdent de nouveau à votre domaine au bout de sept jours (ITP 2.1) ou un jour (ITP 2.2), [!DNL Target] est forcé de placer sur votre domaine un nouveau cookie [!DNL Target] à la place de celui ayant expiré. Le nouveau cookie [!DNL Target] convertit un utilisateur en nouveau visiteur unique, même s’il s’agit d’un même utilisateur. |
| Diminution des périodes de recherche pour les activités [!DNL Target] | La période de recherche des profils de visiteur des activités [!DNL Target]peut être réduite pour la prise de décision. Les cookies [!DNL Target] sont utilisés pour identifier un visiteur et stocker les attributs de profil utilisateur en vue de la personnalisation. Étant donné que les cookies [!DNL Target] peuvent avoir expiré sur Safari après sept jours (ITP 2.1) ou un jour (ITP 2.2), les données de profil utilisateur liées au cookie [!DNL Target] purgé ne peuvent pas être utilisées pour la prise de décision. |

## Mon implémentation actuelle de [!DNL Target] est-elle impactée ?

Dans un navigateur Safari, accédez au site web sur lequel vous disposez d’une bibliothèque JavaScript [!DNL Target]. Si un cookie [!DNL Target] est défini dans le contexte d’un CNAME (`analytics.company.com`, par exemple) vous n’êtes pas impacté par ITP 2.1 ou 2.2.

Si vous utilisez la bibliothèque Experience Cloud ID (ECID) en plus de la bibliothèque JavaScript Target, votre implémentation sera impactée comme décrit dans l’article suivant : [Impact de Safari ITP 2.1 sur les clients Adobe Experience Cloud et Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Comment limiter l’impact d’ITP 2.1, d’ITP 2.2 et des prochaines versions d’ITP sur [!DNL Target] ?

Pour limiter l’impact d’ITP 2.1, d’ITP 2.2 et des prochaines versions d’ITP sur [!DNL Target], effectuez les tâches suivantes :

1. Déployez la bibliothèque Experience Cloud ID (ECID) sur vos pages.

   La bibliothèque ECID active l’infrastructure d’identification des personnes pour les solutions Core Experience Cloud. Elle permet d’identifier les mêmes visiteurs du site et leurs données dans différentes solutions Experience Cloud en attribuant des identifiants persistants et uniques. La bibliothèque ECID sera fréquemment mise à jour afin de vous aider à limiter les modifications liées à ITP qui impactent votre implémentation.

   Pour ITP 2.1 et ITP 2.2, la bibliothèque [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) doit être utilisée pour l'atténuation.

1. Utilisez le CNAME d’Adobe et inscrivez-vous au programme Managed Certificate Program d’Adobe Analytics.

   Une fois la bibliothèque ECID 4.3.0+ installée, vous pouvez utiliser le CNAME et le programme Managed Certificate Program d’Adobe Analytics. Ce programme permet d’implémenter gratuitement un certificat propriétaire pour les cookies propriétaires. L’utilisation du CNAME permet aux clients [!DNL Target] de limiter l’impact d’ITP 2.1 et ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Après avoir déployé une bibliothèque JavaScript Target avec la bibliothèque ECID v4.3.0+ et être inscrit au programme Adobe Managed Certificate Program pour utiliser le CNAME, vous disposez d’un plan de limitation à long terme efficace pour les modifications liées à ITP.

Alors que le secteur s’efforce de créer un site web plus sécurisé pour les consommateurs, [!DNL Adobe Target] s’engage à fournir des expériences personnalisées tout en répondant et en dépassant les attentes des visiteurs en matière de confidentialité. [!DNL Adobe Target] a déjà annoncé la prise en charge des [politiques SameSite Chrome de Google](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) en plus de celle d’ITP 2.1 et d’ITP 2.2 d’Apple.

Alors que les politiques évoluent sans cesse pour protéger les clients, [!DNL Adobe] continue à prendre en charge ces initiatives dans [!DNL Target], tout en permettant à ses clients d’offrir des expériences personnalisées de grande qualité.
