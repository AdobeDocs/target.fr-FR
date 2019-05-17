---
description: Cette rubrique explique comment créer un carrousel pouvant être modifié dans le compositeur d’expérience visuelle.
keywords: Compositeur d’expérience visuelle, VEC, carrousel
seo-description: Cette rubrique explique comment créer un carrousel pouvant être modifié dans le compositeur d’expérience visuelle.
seo-title: Création de carrousels qui fonctionnent dans le compositeur d’expérience visuelle
solution: Target
subtopic: Test multivarié
title: Création de carrousels qui fonctionnent dans le compositeur d’expérience visuelle
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Création de carrousels qui fonctionnent dans le compositeur d’expérience visuelle{#creating-carousels-that-work-in-the-visual-experience-composer}

Cette rubrique explique comment créer un carrousel pouvant être modifié dans le compositeur d’expérience visuelle.

Lorsque vous utilisez la procédure suivante, [!DNL Target] considère toujours que la diapositive sélectionnée est associée au « sélecteur » de la diapositive appropriée, et même si celle-ci est modifiée dans le compositeur d’expérience visuelle au bout de quelques secondes.

1. Créez des espaces réservés d’HTML statique.

   ```
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
   >L’option [!UICONTROL Rendu avec JavaScript] n’est actuellement pas prise en charge si elle est utilisée avec un code personnalisé dans le compositeur d’expérience visuelle.

1. Mettez à jour uniquement les balises className afin de masquer les autres et d’afficher les suivantes avec le délai/l’animation.

   Ne jamais utiliser JavaScript pour mettre la structure DOM à jour.