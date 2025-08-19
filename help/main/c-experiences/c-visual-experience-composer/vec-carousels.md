---
keywords: Compositeur d’expérience visuelle, VEC, carrousel
description: Découvrez comment créer un carrousel modifiable dans le compositeur d’expérience visuelle (VEC [!DNL Target] Visual Experience Composer) d’Adobe.
title: Comment créer des carrousels dans le compositeur d’expérience visuelle ?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 58%

---

# Création de carrousels qui fonctionnent dans le compositeur d’expérience visuelle

Cette rubrique explique comment créer un carrousel qui peut être modifié dans le [!DNL Adobe Target] d’[!UICONTROL Visual Experience Composer] (VEC).

Lorsque vous utilisez la procédure suivante, [!DNL Target] considère toujours que la diapositive sélectionnée est associée au « sélecteur » de la diapositive appropriée, et même si celle-ci est modifiée dans le compositeur d’expérience visuelle au bout de quelques secondes.

1. Créez des espaces réservés d’HTML statique.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Ajoutez un CSS pour la conception de l’apparence.

   Ne pas utiliser JavaScript.

   >[!NOTE]
   >
   >L’option [!UICONTROL Render Using JavaScript] n’est actuellement pas prise en charge si elle est utilisée avec du code personnalisé dans le compositeur d’expérience visuelle.

1. Mettez à jour uniquement les balises className afin de masquer les autres et d’afficher les suivantes avec le délai/l’animation.

   Ne jamais utiliser JavaScript pour mettre la structure DOM à jour.
