---
description: Target Standard peut être intégré à Adobe Scene7 pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
seo-description: Target Standard peut être intégré à Adobe Scene7 pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
seo-title: Paramètres de Scene7
solution: Target
subtopic: Prise en main
title: Paramètres de Scene7
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Paramètres de Scene7{#scene-settings}

Target Standard peut être intégré à Adobe Scene7 pour offrir le module de gestion des actifs numériques (DAM) dans la bibliothèque de contenu.

>[!NOTE]
>
>L’intégration de Target à Scene7 permet la diffusion d’actifs (intégrés à des activités) transférés vers le dossier des actifs Adobe Experience Cloud. Cette intégration ne permet pas d’accéder à tous les actifs transférés vers Scene7 pour la diffusion dans des activités Target.

Si vous possédez un compte Scene7, vous pouvez spécifier vos informations d’identification Scene7. Si vous ne possédez pas de compte Scene7, contactez votre représentant Adobe afin qu’il configure cette fonctionnalité avec un compte Scene7 gratuit associé exclusivement à votre compte Target. Ce compte pourra être utilisé à des fins limitées pour un usage dans Target uniquement. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

Si ce paramètre n’est pas configuré, l’option de permutation d’image n’est pas disponible dans le flux de travaux de création d’activité. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le  [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite exploiter les offres d’image avec des images qui ont été chargées depuis Adobe Experience Cloud en vue de les utiliser dans des activités Target.

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image chargée dans Experience Cloud pour la consommation directe ou à l’extérieur des flux de travaux de ciblage utilisant Adobe Target. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Il est à noter que l’URL de stockage et les URL de publications Scene7 finales des images sont différentes et qu’il ne faut PAS créer d’offres en utilisant le lien de stockage des images, car la livraison ne fonctionnera pas dans de ce cas. Il faut utiliser la capacité des offres d’images, comme expliqué dans notre documentation d’aide.

Pour intégrer Target Standard à Scene7, vous devez indiquer certaines de vos informations Scene7.

1. **Cliquez sur[!UICONTROL Configuration]** &gt; **[!UICONTROL Paramètres Scene7]**.
1. Indiquez les informations de compte Scene7 suivantes : 

   **Région Scene7 :** région de votre compte Scene7 (Amérique du Nord, Europe ou Asie).

   **Dossier ad hoc Scene7 :** emplacement du contenu situé en dehors du dossier Target et téléchargé manuellement vers Scene7.

   **Adresse électronique Scene7 :** adresse électronique utilisée pour la connexion à Scene7.

   **Mot de passe Scene7 :** mot de passe utilisé pour la connexion à Scene7.
1. Cliquez sur **[!UICONTROL Envoyer]**.
