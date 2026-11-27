---
keywords: ciblage;collisions;conflits
description: Empêchez les collisions de diffusion de contenu sur la même page en configurant correctement les activités dans Adobe Target.
title: Comment Éviter Les Collisions D’Activités ?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: 'https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 18%
---
# Collisions d’activités {#activity-collisions}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment utiliser l’onglet **[!UICONTROL Collisions]** pour rechercher des activités susceptibles de diffuser du contenu sur la même page.

>[!ENDSHADEBOX]

Une collision d’activités survient lorsque plusieurs activités sont configurées pour diffuser du contenu sur la même page. Si une collision d’activités se produit, le contenu attendu peut ne pas apparaître sur la page.

L’onglet **[!UICONTROL Collisions]** de la page **[!UICONTROL Aperçu de l’activité]** de [!DNL Adobe Target] répertorie les collisions d’activités sur le site et indique si une activité contient des collisions potentielles. La liste **[!UICONTROL Collisions]** permet de :

* Déterminer si un test est déjà en cours d’exécution sur une page avant la configuration d’une nouvelle activité
* de dépanner une activité si le contenu attendu ne s’affiche pas.

## Accès à l’onglet Collisions {#access-collisions}

Cliquez sur **[!UICONTROL Activités]**, cliquez sur l’activité souhaitée dans la liste, puis accédez au menu **[!UICONTROL Collisions]**.

![Icône Configurer](assets/collisions_1.png)

Toutes les activités partageant la même URL sont répertoriées, quel que soit le ciblage d’audience de chaque activité. L’onglet répertorie les activités susceptibles d’entrer en conflit. Si la collision modifie l’expérience attendue, modifiez l’activité.

## Lire la liste des collisions {#collisions-list}

La liste **[!UICONTROL Collisions]** affiche chaque scénario [!DNL Target] dans lequel la mbox est utilisée et qui utilise la même URL. Pour chaque collision potentielle, la liste affiche l’URL de l’activité, le nom de la mbox où la collision peut se produire et toutes les activités qui correspondent à ces deux critères. En cas de mbox multiples, elles sont toutes répertoriées.

La liste indique également le statut et la priorité de chaque collision potentielle, ainsi que d’autres informations. L’état et la priorité permettent de déterminer la probabilité d’une collision. Pour deux activités susceptibles d’entrer en conflit :

* Si une activité n’est pas active actuellement, une collision ne peut pas se produire. Une collision n’est possible que si l’activité inactive devient active.
* Si la collision potentielle se produit entre deux activités actives ayant la même priorité et la même audience, une collision se produit. La priorité ou le statut peut être modifié pour éviter la collision.
* Si les audiences sont différentes, il existe toujours un risque de collision, car un visiteur particulier peut appartenir à plusieurs audiences.
