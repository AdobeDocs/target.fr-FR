---
keywords: cloud instances;public suffix list;public suffix;cookie;first-party cookie;1st-party cookie;azurewebsites.net;cloudapp.net;amazonaws.com;cloudfront.net;herokuapp.com;firebaseapp.com;targetGlobalSettings;cookieDomain
description: Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester Adobe Target.
title: Utilisation d’instances basées sur le cloud avec Target
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# Utilisation d’instances basées sur le cloud avec Target{#use-cloud-based-instances-with-target}

Informations sur des problèmes que rencontrent les clients lors de l’utilisation d’instances basées sur le cloud pour tester [!DNL Adobe Target].

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces instances peuvent inclure les domaines suivants :

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com`, ou `firebaseapp.com`

Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

**Problème :** Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines.

Les bibliothèques JavaScript [!DNL at.js] et [!DNL mbox.js] utilisent des cookies pour effectuer le suivi des utilisateurs afin de garantir que [!DNL Target] présente toujours une expérience cohérente. Si les bibliothèques JavaScript de [!DNL Target] ne peuvent pas enregistrer les cookies, les demandes [!DNL Target] sont désactivées.

**Solution :** Pour respecter les bonnes pratiques, si vous envisagez d’utiliser des instances basées sur le cloud avec des domaines inclus dans la liste des suffixes publics, veillez à personnaliser le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
