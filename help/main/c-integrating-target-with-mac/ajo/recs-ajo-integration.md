---
keywords: ajo;adobe parcours optimizer;intégration target d’adobe parcours optimizer;recommandations;recommandations target;intégration
description: Intégration  [!DNL Adobe Target Recommendations]  à  [!DNL Adobe Journey Optimizer].
title: Comment utiliser dans les parcours  [!DNL Target Recommendations]  clients à l’aide de  [!DNL Adobe Journey Optimizer] ?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
badgeBeta: label="Bêta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités bêta dans  [!DNL Adobe Target] ?"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# Intégration de [!DNL Adobe Target Recommendations] et de [!DNL Adobe Journey Optimizer]

Cet article fournit des cas d’utilisation et des conseils pour l’intégration de [!DNL Adobe Target Recommendations] à [!DNL Adobe Journey Optimizer], ce qui vous permet de fournir des expériences client connectées, contextuelles et personnalisées.

Cette intégration vous permet de générer davantage de conversions et de voir l’impact des e-mails contenant des recommandations personnalisées.

## Conditions préalables

Pour utiliser l’intégration [!DNL Target Recommendations] et [!DNL Adobe Journey Optimizer], vous avez besoin des éléments suivants :

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implémenté à l’aide de [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Cette fonctionnalité n’est pas disponible avec une licence [!DNL Target Standard] ou lors de l’implémentation de [!DNL Target] avec at.js ou d’autres SDK [!DNL Target].

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target=_blank}.

## Exemples de cas d’utilisation

Ces cas d’utilisation ne sont que quelques-uns des cas d’utilisation possibles pour l’intégration de [!DNL Target Recommendations] à [!DNL Adobe Journey Optimizer] :

* **[!DNL Adobe Journey Optimizer]envoie un e-mail personnalisé après l’abandon du panier** : ce cas d’utilisation est basé sur la visite d’un client sur un site web, le placement d’articles dans son panier, puis sa sortie du site sans terminer le processus d’achat.

  Supposons, par exemple, qu’un visiteur visite le site web d’une entreprise de vêtements et place deux manteaux d’hiver et un sweat dans son panier. Le visiteur est alors distrait et quitte le site web ou n’est pas sûr des achats et ferme le navigateur ou l’application.

  Après une période spécifiée, peut-être quelques heures ou un jour, une action personnalisée dans [!DNL Journey Optimizer] effectue un appel à [!DNL Target Recommendations] pour déterminer le contenu du panier abandonné à l’aide d’un algorithme de [recommandations basées sur le panier](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Journey Optimizer] envoie ensuite à ce visiteur un e-mail personnalisé pour lui rappeler que le processus d’achat n’a pas été terminé, ainsi que des images et des liens vers les articles abandonnés.

* **[!DNL Adobe Journey Optimizer]envoie un e-mail en bloc après les visites du site pour rappeler aux visiteurs quels articles ont été consultés** : ce cas d’utilisation se base sur la visite des visiteurs sur un site web, l’affichage de divers articles, puis le fait de quitter le site ou l’application sans placer d’articles dans le panier.

  Après une période spécifiée, une action personnalisée dans [!DNL Journey Optimizer] appelle [!DNL Target Recommendations] pour déterminer les éléments consultés par chaque visiteur, à l’aide du [!DNL Adobe Experience Cloud Identifier] de chaque visiteur (EDID), du profil de [!DNL Target] du visiteur et d’un algorithme [basé sur l’utilisateur](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Adobe Journey Optimizer] envoie ensuite à chaque membre de l’audience qualifiée un e-mail personnalisé avec des images et des liens vers les éléments consultés de chaque visiteur pour lui permettre de revenir et de procéder à un achat.

  Dans ce scénario, le [!UICONTROL Experience Cloud Visitor ID] (ECID) et le contenu du profil [!DNL Target] de chaque visiteur sont utilisés pour générer la recommandation en fonction de l’algorithme récemment consulté.

  Supposons, par exemple, qu’un visiteur visite un site web de vente au détail et consulte plusieurs montres. Le profil [!DNL Target] de ce visiteur est mis à jour avec une liste des montres consultées. À l’aide de l’ECID et du profil de [!DNL Target] du visiteur, [!DNL Target] envoie la recommandation à [!DNL Journey Optimizer]. [!DNL Journey Optimizer] envoie ensuite un e-mail contenant des images et des liens vers les montres que ce visiteur a consultées, à l’aide de l’algorithme récemment consulté. Un autre visiteur reçoit un e-mail personnalisé contenant des images et des liens vers les éléments qu’il a consultés. Chaque e-mail est personnalisé pour chaque visiteur.

* **[!DNL Adobe Journey Optimizer]envoie un e-mail en bloc aux visiteurs qualifiés après leur visite du site pour leur suggérer des éléments populaires** : ce cas d’utilisation est basé sur la visite d’un visiteur sur un site web, mais sans afficher d’éléments particuliers. L’e-mail est envoyé en bloc à tous les visiteurs qui remplissent les critères d’une audience particulière, par exemple :

  Supposons que le visiteur ne voie aucune montre particulière. Peut-être le visiteur a-t-il simplement cliqué sur le site et consulté des pages de catégories ou des entrées de blog. Par conséquent, le profil [!DNL Target] ne dispose pas d&#39;informations spécifiques sur les éléments récemment consultés. Dans ce cas, [!DNL Target Recommendations] utilise une [recommandation de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md) afin que [!DNL Journey Optimizer] puissiez envoyer un e-mail avec des images et des liens vers des éléments populaires sur le site web pour que le visiteur revienne et effectue éventuellement un achat.
