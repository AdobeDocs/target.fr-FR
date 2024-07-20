---
keywords: Ciblage;compositeur d’expérience visuelle;vec;dépannage du compositeur d’expérience visuelle;dépannage;tls;tls 1.2
description: Découvrez comment résoudre les problèmes dans le [!UICONTROL Visual Experience Composer] (VEC).
title: Comment résoudre les problèmes liés à [!UICONTROL Visual Experience Composer] ?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 24%

---

# Résolution des problèmes liés à [!UICONTROL Visual Experience Composer]

Dans certains cas, des problèmes d’affichage se produisent parfois dans le [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

## Lorsque j’ouvre mon site web dans [!UICONTROL Visual Experience Composer], les bibliothèques [!DNL Target] ne se chargent pas. (Compositeur d’expérience visuelle uniquement)  {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] ajoute deux paramètres (`mboxEdit=1` et `mboxDisable=1`) lors de l’ouverture du site web dans [!UICONTROL Visual Experience Composer].

Si votre site web (en particulier les applications monopage) supprime les paramètres ou les supprime réellement lors de la navigation d’une page à une autre (sans rechargement de page), la fonctionnalité [!DNL Target] est rompue et les bibliothèques [!DNL Target] ne se chargent pas.

Pour éviter ce problème, assurez-vous de ne pas supprimer ces deux paramètres.

## Ma page ne s’ouvre pas dans le compositeur d’expérience avancé ou elle se charge lentement. Les activités ou les expériences se chargent lentement dans le compositeur d’expérience visuelle. (Compositeur d’expérience visuelle uniquement)  {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Plusieurs problèmes peuvent affecter les performances des pages dans les compositeurs d’expérience [!UICONTROL Target]. Les problèmes courants sont les suivants :

* La page ne contient pas de mbox.
* Votre site utilise le blocage par proxy, ce qui ne permet pas à la page d’être ouverte dans les compositeurs d’expérience.
* Votre site n’est pas autorisé à être ouvert dans une iFrame.

Si des problèmes se produisent dans l’élément [!UICONTROL Enhanced Experience Composer], désactivez l’élément [!UICONTROL Enhanced Experience Composer] et utilisez plutôt l’élément [!UICONTROL Visual Experience Composer] .

Pour désactiver [!UICONTROL Enhanced Experience Composer], accédez à **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** et désactivez l’option **[!UICONTROL Enable Enhanced Experience Composer]**.

Le message d’erreur suivant s’affiche dans la console pour certains utilisateurs :

![Message d’erreur de la console](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Si [!UICONTROL Visual Experience Composer] et [!UICONTROL Enhanced Experience Composer] ne fonctionnent pas, utilisez une extension de navigateur telle que [!DNL Requestly] ([!DNL Chrome] ou [!DNL Firefox]) ou Modify Response Headers (Firefox) qui peut remplacer les options d’en-tête X-Frames de votre site et leur permettre d’être chargées dans les iFrames, en activant le VEC. Si vous ne pouvez pas utiliser les extensions de navigateur, utilisez le [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Outre les informations suivantes, vous pouvez utiliser l’ [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) pour [!DNL Google Chrome].


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

1. Désactivez le [!UICONTROL Enhanced Experienced Composer].
1. Installez l’extension de navigateur [!DNL Requestly] sur [!DNL Chrome] ou [!DNL Firefox].
1. Ouvrez l’extension et configurez-la de la manière suivante :
1. Sélectionnez **[!UICONTROL Modify headers]**.
1. Saisissez les entrées suivantes :

   * Nom de la règle
   * Règles de modification

      * Basculez de **[!UICONTROL Add]** vers **[!UICONTROL Remove]**.
      * Basculez de **[!UICONTROL Request]** vers **[!UICONTROL Response]**.
      * Saisissez X-Frame-Options en tant que nom d’en-tête.
      * Répétez les étapes précédentes et saisissez « x-frame-options » comme nom d’en-tête.

        >[!NOTE]
        >
        >Les en-têtes manipulés via [!DNL Requestly] sont sensibles à la casse.

      * Remplacez **[!UICONTROL Equals]** par **[!UICONTROL Contains]** comme condition pour l’URL source et saisissez l’URL de l’activité que vous essayez de charger dans le VEC.

     ![image chrome_extension](assets/chrome_extension.png)

1. Cliquez sur **[!UICONTROL Save]**.

   ![requestly image](assets/requestly.png)

   Vous devriez maintenant pouvoir charger la page rapidement avec le [!UICONTROL Visual Experience Composer].

**Pour utiliser l’extension [!DNL Modify Response Headers] sur [!UICONTROL Firefox] :**

1. Installez le [!UICONTROL Modify Response Headers] sur [!DNL Firefox] et redémarrez le navigateur.
1. Dans vos extensions [!DNL Firefox], sélectionnez l’extension Modify Response Headers.
1. Cliquez sur **[!UICONTROL Preferences]**.
1. Sélectionnez **[!UICONTROL Filter]** dans la liste déroulante [!UICONTROL Action].
1. Dans le champ [!UICONTROL Header Name], saisissez : **[!UICONTROL X-Frame-Options]**.
1. Répétez les étapes 4 et 5 pour ajouter un filtre avec **[!UICONTROL x-frame-options]**.
1. Cliquez sur **[!UICONTROL Add]**.
1. Cliquez sur **[!UICONTROL Start]**.

![Extension Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Après avoir configuré une extension, ouvrez [!DNL Target]. Vos pages doivent désormais se charger dans le [!UICONTROL Visual Experience Composer], même si l’option [!UICONTROL Enhanced Experience Composer] est désactivée.

## Ma page ne s’affiche pas dans le compositeur d’expérience visuelle (compositeur d’expérience visuelle uniquement) {#does-not-load}

* La meilleure compatibilité avec le VEC est assurée par la dernière version de l’extension : [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Pour vérifier si vous utilisez la dernière version, accédez à [!UICONTROL Extensions] > [!UICONTROL Manage Extensions], puis cliquez sur [!UICONTROL Details].

* [!UICONTROL Visual Experience Composer] nécessite des bibliothèques de création pour effectuer des modifications sur la page web. Ces bibliothèques sont intégrées à la bibliothèque at.js et sont téléchargées par l’extension à partir des serveurs [!DNL Adobe] chaque fois que le VEC est utilisé.

  L’extension télécharge la bibliothèque at.js que at.js ou [!DNL Adobe Experience Platform Web SDK] soient déjà inclus dans la page.

  Vérifiez qu’aucune modification non valide n’a été ajoutée aux en-têtes at.js configurés dans la section [!UICONTROL Administration] > [!UICONTROL Implementation] .

* Assurez-vous que la page web ne bloque pas les requêtes obligatoires pour le chargement lorsqu’elle est incorporée dans un iFrame. Cela inclut l’utilisation de directives CSP de frame-ancestors ou de code JS personnalisé incorporé dans le site web du client, les balises meta HTML ou l’en-tête x-frame-options.

* Assurez-vous que le code JavaScript de la page web n’interfère pas avec les bibliothèques de création. N’utilisez pas ou n’incluez pas de fichiers utilisant les noms réservés suivants :

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     En outre, le remplacement accidentel de variables ou d’événements définis dans ces fichiers peut entraîner des problèmes avec le compositeur d’expérience visuelle.

* Le navigateur bloque une page non sécurisée d’un site sécurisé.

  Cliquez sur l’icône située à gauche de l’URL dans la barre d’adresse du navigateur, puis cliquez sur **[!UICONTROL Disable protection on this page]**.

* Vous avez tapé une URL incorrecte.
* Si le chargement de votre site web échoue dans le VEC ou se comporte de manière inattendue, un correctif potentiel consiste à accepter les cookies de votre site web dans le navigateur avant de tenter de charger le site web dans [!DNL Target].

## Le compositeur d’expérience visuelle semble rompu lorsque j’utilise le mode de navigation. (Compositeur d’expérience visuelle uniquement)  {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Lors de l’utilisation du mode de navigation, si vous accédez à une URL pour laquelle [!DNL Target] bibliothèques n’ont pas été implémentées ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=fr){target=_blank} ou [SDK Web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank}) ou si vous avez un en-tête de propagation d’images, le VEC apparaît rompu. En raison de problèmes de sécurité du navigateur, [!DNL Target] ne peut pas accéder correctement à l’URL à laquelle vous avez accédé ou l’URL du VEC ne se met pas à jour de manière cohérente si la page se charge.

Ce problème se produit car le VEC charge la page web dans un `<iframe>`. Les mécanismes de sécurité actuels des navigateurs empêchent l’interface utilisateur [!DNL Target] d’accéder aux éléments du cadre donné en raison de la stratégie de même origine. Les navigateurs bloquent les scripts qui tentent d’accéder à un cadre d’une origine différente et qui contient des informations telles que le `location.href`.

Vous devez utiliser la nouvelle [extension Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (recommandée) ou l’ [ancienne extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) pour injecter la bibliothèque [!DNL Target] dans les pages afin de les parcourir de manière optimale.

## Problèmes provoqués par les conflits CSS dans le [!UICONTROL Visual Experience Composer]

Vérifiez si des fichiers CSS peuvent avoir un impact sur la visibilité lors du chargement de la page web dans l’éditeur. Par exemple, l’utilisation de la propriété `overflow: hidden` sur le corps de la page peut entraîner des problèmes de défilement ou déclencher des événements de clic qui peuvent interférer avec le menu de création.
