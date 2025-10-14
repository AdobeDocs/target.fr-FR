---
keywords: Ciblage;compositeur d’expérience visuelle;vec;dépannage du compositeur d’expérience visuelle;dépannage;tls;tls 1.2
description: Découvrez comment résoudre les problèmes du [!UICONTROL Visual Experience Composer] (VEC).
title: Comment résoudre les problèmes liés à l’[!UICONTROL Visual Experience Composer] ?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 24%

---

# Résolution des problèmes liés à l’[!UICONTROL Visual Experience Composer]

Dans certaines conditions, des problèmes d’affichage surviennent parfois dans le [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

## Lorsque j’ouvre mon site web dans le [!UICONTROL Visual Experience Composer], les bibliothèques [!DNL Target] ne se chargent pas. (Compositeur d’expérience visuelle uniquement)  {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

+++Détails
[!DNL Target] ajoute deux paramètres (`mboxEdit=1` et `mboxDisable=1`) lors de l’ouverture du site web dans le [!UICONTROL Visual Experience Composer].

Si votre site web (en particulier les applications d’une seule page), tronque des paramètres ou les supprime réellement lors de la navigation d’une page à une autre (sans rechargement de page), la fonctionnalité de [!DNL Target] est interrompue et les bibliothèques [!DNL Target] ne se chargent pas.

Pour éviter ce problème, assurez-vous de ne pas supprimer ces deux paramètres.

+++

## Ma page ne s’ouvre pas dans le compositeur d’expérience avancé ou elle se charge lentement. Les activités ou les expériences se chargent lentement dans le compositeur d’expérience visuelle. (Compositeur d’expérience visuelle uniquement)  {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

+++Détails
Plusieurs problèmes peuvent affecter les performances des pages dans les compositeurs d’expérience [!UICONTROL Target]. Les problèmes courants sont les suivants :

* La page ne contient pas de mbox.
* Votre site utilise le blocage par proxy, ce qui ne permet pas à la page d’être ouverte dans les compositeurs d’expérience.
* Votre site n’est pas autorisé à être ouvert dans une iFrame.

Si des problèmes se produisent dans le [!UICONTROL Enhanced Experience Composer], essayez de désactiver le [!UICONTROL Enhanced Experience Composer] et utilisez le [!UICONTROL Visual Experience Composer] à la place.

Pour désactiver le [!UICONTROL Enhanced Experience Composer], accédez à **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** et désactivez l’option **[!UICONTROL Enable Enhanced Experience Composer]**.

Le message d’erreur suivant s’affiche dans la console pour certains utilisateurs :

![Message d’erreur de la console](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Si ni le [!UICONTROL Visual Experience Composer] ni le [!UICONTROL Enhanced Experience Composer] ne fonctionnent, utilisez une extension de navigateur telle que [!DNL Requestly] ([!DNL Chrome] ou [!DNL Firefox]) ou Modifier les en-têtes de réponse (Firefox) qui peuvent remplacer les options d’en-tête X-Frames pour votre site et permettre leur chargement dans les iFrames, ce qui active le compositeur d’expérience visuelle. Si vous ne pouvez pas utiliser d’extensions de navigateur, utilisez le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>En plus des informations suivantes, vous pouvez utiliser l’extension [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) par [!DNL Google Chrome].

>[!NOTE]
>
>Utilisez ces modules externes uniquement dans le cadre de modifications dans le VEC.
>
>Pour l’extension [!DNL Requestly], chaque fois qu’il est nécessaire de supprimer des en-têtes, vous devez effectuer l’une des opérations suivantes :
>
>* Ajoutez des règles d’URL pour les URL que vous souhaitez ouvrir avec le compositeur d’expérience visuelle. Les en-têtes sont alors supprimés uniquement pour ces URL.
>
>* Activez la règle lorsque vous effectuez une modification dans le compositeur d’expérience visuelle et désactivez la règle lorsque vous ne l’utilisez pas.
>
>Pour l’extension [!UICONTROL Modify Response Header] ([!DNL Firefox]), comme vous ne pouvez pas ajouter de règle d’URL, vous devez effectuer les opérations suivantes :
>
>* Activez la règle lorsque vous effectuez une modification dans le compositeur d’expérience visuelle et désactivez la règle lorsque vous ne l’utilisez pas.

**Pour utiliser l’extension [!DNL Requestly] sur [!DNL Chrome] ou [!DNL Firefox] :**

1. Éteignez la [!UICONTROL Enhanced Experienced Composer].
1. Installez l’extension de navigateur [!DNL Requestly] sur [!DNL Chrome] ou [!DNL Firefox].
1. Ouvrez l’extension et configurez-la de la manière suivante :
1. Sélectionnez **[!UICONTROL Modify headers]**.
1. Saisissez les entrées suivantes :

   * Nom de la règle
   * Règles de modification

      * Basculez le **[!UICONTROL Add]** sur **[!UICONTROL Remove]**.
      * Basculez le **[!UICONTROL Request]** sur **[!UICONTROL Response]**.
      * Saisissez X-Frame-Options en tant que nom d’en-tête.
      * Répétez les étapes précédentes et saisissez « x-frame-options » comme nom d’en-tête.

        >[!NOTE]
        >
        >Les en-têtes manipulés via [!DNL Requestly] respectent la casse.

      * Remplacez **[!UICONTROL Equals]** par **[!UICONTROL Contains]** comme condition de l’URL source et saisissez l’URL de l’activité que vous essayez de charger dans le VEC.

     ![image chrome_extension](assets/chrome_extension.png)

1. Cliquez sur **[!UICONTROL Save]**.

   ![image demandée](assets/requestly.png)

   Vous devriez maintenant pouvoir charger rapidement la page avec le [!UICONTROL Visual Experience Composer].

**Pour utiliser l’extension [!DNL Modify Response Headers] sur [!UICONTROL Firefox]:**

1. Installez le [!UICONTROL Modify Response Headers] sur [!DNL Firefox] et redémarrez le navigateur.
1. Dans vos extensions [!DNL Firefox], sélectionnez l’extension Modifier les en-têtes de réponse .
1. Cliquez sur **[!UICONTROL Preferences]**.
1. Sélectionnez **[!UICONTROL Filter]** dans la liste déroulante [!UICONTROL Action] .
1. Dans le champ [!UICONTROL Header Name] , saisissez : **[!UICONTROL X-Frame-Options]**.
1. Répétez les étapes 4 et 5 pour ajouter un filtre avec **[!UICONTROL x-frame-options]**.
1. Cliquez sur **[!UICONTROL Add]**.
1. Cliquez sur **[!UICONTROL Start]**.

![Extension Firefox &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Après avoir configuré une extension, ouvrez [!DNL Target]. Vos pages doivent maintenant se charger dans le [!UICONTROL Visual Experience Composer], même si le [!UICONTROL Enhanced Experience Composer] est désactivé.

+++

## Ma page ne s’affiche pas dans le compositeur d’expérience visuelle (compositeur d’expérience visuelle uniquement) {#does-not-load}

+++Détails
* La meilleure compatibilité avec le VEC est assurée par la version la plus récente de l’extension : [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Pour vérifier si vous utilisez la dernière version, accédez à [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] puis cliquez sur [!UICONTROL Details].

* Le [!UICONTROL Visual Experience Composer] nécessite la création de bibliothèques pour effectuer des modifications sur la page web. Ces bibliothèques sont incorporées dans la bibliothèque at.js et sont téléchargées par l’extension à partir des serveurs [!DNL Adobe] chaque fois que le compositeur d’expérience visuelle est utilisé.

  L’extension télécharge la bibliothèque at.js, qu’at.js ou les [!DNL Adobe Experience Platform Web SDK] soient déjà inclus dans la page.

  Vérifiez qu’aucune modification non valide n’est ajoutée aux en-têtes at.js configurés dans la section [!UICONTROL Administration] > [!UICONTROL Implementation] .

* Assurez-vous que la page web ne bloque pas les requêtes obligatoires pour le chargement lorsqu’elles sont incorporées dans un iFrame. Cela inclut l’utilisation de directives CSP frame-ancestors ou de code JS personnalisé incorporé dans le site web du client, les balises meta HTML ou l’en-tête x-frame-options.

* Assurez-vous que le code JavaScript de la page web n’interfère pas avec les bibliothèques de création. N’utilisez pas et n’incluez pas de fichiers portant les noms réservés suivants :

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     En outre, le remplacement accidentel de variables ou d’événements définis dans ces fichiers peut entraîner des problèmes avec le compositeur d’expérience visuelle.

* Le navigateur bloque une page non sécurisée d’un site sécurisé.

  Cliquez sur l’icône à gauche de l’URL dans la barre d’adresse du navigateur, puis sur **[!UICONTROL Disable protection on this page]**

* Vous avez tapé une URL incorrecte.
* Si votre site web ne charge pas dans le VEC ou se comporte de manière inattendue, un correctif potentiel consiste à accepter les cookies sur votre site web dans le navigateur avant de tenter de charger le site web dans [!DNL Target].

+++

## Le compositeur d’expérience visuelle semble endommagé lorsque j’utilise le mode [!UICONTROL Browse]. (Compositeur d’expérience visuelle uniquement)  {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

+++Détails
Lors de l’utilisation du mode [!UICONTROL Browse], si vous accédez à une URL pour laquelle aucune bibliothèque [!DNL Target] n’est implémentée ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=fr){target=_blank} ou [Adobe Experience Platform Web SDK](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}) ou qui contient un en-tête frame-buster, le compositeur d’expérience visuelle semble endommagé. En raison de problèmes de sécurité du navigateur, [!DNL Target] ne pouvez pas accéder correctement à l’URL à laquelle vous avez accédé ou l’URL du compositeur d’expérience visuelle n’est pas mise à jour de manière cohérente si la page se charge.

Ce problème se produit, car le compositeur d’expérience visuelle charge la page web dans une `<iframe>`. Les mécanismes de sécurité actuels des navigateurs empêchent l’interface utilisateur [!DNL Target] d’accéder aux éléments de l’image donnée en raison de la politique de même origine. Les navigateurs bloquent les scripts qui tentent d’accéder à une image ayant une origine différente et contenant des informations telles que la `location.href`.

Vous devez utiliser la nouvelle extension [Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) pour injecter la bibliothèque de [!DNL Target] dans les pages afin de les parcourir de manière optimale.

+++

## Problèmes provoqués par les conflits CSS dans le [!UICONTROL Visual Experience Composer]

+++Détails
Vérifiez s’il existe des fichiers CSS susceptibles d’avoir un impact sur la visibilité lors du chargement de la page web dans l’éditeur. Par exemple, l’utilisation de la propriété `overflow: hidden` dans le corps de la page peut entraîner des problèmes de défilement ou déclencher des événements de clic qui peuvent interférer avec le menu de création.

+++
