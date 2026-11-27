---
keywords: rediriger;url de redirection;envoyer à une autre page
description: Découvrez comment utiliser l’option Rediriger vers l’URL dans Adobe [!DNL Target] lorsque vous souhaitez envoyer le visiteur vers une autre page plutôt que d’afficher le contenu sur la même page.
title: Puis-je rediriger une page vers une autre URL ?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# Redirection vers une URL {#redirect-to-url}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser l’option **[!UICONTROL Rediriger vers l’URL]** pour envoyer les visiteurs vers une autre page au lieu d’afficher le contenu sur la même page.

>[!ENDSHADEBOX]

L’option **[!UICONTROL Rediriger vers l’URL]** dans [!DNL Adobe Target] envoie un visiteur vers une autre page au lieu d’afficher le contenu sur la même page. Cela convient à la comparaison de deux pages complètement différentes, par opposition aux modifications apportées à des éléments de contenu dans une page. Un test A/B compare ensuite la page A à la page B : une expérience pointe vers la page A par défaut, tandis que l’autre redirige vers la page B.

Une offre de redirection exécute le code JavaScript qui redirige le navigateur. Le code utilise la méthode `window.location.replace();`, de sorte que la page depuis laquelle le visiteur est redirigé n’est pas stockée dans l’historique du navigateur. Le visiteur peut donc toujours utiliser le bouton Précédent du navigateur.

## Création d’une offre de redirection {#create-redirect-offer}

L’expérience qui redirige définit la page vers laquelle les visiteurs sont envoyés et, éventuellement, les conditions de la redirection.

1. Créez une expérience.

1. Dans le cadre **[!UICONTROL Expériences]**, cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) pour l’expérience qui redirige.

1. Cliquez sur **[!UICONTROL Rediriger vers l&#39;URL]**.

   ![Icône Autres actions](assets/redirect_1.png)

1. Dans la boîte de dialogue **[!UICONTROL Rediriger vers l&#39;URL]**, saisissez l&#39;URL de la page B.

   ![Icône Autres actions](assets/redirect_2.png)

1. (Facultatif) Sélectionnez l’option pour inclure les paramètres de requête actuels.

   Lorsque cette option est sélectionnée, tout ce qui suit `?` dans l’URL du visiteur est ajouté à l’URL de redirection au moment de la redirection.

## Limites

Les offres de redirection présentent les limites suivantes :

* **A4T :** une offre de redirection dans une activité qui utilise A4T nécessite une implémentation qui répond à certaines exigences minimales, et d’autres informations importantes s’appliquent. Voir la FAQ sur les [offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
* **Compositeur d’expérience d’après les formulaires :** n’utilisez pas d’offre de redirection dans les mbox qui font partie de la page. Utilisez une offre de redirection uniquement à partir d’une balise de script faisant partie d’HTML `<head>` et utilisez toujours la création automatique et définissez l’offre de redirection pour la mbox globale.

>[!NOTE]
>
>Pour transmettre la valeur référente de la landing page, utilisez une offre HTML au lieu d&#39;une offre de redirection.

## Problèmes connus

Les activités de redirection dans les implémentations d’at.js peuvent entraîner l’insertion d’une boucle dans l’URL de prévisualisation, avec l’offre diffusée à plusieurs reprises. Utilisez le [mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md) pour prévisualiser et tester l’activité à la place. Ce problème n’affecte pas la diffusion réelle de l’offre. (TGT-23019)
