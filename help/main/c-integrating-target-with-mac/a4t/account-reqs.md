---
keywords: Analytics comme source de création de rapports;a4t;A4T;exigences
description: Découvrez comment configurer les exigences du compte d’utilisateur nécessaires à la création d’une activité Adobe Analytics dans Adobe [!DNL Target] à l’aide d’Analytics for [!DNL Target] (A4T).
title: Quelles sont les exigences d’autorisation des utilisateurs requises pour A4T ?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
TQID: https://experienceleague.adobe.com/SGNIoARqe3yN4WvKF4JPIp0t0JCMiSgj--zrjt-ZXJQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 32%

---

# Exigences d’autorisation des utilisateurs

Informations sur les exigences du compte d’utilisateur pour créer une activité basée sur [!DNL Adobe Analytics] dans [!DNL Adobe Target] (A4T).

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité [!DNL Analytics], vous avez besoin d’un compte d’utilisateur [!DNL Analytics] et également d’un compte d’utilisateur [!DNL Target].

Les comptes d’utilisateurs doivent être configurés comme décrit dans les sections suivantes :

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Effectuez les tâches suivantes dans l’[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com) :

### Liez des comptes de solutions à votre Adobe ID

Vos comptes d’utilisateur [!DNL Analytics] et [!DNL Target] doivent être liés à votre Adobe ID.

Pour plus d’informations, voir [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr).

### Configuration de l’appartenance au groupe Experience Cloud

Vous devez être membre d’un ou plusieurs groupes [!DNL Experience Cloud] ayant accès à [!DNL Analytics] et [!DNL Target].

Pour plus d’informations, voir [Gestion des utilisateurs et des produits Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Pour utiliser A4T sur une suite de rapports donnée, vous devez avoir accès à cette suite de rapports et accorder l’accès au groupe de [!DNL Web Services Access] .

1. Dans **[!UICONTROL Admin Console]**, cliquez sur un profil de produit [!DNL Analytics], puis sur l’onglet **[!UICONTROL Permissions]** .

   Vous pouvez ensuite voir à quelles suites de rapports le profil a accès.

1. Assurez-vous que la suite de rapports à laquelle vous souhaitez avoir accès dans [!DNL Target] est l’une de celles répertoriées dans le profil de produit dont vous faites partie.

   L’illustration suivante est un exemple de profil de produit qui a accès à toutes les suites de rapports :

   ![Onglet Autorisations &#x200B;](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configurez l’accès au groupe de [!UICONTROL Web Services Access] .

   L’accès au groupe de [!UICONTROL Web Services Access] dans [!DNL Analytics] est requis pour pouvoir utiliser [!DNL Analytics] comme source de création de rapports pour [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
