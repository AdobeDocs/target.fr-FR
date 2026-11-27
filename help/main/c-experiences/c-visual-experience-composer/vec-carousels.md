---
keywords: Compositeur d’expérience visuelle, VEC, carrousel
description: Découvrez comment créer un carrousel modifiable dans le compositeur d’expérience visuelle (VEC) [!DNL Target] d’Adobe.
title: Comment créer des carrousels dans le compositeur d’expérience visuelle ?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# Création de carrousels qui fonctionnent dans le [!UICONTROL compositeur d’expérience visuelle] {#vec-carousels}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer un carrousel modifiable dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC).

>[!ENDSHADEBOX]

Un carrousel créé avec la structure suivante peut être modifié dans le [!DNL Adobe Target] **[!UICONTROL compositeur d’expérience visuelle]** (VEC). La structure conserve le sélecteur de chaque diapositive valide, de sorte que [!DNL Target] identifie toujours la diapositive correcte, même si la diapositive affichée change quelques secondes après le chargement de la page dans le compositeur d’expérience visuelle.

1. Créez les diapositives comme espaces réservés HTML statiques, avec une diapositive visible et les autres diapositives masquées par la classe .

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Concevez l’aspect avec CSS uniquement. N’utilisez pas JavaScript à cet effet.

   >[!NOTE]
   >
   >L’option **[!UICONTROL Rendre à l’aide de JavaScript]** n’est actuellement pas prise en charge lorsqu’elle est utilisée avec du code personnalisé dans le **[!UICONTROL compositeur d’expérience visuelle]**.

1. Affichez la diapositive suivante en mettant à jour uniquement les noms de classe : masquez les autres diapositives et affichez la diapositive suivante avec un minuteur ou une animation. Ne mettez jamais à jour la structure DOM avec JavaScript.
