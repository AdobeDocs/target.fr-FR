---
description: 'Informations sur la fonction adobe. target. triggerview (viewname, options) pour at. js. '
keywords: adobe.target.notification;élément;sélecteur;notification;extension
seo-description: Informations sur la fonction adobe. target. triggerview (viewname, options) pour la bibliothèque JavaScript d'Adobe Target at. js.
seo-title: Informations sur la fonction adobe. target. triggerview (viewname, options) pour la bibliothèque JavaScript d'Adobe Target at. js.
solution: Target
subtopic: Prise en main
title: adobe.target.triggerView (viewName, options)
topic: Standard
translation-type: tm+mt
source-git-commit: e7ec5af38c1ea55a9cb86f0c706a024bd0f96e6e

---


# adobe. target. triggerview (viewname, options) - at. js 2. x

Cette fonction peut être appelée à chaque chargement d’une nouvelle page ou lorsqu’un composant fait l&#39;objet d&#39;un nouveau rendu sur une page. `adobe.target.triggerView()` doit être implémenté pour les applications monopage (SPA) afin d’utiliser le compositeur d’expérience visuelle (VEC) pour créer des activités de tests A/B et de ciblage d&#39;expérience (XT). Si `adobe.target.triggerView()` n’est pas implémenté sur le site, le compositeur d’expérience visuelle ne peut pas être utilisé pour les applications monopages. Pour plus d&#39;informations, voir [Implémentation d’application monopage](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Cette fonction a été introduite avec at. js 2. x. Cette fonction n&#39;est pas disponible pour at. js version 1.*x*.

| Paramètre | Type | Obligatoire ? | Description |
| --- | --- | --- | --- |
| viewName | Chaîne | Oui | Indiquez n&#39;importe quel nom sous forme de type de chaîne que vous souhaitez pour représenter votre vue. Ce nom de vue apparaît dans le panneau [!UICONTROL Modifications] du compositeur d’expérience visuelle pour que les marketeurs puissent créer des actions et exécuter leurs activités A/B et XT. |
| Options | Objet | Non |  |
| options &gt; page | Booléen | Non | **VRAI :** La valeur par défaut de la page est vrai. Lorsque page = vrai, les notifications sont envoyées au serveur principal [!DNL Target] pour incrémenter le nombre d’impressions.<br>Si aucune mesure d&#39;activité ou d&#39;activité n&#39;est associée à la vue, aucune notification n&#39;est envoyée.<br>**FALSE :** Lorsque page = false, les notifications ne sont pas envoyées pour incrémenter le nombre d&#39;impressions. Cette opération ne doit être utilisée que si vous souhaitez recréer un composant sur une page avec une offre. |

## Exemple : True

`triggerView()` appel pour envoyer une notification au serveur principal Target pour incrémenter les impressions d&#39;activité et d&#39;autres mesures.

```
adobe.target.triggerView("homeView")
```

## Exemple : False

`triggerView()` pour ne pas recevoir de notifications envoyées au serveur principal Target pour le comptage d&#39;impression.

```
adobe.target.triggerView("homeView", {page: false})
```
