---
keywords: Analytics en tant que source du rapports ; a4t ; A4T ; exigences
description: Découvrez comment configurer les exigences de compte d’utilisateur nécessaires pour créer une activité basée sur Adobe Analytics dans Adobe [!DNL Target] using Analytics for [!DNL Target] (A4T).
title: Quelles sont les conditions d’autorisation utilisateur requises pour A4T ?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 36%

---

# Exigences d’autorisation des utilisateurs

Informations sur les exigences du compte utilisateur pour créer une activité basée sur [!DNL Adobe Analytics] dans [!DNL Adobe Target] (A4T).

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité [!DNL Analytics], vous avez besoin d’un compte utilisateur [!DNL Analytics] et également d’un compte utilisateur [!DNL Target].

Les comptes utilisateur doivent être configurés comme décrit dans les sections suivantes :

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Effectuez les tâches suivantes dans [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) :

### Liez des comptes de solutions à votre Adobe ID

Vos comptes utilisateur [!DNL Analytics] et [!DNL Target] doivent être liés à votre Adobe ID.

Pour plus d&#39;informations, voir [Organisations et liaison de comptes](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configuration de l’appartenance au groupe Experience Cloud

Vous devez être membre d’un ou plusieurs groupes [!DNL Experience Cloud] ayant accès à [!DNL Analytics] et [!DNL Target].

Pour plus d’informations, voir [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Pour utiliser A4T sur une suite de rapports donnée, vous devez avoir accès à cette suite de rapports et accorder l’accès au groupe [!DNL Web Services Access].

1. Dans **[!UICONTROL Admin Console]**, cliquez sur un profil de produit [!DNL Analytics], puis sur l&#39;onglet **[!UICONTROL Permissions]**.

   Vous pouvez ensuite identifier les suites de rapports auxquelles le profil a accès.

1. Assurez-vous que la suite de rapports à laquelle vous souhaitez accéder dans [!DNL Target] est l’une des suites répertoriées dans le profil de produits auquel vous faites partie.

   L’illustration suivante représente un exemple de profil de produits ayant accès à toutes les suites de rapports :

   ![Onglet Autorisation du Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configurez l&#39;accès au groupe [!UICONTROL Accès aux services Web].

   L&#39;accès au groupe [!UICONTROL Accès aux services Web] dans [!DNL Analytics] est requis pour pouvoir utiliser [!DNL Analytics] comme source de rapports pour [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
