---
description: Conditions requises du compte utilisateur pour créer une activité basée sur Adobe Analytics dans Adobe Target (A4T).
keywords: Analytics en tant que source des rapports, a4t, A4T
seo-description: Conditions requises du compte utilisateur pour créer une activité basée sur Adobe Analytics dans Adobe Target (A4T).
seo-title: Exigences d’autorisation des utilisateurs
solution: Target,Analytics
title: Exigences d’autorisation des utilisateurs
topic: Reports and Analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

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

Avant de créer ou de visualiser des rapports pour une activité Analytics, vous devez être membre du groupe **[!UICONTROL Accès à tous les rapports]**, ou membre d’un groupe ayant accès à au moins un rapport dans la suite de rapports que vous souhaitez utiliser. Si vous ne pouvez pas visualiser les rapports, assurez-vous que vous êtes membre de l’un de ces groupes.

Pour plus d’informations, voir Profils et groupes [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)produits.

### Configuration de l’accès au groupe d’accès aux services web

Vous devez être membre du groupe d’accès aux services web dans [!DNL Adobe Analytics] pour pouvoir utiliser [!DNL Analytics] en tant que source de création de rapports pour [!DNL Target].

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Aucun privilège supplémentaire n’est requis.
