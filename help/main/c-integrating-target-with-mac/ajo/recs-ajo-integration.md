---
keywords: ajo;adobe parcours optimizer;intégration de target adobe parcours optimizer;recommandations;recommandations target;intégration
description: Utilisation [!DNL Adobe Target Recommendations] avec [!DNL Adobe Journey Optimizer].
title: Comment utiliser [!DNL Target Recommendations] dans les parcours client utilisant [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
source-git-commit: bb6c83ff393656a634e1e8ddcb02b14dc8d4c8d2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# [!DNL Adobe Target Recommendations] et [!DNL Adobe Journey Optimizer] integration

Cet article explique les cas pratiques et les informations pour vous aider à configurer l’intégration entre [!DNL Adobe Target Recommendation] et [!DNL Adobe Journey Optimizer] pour vous aider à offrir à vos clients des expériences connectées, contextuelles et personnalisées.

## Conditions préalables

Pour utiliser la variable [!DNL Target Recommendations] et [!DNL Adobe Journey Optimizer] , vous avez besoin des éléments suivants :

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) mis en oeuvre à l’aide de la fonction [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

  Cette fonctionnalité n’est pas disponible avec un [!DNL Target Standard] licence ou lors de l’implémentation [!DNL Target] avec at.js ou autre [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Exemples de cas d’utilisation

Vous trouverez ci-dessous deux cas d’utilisation possibles pour l’intégration de [!DNL Target Recommendations] avec [!DNL Adobe Journey Optimizer]:

* **[!DNL Customer Journey Optimizer]envoie un email personnalisé après l&#39;abandon de panier**: ce cas d’utilisation est basé sur le fait qu’un client visite un site web, place des articles dans le panier, puis quitte le site sans terminer le processus d’achat.

  Supposons, par exemple, qu’un visiteur visite le site web d’une société de vêtements et place deux manteaux d’hiver et un sweat dans le panier. Le visiteur est ensuite distrait et quitte le site web ou n’est pas certain des achats et ferme le navigateur ou l’application.

  Après une période spécifiée, peut-être quelques heures ou un jour, une action personnalisée dans [!DNL Adobe Journey Optimizer] effectue un appel à [!DNL Target Recommendations] pour déterminer le contenu du panier abandonné. [!DNL Adobe Journey Optimizer] envoie ensuite à ce visiteur un email personnalisé pour lui rappeler que le processus d’achat n’a pas été terminé, ainsi que des images et des liens vers les articles abandonnés.

* **[!DNL Customer Journey Optimizer]envoie un courrier électronique après la visite du site à l’aide du profil utilisateur ;**: ce cas d’utilisation est basé sur le fait qu’un client visite un site web, consulte divers articles, puis quitte le site sans placer d’articles dans le panier.

  Après une période spécifiée, une action personnalisée dans [!DNL Adobe Journey Optimizer] effectue un appel à [!DNL Target Recommendations] pour déterminer les éléments consultés par ce visiteur à l’aide de la variable [!DNL Adobe Experience Cloud Identifier] (EDID). [!DNL Adobe Journey Optimizer] envoie ensuite à ce visiteur un email personnalisé pour lui rappeler que le processus d’achat n’a pas été terminé, ainsi que des images et des liens vers les articles abandonnés.

