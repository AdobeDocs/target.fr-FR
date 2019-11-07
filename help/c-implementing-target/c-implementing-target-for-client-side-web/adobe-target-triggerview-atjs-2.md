---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;fonctions;fonction;viewName;viewname;view name
description: Informations sur la fonction adobe.target.triggerView (viewName, options) pour la bibliothèque JavaScript at.js d’Adobe Target.
title: Informations sur la fonction adobe.target.triggerView (viewName, options) pour la bibliothèque JavaScript at.js d’Adobe Target.
subtopic: Prise en main
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

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
| options &gt; page | Booléen | Non | **TRUE :** La valeur par défaut de la page est vrai. Lorsque page = vrai, les notifications sont envoyées au serveur principal [!DNL Target] pour incrémenter le nombre d’impressions.<br>Si aucune expérience d’activité ou mesure d’activité n’est associée à la vue, aucune notification n’est envoyée.<br>**FALSE :** lorsque page = false, les notifications sont envoyées pour incrémenter le nombre d’impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

## Exemple : True

Appel `triggerView()` pour envoyer une notification au serveur principal Target pour incrémenter les impressions d’activité et d’autres mesures.

```
adobe.target.triggerView("homeView")
```

## Exemple : False

Appel `triggerView()` pour ne pas envoyer de notifications au serveur principal Target pour le comptage d’impression.

```
adobe.target.triggerView("homeView", {page: false})
```
