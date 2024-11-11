---
keywords: ajo;adobe parcours optimizer;intégration de target adobe parcours optimizer;recommandations;recommandations target;intégration
description: Intégrez [!DNL Adobe Target Recommendations] à [!DNL Adobe Journey Optimizer].
title: Comment utiliser  [!DNL Target Recommendations] dans les parcours client utilisant [!DNL Adobe Journey Optimizer] ?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez ce qui est inclus dans Target Premium."
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# Intégrer [!DNL Adobe Target Recommendations] et [!DNL Adobe Journey Optimizer]

Cet article fournit des cas d’utilisation et des conseils pour l’intégration de [!DNL Adobe Target Recommendations] à [!DNL Adobe Journey Optimizer], ce qui vous permet de fournir des expériences client connectées, contextuelles et personnalisées.

Cette intégration vous aide à générer plus de conversions et à voir l’impact des emails contenant des recommandations personnalisées.

## Conditions préalables

Pour utiliser l&#39;intégration [!DNL Target Recommendations] et [!DNL Adobe Journey Optimizer], vous avez besoin des éléments suivants :

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implémenté à l’aide du [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Cette fonctionnalité n’est pas disponible avec une licence [!DNL Target Standard] ou lors de la mise en oeuvre de [!DNL Target] avec at.js ou d’autres SDK [!DNL Target].

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target=_blank}.

## Exemples de cas d’utilisation

Ces cas d’utilisation ne sont que quelques cas d’utilisation possibles pour l’intégration de [!DNL Target Recommendations] à [!DNL Adobe Journey Optimizer] :

* **[!DNL Adobe Journey Optimizer]envoie un email personnalisé après l’abandon de panier** : ce cas d’utilisation est basé sur la visite d’un client sur un site web, le placement d’articles dans le panier, puis le départ du site sans avoir terminé le processus d’achat.

  Supposons, par exemple, qu’un visiteur visite le site web d’une société de vêtements et place deux manteaux d’hiver et un sweat dans le panier. Le visiteur est ensuite distrait et quitte le site web ou n’est pas certain des achats et ferme le navigateur ou l’application.

  Après une période spécifiée, peut-être quelques heures ou par jour, une action personnalisée dans [!DNL Journey Optimizer] lance un appel à [!DNL Target Recommendations] pour déterminer le contenu du panier abandonné à l’aide d’un algorithme [recommandations basées sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Journey Optimizer] envoie alors à ce visiteur un email personnalisé pour lui rappeler que le processus d&#39;achat n&#39;a pas été terminé, ainsi que des images et des liens vers les articles abandonnés.

* **[!DNL Adobe Journey Optimizer]envoie un e-mail en bloc après les visites du site pour rappeler aux visiteurs les articles consultés** : ce cas d’utilisation est basé sur les visiteurs qui ont consulté un site web, consulté divers articles, puis qui quittent le site ou l’application sans placer d’articles dans le panier.

  Après une période spécifiée, une action personnalisée dans [!DNL Journey Optimizer] lance un appel à [!DNL Target Recommendations] pour déterminer les éléments consultés par chaque visiteur, à l’aide de l’ [!DNL Adobe Experience Cloud Identifier] (EDID) de chaque visiteur, du profil [!DNL Target] du visiteur et d’un algorithme [ basé sur l’utilisateur ](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Adobe Journey Optimizer] envoie ensuite à chaque membre de l’audience qualifiée un email personnalisé avec des images et des liens vers les éléments consultés de chaque visiteur pour amener le visiteur à revenir et à effectuer un achat.

  Dans ce scénario, l’ [!UICONTROL Experience Cloud Visitor ID] (ECID) et le contenu du profil [!DNL Target] de chaque visiteur sont utilisés pour générer la recommandation en fonction de l’algorithme récemment consulté.

  Supposons, par exemple, qu’un visiteur visite un site web de vente au détail et consulte plusieurs montres. Le profil [!DNL Target] de ce visiteur est mis à jour avec une liste des montres consultées. À l’aide de l’ECID et du profil [!DNL Target] du visiteur, [!DNL Target] envoie la recommandation à [!DNL Journey Optimizer]. [!DNL Journey Optimizer] envoie ensuite un courrier électronique contenant des images et des liens vers les montres que le visiteur a consultées, à l’aide de l’algorithme récemment consulté. Un autre visiteur reçoit un email personnalisé contenant des images et des liens vers les éléments consultés par ce visiteur. Chaque message électronique est personnalisé pour chaque visiteur.

* **[!DNL Adobe Journey Optimizer]envoie un courrier électronique en masse aux visiteurs qualifiés après la visite du site pour suggérer des éléments populaires** : ce cas d’utilisation est basé sur la visite d’un visiteur sur un site web, mais sans consulter d’éléments spécifiques. L’e-mail est envoyé en bloc à tous les visiteurs qui répondent aux critères d’une audience particulière, par exemple :

  Supposons que le visiteur ne consulte aucune montre particulière. Il se peut que le visiteur ait simplement cliqué sur le site et visualisé des pages de catégorie ou des entrées de blog. Par conséquent, le profil [!DNL Target] ne dispose pas d’informations spécifiques sur les articles récemment consultés. Dans ce cas, [!DNL Target Recommendations] utilise une [recommandation de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) de sorte que [!DNL Journey Optimizer] puisse envoyer un email avec des images et des liens vers des éléments populaires sur le site web pour amener le visiteur à revenir et éventuellement effectuer un achat.
