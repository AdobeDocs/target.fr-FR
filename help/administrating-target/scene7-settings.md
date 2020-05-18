---
description: Target Standard peut être intégré à Adobe Dynamic Media Classic (anciennement Scene7) pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
title: Intégration de Dynamic Media Classic intégration de configuration
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 95%

---


# Intégration de Dynamic Media Classic{#scene-settings}

Target  peut être intégré à Adobe Dynamic Media Classic (anciennement Scene7) pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.

>[!NOTE]
>
>L’intégration de Target avec Dynamic Media Classic permet la diffusion d’actifs (intégrés à des activités) transférés vers le dossier des actifs Adobe Experience Cloud. Cette intégration ne permet pas d’accéder à tous les actifs transférés vers Dynamic Media Classic pour la diffusion dans des activités Target.

Si vous disposez déjà d’un compte multimédia dynamique, vous pouvez fournir vos informations d’identification existantes. Si vous n’avez pas de compte, vous pouvez demander un compte Dynamic Media Classic à utilisation restreinte sans frais supplémentaires auprès de votre représentant Adobe. Ce compte pourra être utilisé à des fins limitées pour un usage dans Target uniquement. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

Si ce paramètre n’est pas configuré, l’option de permutation d’image n’est pas disponible dans le flux de travaux de création d’activité. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite exploiter les offres d’image avec des images qui ont été chargées depuis Adobe Experience Cloud en vue de les utiliser dans des activités Target.

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image chargée dans Experience Cloud pour la consommation directe ou à l’extérieur des flux de travaux de ciblage utilisant Adobe Target. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Il est à noter que l’URL de stockage et les URL de publications finales des images depuis Dynamic Media sont différentes et qu’il ne faut PAS créer d’offres en utilisant le lien de stockage des images, car la livraison ne fonctionnera pas dans de ce cas. Il faut utiliser la capacité des offres d’images, comme expliqué dans notre documentation d’aide.

Pour l’intégrer à Dynamic Media Classic (Scene7), vous devez spécifier les informations suivantes.

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Settings]**.

1. Spécifiez les informations de compte Dynamic Media Classic suivantes :

   **Région :** région de votre compte Dynamic Media (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers Dynamic Media

   **Adresse électronique :** adresse électronique utilisée pour la connexion à Dynamic Media Classic (Scene7).

   **Mot de passe :** mot de passe utilisé pour la connexion à Dynamic Media Classic (Scene7).

1. Cliquez sur **[!UICONTROL Envoyer]**.
