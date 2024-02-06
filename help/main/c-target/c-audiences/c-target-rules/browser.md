---
keywords: options du navigateur;type;type de navigateur;langue du navigateur;langue;version;version du navigateur
description: Découvrez comment créer des audiences dans [!DNL Adobe Target] pour cibler les utilisateurs qui utilisent un navigateur spécifique ou des options de navigateur spécifiques lorsqu’ils visitent votre page.
title: Puis-je cibler les visiteurs en fonction du type de navigateur ?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 4395caa7e40717c59067eaedff5e53776768eda9
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 36%

---

# Navigateur

Vous pouvez cibler les visiteurs qui utilisent un navigateur spécifique ou des options de navigateur spécifiques lors de l’accès à votre page.

Les navigateurs suivants peuvent être ciblés :

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>à compter du 30 avril 2024, [!DNL iPad] et [!DNL iPhone] est supprimé de la [!UICONTROL Navigateur] type liste déroulante lors de la création de catégories pour les audiences. Pour obtenir des paramètres de contournement, voir [Abandon de l’attribut d’audience iPad et iPhone du navigateur (30 avril 2024)](#deprecation) ci-dessous

Il existe deux façons de cibler les navigateurs :

* **Audience prédéfinie :** Utilisez l’audience prédéfinie si vous souhaitez cibler uniquement les visiteurs qui utilisent un navigateur spécifique pour accéder à votre site. Par exemple, si vous proposez une [!DNL Chrome] extension, vous ne ciblez que [!DNL Chrome] utilisateurs.

   1. Lors de la configuration de votre activité, sélectionnez le navigateur dans la liste déroulante.

      Cette option cible l’activité uniquement pour les visiteurs qui utilisent le navigateur spécifié.

      ![Utilisateurs de Chrome pour Target](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Règle d’audience de navigateur personnalisée :** Une audience personnalisée vous permet de cibler plusieurs navigateurs ou de configurer des règles ou des exclusions pour des navigateurs, des versions de navigateur ou des langues de navigateur spécifiques. Cette fonctionnalité offre une flexibilité considérable lors du ciblage d’une activité basée sur les attributs du navigateur.

   1. Dans le [!DNL Target] interface, cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Création d’une audience]**.
   1. Nommez l’audience et ajoutez une description facultative.
   1. Glisser-déposer **[!UICONTROL Navigateur]** dans le créateur d’audiences.

      ![Règles > Navigateur](assets/target_browser.png)

   1. Cliquez sur **[!UICONTROL Sélectionner]**, puis sélectionnez l’une des options suivantes :

      * **Type :** cibler ou exclure un navigateur spécifique. Voir [Type](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Langue :** Ciblez ou excluez certains navigateurs configurés pour utiliser des langues spécifiques. Voir [Langue](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Version :** cibler ou exclure certaines versions de navigateur. Voir [Version](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
   1. Cliquez sur **[!UICONTROL Done]** (Terminé).

  L’exemple suivant illustre une audience qui comprend [!DNL Microsoft Edge] utilisateurs des versions 91 ou 92 :

  ![Target Edge 91 ou 92](assets/target_edge.png)

## Options de navigateur {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Ciblez ou excluez des participants aux activités en fonction du type, de la langue ou de la version de leur navigateur.

### Type {#section_6ADC758F23F145B3A310151546D83D56}

Ciblez ou excluez un navigateur spécifique.

Sélectionnez **[!UICONTROL Type]**, puis choisissez « est égal à » ou « n’est pas égal à ».

* [!UICONTROL Est égal à]: ciblez les navigateurs sélectionnés.
* [!UICONTROL N’est pas égal à]: exclut les navigateurs sélectionnés.

Sélectionnez un ou plusieurs navigateurs. De nombreuses options sont connectées avec un OU.

### Langue {#section_7520D1AA464A45A6843EABE2D2B431A1}

Ciblez ou excluez certains navigateurs configurés pour utiliser des langues spécifiques.

Par exemple, si une offre n’est disponible qu’en anglais, vous pouvez cibler les navigateurs dont la langue définie est l’anglais. Sinon, si votre page n’est pas compatible avec le format double octet, vous pouvez exclure les navigateurs utilisant les langues d’Asie de l’Est.

L’inclusion ou l’exclusion d’une langue de navigateur peut fournir un ciblage des visiteurs plus précis que le ciblage basé sur la géographie dans les cas où la langue est plus importante que l’emplacement. Par exemple, si vous proposez un article écrit en anglais, vous pouvez soit cibler les pays anglophones, soit cibler les navigateurs dont la langue définie est l’anglais. Le ciblage du navigateur permet aux anglophones vivant dans un pays dont l’anglais n’est pas la langue première de consulter l’article.

Sélectionnez **[!UICONTROL Langue]**, puis choisissez « est égal à » ou « n’est pas égal à ».

* [!UICONTROL Est égal à]: cible les langues de navigateur sélectionnées.
* [!UICONTROL N’est pas égal à]: exclut les langues de navigateur sélectionnées.

Sélectionnez une ou plusieurs langues. De nombreuses options sont connectées avec un OU.

Les langues de navigateur suivantes peuvent être ciblées ou exclues :

* Anglais
* Français
* Allemand
* Japonais
* Coréen
* Portugais
* Russe
* Espagnol
* Chinois traditionnel

### Version {#section_37CC8CE45DA04E8682AE6388321BA6EF}

Ciblez ou excluez certaines versions de navigateur.

Par exemple, si votre page n’apparaît pas correctement dans [!DNL Internet Explorer] version 11 ou antérieure, vous pouvez créer une audience qui exclut ces versions. Dans ce cas, vous configurez une règle où le type de navigateur est égal à [!DNL Internet Explorer] et ajoutez une deuxième règle où la version est inférieure ou égale à 11.

Sélectionnez **[!UICONTROL Version]**, puis choisissez un opérateur :

* [!UICONTROL Est égal]
* [!UICONTROL N’est pas égal à]
* [!UICONTROL Est supérieur à]
* Est supérieur ou égal à
* [!UICONTROL Est inférieur à]
* [!UICONTROL Est inférieur ou égal à]

Saisissez le numéro de version. Seules les versions majeures peuvent être saisies dans le champ de texte. La version spécifiée comprend toutes les versions mineures qui lui sont associées. Par exemple, si vous spécifiez la version 10, les visiteurs de la version 10.1 sont également inclus.

De nombreuses options sont connectées avec un OU.

## Vidéo de formation : création d’audiences ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Obsolescence de l’iPad et de l’iPhone dans l’attribut d’audience Navigateur (30 avril 2024) {#deprecation}

[!DNL Adobe Target] vous permet de [cibler sur l’un des attributs de catégorie les plus courants](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les utilisateurs qui utilisent un navigateur ou des options de navigateur spécifiques lorsqu’ils visitent votre page.

À compter du 30 avril 2024, iPad et iPhone seront retirés de la [!UICONTROL Navigateur] Liste déroulante de type dans la [!DNL Target] de l’interface utilisateur lors de la création de catégories pour les audiences ;

Audiences intégrées créées à l’aide du [!DNL Target] L’interface utilisateur, telle que &quot;Navigateur : iPad&quot; et &quot;Navigateur : iPhone&quot;, sera automatiquement déplacée vers la nouvelle définition d’audience. Cependant, à partir de maintenant, vous devrez utiliser les paramètres [décrit ci-dessous](#ui).

Si vous utilisez `user.browserType` dans les scripts de profil pour vérifier s’il s’agit d’une iPhone ou d’une iPad (par exemple, `user.browserType == 'iphone'` ou `user.browserType != 'ipad'`), ces scripts de profil doivent être modifiés comme suit : [instructions ci-dessous](#profile-scripts) avant le 30 avril 2024 pour s’assurer que ces audiences continuent à fonctionner comme prévu.

Les audiences JavaScript sont des audiences héritées utilisant des expressions Target obsolètes avec le [!DNL Target Classic] Interface utilisateur. Ces audiences peuvent uniquement être modifiées via l’API. Les clients ne doivent mettre à jour ces audiences que s’ils continuent à utiliser des audiences héritées dans les activités.

### Audiences créées à l’aide de la fonction [!DNL Target] Interface utilisateur {#ui}

Les paramètres suivants pourront être utilisés à l’avenir :

* **Pour les correspondances de navigateur[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL correspond à] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Pour la tablette correspondant au navigateur**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![mobile is tablet](/help/main/r-release-notes/assets/is-tablet.png)

* **Pour les correspondances de navigateur avec iPad**: [!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPad] avec un conteneur Et avec [!UICONTROL Mobile] > [!UICONTROL Tablette] is [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Pour les correspondances de navigateur avec iPhone**: [!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPhone] avec un conteneur Et avec [!UICONTROL Mobile] > [!UICONTROL Téléphone mobile] is [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Il existe de nombreux autres paramètres possibles qui peuvent être utilisés, par exemple lorsque des conditions sont annulées. Voici des exemples de conditions négatives :

* **Pour le navigateur ne correspond pas à iPhone**: [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL ne correspond pas à] [!UICONTROL Apple] avec un conteneur Ou avec [!UICONTROL Mobile] > [!UICONTROL Téléphone mobile] is [!UICONTROL false]

  ![Pas de téléphone mobile](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Pour le navigateur ne correspond pas à iPad**: [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL ne correspond pas à] [!UICONTROL Apple] avec un conteneur Ou avec [!UICONTROL Mobile] > [!UICONTROL Tablette] is [!UICONTROL false].

  ![Tablette non](/help/main/r-release-notes/assets/tablet-false.png)

### Audiences créées à l’aide de scripts de profil {#profile-scripts}

Si vous utilisez `user.browserType` dans l’héritage [!DNL Target Classic] audiences ou dans les scripts de profil, les modifications doivent inclure les éléments suivants :

>[!NOTE]
>
>La publication des profils suivants est prévue pour les prochaines semaines, à compter du 24 janvier 2024. La variable [notes de mise à jour actuelles](/help/main/r-release-notes/release-notes.md) sera mis à jour lorsque ces profils seront disponibles.
>
>Ces profils permettent d’effectuer les modifications suivantes :
>
>* `profile.mobile.isTablet`
>
>* `profile.mobile.isMobilePhone`

* **BrowserType est iPhone**:

  Remplacer :

  `user.browserType=="iphone"`

  Avec :

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType n’est pas iPhone**:

  Remplacer :

  `user.browserType!="iphone"`

  Avec :

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType est iPad**:

  Remplacer :

  `user.browserType=="ipad"`

  Avec :

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType n’est pas iPad**:

  Remplacer :

  `user.browserType!="ipad"`

  Avec :

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`