---
keywords: ajo;adobe parcours optimizer;intégration de target adobe parcours optimizer;recommandations;recommandations target;intégration
description: Intégrer [!DNL Adobe Target Recommendations] avec [!DNL Adobe Journey Optimizer].
title: Comment utiliser [!DNL Target Recommendations] dans les parcours client utilisant [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
source-git-commit: 9cf9236dbd830796ef5362a9e292de7ec6fd8491
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Intégrer [!DNL Adobe Target Recommendations] et [!DNL Adobe Journey Optimizer]

Cet article explique les cas pratiques et les informations pour vous aider à configurer l’intégration entre [!DNL Adobe Target Recommendations] et [!DNL Adobe Journey Optimizer] pour vous aider à offrir à vos clients des expériences connectées, contextuelles et personnalisées.

Cette intégration vous aide à générer plus de conversions et à voir l’impact des emails contenant des recommandations personnalisées.

## Conditions préalables

Pour utiliser la variable [!DNL Target Recommendations] et [!DNL Adobe Journey Optimizer] , vous avez besoin des éléments suivants :

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) mis en oeuvre à l’aide de la fonction [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}.

  Cette fonctionnalité n’est pas disponible avec un [!DNL Target Standard] licence ou lors de l’implémentation [!DNL Target] avec at.js ou autre [!DNL Target] SDK.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Exemples de cas d’utilisation

Voici quelques cas d’utilisation possibles pour l’intégration de [!DNL Target Recommendations] avec [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]envoie un email personnalisé après l&#39;abandon de panier**: ce cas d’utilisation est basé sur le fait qu’un client visite un site web, place des articles dans le panier, puis quitte le site sans terminer le processus d’achat.

  Supposons, par exemple, qu’un visiteur visite le site web d’une société de vêtements et place deux manteaux d’hiver et un sweat dans le panier. Le visiteur est ensuite distrait et quitte le site web ou n’est pas certain des achats et ferme le navigateur ou l’application.

  Après une période spécifiée, quelques heures ou un jour, une action personnalisée dans [!DNL Adobe Journey Optimizer] effectue un appel à [!DNL Target Recommendations] pour déterminer le contenu du panier abandonné à l’aide d’une [recommandations basées sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algorithme. [!DNL Adobe Journey Optimizer] envoie ensuite à ce visiteur un email personnalisé pour lui rappeler que le processus d’achat n’a pas été terminé, ainsi que des images et des liens vers les articles abandonnés.

* **[!DNL Adobe Journey Optimizer]envoie un courrier électronique après la visite du site pour rappeler au visiteur les éléments qui ont été consultés ;**: ce cas d’utilisation est basé sur le fait qu’un visiteur visite un site web, consulte différents articles, puis quitte le site ou l’application sans placer d’articles dans le panier.

  Après une période spécifiée, une action personnalisée dans [!DNL Adobe Journey Optimizer] effectue un appel à [!DNL Target Recommendations] pour déterminer les éléments consultés par ce visiteur, à l’aide de la variable [!DNL Adobe Experience Cloud Identifier] (EDID), le [!DNL Target] et un [en fonction des utilisateurs](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algorithme. [!DNL Adobe Journey Optimizer] envoie ensuite à ce visiteur un e-mail personnalisé contenant des images et des liens vers les éléments consultés afin d’amener le visiteur à revenir et à faire un achat.

  Dans ce scénario, la variable [!UICONTROL Identifiant visiteur Experience Cloud] (ECID) et le contenu du rapport [!DNL Target] est utilisé pour générer la recommandation en fonction de l’algorithme récemment consulté.

  Supposons, par exemple, qu’un visiteur visite un site web de vente au détail et consulte plusieurs montres. de ce visiteur [!DNL Target] Le profil est mis à jour avec une liste des montres consultées. Utilisation de l’ECID et de la variable [!DNL Target] profile, [!DNL Target] envoie la recommandation à [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] envoie ensuite un e-mail contenant des images et des liens vers les montres que ce visiteur a consultées à l’aide de l’algorithme récemment consulté.

* **[!DNL Adobe Journey Optimizer]envoie un courrier électronique après une visite de site pour suggérer des articles populaires ;**: ce cas d’utilisation est basé sur le fait qu’un visiteur visite un site web, mais ne consulte aucun élément particulier. Contrairement aux cas pratiques précédents, l’email est envoyé en bloc à tous ceux qui répondent aux critères d’une audience particulière, par exemple.

  Supposons que le visiteur ne consulte aucune montre particulière. Il se peut que le visiteur ait simplement cliqué sur le site et visualisé des pages de catégorie ou des entrées de blog. Par conséquent, la variable [!DNL Target] profile ne contient pas d’informations spécifiques sur les articles récemment consultés. Dans ce cas, [!DNL Target Recommendations] peut utiliser une [recommandation de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) so [!DNL Adobe Journey Optimizer] peut envoyer un email contenant des images et des liens vers des articles populaires sur le site web pour inciter le visiteur à revenir et éventuellement à faire un achat.


