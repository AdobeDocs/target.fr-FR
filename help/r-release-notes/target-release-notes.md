---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f6efc1e921535abdd11501979d6f44e84e443a1f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 55%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 11 octobre 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.2 (13 octobre 2021)

Les améliorations suivantes ont été apportées lors de l’utilisation de [!DNL Target] [!UICONTROL Audiences] avec la balise [!DNL Adobe Experience Platform Web SDK] :

* Ajout d’icônes d’avertissement, de fenêtres contextuelles et de messages à différents emplacements de l’interface utilisateur [!DNL Target] pour indiquer que l’audience a été supprimée à la source et n’est plus disponible pour être utilisée dans les activités [!DNL Target].

   Les illustrations suivantes présentent certains des emplacements d’affichage des icônes, des fenêtres contextuelles et des messages :

   *  Page Liste des activités

      ![Audience supprimée dans le message source sur la page de liste des activités](assets/deleted-at-source-audiences-list.png)

   * Page [!UICONTROL Aperçu] de l’activité :

      ![Audience supprimée dans le message source sur la page d’aperçu](assets/deleted-at-source-overview.png)

   *  Étape des expériences du workflow de création de l’activité :

      ![Audience supprimée au niveau du message source sur la page   Experience](assets/deleted-at-source-experiences.png)

   *  Étape de ciblage du workflow de création d’activité :

      ![Audience supprimée au niveau du message source sur la   page de ciblage](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Étape Objectifs et ] paramètres du workflow de création d’activité :

      ![Audience supprimée au niveau du message source sur la page  [!UICONTROL Objectifs et ] Paramètres](assets/deleted-at-source-goals-settings.png)

   * Amélioration de l’audience ([!UICONTROL Remplacer l’audience] à l’étape [!UICONTROL Ciblage] du workflow de création d’activité) :

* Si vous tentez d’utiliser la fonction Combiner les audiences et que l’une des audiences a été supprimée à la source, l’option [!UICONTROL Enregistrer] est désactivée.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
