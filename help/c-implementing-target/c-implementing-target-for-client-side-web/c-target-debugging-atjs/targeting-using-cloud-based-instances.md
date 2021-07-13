---
keywords: instances du cloud;liste des suffixes publics;suffixe public;cookie;cookie propriétaire;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Explorez les problèmes (avec les solutions) auxquels sont confrontés les clients lors de l’utilisation d’instances basées sur le cloud pour tester l’Adobe [!DNL Target] ou à des fins de preuve de concept.
title: Puis-je utiliser [!DNL Target] avec des instances basées sur le cloud ?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 67%

---

# Utilisation d’instances basées sur le cloud avec Target

Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester [!DNL Adobe Target].

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces instances peuvent inclure les domaines suivants :

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`, ou `firebaseapp.com`

Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

**Problème :** Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines.

La bibliothèque JavaScript [!DNL at.js] utilise des cookies pour effectuer le suivi des utilisateurs afin de s’assurer que [!DNL Target] présente toujours une expérience cohérente. Si la bibliothèque JavaScript [!DNL Target] ne peut pas enregistrer les cookies, les demandes [!DNL Target] sont désactivées.

**Solution :** Pour respecter les bonnes pratiques, si vous envisagez d’utiliser des instances basées sur le cloud avec des domaines inclus dans la liste des suffixes publics, veillez à personnaliser le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
