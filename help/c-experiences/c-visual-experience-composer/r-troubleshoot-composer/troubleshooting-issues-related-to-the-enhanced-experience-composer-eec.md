---
keywords: Ciblage;compositeur d’expérience avancé;compositeur d’expérience visuelle;dépannage compositeur d’expérience avancé;résolution des problèmes
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans l’Adobe [!DNL Target] Compositeur d’expérience amélioré (CEE) dans certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience amélioré ?
feature: Compositeur d’expérience visuelle (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
translation-type: tm+mt
source-git-commit: 28e21ea0b0e2306a54c9353ae57de7de5d94f564
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 61%

---

# Résolution des problèmes liés au compositeur d’expérience amélioré

Des problèmes d’affichage se produisent parfois dans le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience amélioré] (CEE) dans certaines conditions.

## Le compositeur d’expérience avancé ne charge pas une URL AQ interne non accessible sur une adresse IP publique. (Compositeur d’expérience avancé uniquement) {#section_D29E96911D5C401889B5EACE267F13CF}

Vous pouvez y remédier en plaçant sur la liste autorisée les adresses IP suivantes. Ces adresses IP sont destinées au serveur Adobe utilisé pour le proxy du compositeur d’expérience avancé. Elles ne sont requises que pour la modification des activités. Les visiteurs de votre site n&#39;ont pas besoin de ces adresses IP placées sur la liste autorisée

Demandez à votre équipe informatique de placer sur la liste autorisée les adresses IP suivantes :

* 52,16,72,74
* 52,5.174,79
* 54 246 238,65
* 54 249 183 154
* 54.65.105.214
* 54,82,142,68

Le message d’erreur suivant peut s’afficher dans Target :

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Voici les raisons pour lesquelles ce message d’erreur s’affiche et les solutions pour corriger la situation :

* **Problème :** le domaine de votre site web (FAI) bloque le compositeur d’expérience avancé.

   **Solution :** Placez sur la liste autorisée les adresses IP répertoriées ci-dessus.

* **Problème :** Les adresses IP sont placées sur la liste autorisée mais votre site Web ne prend pas en charge TLS version 1.2. La Cible utilise actuellement la configuration par défaut de 1.2. Avant la Cible 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d&#39;informations, voir Modifications [ du chiffrement ](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)TLS (Transport Layer Security).

   **Solution :** voir la question : Le compositeur d’expérience visuelle avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.2.

## Le compositeur d’expérience avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.0. (Compositeur d’expérience avancé uniquement) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Le message d’erreur décrit ci-dessus dans « Le compositeur d’expérience visuelle avancé ne se charge pas sur les pages sécurisées de mon site » peut s’afficher si les adresses IP ci-dessus sont placées sur la liste autorisée mais que votre site Web ne prend pas en charge TLS version 1.2. La Cible utilise actuellement la configuration par défaut de 1.2. Avant la Cible 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d&#39;informations, voir [TLS (Transport Layer Security) Encryption Changes](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Pour vérifier la version TLS de votre site web en utilisant Firefox (les autres navigateurs suivent des étapes similaires) :

1. Ouvrez le site web concerné dans Firefox.
1. Cliquez sur l’icône **[!UICONTROL Afficher les informations du site]** dans la barre d’adresse du navigateur.

   ![](assets/firefox_more_info.png)

1. Cliquez sur **[!UICONTROL Afficher les détails de la connexion]** > **[!UICONTROL Plus d’informations]**.

   ![](assets/firefox_more_info_2.png)

1. Examinez les informations de version TLS dans l’option Détails techniques :

   ![](assets/firefox_more_info_3.png)

1. Si vous constatez que votre site web affiche TLS 1.0, reportez-vous à [Modifications du chiffrement de TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) pour obtenir des informations sur la politique de prise en charge de TLS de Target. Pour remédier à la situation (valable jusqu’au 12 septembre 2018), contactez le [Service d’assistance clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir la configuration avec votre version TLS et du domaine.

## Je reçois des messages de délai d’expiration ou des erreurs « accès refusé » lors du chargement de sites où un serveur proxy est activé. (Compositeur d’expérience avancé uniquement) {#section_60CBB9022DC449F593606C0E6252302D}

Assurez-vous que les adresses IP du serveur proxy ne sont pas bloquées dans votre environnement.
