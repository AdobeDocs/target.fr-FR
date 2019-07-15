---
description: Target Standard peut être intégré à Adobe Dynamic Media Classic (anciennement Scene 7) pour fournir la gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
seo-description: Target Standard peut être intégré à Adobe Dynamic Media Classic (anciennement Scene 7) pour fournir la gestion des actifs numériques (DAM) dans la bibliothèque de contenu.
seo-title: Intégration de Dynamic Media Classic
solution: Target
subtopic: Prise en main
title: Intégration de Dynamic Media Classic
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic integration{#scene-settings}

Target Standard peut être intégré à Adobe Dynamic Media Classic (anciennement Scene 7) pour fournir la gestion des actifs numériques (DAM) dans la bibliothèque de contenu.

>[!NOTE]
>
>L&#39;intégration de Target avec Dynamic Media Classic permet la diffusion de ressources (dans le cadre d&#39;activités) téléchargées dans le dossier des ressources Adobe Experience Cloud. Cette intégration n&#39;autorise pas l&#39;accès à tous les fichiers transférés dans Dynamic Media Classic pour une diffusion dans les activités Target.

Si vous disposez déjà d&#39;un compte multimédia dynamique, vous pouvez fournir vos informations d&#39;identification existantes. Si vous n&#39;avez pas de compte, vous pouvez demander un compte Dynamic Media Classic à utilisation restreinte sans frais supplémentaires auprès de votre représentant Adobe. Ce compte pourra être utilisé à des fins limitées pour un usage dans Target uniquement. Ce service est mis à la disposition des clients pour les flux de travaux nécessitant une fonctionnalité de permutation d’image.

Si ce paramètre n’est pas configuré, l’option de permutation d’image n’est pas disponible dans le flux de travaux de création d’activité. Une fois ce paramètre configuré, l’option de permutation ou de modification d’image devient disponible à la fois dans le [compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Vous pouvez ensuite exploiter les offres d’image avec des images qui ont été chargées depuis Adobe Experience Cloud en vue de les utiliser dans des activités Target.

Si vous souhaitez référencer une adresse URL d’image publique directement dans une offre ou dans un code personnalisé lors de la création d’une activité, vous devez déployer l’image sur vos propres serveurs Web et utiliser votre propre URL dans le code. Il n’existe aucun moyen d’obtenir l’URL publiée d’une image chargée dans Experience Cloud pour la consommation directe ou à l’extérieur des flux de travaux de ciblage utilisant Adobe Target. En vertu des conditions contractuelles, cette fonctionnalité n’est pas autorisée.

Notez que l&#39;URL de stockage et les URL finales de publication des images issues de médias dynamiques sont différentes et qu&#39;il est impossible de créer des offres à l&#39;aide du lien de stockage des images car la diffusion ne fonctionnera pas dans ce cas. Il faut utiliser la capacité des offres d’images, comme expliqué dans notre documentation d’aide.

Pour intégrer Dynamic Media Classic (Scene 7), vous devez spécifier les informations suivantes.

1. **Cliquez sur[!UICONTROL Configuration]** &gt; **[!UICONTROL Paramètres Scene7]**.
1. Spécifiez les informations de compte Classic Media Classic suivantes :

   **Région :** La région de votre compte multimédia dynamique : Amérique du Nord, Europe ou Asie.

   **Dossier ad hoc :** Emplacement du contenu situé en dehors du dossier cible et téléchargé manuellement vers le contenu multimédia dynamique.

   **Adresse électronique :** Adresse électronique utilisée pour la connexion à Dynamic Media Classic (Scene 7).

   **Mot de passe :** mot de passe utilisé pour la connexion à Dynamic Media Classic (Scene 7).
1. Cliquez sur **[!UICONTROL Envoyer]**.
