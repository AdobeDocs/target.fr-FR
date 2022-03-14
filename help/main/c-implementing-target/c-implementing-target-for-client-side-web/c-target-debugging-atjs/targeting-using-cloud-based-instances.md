---
keywords: instances du cloud;liste des suffixes publics;suffixe public;cookie;cookie propriétaire;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Explorez les problèmes (avec les solutions) auxquels sont confrontés les clients lors de l’utilisation d’instances basées sur le cloud pour tester l’Adobe. [!DNL Target] ou à des fins de preuve de concept.
title: Puis-Je Utiliser [!DNL Target] avec les instances basées sur le cloud ?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 70%

---

# Utilisation d’instances basées sur le cloud avec Target

Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester [!DNL Adobe Target].

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces instances peuvent inclure les domaines suivants :

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`, ou `firebaseapp.com`

Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

**Problème :** Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines.

Le [!DNL at.js] La bibliothèque JavaScript utilise des cookies pour effectuer le suivi des utilisateurs afin de s’assurer que [!DNL Target] présente toujours une expérience cohérente. Si la variable [!DNL Target] La bibliothèque JavaScript ne peut pas enregistrer les cookies, [!DNL Target] Les demandes sont désactivées.

**Solution :** Pour respecter les bonnes pratiques, si vous envisagez d’utiliser des instances basées sur le cloud avec des domaines inclus dans la liste des suffixes publics, veillez à personnaliser le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
