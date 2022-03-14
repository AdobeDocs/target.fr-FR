---
keywords: Analytics en tant que source des rapports;a4t;A4T;conditions requises
description: Découvrez comment configurer les exigences du compte utilisateur nécessaires pour créer une activité Adobe Analytics dans Adobe [!DNL Target] utilisation d’Analytics pour [!DNL Target] (A4T).
title: Quelles sont les exigences en matière d’autorisation des utilisateurs requises pour A4T ?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 34%

---

# Exigences d’autorisation des utilisateurs

Informations sur les exigences du compte utilisateur pour créer une activité basée sur [!DNL Adobe Analytics] dans [!DNL Adobe Target] (A4T).

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité [!DNL Analytics], vous avez besoin d’un compte utilisateur [!DNL Analytics] et également d’un compte utilisateur [!DNL Target].

Les comptes utilisateur doivent être configurés comme décrit dans les sections suivantes :

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Effectuez les tâches suivantes dans [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) :

### Liez des comptes de solutions à votre Adobe ID

Vos comptes utilisateur [!DNL Analytics] et [!DNL Target] doivent être liés à votre Adobe ID.

Pour plus d’informations, voir [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

### Configuration de l’appartenance au groupe Experience Cloud

Vous devez être membre d’un ou plusieurs groupes [!DNL Experience Cloud] ayant accès à [!DNL Analytics] et [!DNL Target].

Pour plus d’informations, voir [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Pour utiliser A4T sur une suite de rapports donnée, vous devez avoir accès à cette suite et accorder l’accès à la variable [!DNL Web Services Access] groupe.

1. Dans **[!UICONTROL Admin Console]**, cliquez sur un [!DNL Analytics] profil de produit, puis cliquez sur **[!UICONTROL Autorisations]** .

   Vous pouvez ensuite voir à quelles suites de rapports le profil a accès.

1. Assurez-vous que la suite de rapports à laquelle vous souhaitez accéder dans [!DNL Target] est l’une des listes répertoriées dans le profil de produits dont vous faites partie.

   L’illustration suivante est un exemple de profil de produit ayant accès à toutes les suites de rapports :

   ![Onglet Autorisations du Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configurez l’accès au [!UICONTROL Accès aux services web] groupe.

   L’accès au [!UICONTROL Accès aux services web] du groupe [!DNL Analytics] est nécessaire pour pouvoir utiliser [!DNL Analytics] comme source de création de rapports pour [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
