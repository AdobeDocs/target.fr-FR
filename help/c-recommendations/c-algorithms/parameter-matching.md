---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: Filtrez dynamiquement dans Adobe Target en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).
title: Filtrage par correspondance de paramètres dans les règles d’inclusion dynamique dans Adobe Target
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![Correspondance des paramètres PREMIUM](/help/assets/premium.png)

Filtrez dynamiquement en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).

Par exemple, il est recommandé de ne recommander que le contenu qui correspond au paramètre de page &quot;industrie&quot; ou à d’autres paramètres, tels que les dimensions du périphérique ou la géolocalisation, comme dans les exemples suivants.

* Les paramètres de mbox pour la largeur et la hauteur d’écran peuvent être utilisés pour cible des visiteurs mobiles et ne recommander que les périphériques et accessoires mobiles.
* Les paramètres régionaux de géolocalisation peuvent être utilisés pour renvoyer des recommandations d&#39;outils pendant l&#39;hiver. Les souffleurs de neige et autres outils de réduction de la neige peuvent être recommandés aux visiteurs dans les régions où il neige, mais pas aux visiteurs dans les régions où il ne neige pas.

>[!NOTE]
>
>Si l’activité a été créée avant le 31 octobre 2016, sa diffusion échouera si elle utilise le filtre &quot;Correspondance des paramètres&quot;. Pour contourner ce problème, procédez comme suit :
>
>* Créez une activité et ajoutez-y des critères.
>* Utilisez un critère qui ne contient pas le filtre « Correspondance de paramètres ».
>* Supprimez le filtre « Correspondance de paramètres » des critères.


Opérateurs disponibles :

* est égal à
* n’est pas égal à
* contient
* ne contient pas
* commence par
* se termine par
* est supérieur ou égal à
* est inférieur ou égal à
* est compris entre