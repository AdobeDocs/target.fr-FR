---
kewords: redirect;redirect url;send to different page
description: Découvrez comment utiliser l’option Rediriger vers l’URL dans  [!DNL Target] lorsque vous souhaitez envoyer le visiteur sur une autre page plutôt que d’afficher le contenu sur la même page.
title: Puis-je rediriger une page vers une autre URL ?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 80%

---

# Redirection vers une URL

Utilisez l’option [!UICONTROL Rediriger vers l’URL] dans [!DNL Adobe Target] lorsque vous souhaitez envoyer le visiteur vers une autre page plutôt que d’afficher le contenu sur la même page.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A et la page B. Configurez une campagne de test A/B avec deux expériences : une pointant vers la page par défaut A et l’autre effectuant une redirection vers la page B. Dans le menu Action d’expérience, localisé en cliquant sur l’étiquette de lettre de l’expérience, sélectionnez **[!UICONTROL Rediriger vers l’URL]** et indiquez l’URL de la page B. L’offre est configurée pour rediriger le visiteur vers une page différente.

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Il utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

Les offres de redirection ont quelques limites :

* Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Lors de l’utilisation du compositeur d’expérience d’après les formulaires, les offres de redirection ne doivent pas être utilisées dans des mbox qui font partie de la page. Une offre de redirection ne doit être utilisée qu’à partir d’une balise de script qui fait partie de la balise HTML `<head>`. Vous devez toujours utiliser l’auto création et définir l’offre de redirection pour la mbox globale.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page de destination, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

Pour créer une offre de redirection :

1. Créez une expérience.
1. Dans le cadre [!UICONTROL Expériences], cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallList.svg) ) pour l’expérience souhaitée.
1. Cliquez sur **[!UICONTROL Rediriger vers l’URL]**.
1. Dans la boîte de dialogue Rediriger vers l’URL , saisissez l’URL.
1. Si vous le souhaitez, sélectionnez l’option permettant d’inclure les paramètres de requête actuels.

   Si cette option est sélectionnée, tout élément après le point d’interrogation (?) dans l’URL du visiteur est ajouté à l’URL de redirection au moment de la redirection.

1. (Facultatif) Créez des règles supplémentaires.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox

   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.

## Problèmes connus

* Dans les mises en œuvre d’at.js, les activités de redirection peuvent provoquer l’entrée dans une boucle de l’URL d’aperçu (la distribution de l’offre se répète). Vous pouvez utiliser le [mode Assurance qualité](/help/main/c-activities/c-activity-qa/activity-qa.md) au lieu d’effectuer l’aperçu et la vérification de la qualité. Ce problème n’a aucun impact sur la distribution réelle de l’offre. (TGT-23019)
