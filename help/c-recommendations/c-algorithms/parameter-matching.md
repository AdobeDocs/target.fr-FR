---
keywords: règles d’inclusion ; critères d’inclusion ; recommandations ; promotion ; promotions ; filtrage dynamique ; dynamique ; correspondance de paramètre
description: Découvrez comment filtrer dynamiquement dans Adobe Target en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).
title: Comment puis-je filtrer par correspondance de paramètres dans les Activités Recommendations ?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![Correspondance ](/help/assets/premium.png) PREMIUMParameter

Filtrez dynamiquement en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).

Par exemple, il est recommandé de ne recommander que le contenu qui correspond au paramètre de page &quot;industrie&quot; ou à d’autres paramètres, tels que les dimensions du périphérique ou la géolocalisation, comme dans les exemples suivants.

* Les paramètres de mbox pour la largeur et la hauteur d’écran peuvent être utilisés pour cible des visiteurs mobiles et ne recommander que les périphériques et accessoires mobiles.
* Créez une règle de recommandation qui renvoie uniquement les téléphones mobiles les plus vendus qui correspondent ou dépassent la hauteur d’écran du périphérique mobile sur lequel le visiteur utilise la vue de la page.
* Les paramètres régionaux de géolocalisation peuvent être utilisés pour renvoyer des recommandations d&#39;outils pendant l&#39;hiver. Les souffleurs de neige et autres outils de réduction de la neige peuvent être recommandés aux visiteurs dans les régions où il neige, mais pas aux visiteurs dans les régions où il ne neige pas.

>[!NOTE]
>
>Si l’activité a été créée avant le 31 octobre 2016, sa diffusion échouera si elle utilise le filtre &quot;Correspondance des paramètres&quot;. Pour contourner ce problème, procédez comme suit :
>
>* Créez une activité et ajoutez-y des critères.
>* Utilisez un critère qui ne contient pas le filtre « Correspondance de paramètres ».
>* Supprimez le filtre « Correspondance de paramètres » des critères.


## Exemples de correspondance de paramètres

[!UICONTROL La ] correspondance des paramètres vous permet de recommander le contenu qui correspond aux paramètres de page ou aux paramètres de l’visiteur, tels que les dimensions de l’appareil ou la géolocalisation, comme dans l’exemple suivant :

[!DNL Recommendations] peut correspondre aux valeurs de paramètre envoyées dans l’ [!DNL Target] appel. Dans cette instance, [!DNL Target] détecte qu&#39;un visiteur utilise un périphérique mobile, en fonction des paramètres de hauteur et de largeur d&#39;écran envoyés dans l&#39;appel [!DNL Target], et recommande uniquement les éléments qui sont des périphériques mobiles.

Examinez l’exemple d’appel de Cible suivant :

![Appel de cible](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Sur la page qu’un visiteur consulte, il voit les produits des dispositifs portables.

![Produits de périphériques mobiles](/help/c-recommendations/c-algorithms/assets/phones.png)
