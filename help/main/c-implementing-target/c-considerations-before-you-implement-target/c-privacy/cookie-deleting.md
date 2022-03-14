---
keywords: cookie;cookies;supprimer un cookie;supprimer un cookie cible;google chrome;mozilla firefox;firefox;microsoft edge;safari
description: Découvrez comment supprimer votre [!DNL Target] des cookies de navigateur afin que vous puissiez valider vos expériences.
title: Comment supprimer la variable [!DNL Target] Cookie ?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 4%

---

# Supprimez la variable [!DNL Target] cookie

Vous pouvez supprimer vos [!DNL Adobe Target] le cookie du navigateur (mbox) afin que vous puissiez valider toutes vos expériences lors du test.

Si la variable [!DNL Target] (mbox), vous êtes considéré comme un nouveau visiteur et vous avez une nouvelle expérience. Il existe plusieurs manières de supprimer votre mbox sans supprimer l’ensemble des cookies de navigateur.

>[!NOTE]
>
>Les instructions suivantes sont correctes pour les navigateurs et les versions répertoriés. Recherchez sur Internet des instructions relatives à votre navigateur ou version spécifique.

## Supprimez la variable [!DNL Target] cookie depuis Google Chrome

Version 84.0.4147.105

1. Cliquez sur le bouton **Chrome** menu > **Préférences**.
1. Cliquez sur le bouton **Confidentialité et sécurité** .
1. Cliquez sur **Cookies et autres données de site**.
1. Cliquez sur **Afficher tous les cookies et les données du site**.
1. Développez l’objet `adobe.com` , sélectionnez **mbox** , puis cliquez sur l’icône de suppression (X).

## Supprimez la variable [!DNL Target] cookie de Mozilla Firefox

Version 79.0

### Supprimer tous les cookies associés à `adobe.com`

1. Cliquez sur le bouton **Firefox** menu > **Préférences**.
1. Cliquez sur le bouton **Confidentialité et sécurité** .
1. Sous **Cookies et données du site**, cliquez sur **Gérer les données**.
1. Sélectionnez la `adobe.com` site, puis cliquez sur **Supprimer la sélection**.

   >[!NOTE]
   >
   >Cette opération supprime tous les cookies associés à la variable `adobe.com` site. Si vous souhaitez supprimer un cookie individuel d’un site, suivez les instructions ci-dessous.

### Suppression d’un cookie individuel (mbox)

1. Dans Firefox, cliquez sur **Outils** > **Développeur web** > **Inspecteur de stockage**.
1. Cliquez sur le bouton **Avancé** .
1. Accédez à la page web qui contient le cookie que vous souhaitez supprimer.
1. Développez l’objet **Cookies** , puis cliquez sur `https://experience.adobe.com`.
1. Cliquez avec le bouton droit de la souris sur le **mbox** cookie, puis cliquez sur **Supprimer**.

## Supprimez la variable [!DNL Target] cookie de Microsoft Edge

Version 84.0.522.52

1. Cliquez sur le bouton **Microsoft Edge** menu > **Préférences**.
1. Cliquez sur le bouton **Autorisations du site** .
1. Cliquez sur **Cookies et données du site**.
1. Cliquez sur **Afficher tous les cookies et les données du site**.
1. Développez l’objet `adobe.com` , sélectionnez **mbox** , puis cliquez sur l’icône de suppression (X).

## Supprimez la variable [!DNL Target] cookie depuis Apple Safari

Version 13.1.2

### Supprimer tous les cookies associés à `adobe.com`

1. Cliquez sur le bouton **Safari** menu > **Préférences**.
1. Cliquez sur le bouton **Confidentialité** .
1. Cliquez sur **Gérer les données du site web**.
1. Sélectionnez les sites des cookies que vous souhaitez supprimer, puis cliquez sur **Supprimer**.

   >[!NOTE]
   >
   >Cette opération supprime tous les cookies associés à la variable `adobe.com` site. Si vous souhaitez supprimer un cookie individuel d’un site, suivez les instructions ci-dessous.

### Suppression d’un cookie individuel (mbox)

1. Cliquez sur le bouton **Safari** menu > **Préférences**.
1. Cliquez sur le bouton **Avancé** .
1. Sélectionnez la **Afficher le menu Développer dans la barre de menus** .
1. Accédez à la page web qui contient le cookie que vous souhaitez supprimer.
1. Cliquez sur le bouton **Développer** menu > **Afficher l’Inspecteur Web**.
1. Cliquez sur le bouton **Stockage** .
1. Développez l’objet **Cookies** , puis cliquez sur `www.adobe.com`.
1. Cliquez avec le bouton droit de la souris sur le **mbox** cookie, puis cliquez sur **Supprimer**.
