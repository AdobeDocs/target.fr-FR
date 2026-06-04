---
keywords: ciblage;collisions;conflits
description: Empêchez les collisions de diffusion de contenu sur la même page en configurant correctement les activités dans Adobe Target.
title: Comment Éviter Les Collisions D’Activités ?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 49%

---

# Collisions d’activités

L’onglet [!UICONTROL Collisions] de la page [!UICONTROL Présentation des activités] de [!DNL Adobe Target] répertorie les collisions d’activités sur votre site.

Une collision d’activités survient lorsque plusieurs activités sont configurées pour diffuser du contenu sur la même page. Si une collision d’activités se produit, vous ne pourrez peut-être pas afficher le contenu attendu sur votre page.

L’onglet [!UICONTROL Collisions] est disponible sur la page d’aperçu de l’activité et peut vous informer si votre activité contient des collisions potentielles.

Pour accéder à l’onglet [!UICONTROL Collisions], cliquez sur **[!UICONTROL Activités]** > cliquez sur l’activité souhaitée dans la liste > puis cliquez sur **[!UICONTROL Collisions]** dans le rail de gauche.

Toutes les activités partageant la même URL sont répertoriées, quel que soit le ciblage d’audience de chaque activité. Ouvrez cet onglet pour obtenir une liste des activités pouvant entrer en collision. Si la collision modifie l’expérience attendue, modifiez l’activité.

La liste [!UICONTROL Collisions] vous aide à :

* d’identifier si un test est déjà en cours d’exécution sur une page avant de configurer une nouvelle activité ;
* de dépanner une activité si le contenu attendu ne s’affiche pas.

La liste [!UICONTROL Collisions] affiche chaque scénario [!DNL Target] où la mbox est utilisée et qui utilise la même URL. Pour chaque collision potentielle, la liste affiche l’URL de l’activité, le nom de la mbox où la collision peut se produire et toutes les activités qui correspondent à ces deux critères. En cas de mbox multiples, elles sont toutes répertoriées.

La liste affiche le statut et la priorité de chaque collision potentielle, ainsi que d’autres informations. Vous pouvez utiliser le statut et la priorité pour vous aider à déterminer la probabilité qu’une collision se produise. Prenons deux activités qui pourraient entrer en conflit. Si une activité n’est pas active actuellement, une collision ne peut pas se produire. Une collision n’est possible que si l’activité inactive devient active. Si la collision potentielle se produit entre deux activités actives ayant la même priorité et la même audience, une collision se produit. Vous pouvez modifier la priorité ou le statut pour prévenir la collision.

Si les audiences sont différentes, il existe une collision potentielle car il est possible qu’un visiteur spécifique puisse appartenir à plusieurs audiences.
