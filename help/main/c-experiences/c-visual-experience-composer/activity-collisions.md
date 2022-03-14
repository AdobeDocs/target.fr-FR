---
keywords: ciblage;collisions;conflits
description: Des collisions se produisent lorsque plusieurs activités sont configurées pour diffuser du contenu sur la même page. Découvrez comment éviter les collisions lors de l’utilisation d’Adobe Target.
title: Comment Éviter Les Collisions D’Activité ?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 79%

---

# Collisions d’activités

Le [!UICONTROL Collisions] sur l’onglet [!UICONTROL Présentation de l’activité] page [!DNL Adobe Target] répertorie les collisions d’activités sur votre site.

Une collision d’activités survient lorsque plusieurs activités sont configurées pour diffuser du contenu sur la même page. Si une collision d’activités se produit, vous ne pourrez peut-être pas afficher le contenu attendu sur votre page.

Si votre activité contient des collisions potentielles, l’onglet [!UICONTROL Collisions] est disponible sur la page d’aperçu de l’activité. Toutes les activités partageant la même URL sont répertoriées, quel que soit le ciblage d’audience de chaque activité. Ouvrez cet onglet pour obtenir une liste des activités pouvant entrer en collision. Cliquez sur une activité dans la liste pour afficher la page d’aperçu de cette dernière. Si la collision modifie l’expérience attendue, modifiez l’activité.

Le [!UICONTROL Collisions] vous aide à :

* d’identifier si un test est déjà en cours d’exécution sur une page avant de configurer une nouvelle activité ;
* de dépanner une activité si le contenu attendu ne s’affiche pas.

Le [!UICONTROL Collisions] affiche toutes les [!DNL Target] , où la mbox est utilisée et utilise la même URL. Pour chaque collision potentielle, la liste affiche l’URL de l’activité, le nom de la mbox pour laquelle la collision peut se produire ainsi que toute activité qui correspond à ces deux critères. En cas de mbox multiples, elles sont toutes répertoriées.

La liste affiche le statut et la priorité de chaque collision potentielle, ainsi que d’autres informations. Vous pouvez utiliser le statut et la priorité pour vous aider à déterminer la probabilité qu’une collision se produise. Par exemple, en cas de collision potentielle entre deux activités, une étant inactive, aucune collision réelle ne se produira tant que l’activité inactive n’est pas activée. En cas de collision potentielle entre deux activités actives avec la même priorité et la même audience, une collision se produit. Vous pouvez modifier la priorité ou le statut pour prévenir la collision.

Si les audiences sont différentes, il existe une collision potentielle car il est possible qu’un visiteur spécifique puisse appartenir à plusieurs audiences.
