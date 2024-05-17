---
keywords: Ciblage;compositeur d’expérience avancé;compositeur d’expérience visuelle;dépannage compositeur d’expérience avancé;résolution des problèmes
description: Découvrez comment résoudre les problèmes qui se produisent parfois dans l’Adobe [!DNL Target] Compositeur d’expérience avancé dans certaines conditions.
title: Comment résoudre les problèmes liés au compositeur d’expérience avancé ?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 23%

---

# Résolution des problèmes liés à [!UICONTROL Enhanced Experience Composer]

Des problèmes d’affichage se produisent parfois dans la variable [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (CEE) sous certaines conditions.

## Le compositeur d’expérience avancé ne charge pas une URL AQ interne qui n’est pas accessible sur une adresse IP publique. {#section_D29E96911D5C401889B5EACE267F13CF}

Cela peut être résolu en plaçant sur la liste autorisée les adresses IP suivantes. Ces adresses IP sont destinées au serveur de l’Adobe utilisé pour le proxy du compositeur d’expérience avancé. Elles ne sont requises que pour la modification des activités. Les visiteurs de votre site n’ont pas besoin que ces adresses IP soient placées sur la liste autorisée.

Demandez à votre équipe informatique de placer sur la liste autorisée les adresses IP suivantes :

* 34.254.77.200
* 54.73.207.147
* 54.229.152.123
* 3.224.194.242
* 54.90.51.39
* 34.228.136.112
* 54.150.116.11
* 18.178.142.8
* 54.199.107.77
* 99.80.139.221
* 54.78.56.224
* 54.247.179.246
* 54.80.219.243
* 34 201 235 54
* 54.196.224.236
* 35.75.212.45
* 52.199.184.130
* 18.180.161.176

Le message d’erreur suivant peut s’afficher dans [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![Image EEC_error](assets/EEC_error.png)

Voici les raisons pour lesquelles ce message d’erreur s’affiche et les solutions pour corriger la situation :

* **Problème :** Votre domaine de site web (FAI) bloque la variable [!UICONTROL Enhanced Experience Composer].

  **Solution :** Placez sur la liste autorisée les adresses IP répertoriées ci-dessus.

* **Problème :** Les adresses IP sont placées sur la liste autorisée, mais votre site web ne prend pas en charge TLS version 1.2. [!DNL Target] utilise actuellement la configuration par défaut de 1.2. Avant le [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d’informations, voir [Modifications du chiffrement de TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Solution :** Voir la question suivante (La [!UICONTROL Enhanced Visual Experience Composer] ne se chargera pas sur les pages sécurisées de mon site qui utilisent TLS 1.2).

## Le compositeur d’expérience avancé ne se charge pas sur les pages sécurisées de mon site qui utilisent TLS 1.0. (Compositeur d’expérience avancé uniquement)  {#section_C5B31E3D32A844F68E5A8153BD17551F}

Le message d’erreur décrit ci-dessus peut s’afficher dans la section &quot;The [!UICONTROL Enhanced Visual Experience Composer] ne se chargera pas sur les pages sécurisées de mon site.&quot; si les adresses IP ci-dessus sont placées sur la liste autorisée mais que votre site web ne prend pas en charge TLS version 1.2. [!DNL Target] utilise actuellement la configuration par défaut de 1.2. Avant le [!DNL Target] 18.4.1 (25 avril 2018), la configuration par défaut prenait en charge TLS 1.0. Pour plus d’informations, voir [Modifications du chiffrement de TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Pour vérifier la version TLS de votre site web en utilisant Firefox (les autres navigateurs suivent des étapes similaires) :

1. Ouvrez le site web concerné dans Firefox.
1. Cliquez sur le bouton **[!UICONTROL Show Site Information]** dans la barre d’adresse du navigateur.

   ![image firefox_more_info](assets/firefox_more_info.png)

1. Cliquez sur **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![image firefox_more_info_2](assets/firefox_more_info_2.png)

1. Examinez les informations de version TLS dans l’option Détails techniques :

   ![image firefox_more_info_3](assets/firefox_more_info_3.png)

1. Si vous constatez que votre site web affiche TLS 1.0, voir [Modifications du chiffrement de TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} pour plus d’informations sur la politique de prise en charge de TLS de Target. Pour remédier à la situation (valable jusqu’au 12 septembre 2018){target=_blank}, contactez pour [Assistance clientèle](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour la configuration avec votre version TLS et le domaine.

## Je reçois des messages de délai d’expiration ou des erreurs « accès refusé » lors du chargement de sites où un serveur proxy est activé. (Compositeur d’expérience avancé uniquement)  {#section_60CBB9022DC449F593606C0E6252302D}

Assurez-vous que les adresses IP du serveur proxy ne sont pas bloquées dans votre environnement.
