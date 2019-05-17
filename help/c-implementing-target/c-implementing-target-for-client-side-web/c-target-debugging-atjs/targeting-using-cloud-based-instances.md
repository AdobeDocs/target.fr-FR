---
description: Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester Adobe Target.
keywords: instances du cloud;liste des suffixes publics;suffixe public;cookie;cookie propriétaire;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
seo-description: Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester Adobe Target.
seo-title: Utilisation d’instances basées sur le cloud avec Target
solution: Target
title: Utilisation d’instances basées sur le cloud avec Target
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Utilisation d’instances basées sur le cloud avec Target{#use-cloud-based-instances-with-target}

Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester [!DNL Adobe Target].

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces instances peuvent inclure les domaines suivants :

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`, ou `firebaseapp.com`

Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

**Problème :** Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines.

Les bibliothèques JavaScript [!DNL at.js] et [!DNL mbox.js] utilisent des cookies pour effectuer le suivi des utilisateurs afin de garantir que [!DNL Target] présente toujours une expérience cohérente. Si les bibliothèques JavaScript de [!DNL Target] ne peuvent pas enregistrer les cookies, les demandes [!DNL Target] sont désactivées.

**Solution :** Pour respecter les bonnes pratiques, si vous envisagez d’utiliser des instances basées sur le cloud avec des domaines inclus dans la liste des suffixes publics, veillez à personnaliser le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
