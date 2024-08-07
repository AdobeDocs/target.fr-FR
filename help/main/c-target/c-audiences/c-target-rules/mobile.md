---
keywords: ciblage;mobile;mobile target;deviceatlas;iphone;modèles d’iphone;device atlas;largeur d’affichage;largeur d’affichage;hauteur d’affichage;type d’appareil;hauteur d’affichage;téléphone;tablette;modèle d’appareil
description: Découvrez comment créer des audiences dans  [!DNL Adobe Target]  pour cibler des appareils mobiles.
title: Puis-je cibler les visiteurs en fonction des options mobiles ?
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 34%

---

# Mobile

Créez des audiences dans [!DNL Adobe Target] pour cibler les périphériques mobiles en fonction de paramètres tels que le périphérique mobile, le type de périphérique, le fournisseur du périphérique, les dimensions de l’écran, etc.

Par exemple, vous souhaitez peut-être afficher un contenu différent aux utilisateurs qui visitent votre page à l’aide d’un téléphone que s’ils la visitent à l’aide d’un ordinateur. Dans ce cas, vous pouvez sélectionner l’audience [!UICONTROL Mobile], puis l’option **[!UICONTROL Is Mobile Phone]**. Vous pouvez ensuite ajouter les détails spécifiques qui vous semblent importants, tels que le type de téléphone, la taille de l’écran (en pixels), etc.

Le ciblage mobile est fourni par [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), un service de DotMobi. DeviceAtlas est une base de données complète de périphériques mobiles créée à partir des données compilées provenant de nombreuses sources, dont les fabricants et les opérateurs réseau. Ces données sont alors vérifiées, référencées et validées pour mettre à disposition une importante base de données des périphériques mobiles.

Les périphériques sont détectés en analysant les chaînes d’agent-utilisateur. Certains fabricants de périphériques, notamment Apple, inhibent cette fonctionnalité en ne fournissant pas suffisamment d’informations dans l’agent-utilisateur.

Par exemple, aux États-Unis, les appareils Apple ne partagent pas de jetons spécifiques aux modèles. En conséquence, il n’est pas possible de détecter les modèles iPhone (tels qu’iPhone 12 Pro, iPhone 12, iPhone 11 Pro Max, etc.) à l’aide d’une méthode simple basée sur les mots-clés.

Pour résoudre ce problème, [!DNL Target] collecte des données supplémentaires afin de détecter avec précision les iPhone et autres appareils Apple à l’aide des paramètres suivants :

| Paramètre | Type | Description |
|--- |--- |--- |
| devicePixelRatio | Chaîne | Rapport entre les pixels physiques et les pixels indépendants de l’appareil (dips) sur le navigateur. Par exemple, &quot;1.5&quot; ou &quot;2&quot; |
| screenOrientation | Chaîne | L’appareil et le moteur JavaScript du navigateur prennent en charge l’orientation d’appareil. Peut être Paysage ou Portrait. |
| webGLRenderer | Chaîne | Rendu de navigateur du pilote graphique. |

>[!NOTE]
>
>Les clients qui utilisent le SDK Mobile n’ont rien à faire pour appliquer cette fonctionnalité. Les clients qui utilisent at.js doivent [mettre à niveau vers at.js version 1.5.0](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} (ou ultérieure).

Vous pouvez choisir plusieurs propriétés d’appareil mobile. Plusieurs sélections sont unies par un opérateur OU.

Les clients qui utilisent une intégration personnalisée (n’utilisant pas at.js ou le SDK mobile) peuvent collecter ces paramètres eux-mêmes et les transmettre en tant que paramètres mbox.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Faites glisser **[!UICONTROL Mobile]** dans le volet du créateur d’audiences.
1. Cliquez sur **[!UICONTROL Select]**, puis sélectionnez l’une des options suivantes :

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
   >Vous pouvez effectuer un ciblage selon l’opérateur de téléphonie mobile à l’aide des [paramètres de géolocalisation](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670).

1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Done]**.

L’illustration suivante présente une audience ciblant les visiteurs qui utilisent des appareils fabriqués par Google et qui sont des appareils mobiles.

![Ciblage d’appareils mobiles](assets/target_mobile.png)

## Considérations

Tenez compte des informations suivantes lors du ciblage des périphériques mobiles :

### Ciblage des périphériques exécutant iOS 12.2 ou une version ultérieure

En raison des nouvelles modifications introduites dans iOS 12.2, la création d’une audience avec des règles définies par [!UICONTROL Device Marketing Name] et [!UICONTROL Device Model] qui spécifient les modèles iPhone est affectée. [!DNL Target] ne peut plus cibler les utilisateurs pour lesquels des iPhone avec iOS 12.2 (ou version ultérieure) sont installés. Cependant, si ces utilisateurs ne disposent pas d’iOS 12.2 (ou version ultérieure), le ciblage du modèle iPhone continue de fonctionner correctement.

La mise à jour d’iOS 12.2 (ou version ultérieure) n’a aucune incidence sur l’identification des modèles suivants, car ces modèles ne prennent pas en charge la mise à niveau vers iOS 12.2 : iPhone, iPhone 3G, iPhone 3GS, iPhone 4, iPhone 4s, iPhone 5, iPhone 5c, iPad 2, affichage/Retina, Retina (4e génération), iPod 4 et iPod Touch 5.

### Ciblage des périphériques exécutant Safari 14.0.2 (ou version ultérieure)

Lors de l’utilisation de règles mobiles pour cibler des appareils exécutant Safari version 14.0.2 (ou ultérieure) sur macOS, en raison d’un problème connu impliquant des agents utilisateur Apple et DeviceAtlas, [!DNL Target] identifie de manière incorrecte Safari sur les appareils Mac et iPad. Cette question sera abordée à l’avenir.

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
