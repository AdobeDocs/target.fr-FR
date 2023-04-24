---
keywords: paramètres personnalisés;paramètres personnalisés target;targetpageparams;ciblage des paramètres mbox
description: Découvrez comment transmettre des paramètres personnalisés à [!DNL Adobe Target] pour une utilisation dans les audiences.
title: Puis-je cibler les visiteurs en fonction de paramètres personnalisés ?
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 41%

---

# Paramètres personnalisés

Les paramètres personnalisés sont des paramètres de mbox dans [!DNL Adobe Target]. Si vous transférez des paramètres de mbox à des mbox, ou utilisez la méthode `targetPageParams` , ces paramètres s’affichent ici pour être utilisés dans les audiences.

Pour plus d’informations, voir [Transfert de paramètres à une mbox globale](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html){target=_blank}.

Lors de la création d’une audience personnalisée basée sur un paramètre mbox, `mboxParameter` ne vous demande plus le `mboxName`. Le nom de la mbox est à présent facultatif. Cette modification vous permet d’utiliser les paramètres de plusieurs mbox ou de référencer un paramètre qui n’a pas encore été enregistré.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Glisser-déposer **[!UICONTROL Personnalisé]** dans le créateur d’audiences.

   Pour sélectionner le paramètre désiré :

   * Lors de la création d’une audience, sélectionnez un nom de paramètre dans la liste, commencez à saisir les premiers caractères du nom de paramètre souhaité ou saisissez le nom complet du nom de paramètre souhaité.
   * Si vous vous souvenez du nom de la mbox, mais pas du nom du paramètre, utilisez la méthode [!UICONTROL Filtrer par] liste déroulante pour filtrer sur une mbox connue transmettant le paramètre souhaité.

   Quelle que soit la méthode, il n’existe aucun lien entre la mbox et le paramètre. L’audience fonctionne en fonction du paramètre dans toutes les mbox qui transmettent ce paramètre.

   >[!NOTE]
   >
   >La mbox que vous sélectionnez dans la [!UICONTROL Filtrer par] La liste déroulante n’est pas enregistrée lors de la création de l’activité. Cette option permet de filtrer les paramètres en fonction de la mbox sélectionnée.

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
   * Le paramètre est présent
   * Le paramètre n’est pas présent
   * La valeur du paramètre est présente
   * La valeur du paramètre n’est pas présente
   * Le paramètre ou la valeur n’est pas présent
   * Commencez avec les sections
   * Se termine par

   ![Audience de paramètre personnalisé](assets/custom.png)

1. Entrez chaque valeur sur une nouvelle ligne.
1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Terminé]**.

La [carte contextuelle de détails de définition](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) affiche le nom du paramètre dans la section Règles. **** Il n’y a aucune référence à la mbox utilisée pour le filtrage.

>[!NOTE]
>
>Pour les audiences personnalisées créées avant l’événement [!DNL Target] Version 18.5.1 (22 mai 2018), les noms de mbox ne s’affichent pas dans la carte contextuelle de définition de l’audience. Enregistrez à nouveau l’audience personnalisée pour que le nom de la mbox s’affiche dans la carte.

## Considérations {#considerations}

* Les audiences et les activités sont évaluées pour une mbox spécifique. Par exemple, si la mbox globale transmet un certain paramètre, mais que la mbox régionale ne le fait pas, l’activité/l’audience ciblant ce paramètre n’est pas qualifiée dans la mbox régionale.
* Le ciblage n’est pas évalué sur les paramètres mbox internes, tels que mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId et mboxVersion.

## Vidéo de formation : Création d’audiences ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
