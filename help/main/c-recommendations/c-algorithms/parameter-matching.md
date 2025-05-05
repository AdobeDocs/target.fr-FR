---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance de paramètres
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).
title: Comment filtrer par correspondance de paramètres dans les activités Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 10%

---

# [!UICONTROL Parameter Matching]

Filtrez de manière dynamique en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).

Par exemple, recommandez uniquement le contenu correspondant au paramètre de page « secteur » ou à d’autres paramètres, tels que les dimensions de l’appareil ou la géolocalisation, comme dans les exemples suivants.

* Les paramètres de mbox relatifs à la largeur et à la hauteur de l’écran peuvent être utilisés pour cibler les visiteurs mobiles et ne recommander que des appareils mobiles et des accessoires.
* Créez une règle de recommandations qui renvoie uniquement les téléphones mobiles les plus vendus qui correspondent ou dépassent la hauteur d’écran de l’appareil mobile que le visiteur utilise pour afficher la page.
* Les paramètres de géolocalisation régionaux peuvent être utilisés pour renvoyer des recommandations d’outils pendant l’hiver. Les souffleuses à neige et d&#39;autres outils d&#39;abattement de neige peuvent être recommandés pour les visiteurs dans les zones où il neige mais pas recommandé pour les visiteurs dans les zones où il ne neige pas.

>[!NOTE]
>
>Si l’activité a été créée avant le 31 octobre 2016, sa diffusion échoue si elle utilise le filtre « Correspondance de paramètres ». Pour contourner ce problème, procédez comme suit :
>
>* Créez une activité et ajoutez-y des critères.
>* Utilisez un critère qui ne contient pas le filtre « Correspondance de paramètres ».
>* Supprimez le filtre « Correspondance de paramètres » des critères.

## Exemples de correspondance de paramètres

[!UICONTROL Parameter Matching] vous permet de recommander du contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation, comme dans l’exemple suivant :

[!DNL Recommendations] pouvez correspondre aux valeurs de paramètre envoyées dans l’appel [!DNL Target]. Dans ce cas, [!DNL Target] détecte qu’un visiteur utilise un appareil mobile, en fonction des paramètres de hauteur et de largeur d’écran envoyés dans l’appel [!DNL Target], et recommande uniquement les éléments qui sont des appareils mobiles.

Examinons l’exemple d’appel Target suivant :

![Appel Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Sur la page qu’un visiteur ou une visiteuse consulte, des produits pour appareils mobiles s’affichent.

![Produits pour appareils mobiles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
