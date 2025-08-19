---
keywords: paramètres personnalisés;paramètres personnalisés target;targetpageparams;ciblage des paramètres mbox
description: Découvrez comment transmettre des paramètres personnalisés à  [!DNL Adobe Target]  pour une utilisation dans les audiences.
title: Puis-je cibler les visiteurs et visiteuses en fonction de paramètres personnalisés ?
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 38%

---

# Paramètres personnalisés

Les paramètres personnalisés sont des paramètres mbox dans [!DNL Adobe Target]. Si vous transmettez des paramètres de mbox aux mbox ou utilisez la fonction `targetPageParams`, ces paramètres apparaissent ici pour être utilisés dans les audiences.

Pour plus d’informations, voir [ Transmettre des paramètres à une mbox globale ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=fr){target=_blank}.

Lors de la création d’une audience personnalisée basée sur un paramètre mbox, `mboxParameter` ne vous demande plus le `mboxName`. Le nom de la mbox est à présent facultatif. Cette modification vous permet d’utiliser les paramètres de plusieurs mbox ou de référencer un paramètre qui n’a pas encore été enregistré.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Glissez-déposez **[!UICONTROL Custom]** dans le Créateur d’audience.

   Pour sélectionner le paramètre désiré :

   * Lors de la création d’une audience, sélectionnez un nom de paramètre dans la liste, commencez à saisir les premiers caractères du nom de paramètre souhaité ou saisissez-en le nom complet.
   * Si vous vous souvenez du nom de la mbox, mais pas du nom du paramètre, utilisez la liste déroulante [!UICONTROL Filter by] pour filtrer une mbox connue en transmettant le paramètre souhaité.

   Quelle que soit la méthode, il n’existe aucun lien entre la mbox et le paramètre. L’audience fonctionne en fonction du paramètre sur toutes les mbox qui transmettent ce paramètre.

   >[!NOTE]
   >
   >La mbox que vous sélectionnez dans la liste déroulante [!UICONTROL Filter By] n’est pas enregistrée lors de la création de l’activité. Cette option permet de filtrer les paramètres en fonction de la mbox sélectionnée.

   Si vous modifiez une audience existante, le critère de filtrage s’affiche avec le nom de mbox fourni lors de la création.

1. Sélectionnez un évaluateur :

   * Contient (non-respect de la casse)
   * Ne contient pas (non-respect de la casse)
   * Est égal
   * N’est pas égal à
   * Est supérieur à
   * Est supérieur ou égal à
   * Est inférieur à
   * Est inférieur ou égal à
   * Paramètre présent
   * Paramètre absent
   * Valeur du paramètre présente
   * La valeur du paramètre n’est pas présente
   * Paramètre ou valeur non présent
   * Commencez avec les sections
   * Se termine par

   ![Audience de paramètre personnalisé](assets/custom.png)

1. Entrez chaque valeur sur une nouvelle ligne.
1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Done]**.

La vignette pop-up [définition des détails](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) de l’audience affiche le nom du paramètre dans la section **[!UICONTROL Rules]**. Il n’y a aucune référence à la mbox utilisée pour le filtrage.

>[!NOTE]
>
>Pour les audiences personnalisées créées avant la version 18.5.1 de [!DNL Target] (22 mai 2018), les noms de mbox ne s’affichent pas dans la carte pop-up de définition de l’audience. Enregistrez à nouveau l’audience personnalisée pour obtenir le nom de la mbox à afficher dans la carte.

## Considérations {#considerations}

* Les audiences et les activités sont évaluées pour une mbox spécifique. Par exemple, si la mbox globale transmet un certain paramètre, mais pas la mbox régionale, le ciblage de l’activité/de l’audience pour ce paramètre n’est pas qualifié pour sur la mbox régionale.
* Le ciblage n’est pas évalué sur les paramètres de mbox internes, tels que mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId et mboxVersion.

## Vidéo de formation : création d’audiences ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
