---
keywords: options du navigateur;type;type de navigateur;langue du navigateur;langue;version;version du navigateur
description: Découvrez comment créer des audiences dans [!DNL Adobe Target] pour cibler les utilisateurs qui utilisent un navigateur spécifique ou des options de navigateur spécifiques lorsqu’ils visitent votre page.
title: Puis-je cibler les visiteurs en fonction du type de navigateur ?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 335b5eaa9240fb4ecc592063bebd3ba977fb8d6e
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 53%

---

# Navigateur

Vous pouvez cibler les visiteurs qui utilisent un navigateur spécifique ou des options de navigateur spécifiques lors de l’accès à votre page.

Les navigateurs suivants peuvent être ciblés :

* Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad 
* iPhone

>[!IMPORTANT]
>
>À compter du 30 avril 2024, iPad et iPhone seront retirés de la [!UICONTROL Navigateur] type liste déroulante lors de la création de catégories pour les audiences. Pour obtenir des paramètres de contournement, voir [Abandon de l’attribut d’audience iPad et iPhone du navigateur (30 avril 2024)](#deprecation) ci-dessous

Il existe deux façons de cibler les navigateurs :

* **Audience prédéfinie :** Utilisez l’audience prédéfinie si vous souhaitez cibler uniquement les visiteurs qui utilisent un navigateur spécifique pour accéder à votre site. Par exemple, si vous proposez une extension Chrome, vous ne ciblerez que les utilisateurs de Chrome.

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

  L’exemple suivant illustre une audience qui inclut les utilisateurs de Microsoft Edge sur les versions 91 ou 92 :

  ![Target Edge 91 ou 92](assets/target_edge.png)

## Options de navigateur {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Ciblez ou excluez des participants aux activités en fonction du type, de la langue ou de la version de leur navigateur.

### Type {#section_6ADC758F23F145B3A310151546D83D56}

Ciblez ou excluez un navigateur spécifique.

Sélectionnez **[!UICONTROL Type]**, puis choisissez « est égal à » ou « n’est pas égal à ».

* Est égal à : cible les navigateurs sélectionnés.
* N’est pas égal à : exclut les navigateurs sélectionnés.

Sélectionnez un ou plusieurs navigateurs. De nombreuses options sont connectées avec un OU.

### Langue {#section_7520D1AA464A45A6843EABE2D2B431A1}

Ciblez ou excluez certains navigateurs configurés pour utiliser des langues spécifiques.

Par exemple, si une offre n’est disponible qu’en anglais, vous pouvez cibler les navigateurs dont la langue définie est l’anglais. Sinon, si votre page n’est pas compatible avec le format double octet, vous pouvez exclure les navigateurs utilisant les langues d’Asie de l’Est.

L’inclusion ou l’exclusion d’une langue de navigateur peut fournir un ciblage des visiteurs plus précis que le ciblage basé sur la géographie dans les cas où la langue est plus importante que l’emplacement. Par exemple, si vous proposez un article écrit en anglais, vous pouvez soit cibler les pays anglophones, soit cibler les navigateurs dont la langue définie est l’anglais. Le ciblage du navigateur permet aux anglophones vivant dans un pays dont l’anglais n’est pas la langue première de consulter l’article.

Sélectionnez **[!UICONTROL Langue]**, puis choisissez « est égal à » ou « n’est pas égal à ».

* Est égal à : cible les langues de navigateur sélectionnées.
* N’est pas égal à : exclut les langues de navigateur sélectionnées.

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

Par exemple, si votre page ne s’affiche pas correctement dans Internet Explorer version 11 ou antérieure, vous pouvez créer une audience qui exclut ces versions. Dans ce cas, vous devez créer une règle où le type de navigateur est égal à Internet Explorer puis ajouter une seconde règle où la version est inférieure ou égale à 11.

Sélectionnez **[!UICONTROL Version]**, puis choisissez un opérateur :

* Est égal
* N’est pas égal à
* Est supérieur à
* Est supérieur ou égal à
* Est inférieur à
* Est inférieur ou égal à

Saisissez le numéro de version. Seules les versions majeures peuvent être saisies dans le champ de texte. La version spécifiée comprend toutes les versions mineures qui lui sont associées. Par exemple, si vous spécifiez la version 10, les visiteurs de la version 10.1 sont également inclus.

De nombreuses options sont connectées avec un OU.

## Vidéo de formation : création d’audiences ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Abandon de l’attribut d’audience iPad et iPhone du navigateur (30 avril 2024) {#deprecation}

[!DNL Adobe Target] vous permet de [cibler sur l’un des attributs de catégorie les plus courants](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les utilisateurs qui utilisent un navigateur ou des options de navigateur spécifiques lorsqu’ils visitent votre page.

À compter du 30 avril 2024, iPad et iPhone seront retirés de la [!UICONTROL Navigateur] type liste déroulante lors de la création de catégories pour les audiences.

Si des audiences ciblent des iPad ou des iPhones à l’aide de la variable [!UICONTROL Navigateur] , vous devez modifier ces paramètres avant le 30 avril 2024 pour vous assurer que ces audiences continuent à fonctionner comme prévu.

Les paramètres suivants pourront être utilisés à l’avenir :

* [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL correspond à] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![mobile est une tablette](/help/main/r-release-notes/assets/is-tablet.png)

* [!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPad] avec un conteneur Et avec [!UICONTROL Mobile] > [!UICONTROL Tablette] is [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* [!UICONTROL Mobile] > [!UICONTROL Nom marketing du périphérique] [!UICONTROL correspond à] [!DNL iPhone] avec un conteneur Et avec [!UICONTROL Mobile] > [!UICONTROL Téléphone mobile] is [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Il existe de nombreux autres paramètres possibles qui peuvent être utilisés, par exemple lorsque des conditions sont annulées. Voici des exemples de conditions négatives :

* [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL ne correspond pas à] [!UICONTROL Apple] avec un conteneur Ou avec [!UICONTROL Mobile] > [!UICONTROL Téléphone mobile] is [!UICONTROL false]

  ![Pas de téléphone mobile](/help/main/r-release-notes/assets/mobile-phone-false.png)

* [!UICONTROL Mobile] > [!UICONTROL Fournisseur de périphérique] [!UICONTROL ne correspond pas à] [!UICONTROL Apple] avec un conteneur Ou avec [!UICONTROL Mobile] > [!UICONTROL Tablette] is [!UICONTROL false].

  ![Tablette non](/help/main/r-release-notes/assets/tablet-false.png)

Si vous utilisez `user.browserType` dans les segments JavaScript, les modifications peuvent inclure les éléments suivants :

* BrowserType est iPhone

  Remplacer :

  `user.browserType=="iphone"`

  Avec :

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("iphone")`

* BrowserType n’est pas iPhone

  Remplacer :

  `user.browserType!="iphone"`

  Avec :

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("iphone")`

* BrowserType est iPad

  Remplacer :

  `user.browserType=="ipad"`

  Avec :

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("ipad")`

* BrowserType n’est pas iPad

  Remplacer :

  `user.browserType!="ipad"`

  Avec :

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("ipad")`