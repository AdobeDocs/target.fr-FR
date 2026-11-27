---
keywords: tests de modèle;modèle;même expérience sur des pages similaires;test de modèles
description: Découvrez comment utiliser le compositeur d’expérience visuelle (VEC) [!DNL Target] d’Adobe pour inclure la même expérience sur plusieurs pages structurées de manière similaire ou contenant les mêmes éléments de modèle.
title: Puis-je inclure la même expérience sur des pages similaires ?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: 'https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: ef98a6e0-f26c-4870-9bd4-e6b72e9cc699
    internal-label: Experiences and offers
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 17%
---
# Inclure la même expérience sur des pages similaires {#similar-pages}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser les règles de diffusion de page dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) pour inclure la même expérience sur des pages ayant une structure similaire.

>[!ENDSHADEBOX]

Un modèle de page dans [!DNL Adobe Target] fournit une structure aux pages. Lorsque les pages contiennent des éléments similaires, les variations de ces éléments de page à structure similaire peuvent être testées sur plusieurs pages ou sur un domaine entier.

Pour fonctionner correctement, cette fonction doit être utilisée sur des pages ayant une structure similaire ou contenant des éléments de modèle structurés de la même manière sur toutes les pages.

>[!IMPORTANT]
>
>L’utilisation de cette fonctionnalité pour modifier des éléments sur des pages différentes entraîne probablement des résultats inattendus.

Cette fonction peut être utilisée, par exemple, pour effectuer l’une des opérations suivantes :

* Tester une barre de navigation globale en réorganisant ou supprimant des éléments
* Supprimer un élément de toutes les pages de produits qui utilisent un modèle de page spécifique
* Ajouter une bannière à toutes les pages de produits
* Modifier la disposition du modèle d’article

## Spécification des pages pour une expérience {#specify-pages}

Les pages sur lesquelles apparaît une expérience sont spécifiées avec des règles de diffusion de page. Les règles peuvent inclure des pages spécifiques ou appliquer la modification à l’ensemble du site ou du domaine.

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/main/c-activities/activities.md).

1. Dans le [!UICONTROL compositeur d’expérience visuelle] (VEC), cliquez sur l’icône **[!UICONTROL Configurer]** ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ), puis sélectionnez **[!UICONTROL Diffusion de page]**.

   ![Activités](assets/vec_edit_1.png)

1. Cliquez sur **[!UICONTROL Ajouter une règle]**, puis spécifiez les critères des pages auxquelles ajouter l’expérience.

1. Spécifiez la plage de pages : **[!UICONTROL URL]**, **[!UICONTROL Domaine]**, **[!UICONTROL Chemin]**, **[!UICONTROL Fragment de hachage (#)]** (partie d’une URL qui suit le symbole #), **[!UICONTROL Requête]** ou **[!UICONTROL Personnalisé]**.

   Pour plus d&#39;informations sur la façon dont [!DNL Target] évalue les URL, consultez [FAQ sur les cibles et les audiences](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).

   ![Activités](assets/vec_edit_2.png)

1. Sélectionnez un opérateur. L’opérateur indique comment les éléments après l’opérateur sont associés à la plage de pages.

1. Saisissez les chaînes qui définissent l’emplacement d’ajout de l’expérience, par exemple le domaine ou les chaînes contenues dans le nom de la page.

   Par exemple, si **[!UICONTROL Domaine]** et **[!UICONTROL Est (sensible à la casse)]** sont sélectionnés, saisissez le domaine dans lequel l’expérience est ajoutée à toutes les pages.

   Plusieurs éléments peuvent être inclus. Plusieurs éléments utilisent la logique OR, ce qui signifie que tout élément unique de la liste rend la condition vraie.

1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]** et répétez les étapes 3 à 6 pour saisir des critères supplémentaires.

   Plusieurs critères sont associés avec la logique ET. [!DNL Target] ajoute l’expérience à toutes les pages qui correspondent aux critères spécifiés.

>[!IMPORTANT]
>
>[!DNL Target] ne pouvant pas vérifier les pages pour s&#39;assurer qu&#39;elles apparaissent comme prévu, il est toujours important, lors de l&#39;utilisation de cette fonctionnalité, de tester les pages affectées avant de les rendre publiques.

## Cas d’utilisation {#use-cases}

Les règles de modèle peuvent être utilisées sur un site de différentes manières, comme le montre le cas d’utilisation suivant.

### Rendu de la même activité sur l’ensemble du domaine {#entire-domain}

Les règles de modèle peuvent générer la même activité sur l’ensemble du domaine, par exemple :

* Pour inclure un en-tête ou un pied de page global
* Pour inclure une bannière globale (par exemple, les annonces COVID-19)
* Pour inclure une promotion de livraison gratuite internationale

1. Créez ou modifiez une activité comme décrit dans [Activités](/help/main/c-activities/activities.md).

1. Pour spécifier le domaine dans lequel l’expérience apparaît, dans le [!UICONTROL compositeur d’expérience visuelle], cliquez sur l’icône **[!UICONTROL Configurer]** ( ![icône Configurer](/help/main/assets/icons/Setting.svg) ), puis sélectionnez **[!UICONTROL Diffusion de page]**.

1. Cliquez Sur **[!UICONTROL Ajouter Une Règle]** > **[!UICONTROL Domaine]**.

1. Dans la liste déroulante **[!UICONTROL Choisir l&#39;évaluateur]**, sélectionnez **[!UICONTROL Contient]**, puis spécifiez le domaine.

   ![Activités](assets/vec_edit_3.png)
