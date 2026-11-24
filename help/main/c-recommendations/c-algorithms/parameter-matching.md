---
keywords: règles d’inclusion;critères d’inclusion;recommandations;promotion;promotions;filtrage dynamique;dynamique;correspondance de paramètres
description: Découvrez comment filtrer dynamiquement dans Adobe [!DNL Target] Recommendations en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).
title: Correspondance des paramètres
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
TQID: 'https://experienceleague.adobe.com/GTli-O1p4Gm2Fg9J-L0ukQ8dSw2t-da8OatFLP8Ks9g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 8%
---
# Correspondance des paramètres {#parameter-matching}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment filtrer les recommandations de manière dynamique dans [!DNL Adobe Target Recommendations] en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).

>[!ENDSHADEBOX]

**[!UICONTROL La correspondance des paramètres]** recommande uniquement le contenu correspondant aux paramètres de la page ou aux paramètres du visiteur, tels que les dimensions de l’appareil ou la géolocalisation. Par exemple, seul le contenu correspondant au paramètre de page « secteur » peut être recommandé. Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Pour plus d’informations, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Voici d’autres exemples :

* Les paramètres de mbox relatifs à la largeur et à la hauteur de l’écran peuvent être utilisés pour cibler les visiteurs mobiles et ne recommander que des appareils mobiles et des accessoires.
* Une règle de recommandations ne peut renvoyer que les téléphones mobiles les plus vendus qui correspondent ou dépassent la hauteur d’écran de l’appareil mobile que le visiteur utilise pour afficher la page.
* Les paramètres de géolocalisation régionaux peuvent être utilisés pour renvoyer des recommandations d’outils pendant l’hiver. Des souffleuses à neige et d&#39;autres outils de déneigement peuvent être recommandés aux visiteurs dans les zones où il neige mais pas aux visiteurs dans les zones où il ne neige pas.

## Exemples de correspondance de paramètres

[!DNL Recommendations] peut correspondre aux valeurs de paramètre envoyées dans l’appel [!DNL Target]. Dans l’exemple suivant, [!DNL Target] détecte qu’un visiteur utilise un appareil mobile, en fonction des paramètres de hauteur et de largeur d’écran envoyés dans l’appel [!DNL Target], et recommande uniquement les éléments qui sont des appareils mobiles.

Prenons l’exemple d’appel [!DNL Target] suivant :

![Appel de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Les produits pour appareils mobiles s’affichent sur la page consultée par un visiteur.

![Produits pour appareils mobiles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
