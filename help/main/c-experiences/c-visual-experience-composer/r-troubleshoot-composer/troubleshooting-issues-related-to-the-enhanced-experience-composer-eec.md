---
keywords: Ciblage;compositeur d’expérience avancé;compositeur d’expérience visuelle;dépannage compositeur d’expérience avancé;résolution des problèmes
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans l’Adobe [!DNL Target] Compositeur d’expérience avancé dans certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience avancé ?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 53%

---

# Résolution des problèmes liés au [!UICONTROL Compositeur d’expérience avancé]

Des problèmes d’affichage se produisent parfois dans la variable [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience avancé] (CEE) sous certaines conditions.

## Le compositeur d’expérience avancé ne charge pas une URL AQ interne non accessible sur une adresse IP publique. {#section_D29E96911D5C401889B5EACE267F13CF}

Cela peut être résolu en plaçant sur la liste autorisée les adresses IP suivantes. Ces adresses IP sont destinées au serveur de l’Adobe utilisé pour le proxy du compositeur d’expérience avancé. Elles ne sont requises que pour la modification des activités. Les visiteurs de votre site n’ont pas besoin que ces adresses IP soient placées sur la liste autorisée.

Demandez à votre équipe informatique de placer sur la liste autorisée les adresses IP suivantes :

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

Le message d’erreur suivant peut s’afficher dans [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Voici les raisons pour lesquelles ce message d’erreur s’affiche et les solutions pour corriger la situation :

* **Problème :**[!UICONTROL le domaine de votre site web (FAI) bloque le compositeur d’expérience avancé].

   **Solution :** Placez sur la liste autorisée les adresses IP répertoriées ci-dessus.

* **Problème :** Les adresses IP sont placées sur la liste autorisée, mais votre site web ne prend pas en charge TLS version 1.2. [!DNL Target] utilise actuellement la configuration par défaut de la version 1.2. [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d’informations, voir [Modifications du chiffrement de TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

   **Solution :**[!UICONTROL voir la question : Le compositeur d’expérience visuelle avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.2.]

## Le compositeur d’expérience avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.0. (Compositeur d’expérience avancé uniquement)  {#section_C5B31E3D32A844F68E5A8153BD17551F}

Le message d’erreur décrit ci-dessus peut s’afficher dans la section &quot;The [!UICONTROL Compositeur d’expérience visuelle amélioré] ne se chargera pas sur les pages sécurisées de mon site.&quot; si les adresses IP ci-dessus sont placées sur la liste autorisée mais que votre site web ne prend pas en charge TLS version 1.2. [!DNL Target] utilise actuellement la configuration par défaut de la version 1.2. [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d’informations, voir [Modifications du chiffrement de TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

Pour vérifier la version TLS de votre site web en utilisant Firefox (les autres navigateurs suivent des étapes similaires) :

1. Ouvrez le site web concerné dans Firefox.
1. Cliquez sur l’icône **[!UICONTROL Afficher les informations du site]** dans la barre d’adresse du navigateur.

   ![](assets/firefox_more_info.png)

1. Cliquez sur **[!UICONTROL Afficher les détails de la connexion]** > **[!UICONTROL Plus d’informations]**.

   ![](assets/firefox_more_info_2.png)

1. Examinez les informations de version TLS dans l’option Détails techniques :

   ![](assets/firefox_more_info_3.png)

1. Si vous constatez que votre site web affiche TLS 1.0, reportez-vous à [Modifications du chiffrement de TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/) pour obtenir des informations sur la politique de prise en charge de TLS de Target. Pour remédier à la situation (valable jusqu’au 12 septembre 2018), contactez le [Service d’assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir la configuration avec votre version TLS et du domaine.

## Je reçois des messages de délai d’expiration ou des erreurs « accès refusé » lors du chargement de sites où un serveur proxy est activé. (Compositeur d’expérience avancé uniquement)  {#section_60CBB9022DC449F593606C0E6252302D}

Assurez-vous que les adresses IP du serveur proxy ne sont pas bloquées dans votre environnement.
