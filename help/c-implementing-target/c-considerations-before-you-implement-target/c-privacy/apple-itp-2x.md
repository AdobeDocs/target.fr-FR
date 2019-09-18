---
description: Informations sur la prise en charge de Target pour les API 2.1 et 2.2 d’Apple via la bibliothèque Experience Cloud ID (ECID) 4.3.
keywords: pomme;ITP;prévention intelligente du suivi
seo-description: Informations sur la prise en charge d’Adobe Target pour les applications Apple ITP 2.1 et ITP 2.2 via la bibliothèque Experience Cloud ID (ECID) 4.3.
seo-title: Prise en charge d’Adobe Target et d’Apple ITP
solution: Target
subtopic: Prise en main
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention (ITP) est une initiative d’Apple visant à protéger la confidentialité des utilisateurs de Safari. La première version d’ITP, publiée en 2017, visait l’utilisation de cookies tiers. En fait, Apple a bloqué l’intégralité des cookies tiers, ce qui à son tour a causé de graves problèmes de tête pour les sociétés du secteur des technologies de l’annonce et du marketing, car les cookies tiers sont généralement utilisés pour le suivi des visiteurs et la collecte des données sur les visiteurs. Aujourd’hui, Apple est sur le point d’imposer des limites et des restrictions sur la manière dont les cookies propriétaires sont utilisés dans Safari.

Ces versions de ITP incluent les restrictions suivantes :

| Version | Détails |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Les cookies côté client qui sont placés dans le navigateur à l’aide de l’ `document.cookie` API ont été plafonnés à une expiration de sept jours.<br>Publié le 21 février 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Le plafond d'expiration de sept jours a été considérablement réduit à un jour.<br>Publié le 24 avril 2019. |

## Quel est l’impact pour moi en tant que client Adobe Target ?

[!DNL Target] fournit des bibliothèques JavaScript que vous pouvez déployer sur vos pages afin de [!DNL Target] fournir une personnalisation en temps réel à vos visiteurs. Il existe trois bibliothèques JavaScript Target ([at.js 1.*x* et at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)et [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) qui placent des [!DNL Target] cookies côté client dans les navigateurs de vos visiteurs via l’ `document.cookie` API. Par conséquent, [!DNL Target] les cookies sont affectés par les ITP 2.1 et 2.2 d’Apple et expireront au bout de sept jours (avec ITP 2.1) et après un jour (avec ITP 2.2).

L’impact d’Apple ITP 2.1 et 2.1 [!DNL Target] dans les domaines suivants :

| Impact | Détails |
| --- | --- |
| Augmentation potentielle du nombre de visiteurs uniques | Comme la fenêtre d’expiration est définie sur sept jours (avec ITP 2.1) et un jour (avec ITP 2.2), vous pouvez constater une augmentation du nombre de visiteurs uniques provenant des navigateurs Safari. Si vos visiteurs reviennent sur votre domaine après sept jours (ITP 2.1) ou un jour (ITP 2.2), [!DNL Target] est forcé de placer un nouveau [!DNL Target] cookie sur votre domaine à la place du cookie arrivé à expiration. Le nouveau [!DNL Target] cookie se traduit par un nouveau visiteur unique, même si l’utilisateur est le même. |
| Diminution des périodes de recherche pour [!DNL Target] les activités | Les profils des visiteurs pour [!DNL Target] les activités peuvent avoir une période de consultation réduite pour la prise de décision. [!DNL Target] les cookies sont utilisés pour identifier un visiteur et stocker les attributs de profil utilisateur pour la personnalisation. Étant donné que [!DNL Target] les cookies peuvent expirer dans Safari après sept jours (ITP 2.1) ou un jour (ITP 2.2), les données de profil utilisateur liées au [!DNL Target] cookie purgé ne peuvent pas être utilisées pour la prise de décision. |

## Est-ce que ma mise en oeuvre actuelle est [!DNL Target] impactée ?

Dans un navigateur Safari, accédez à votre site Web sur lequel vous disposez d’une bibliothèque [!DNL Target] JavaScript. Si un [!DNL Target] cookie est défini dans le contexte d’un CNAME, par exemple `analytics.company.com`, vous n’êtes pas affecté par ITP 2.1 ou 2.2.

Si vous utilisez la bibliothèque ECID (Experience Cloud ID) en plus de la bibliothèque JavaScript Target, votre implémentation sera affectée de la manière décrite dans cet article : Impact de [Safari ITP 2.1 sur les clients](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)Adobe Experience Cloud et Experience Platform.

## Comment puis-je atténuer l'impact de ITP 2.1, ITP 2.2 et des futures versions ITP sur [!DNL Target]?

Pour atténuer l'impact de ITP 2.1, ITP 2.2 et des versions futures de ITP [!DNL Target], effectuez les tâches suivantes :

1. Déployez la bibliothèque d’ID d’expérience Cloud (ECID) sur vos pages.

   La bibliothèque ECID active le cadre d’identification des personnes pour les solutions de base Experience Cloud. La bibliothèque ECID vous permet d’identifier les mêmes visiteurs du site et leurs données dans différentes solutions Experience Cloud en attribuant des identifiants uniques et persistants. La bibliothèque ECID sera fréquemment mise à jour afin de vous aider à atténuer les modifications liées au protocole ITP qui affectent votre implémentation.

   Pour ITP 2.1 et ITP 2.2, la bibliothèque [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) doit être utilisée pour l'atténuation.

1. Utilisez le CNAME d’Adobe et inscrivez-vous au programme de certificats gérés d’Adobe Analytics.

   Après avoir installé la bibliothèque ECID 4.3.0+, vous pouvez tirer parti du CNAME d’Adobe Analytics et du programme de certificats gérés. Ce programme vous permet de mettre en oeuvre gratuitement un certificat propriétaire pour les cookies propriétaires. L’utilisation de CNAME aidera [!DNL Target] les clients à atténuer l’impact de ITP 2.1 et ITP 2.2.

   Si vous n’utilisez pas CNAME, vous pouvez lancer le processus en discutant avec votre gestionnaire de compte et en vous inscrivant au programme [de certificats gérés](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)Adobe.

Après avoir déployé une bibliothèque JavaScript Target en association avec la bibliothèque ECID v4.3.0+ et vous être inscrit au programme de certificats gérés Adobe pour tirer parti de CNAME, vous disposez d’un plan d’atténuation robuste et à long terme pour les modifications liées au protocole ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] a déjà annoncé la prise en charge des stratégies [Chrome du même site de](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, en plus de la prise en charge des protocoles ITP 2.1 et ITP 2.2 d’Apple.

Alors que les politiques continuent d’évoluer pour protéger nos consommateurs, [!DNL Adobe] nous continuerons également à soutenir ces initiatives dans [!DNL Target], tout en aidant nos clients à offrir les meilleures expériences personnalisées de classe.
