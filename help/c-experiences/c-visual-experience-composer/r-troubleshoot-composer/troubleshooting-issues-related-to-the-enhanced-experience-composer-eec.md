---
keywords: Ciblage;compositeur d’expérience avancé;compositeur d’expérience visuelle;dépannage compositeur d’expérience avancé;résolution des problèmes
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans l’Adobe [!DNL Target] Compositeur d’expérience amélioré (CEE) dans certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience amélioré ?
feature: 'Compositeur d’expérience visuelle (VEC) '
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 53%

---

# Résolution des problèmes liés au [!UICONTROL compositeur d’expérience amélioré]

Des problèmes d’affichage se produisent parfois dans le [!DNL Adobe Target] [!UICONTROL compositeur d’expérience amélioré] (CEE) dans certaines conditions.

## Le compositeur d’expérience avancé ne charge pas une URL AQ interne non accessible sur une adresse IP publique. {#section_D29E96911D5C401889B5EACE267F13CF}

Vous pouvez y remédier en plaçant sur la liste autorisée les adresses IP suivantes. Ces adresses IP sont destinées au serveur d&#39;Adobe utilisé pour le proxy CEE. Elles ne sont requises que pour la modification des activités. Les visiteurs de votre site n’ont pas besoin que ces adresses IP soient placées sur la liste autorisée.

Demandez à votre équipe informatique de placer sur la liste autorisée les adresses IP suivantes :

* 52.55.99.45
* 52.51.238.221
* 52.193.67.35

Le message d’erreur suivant peut s’afficher dans [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Voici les raisons pour lesquelles ce message d’erreur s’affiche et les solutions pour corriger la situation :

* **Problème :**[!UICONTROL le domaine de votre site web (FAI) bloque le compositeur d’expérience avancé].

   **Solution :** Placez sur la liste autorisée les adresses IP répertoriées ci-dessus.

* **Problème :** Les adresses IP sont placées sur la liste autorisée mais votre site Web ne prend pas en charge TLS version 1.2.  [!DNL Target] utilise actuellement la configuration par défaut de 1.2. Avant la version  [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d&#39;informations, voir Changements [ ](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) de chiffrement TLS (Transport Layer Security).

   **Solution :**[!UICONTROL voir la question : Le compositeur d’expérience visuelle avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.2.]

## Le compositeur d’expérience avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.0. (Compositeur d’expérience avancé uniquement)  {#section_C5B31E3D32A844F68E5A8153BD17551F}

Le message d’erreur décrit ci-dessus dans &quot;Le [!UICONTROL compositeur d’expérience visuelle amélioré] ne se charge pas sur les pages sécurisées de mon site.&quot; si les adresses IP ci-dessus sont placées sur la liste autorisée mais que votre site Web ne prend pas en charge TLS version 1.2. [!DNL Target] utilise actuellement la configuration par défaut de 1.2. Avant [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d&#39;informations, voir [TLS (Transport Layer Security) Encryption Changes](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Pour vérifier la version TLS de votre site web en utilisant Firefox (les autres navigateurs suivent des étapes similaires) :

1. Ouvrez le site web concerné dans Firefox.
1. Cliquez sur l’icône **[!UICONTROL Afficher les informations du site]** dans la barre d’adresse du navigateur.

   ![](assets/firefox_more_info.png)

1. Cliquez sur **[!UICONTROL Afficher les détails de la connexion]** > **[!UICONTROL Plus d’informations]**.

   ![](assets/firefox_more_info_2.png)

1. Examinez les informations de version TLS dans l’option Détails techniques :

   ![](assets/firefox_more_info_3.png)

1. Si vous constatez que votre site web affiche TLS 1.0, reportez-vous à [Modifications du chiffrement de TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) pour obtenir des informations sur la politique de prise en charge de TLS de Target. Pour remédier à la situation (valable jusqu’au 12 septembre 2018), contactez le [Service d’assistance clientèle](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour obtenir la configuration avec votre version TLS et du domaine.

## Je reçois des messages de délai d’expiration ou des erreurs « accès refusé » lors du chargement de sites où un serveur proxy est activé. (Compositeur d’expérience avancé uniquement)  {#section_60CBB9022DC449F593606C0E6252302D}

Assurez-vous que les adresses IP du serveur proxy ne sont pas bloquées dans votre environnement.
