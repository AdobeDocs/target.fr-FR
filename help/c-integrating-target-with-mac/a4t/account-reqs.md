---
keywords: Analytics as reporting source;a4t;A4T;requirements
description: Conditions requises du compte utilisateur pour créer une activité basée sur Adobe Analytics dans Adobe Target (A4T).
title: Exigences d’autorisation des utilisateurs
feature: a4t implementation
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 49%

---


# Exigences d’autorisation des utilisateurs

Informations sur les exigences du compte utilisateur pour créer une activité basée sur [!DNL Adobe Analytics] dans [!DNL Adobe Target] (A4T).

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité [!DNL Analytics], vous avez besoin d’un compte utilisateur [!DNL Analytics] et également d’un compte utilisateur [!DNL Target].

Les comptes utilisateur doivent être configurés comme décrit dans les sections suivantes :

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Effectuez les tâches suivantes dans [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) :

### Liez des comptes de solutions à votre Adobe ID

Vos comptes utilisateur [!DNL Analytics] et [!DNL Target] doivent être liés à votre Adobe ID.

Pour plus d’informations, voir [Organisations et liaison de comptes](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configuration de l’appartenance au groupe Experience Cloud

Vous devez être membre d’un ou plusieurs groupes [!DNL Experience Cloud] ayant accès à [!DNL Analytics] et [!DNL Target].

Pour plus d’informations, voir [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Configurez l&#39;accès à la suite de rapports [!DNL Analytics] :

Pour utiliser A4T sur une suite de rapports donnée, vous devez avoir accès à cette suite de rapports.

1. Dans **[!UICONTROL Admin Console]**, cliquez sur un profil de produit [!DNL Analytics], puis sur l&#39;onglet **[!UICONTROL Permissions]**.

   Vous pouvez ensuite identifier les suites de rapports auxquelles le profil a accès.

1. Assurez-vous que la suite de rapports à laquelle vous souhaitez accéder dans [!DNL Target] est l’une des suites répertoriées dans le profil de produits auquel vous faites partie.

   L’illustration suivante représente un exemple de profil de produits ayant accès à toutes les suites de rapports :

   ![Onglet Autorisation du Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
