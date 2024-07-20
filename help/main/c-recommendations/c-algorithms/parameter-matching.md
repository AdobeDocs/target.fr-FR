---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance des paramètres
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant les éléments (entités) à une valeur dans la requête (API ou mbox).
title: Comment filtrer par correspondance de paramètres dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 10%

---

# Correspondance de paramètres

Filtrez dynamiquement en comparant les éléments (entités) à une valeur de la requête (API ou mbox).

Par exemple, recommandez uniquement du contenu correspondant au paramètre de page &quot;secteur&quot; ou à d’autres paramètres, tels que les dimensions de l’appareil ou la géolocalisation, comme dans les exemples suivants.

* Les paramètres de mbox pour la largeur et la hauteur d’écran peuvent être utilisés pour cibler les visiteurs mobiles et recommander uniquement les appareils et accessoires mobiles.
* Créez une règle de recommandations qui renvoie uniquement les téléphones mobiles les plus vendus qui correspondent ou dépassent la hauteur d’écran de l’appareil mobile sur lequel le visiteur consulte la page.
* Les paramètres de géolocalisation régionaux peuvent être utilisés pour renvoyer des recommandations d’outils pendant l’hiver. Des souffleurs de neige et autres outils de réduction de la neige peuvent être recommandés aux visiteurs des zones où il neige, mais pas aux visiteurs des zones où il ne neige pas.

>[!NOTE]
>
>Si l’activité a été créée avant le 31 octobre 2016, sa diffusion échoue si elle utilise le filtre &quot;Correspondance de paramètres&quot;. Pour contourner ce problème, procédez comme suit :
>
>* Créez une activité et ajoutez-y des critères.
>* Utilisez un critère qui ne contient pas le filtre « Correspondance de paramètres ».
>* Supprimez le filtre « Correspondance de paramètres » des critères.

## Exemples de correspondance de paramètres

[!UICONTROL Parameter Matching] vous permet de recommander du contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation, comme dans l’exemple suivant :

[!DNL Recommendations] peut correspondre aux valeurs de paramètre envoyées dans l’appel [!DNL Target]. Dans cette instance, [!DNL Target] détecte qu’un visiteur utilise un appareil mobile, en fonction de la hauteur et de la largeur d’écran envoyées dans l’appel [!DNL Target] et recommande uniquement les éléments qui sont des appareils mobiles.

Examinez l’exemple d’appel Target suivant :

![Appel Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Sur la page qu’un visiteur consulte, il voit des produits d’appareil mobile.

![ Produits pour appareils mobiles ](/help/main/c-recommendations/c-algorithms/assets/phones.png)
