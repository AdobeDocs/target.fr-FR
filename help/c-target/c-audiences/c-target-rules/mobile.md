---
keywords: ciblage;mobile;mobile target;deviceatlas;iphone;modèles d’iphone;device atlas;largeur d’affichage;largeur d’affichage;hauteur d’affichage;type d’appareil;hauteur d’affichage;téléphone;tablette;modèle d’appareil
description: Découvrez comment créer des audiences dans Adobe Target pour cible des périphériques mobiles en fonction de paramètres tels que les périphériques mobiles, le type de périphérique, le fournisseur de périphérique, les dimensions d’écran (en pixels), etc.
title: Puis-je Cible des Visiteurs en fonction des options mobiles ?
feature: Audiences
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 93%

---


# Mobile{#mobile}

Création d’audiences pour cibler les périphériques mobiles basés sur des paramètres tels que le périphérique mobile, le type de périphérique, le fournisseur du périphérique, les dimensions de l’écran (en pixels), etc.

Par exemple, vous souhaitez peut-être afficher un contenu différent aux utilisateurs qui visitent votre page depuis un téléphone par rapport aux utilisateurs qui la visitent depuis un ordinateur. Dans ce cas, vous pouvez sélectionner l’audience Mobile, puis l’option **[!UICONTROL Téléphone mobile]**, et ajouter tous les détails spécifiques qui vous semblent importants tels que le type de téléphone, la taille de l’écran (en pixels), etc.

Le ciblage mobile est fourni par [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), un service de DotMobi. DeviceAtlas est une base de données complète de périphériques mobiles créée à partir des données compilées provenant de nombreuses sources, dont les fabricants et les opérateurs réseau. Ces données sont alors vérifiées, référencées et validées pour mettre à disposition une importante base de données des périphériques mobiles.

Les périphériques sont détectés en analysant les chaînes d’agent-utilisateur. Certains fabricants de périphériques, notamment Apple, inhibent cette fonctionnalité en ne fournissant pas suffisamment d’informations dans l’agent-utilisateur.

Par exemple, aux États-Unis, les appareils Apple ne partagent pas de jetons spécifiques aux modèles. Il n’est alors pas possible de détecter les modèles d’iPhone (iPhone 5S, iPhone SE, iPhone 6, etc.) en appliquant une méthode simple fondée sur les mots-clés.

Pour résoudre ce problème, Target collecte des données supplémentaires afin de détecter précisément les iPhone et autres appareils Apple à l’aide des paramètres suivants :

| Paramètre | Type | Description |
|--- |--- |--- |
| devicePixelRatio | Chaîne | Rapport entre les pixels physiques et les pixels indépendants de l’appareil (dips) sur le navigateur. Par exemple « 1,5 » ou « 2 » |
| screenOrientation | Chaîne | L’appareil et le moteur JavaScript du navigateur prennent en charge l’orientation d’appareil. Peut être Paysage ou Portrait. |
| webGLRenderer | Chaîne | Rendu de navigateur du pilote graphique. |

>[!NOTE]
>
>Les clients utilisant le SDK mobile n’ont aucune mesure à prendre pour exploiter cette fonctionnalité. Les clients utilisant at.js doivent [procéder à une mise à niveau vers at.js version 1.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) (ou version ultérieure).

Vous pouvez choisir plusieurs propriétés d’appareil mobile. Les sélections multiples sont jointes par l’opérateur OU.

Les clients qui utilisent une intégration personnalisée (n’utilisant pas at.js ou le SDK mobile) peuvent collecter ces paramètres eux-mêmes et les transmettre en tant que paramètres mbox.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Cliquez sur **[!UICONTROL Ajouter une règle]** > **[!UICONTROL Mobile]**.
1. Cliquez sur **[!UICONTROL Sélectionner]**, puis sélectionnez l’une des options suivantes :

   * Nom marketing du périphérique
   * Modèle de périphérique
   * Fournisseur de périphérique
   * Appareil mobile
   * Téléphone mobile
   * Tablette
   * Système d’exploitation
   * Hauteur de l’écran (px)
   * Largeur de l’écran (px)

   >[!NOTE]
   >
   >En raison des nouvelles modifications introduites dans iOS 12.2, la création d’une audience avec des règles définies par le nom marketing du périphérique et le modèle du périphérique qui spécifient les modèles iPhone est affectée. Nous ne pouvons plus cibler les utilisateurs qui disposent d’iOS 12.2 sur leur iPhone. Toutefois, si ces utilisateurs ne disposent pas d’iOS 12.2, le ciblage du modèle iPhone continue de fonctionner correctement.
   >
   >La mise à jour iOS 12.2 n’a aucune incidence sur l’identification des modèles suivants, car ces modèles ne prennent pas en charge la mise à niveau vers iOS 12.2 : iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad, iPad 2, iPad/Retina display, iPad Retina (4ème Gen), iPod Touch 4, et iPod Touch 5.

   >[!NOTE]
   >
   >Vous pouvez effectuer un ciblage selon l’opérateur de téléphonie mobile à l’aide des [paramètres de géolocalisation](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

L’illustration suivante montre une audience ciblant les visiteurs qui utilisent des appareils fabriqués par Google et qui sont des périphériques mobiles.

![Ciblage de périphériques mobiles](assets/target_mobile.png)

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
