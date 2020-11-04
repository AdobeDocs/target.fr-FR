---
keywords: Analytics as reporting source;a4t;A4T
description: Conditions requises du compte utilisateur pour créer une activité basée sur Adobe Analytics dans Adobe Target (A4T).
title: Exigences d’autorisation des utilisateurs
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 3215aa7c5ce986ff335dd2669c250ef5900d8789
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 51%

---


# Exigences d’autorisation des utilisateurs {#user-permission-requirements}

Informations sur les exigences du compte utilisateur pour créer une activité basée sur [!DNL Adobe Analytics] dans [!DNL Adobe Target] (A4T).

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité [!DNL Analytics], vous avez besoin d’un compte utilisateur [!DNL Analytics] et également d’un compte utilisateur [!DNL Target].

Les comptes utilisateur doivent être configurés comme décrit dans les sections suivantes :

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Effectuez les tâches suivantes dans [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) :

### Liez des comptes de solutions à votre Adobe ID

Vos comptes utilisateur [!DNL Analytics] et [!DNL Target] doivent être liés à votre Adobe ID.

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configuration de l’appartenance au groupe Experience Cloud

Vous devez être membre d’un ou plusieurs groupes [!DNL Experience Cloud] ayant accès à [!DNL Analytics] et [!DNL Target].

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Effectuez les tâches suivantes dans [!DNL Adobe Analytics] :

### Configuration de l’accès à la suite de rapports Analytics

Pour utiliser A4T sur une suite de rapports donnée, vous devez avoir accès à cette suite de rapports. Pour accéder au [!UICONTROL Admin Console], cliquez sur un profil de [!DNL Analytics] produit, puis sur l’onglet [!UICONTROL Autorisations] . Vous pouvez ensuite identifier les suites de rapports auxquelles le profil a accès. Assurez-vous que la suite de rapports à laquelle vous souhaitez accéder dans [!DNL Target] est l’une des suivantes répertoriées dans le profil de produits auquel vous faites partie.

L’illustration suivante représente un exemple de profil de produits ayant accès à toutes les suites de rapports :

![Onglet Autorisation du Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
