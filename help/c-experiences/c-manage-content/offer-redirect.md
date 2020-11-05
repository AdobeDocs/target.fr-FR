---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Informations sur les offres de redirection d’Adobe Target qui entraîne la redirection du navigateur vers une nouvelle page.
title: Création d’offres de redirection
feature: offers
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 98%

---


# Création d’offres de redirection{#create-redirect-offers}

L’offre de redirection déclenche une redirection vers une nouvelle page au niveau du navigateur.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A et la page B. Configurez une campagne de test A/B avec deux expériences : une pointant vers la page par défaut A et l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une page différente.

>[!NOTE]
>
>Vous ne pouvez pas rediriger les offres dans ajax mbox (`mboxUpdate`).
>
>Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

>[!NOTE]
>
>Si vous souhaitez transmettre la valeur de référence de la page d’entrée, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

**Pour créer une offre de redirection :**

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **[!UICONTROL Offres (code)]**.
1. Cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Offre de redirection]**.
1. Saisissez le nom de l’offre.
1. Entrez l’URL du contenu ou de la destination unique vers lequel ou laquelle vous souhaitez rediriger les visiteurs. Cette URL doit être une URL absolue.

   >[!NOTE]
   >
   >Les offres de redirection engendrent une boucle infinie si l’URL de redirection qualifie également l’utilisateur pour la même activité. Vous devez veiller à ce que l’utilisateur ne se qualifie pas à nouveau pour l’activité après avoir été redirigé.

1. Sélectionnez les options pour personnaliser votre offre de redirection :

* **Inclure tous les paramètres d’URL :** cochez cette case si vous voulez que les paramètres d’URL présents dans la page précédente soient propagés à la page de redirection.

   Par exemple : vous souhaitez rediriger directement les visiteurs d’une page destinée aux hommes vers une page de catégorie de chemises pour homme. Vous voulez également que les paramètres dynamiques de l’URL soient transmis, car c’est de cette façon que vous déterminez comment les utilisateurs ont eu accès à votre site : par courrier électronique, bannière publicitaire, publicité de recherche ou de manière organique. Si vous cochez cette case, votre offre de redirection sur la page [!DNL `https://www.mycompany.com/mens.html?emailId=123`] devient automatiquement [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] lorsque tout ce que vous avez entré dans la zone URL était [!DNL `https://www.mycompany.com/mensShirts.html`].

* **Transmettre l’ID de session de la mbox (requis pour la redirection vers un autre domaine) :** cochez cette case si vous souhaitez que `sessionId` soit automatiquement ajouté à la redirection. Cela est uniquement nécessaire lorsque vous testez des clics d’un courrier électronique ou d’un domaine à un autre. Le paramètre `sessionId` est comparé au cookie du visiteur afin que le visiteur puisse être toujours suivi et que le contenu approprié s’affiche.

   Si vous utilisez la configuration de cookies propriétaires et tiers, il n’est pas nécessaire de transmettre le paramètre mboxsessionId lors de la transition entre domaines. Comme il est persistant sur le cookie tiers, il n’est pas nécessaire dans l’URL.

>[!NOTE]
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Vidéo de formation : Le Référentiel de contenu (4:56) ![badge Aperçu](/help/assets/overview.png)

Cette vidéo fournit des informations sur la gestion du contenu.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/assets/creative-cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387)
