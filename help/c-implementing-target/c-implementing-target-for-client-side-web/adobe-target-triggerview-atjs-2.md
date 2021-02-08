---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;fonctions;fonction;viewName;viewname;view name
description: Utilisez la fonction adobe.cible.triggerView() pour la bibliothèque JavaScript Adobe Target at.js à utiliser dans les applications à page unique (SPA). (at.js 2.x)
title: Comment utiliser la fonction adobe.cible.triggerView() ?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 84%

---


# adobe.target.triggerView (viewName, options) - at.js 2.x

Cette fonction peut être appelée à chaque chargement d’une nouvelle page ou lorsqu’un composant fait l’objet d’un nouveau rendu sur une page. `adobe.target.triggerView()` doit être implémenté pour les applications monopage (SPA) afin d’utiliser le compositeur d’expérience visuelle (VEC) pour créer des activités de tests A/B et de ciblage d’expérience (XT). Si `adobe.target.triggerView()` n’est pas implémenté sur le site, le compositeur d’expérience visuelle ne peut pas être utilisé pour les applications monopages. Pour plus d’informations, voir [Implémentation d’application monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Cette fonction a été introduite avec at.js 2.x. Cette fonction n’est pas disponible pour at.js version 1.*x*.

| Paramètre | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| viewName | Chaîne | Oui | Transmettez n’importe quel nom en tant que type de chaîne que vous souhaitez représenter votre vue. Ce nom de vue apparaît dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
| Options | Objet | Non |  |
| options > page | Booléen | Non | **TRUE :** La valeur par défaut de la page est vrai. Lorsque page = vrai, les notifications sont envoyées au serveur principal [!DNL Target] pour incrémenter le nombre d’impressions.<br>Une notification est toujours envoyée par défaut lorsqu’un message  `triggerView` est appelé, sauf si options > page est défini sur false.<br>**FALSE :** lorsque page = false, les notifications sont envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

## Exemple : True

Appel `triggerView()` pour envoyer une notification au serveur principal Target pour incrémenter les impressions d’activité et d’autres mesures.

```javascript
adobe.target.triggerView("homeView")
```

## Exemple : False

Appel `triggerView()` pour ne pas envoyer de notifications au serveur principal Target pour le comptage d’impression.

```javascript
adobe.target.triggerView("homeView", {page: false})
```
