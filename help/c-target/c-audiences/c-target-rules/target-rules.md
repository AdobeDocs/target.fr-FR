---
keywords: ciblage;catégories target;conditions target;gestionnaire d’audience;paramètres de profil personnalisés;profil du visiteur;paramètres utilisateur personnalisés;règles target
description: Découvrez comment utiliser des catégories (navigateur, géolocalisation, réseau, système d’exploitation, profil du visiteur) pour cibler du contenu.
title: Quelles sont les catégories d’audiences ?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 50%

---

# Catégories d’audiences

Vous pouvez cibler sur n’importe quel attribut de catégorie à l’aide de [!DNL Adobe Target]. Pour créer des règles de ciblage (ou groupes) pour chaque attribut, faites glisser les attributs de votre choix dans le créateur d’audiences .

![Attributs pour les audiences](/help/c-target/c-audiences/assets/attributes.png)

Lorsqu’une catégorie spécifique est sélectionnée, vous pouvez appliquer une ou plusieurs conditions de ciblage. Par exemple, dans la catégorie Géo, définissez une règle comme Ville=San Francisco. L’ajout de plusieurs valeurs crée une condition OU. Le visiteur doit correspondre uniquement à l’une des valeurs pour satisfaire à la condition de ciblage. Pour les conditions ET sur le même paramètre, créez une cible d’expression personnalisée.

Une fois une règle créée, cliquez sur **[!UICONTROL Terminé]**. Une synthèse de la règle s’affiche en regard du lien de ciblage pour le niveau ciblé.

Vous pouvez affiner davantage une règle en ajoutant d’autres conditions ou en créant des règles supplémentaires dans d’autres catégories. Par exemple, vous pouvez cibler uniquement les utilisateurs Firefox de San Francisco qui ont accédé à votre site à partir de Google. Définissez la catégorie [!UICONTROL Géo] pour cibler les utilisateurs de San Francisco, la catégorie [!UICONTROL Navigateur] pour cibler les utilisateurs à l’aide de Firefox et la catégorie [!UICONTROL Sources de trafic] pour cibler les utilisateurs provenant de [!UICONTROL Google]. Les règles créées dans plusieurs catégories sont combinées avec l’opérateur AND.

Pour créer des règles de ciblage complexes qui incluent des opérations OU sur plusieurs catégories, créez une cible d’expression.

Vous pouvez également cibler des paramètres de profil personnalisés et des paramètres `user.`. Lors de l’ajout d’une audience, effectuez un glisser-déposer de **[!UICONTROL Profil du visiteur]**, puis sélectionnez le paramètre que vous souhaitez utiliser pour cibler votre activité. Si le paramètre souhaité ne s’affiche pas, il n’a pas été déclenché par une mbox.

Utilisez la zone de recherche pour effectuer des recherches dans votre liste d’[!UICONTROL audiences]. Vous pouvez effectuer une recherche sur une partie du nom de l’audience ou placer une chaîne spécifique entre guillemets.

Vous pouvez trier la liste [!UICONTROL Audience] par nom d’audience ou par date de dernière modification. Pour trier par nom ou date, cliquez sur l’en-tête de la colonne, puis choisissez d’afficher les audiences par ordre croissant ou décroissant.

## Vidéo de formation : Création d’audiences ![Badge du tutoriel](/help/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
