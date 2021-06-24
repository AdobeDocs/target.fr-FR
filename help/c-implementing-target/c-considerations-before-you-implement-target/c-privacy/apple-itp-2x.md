---
keywords: apple;ITP;prévention du suivi intelligent;experience cloud id;ecid
description: Découvrez l’Adobe [!DNL Target] et l’impact de l’initiative ITP (Intelligent Tracking Prevention) d’Apple qui vise à protéger la confidentialité des utilisateurs Safari.
title: Comment  [!DNL Target] Gère-t-il la prise en charge d’ITP Apple ?
feature: Confidentialité et sécurité
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 52%

---

# ITP (Intelligent Tracking Prevention) 2.x d’Apple

Informations sur la [!DNL Adobe Target] prise en charge d’ITP 2.x d’Apple via la bibliothèque d’ID Experience Cloud (ECID) 4.3.

ITP (Intelligent Tracking Prevention) est une initiative d’Apple pour protéger la confidentialité des utilisateurs de Safari. La première version d’ITP, qui date de 2017, concernait l’utilisation des cookies tiers. En fait, Apple bloquait entièrement les cookies tiers, ce qui gênait les entreprises technologiques et marketing, car ceux-ci servent généralement au suivi des visiteurs et à la collecte des données des visiteurs. Maintenant, Apple souhaite limiter l’utilisation des cookies propriétaires dans Safari.

Ces versions d’ITP comprennent les restrictions suivantes :

| Version | Détails |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Limite à sept jours le délai d’expiration des cookies côté client qui sont placés sur le navigateur à l’aide de l’API `document.cookie`.<br>Publié le 21 février 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Réduit de façon drastique la limite de délai d’expiration de sept jours à un jour.<br>Publié le 24 avril 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Suppression de plusieurs solutions de contournement, comme l’utilisation de localStorage ou de JavaScript `Document.referrer property`.<br>Publié le 23 septembre 2019. |

## Quel est l’impact pour moi en tant que client [!DNL Target] Adobe ? {#impact}

[!DNL Target] fournit des bibliothèques JavaScript que vous pouvez déployer sur vos pages afin que [!DNL Target] puisse effectuer une personnalisation en temps réel pour vos visiteurs. Il existe trois bibliothèques JavaScript Target at.js 1.x, at.js 2.x qui placent des cookies [!DNL Target] côté client sur les navigateurs de vos visiteurs via l’API `document.cookie`. Par conséquent, les cookies [!DNL Target] sont affectés par ITP 2.x d’Apple et expireront au bout de sept jours (avec ITP 2.1) et après un jour (avec ITP 2.2 et ITP 2.3).

ITP 2.x d’Apple a un impact sur [!DNL Target] dans les domaines suivants :

| Impact | Détails |
| --- | --- |
| Augmentation éventuelle du nombre de visiteurs uniques | Étant donné que la fenêtre d’expiration est définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), vous pouvez constater une augmentation des visiteurs uniques provenant des navigateurs Safari. Si vos visiteurs reviennent sur votre domaine au bout de sept jours (ITP 2.1) ou un jour (ITP 2.2 et ITP 2.3), [!DNL Target] est forcé de placer un nouveau cookie [!DNL Target] sur votre domaine à la place du cookie expiré. Le nouveau cookie [!DNL Target] convertit un utilisateur en nouveau visiteur unique, même s’il s’agit d’un même utilisateur. |
| Diminution des périodes de recherche pour les activités [!DNL Target] | La période de recherche des profils de visiteur des activités [!DNL Target]peut être réduite pour la prise de décision. Les cookies [!DNL Target] sont utilisés pour identifier un visiteur et stocker les attributs de profil utilisateur en vue de la personnalisation. Étant donné que les cookies [!DNL Target] peuvent avoir expiré sur Safari après sept jours (ITP 2.1) ou un jour (ITP 2.2 et 2.3), les données de profil utilisateur liées au cookie [!DNL Target] purgé ne peuvent pas être utilisées pour la prise de décision. |
| Scripts de profil basés sur 3rdPartyID | La fenêtre d’expiration étant définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), les [scripts de profil](/help/c-target/c-visitor-profile/profile-parameters.md) basés sur le cookie 3rdPartyID cesseront de fonctionner à l’expiration. |
| URL d’AQ/d’aperçu des périphériques iOS | La fenêtre d’expiration étant définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2 et ITP 2.3), [les URL d’assurance qualité/aperçu](/help/c-activities/c-activity-qa/activity-qa.md) cesseront de fonctionner lors de l’expiration, car les URL sont basées sur le cookie 3rdPartyID. |

## Mon implémentation actuelle de [!DNL Target] est-elle impactée ?

Dans un navigateur Safari, accédez au site web sur lequel vous disposez d’une bibliothèque JavaScript [!DNL Target]. Si un cookie [!DNL Target] est défini dans le contexte d’un CNAME, tel que `analytics.company.com`, alors vous n’êtes pas affecté par ITP 2.x.

Si vous utilisez la bibliothèque Experience Cloud ID (ECID) en plus de la bibliothèque JavaScript Target, votre implémentation sera impactée comme décrit dans l’article suivant : [Impact de Safari ITP 2.1 sur les clients Adobe Experience Cloud et Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Comment limiter l’impact des prochaines versions d’ITP 2.x sur Target ?

Pour atténuer l’impact des futures versions d’ITP 2.x sur Target, effectuez les tâches suivantes :

1. Déployez la bibliothèque Experience Cloud ID (ECID) sur vos pages.

   La bibliothèque ECID active l’infrastructure d’identification des personnes pour les solutions Core Experience Cloud. Elle permet d’identifier les mêmes visiteurs du site et leurs données dans différentes solutions Experience Cloud en attribuant des identifiants persistants et uniques. La bibliothèque ECID sera fréquemment mise à jour afin de vous aider à limiter les modifications liées à ITP qui impactent votre implémentation.

   Pour ITP 2.x, [La bibliothèque ECID 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html?lang=fr) doit être utilisée pour la limitation.

1. Utilisez le CNAME d’Adobe et inscrivez-vous au programme Managed Certificate Program d’Adobe Analytics.

   Une fois la bibliothèque ECID 4.3.0+ installée, vous pouvez utiliser le CNAME et le programme Managed Certificate Program d’Adobe Analytics. Ce programme permet d’implémenter gratuitement un certificat propriétaire pour les cookies propriétaires. L’utilisation de CNAME permet aux clients [!DNL Target] d’atténuer l’impact d’ITP 2.x.

   Si vous n’utilisez pas CNAME, vous pouvez lancer le processus en contactant le représentant de votre compte et en vous inscrivant au [programme de certificat géré par Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Après avoir déployé une bibliothèque JavaScript Target avec la bibliothèque ECID v4.3.0+ et être inscrit au programme Adobe Managed Certificate Program pour utiliser le CNAME, vous disposez d’un plan de limitation à long terme efficace pour les modifications liées à ITP.

Alors que le secteur s’efforce de créer un site web plus sécurisé pour les consommateurs, [!DNL Adobe Target] s’engage à fournir des expériences personnalisées tout en répondant et en dépassant les attentes des visiteurs en matière de confidentialité. [!DNL Adobe Target] a déjà annoncé la prise en charge des  [politiques SameSite Chrome de ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, en plus de la prise en charge d’ITP 2.x d’Apple.

Alors que les politiques évoluent sans cesse pour protéger les clients, [!DNL Adobe] continue à prendre en charge ces initiatives dans [!DNL Target], tout en permettant à ses clients d’offrir des expériences personnalisées de grande qualité.
