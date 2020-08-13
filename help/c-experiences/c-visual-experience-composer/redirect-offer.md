---
description: Utilisez cette option lorsque vous souhaitez envoyer le visiteur vers une page différente plutôt que d’afficher le contenu sur la même page.
title: Redirection vers une URL
feature: vec
subtopic: Multivariate Test
topic: Standard
uuid: e6515279-8a6e-4265-aa2d-700ee81eb143
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 100%

---


# Redirection vers une URL{#redirect-to-a-url}

Utilisez cette option lorsque vous souhaitez envoyer le visiteur vers une page différente plutôt que d’afficher le contenu sur la même page.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A et la page B. Configurez une campagne de test A/B avec deux expériences : une pointant vers la page par défaut A et l’autre effectuant une redirection vers la page B. Dans le menu Action d’expérience, localisé en cliquant sur l’étiquette de lettre de l’expérience, sélectionnez **[!UICONTROL Rediriger vers l’URL]** et indiquez l’URL de la page B. L’offre est configurée pour rediriger le visiteur vers une page différente.

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Il utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

Les offres de redirection ont quelques limites :

* Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Lors de l’utilisation du compositeur d’expérience d’après les formulaires, les offres de redirection ne doivent pas être utilisées dans des mbox qui font partie de la page. Une offre de redirection ne doit être utilisée qu’à partir d’une balise de script qui fait partie de la balise HTML `<head>`. Vous devez toujours utiliser l’auto création et définir l’offre de redirection pour la mbox globale.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page d’entrée, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

Pour créer une offre de redirection :

1. Créez une expérience.
1. Pointez votre curseur sur une expérience, puis cliquez sur l’icône Rediriger vers l’URL (![](assets/icon_redirect_url.png)).

   ![](assets/exp_actions.png)

1. Saisissez l’URL.
1. Si vous le souhaitez, sélectionnez l’option permettant d’inclure les paramètres de requête actuels.

   Si cette option est sélectionnée, tout élément après le point d’interrogation (?) dans l’URL du visiteur est ajouté à l’URL de redirection au moment de la redirection.

   Cette option est sélectionnée par défaut.
1. (Facultatif) Créez des règles supplémentaires.

   Les règles supplémentaires peuvent être basées sur les éléments suivants :

   * URL
   * Domaine
   * Chemin
   * Fragment de hachage (#)
   * Requête
   * Paramètre de mbox
   Les règles supplémentaires peuvent être jointes à l’URL à l’aide d’un opérateur ET ou OU. Toutes les règles ajoutées sont évaluées les unes par rapport aux autres avec un opérateur ET.
