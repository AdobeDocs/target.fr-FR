---
description: Informations sur la prise en charge de Target pour ITP 2.1 et ITP 2.2 d'Apple via la bibliothèque d'Experience Cloud ID (ECID) 4.3.
keywords: apple ; ITP ; prévention intelligente du suivi
seo-description: Informations sur la prise en charge d'Adobe Target pour ITP 2.1 et ITP 2.2 d'Apple via la bibliothèque d'Experience Cloud ID (ECID) 4.3.
seo-title: Prise en charge d'Adobe Target et ITP Apple
solution: Target
subtopic: Prise en main
title: Apple ITP 2. x
topic: Standard
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple Intelligent Tracking Prevention (ITP) 2. x

Intelligent Tracking Prevention (ITP) est l'initiative d'Apple visant à protéger la confidentialité des utilisateurs Safari. La première version d'ITP, qui était 2017, concernait l'utilisation de cookies tiers. En fait, Apple bloquait les cookies tiers, ce qui entraînait un gros ralentissement pour les technologies publicitaires et les sociétés technologiques car les cookies tiers sont généralement utilisés pour le suivi des visiteurs et la collecte des données des visiteurs. Désormais, Apple est en mesure de placer des restrictions et des restrictions sur la manière dont les cookies propriétaires sont utilisés dans Safari.

Ces versions d'ITP incluent les restrictions suivantes :

| Version | Détails |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>Publié le 21 février 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Réduction drastique du délai d'expiration de sept jours à un jour.<br>Publié le 24 avril 2019. |

## Quel est l'impact sur moi en tant que client Adobe Target ?

[!DNL Target] fournit des bibliothèques JavaScript que vous déployez sur vos pages afin [!DNL Target] de fournir une personnalisation en temps réel à vos visiteurs. There are three Target JavaScript libraries ([at.js 1.*x* et at. js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)et [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) qui placent [!DNL Target] des cookies côté client sur les navigateurs des visiteurs via `document.cookie` l'API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.1 and 2.2 and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2).

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| Impact | Détails |
| --- | --- |
| Augmentation potentielle du nombre de visiteurs uniques | Etant donné que la fenêtre d'expiration est définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2), une augmentation peut s'afficher de visiteurs uniques provenant des navigateurs Safari. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | Visitor profiles for [!DNL Target] activities might have a decreased lookback period for decisioning. [!DNL Target] Les cookies sont utilisés pour identifier un visiteur et stocker les attributs de profil des utilisateurs pour la personnalisation. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. Déployez la bibliothèque Experience Cloud ID (ECID) sur vos pages.

   La bibliothèque ECID active la structure d'identification des personnes pour les solutions noyau Experience Cloud. La bibliothèque ECID vous permet d'identifier les mêmes visiteurs du site et leurs données dans différentes solutions Experience Cloud en attribuant des identifiants persistants et uniques. La bibliothèque ECID sera fréquemment mise à jour afin de vous aider à atténuer les modifications liées à ITP qui affectent votre implémentation.

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. Utilisez le CNAME d'Adobe et le programme de certificat géré d'Adobe Analytics.

   Après avoir installé la bibliothèque ECID 4.3.0 +, vous pouvez exploiter le CNAME et le programme de certificat géré d'Adobe Analytics. Ce programme vous permet de mettre en œuvre gratuitement un certificat propriétaire pour les cookies propriétaires. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

Après avoir déployé une bibliothèque JavaScript Target conjointement avec la bibliothèque ECID v 4.3.0 + et l'avoir inscrite au programme Adobe Managed Certificate Program pour exploiter CNAME, vous disposez d'un plan d'atténuation puissant et à long terme pour les modifications liées à ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] a déjà annoncé la prise en charge [des stratégies Google samesite Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) en plus de la prise en charge des protocoles ITP 2.1 et ITP 2.2 Apple.

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
