---
keywords: profil du visiteur, profil du visiteur target
description: Découvrez comment créer des audiences dans [!DNL Adobe Target] pour cibler les visiteurs qui répondent à des paramètres de profil spécifiques, tels que les visiteurs nouveaux ou réguliers, l’affinité catégorielle, etc.
title: Puis-Je Cibler Les Visiteurs Qui Rencontrent Des Paramètres De Profil Spécifiques ?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# Profil du visiteur

Créez des audiences dans [!DNL Adobe Target] pour cibler les visiteurs qui correspondent à des paramètres de profil spécifiques.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Faites glisser **[!UICONTROL Profil du visiteur]** dans le volet du créateur d’audiences.

1. Cliquez sur **[!UICONTROL Sélectionner]**, puis sélectionnez l’une des options suivantes :

   ![](assets/target_visitor_profile.png)

   Les paramètres de profil du visiteur sont transmis via la mbox (profil). Vous pouvez cibler les visiteurs nouveaux ou récurrents, ou inclure tous les utilisateurs.

   * [!UICONTROL Nouveau visiteur]
   * [!UICONTROL Visiteur récurrent]
   * [!UICONTROL Dans d’autres tests]
   * [!UICONTROL Pas dans d’autres tests]
   * [!UICONTROL Première page de la session]
   * [!UICONTROL Pas la première page de la session]
   * [!UICONTROL Affinité catégorielle]

   Un profil du visiteur est créé en local dans la mémoire périphérique pour chaque appel mbox comportant de nouvelles données `mboxPC`. Après 30 minutes d’inactivité, le profil est enregistré dans la base de données [!DNL Target] et est accessible depuis d’autres périphéries.

   Lorsqu’un visiteur du site se connecte en milieu de session et obtient un `3rdpartyId`, tous les attributs de profil antérieurement chargés liés à `3rdPartyId` sont immédiatement disponibles.

   Vous pouvez cibler des paramètres de profil personnalisés et des paramètres `user.`. Sélectionnez le paramètre que vous souhaitez utiliser pour cibler votre activité. Si le paramètre souhaité ne s’affiche pas, il n’a pas été déclenché par une mbox.

1. (Facultatif) Configurez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Terminé]**.

## Vidéo de formation : Création d’audiences ![Badge Aperçu](/help/assets/overview.png)

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
