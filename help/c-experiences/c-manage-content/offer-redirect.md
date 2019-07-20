---
description: L’offre de redirection déclenche une redirection vers une nouvelle page au niveau du navigateur.
keywords: offre de redirection;créer une offre de redirection;ajouter une offre html;transférer tous les paramètres d’URL dans une offre de redirection;transférer mboxSessionId dans une offre de redirection (disponible uniquement lorsque la redirection est effectuée vers un domaine différent)
seo-description: L’offre de redirection déclenche une redirection vers une nouvelle page au niveau du navigateur.
seo-title: Création d’offres de redirection
solution: Target
title: Création d’offres de redirection
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Création d’offres de redirection{#create-redirect-offers}

L’offre de redirection déclenche une redirection vers une nouvelle page au niveau du navigateur.

Vous pouvez avoir deux pages complètement différentes à tester au lieu de modifier simplement des éléments de contenu d’une page. Dans ce cas, votre test A/B compare la page A et la page B. Configurez une campagne de test A/B avec deux expériences : une pointant vers la page par défaut A et l’autre redirigeant vers la page B. L’offre est configurée pour rediriger le visiteur vers une page différente.

>[!NOTE] {class="- topic/note "}
>
>Vous ne pouvez pas rediriger les offres dans ajax mbox (`mboxUpdate`).

>[!NOTE]
>
>Pour les offres de redirection dans les activités utilisant A4T, votre mise en œuvre doit respecter certaines conditions préalables minimales. En outre, vous devez prendre connaissance de certaines informations importantes. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

Pour plus d’informations sur le paramétrage d’une expérience qui redirige, consultez [Redirection vers une URL](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

L’offre de redirection exécute un code JavaScript pour rediriger le navigateur. Ce code utilise la méthode `window.location.replace();`, de sorte que la page à partir de laquelle le visiteur est redirigé ne soit pas stockée dans l’historique du navigateur. Le visiteur peut ainsi toujours utiliser le bouton permettant de retourner à la page précédente dans le navigateur.

>[!NOTE] {class="- topic/note "}
>
>Si vous souhaitez transmettre la valeur de référence de la page d’entrée, il est recommandé d’utiliser une offre HTML plutôt qu’une offre de redirection.

**Pour créer une offre de redirection :**

1. Cliquez sur **[!UICONTROL Offres]**, puis sélectionnez l’onglet **Offres (code)[!UICONTROL .]**
1. Cliquez sur **[!UICONTROL Créer]** &gt; **[!UICONTROL Offre de redirection]**.
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

>[!NOTE] {class="- topic/note "}
>
>Avant de commencer ces tests, demandez à votre consultant d’implémentation.

## Vidéo de formation : Le Référentiel de contenu (4:56)

Cette vidéo fournit des informations sur la gestion du contenu.

* Connexion entre la [bibliothèque des ressources Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/creative_cloud.html) et la bibliothèque de contenu Target
* Offres HTML personnalisées
* Offre HTML personnalisée dans le compositeur d’expérience visuelle

>[!VIDEO](https://video.tv.adobe.com/v/17387?captions=fre_fr)
