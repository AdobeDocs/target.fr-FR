---
keywords: interface utilisateur de target;interface utilisateur;iu;annonces;événements;notifications
description: Familiarisez-vous avec l’interface utilisateur et trouvez des liens vers des informations plus détaillées pour tirer le meilleur parti de  [!DNL Target].
title: Comment naviguer dans l’interface utilisateur de  [!DNL Target]  ?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 1ab7bb6aef5982f13191ff4f0573e87aac815938
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 28%

---

# Présentation de l’interface utilisateur de [!DNL Target]

L’interface utilisateur suit un format logique et convivial pour vous aider à tirer le meilleur parti d’[!DNL Adobe Target]. Le bref aperçu suivant vous permet de vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.

## En-tête de l’interface utilisateur de [!DNL Target]

L’en-tête situé en haut de l’interface utilisateur de [!DNL Target] contient des onglets et des options qui vous permettent de parcourir les différentes fonctionnalités de la solution. Vous pouvez également changer d’organisation et de solution de [!DNL Adobe Experience Cloud], fournir des commentaires si vous faites partie d’un programme Beta, accéder à l’assistant AI, obtenir de l’aide et des notifications, gérer votre profil de [!DNL Adobe] et vous déconnecter de [!DNL Target].

![En-tête de Target](/help/main/c-intro/assets/target-header.png)

Les onglets situés sur le côté gauche vous permettent d’accéder aux différentes fonctionnalités de [!DNL Target], qui sont abordées plus loin. Commençons par examiner les options du côté droit avant de discuter des onglets.

### [!UICONTROL Organization]

Une *organisation* est l’entité qui permet à un administrateur de configurer des groupes et des utilisateurs et de contrôler l’authentification unique dans [!DNL Adobe Experience Cloud]. L’organisation fonctionne comme une société de connexion qui couvre tous les produits et solutions [!DNL Experience Cloud]. L’organisation correspond le plus souvent au nom de votre société. Toutefois, une société peut détenir plusieurs organisations.

Sélectionnez l’organisation souhaitée dans la liste déroulante [!UICONTROL Organization] si votre société comporte plusieurs organisations :

![Liste déroulante Organisation](/help/main/c-intro/assets/organizations.png)

### [!UICONTROL Beta Feedback]

(Conditionnel) Si vous faites partie d’un programme [!DNL Target] Beta officiel, l’icône [!UICONTROL Beta Feedback] s’affiche.

![Icône Commentaires Beta](/help/main/c-intro/assets/beta-feedback.png)

Fournissez une description pour vos commentaires, incluez les fichiers ou les captures d’écran applicables et tout autre détail supplémentaire, si nécessaire, puis cliquez sur **[!UICONTROL Submit]**.

### [!DNL AI Assistant] (sortie prévue le 20 mai 2025)

(Conditionnel) Si votre entreprise vous a accordé des droits d’utilisation de l’assistant AI, cliquez sur l’icône de l’assistant AI.

### Aide

L’icône d’aide vous permet d’accéder à des informations, des vidéos, des blogs et bien plus encore pour vous aider à utiliser [!DNL Target] plus efficacement. Vous pouvez créer un ticket d’assistance, trouver des numéros de téléphone d’assistance, poser des questions sur Twitter ou laisser des commentaires sur [!DNL Target] pour nous faire part de l’état de l’équipe d’[!DNL Target].

![Aide](/help/main/c-intro/assets/help.png)

### Notifications et annonces {#notifications-announcements}

Les panneaux [!UICONTROL Notifications] et [!UICONTROL Announcements] vous permettent de rester informé sur tout ce qui [!DNL Adobe Target]. Les notifications proactives vous permettent de connaître l’état des solutions [!DNL Adobe Experience Cloud] et des événements [!DNL Target]. Les annonces proactives vous avertissent des événements de panne et de maintenance.

Cliquez sur l’icône représentant une cloche dans l’en-tête pour afficher les notifications :

![Icône cloche pour les notifications et les annonces](assets/bell-icon.png)

Le panneau contient des onglets pour [!UICONTROL Notifications] et [!UICONTROL Announcements].

![Notifications](assets/notifications.png)

Les sections suivantes contiennent des informations sur chaque onglet et sur la configuration des notifications et des annonces :

#### Notifications {#notifications}

Les notifications d’événement [!DNL Target] incluent les éléments suivants :

* **Activités** : notifications pour tous les types d’activité lorsqu’une activité est approuvée ou désactivée, manuellement ou lorsqu’elle atteint sa date de début ou de fin. La notification inclut le nom de l’activité avec un lien vers sa page d’aperçu.

  Les notifications sont configurables et sont reçues, par défaut, par les administrateurs de produit, les éditeurs et les approbateurs dans l’espace de travail de l’activité pour les comptes [!DNL Target Premium]. Pour les comptes [!DNL Target Standard], les notifications sont reçues par tous les éditeurs et approbateurs.

  Les notifications sont formatées comme suit :

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Scripts de profil** : notifications lorsqu’un script de profil est activé ou désactivé, manuellement ou par [!DNL Target].

  Les notifications sont configurables et sont reçues, par défaut, par les administrateurs et les approbateurs de produit pour les comptes [!DNL Target Premium] et [!DNL Target Standard].

  Les notifications sont formatées comme suit :

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Flux de recommandations** : notifications lorsqu’un flux de [!DNL Recommendations] est activé ou désactivé, manuellement ou par [!DNL Target]. Des notifications sont également envoyées lorsqu’un flux de [!DNL Recommendations] échoue.

  Les notifications sont configurables et sont reçues, par défaut, par les administrateurs et les approbateurs de produit pour les comptes [!DNL Target Premium]. [!DNL Recommendations] est une fonctionnalité [!DNL Target Premium] et n’est pas disponible dans [!DNL Target Standard].

  Les notifications sont formatées comme suit :

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Vous pouvez marquer les notifications individuelles comme lues en pointant sur la notification souhaitée, puis en cliquant sur la coche. Vous pouvez marquer toutes les notifications comme lues ou les afficher en cliquant sur [!UICONTROL "Mark as Read"] ou [!UICONTROL "View All"] au bas du panneau.

Vous pouvez également définir un rappel pour recevoir une nouvelle notification en pointant sur une notification, en cliquant sur l’icône « [!UICONTROL Remind me] », puis en sélectionnant le moment où vous souhaitez recevoir une notification : 5 minutes, 15 minutes, une heure ou demain.

#### Annonces

Les annonces proactives vous avertissent des événements de panne et de maintenance.

Vous trouverez des informations plus détaillées sur la page [Statut d’Adobe](https://status.adobe.com/fr).

### Configuration des notifications et des annonces

Pour modifier vos préférences de notifications :

1. Cliquez sur l’icône d’engrenage, puis sur **[!UICONTROL Notifications]**.
1. Sous **[!UICONTROL Target]**, cliquez sur **[!UICONTROL Customize]**.
1. Sélectionnez ou désélectionnez les catégories pour lesquelles vous souhaitez recevoir des notifications :

   * Demandes : lorsqu’une personne vous envoie une demande pour approuver un objet ou pour accorder l’accès à un objet. Impossible de se désabonner de cette catégorie.
   * Affecté à moi : lorsqu’un utilisateur vous affecte un objet.
   * Mentions : lorsqu’une personne vous mentionne dans un commentaire.
   * Nouvelles versions : lorsqu’une nouvelle version est disponible pour un produit ou un service auquel vous avez accès.
   * Partagé avec moi : lorsque quelqu’un partage un objet avec vous.
   * Mises à jour sur le contenu : lorsqu’une personne modifie, supprime ou commente un objet que vous avez créé ou suivi.
   * Autres :

   >[!NOTE]
   >
   >Les catégories « Nouvelles versions » et « Mises à jour de contenu » sont les seules catégories de notification qui s’appliquent à [!DNL Target]. Les autres catégories s’appliquent aux autres solutions Adobe.

1. Sélectionnez les catégories qui doivent être considérées comme prioritaires.
1. Sélectionnez les notifications pour lesquelles vous souhaitez afficher des alertes dans votre navigateur.

   Ces alertes s’affichent dans le coin supérieur droit de votre navigateur pendant quelques secondes. Vous pouvez choisir d’afficher les catégories à priorité élevée, toutes les catégories ou de masquer tous les pop-ups de notification. Vous pouvez également configurer si vous souhaitez que les notifications restent visibles jusqu’à ce que vous les ignoriez ou configurer la durée de la notification.

1. Sélectionnez la fréquence à laquelle vous souhaitez recevoir les e-mails de notification :

   * Ne pas envoyer d’e-mails
   * Notifications instantanées
   * Envoi quotidien
   * Envoi hebdomadaire

### Sélecteur d’applications

Le sélecteur d’applications vous permet d’accéder rapidement aux solutions [!DNL Adobe Experience Cloud] auxquelles vous avez accès.

![Sélecteur d’applications](/help/main/c-intro/assets/apps.png)

### Profil

Cliquez sur l’avatar de votre profil pour modifier vos préférences [!DNL Adobe Experience Cloud] ou pour vous déconnecter de [!DNL Target]. Vous pouvez également accéder à votre profil [!DNL Adobe] ou le modifier.

![Avatar du profil](/help/main/c-intro/assets/change-language.png)

Examinons maintenant les onglets situés sur le côté gauche de l’en-tête [!DNL Target].

## Activités

La liste **[!UICONTROL Activities]** est la vue par défaut lorsque vous ouvrez [!DNL Target]. Vous pouvez créer des activités à partir de cette page et gérer les activités existantes.

![Liste des activités](/help/main/c-intro/assets/activities-list.png)

Consultez [Activités](/help/main/c-activities/activities.md) pour obtenir des informations détaillées sur les types d’activités disponibles dans [!DNL Target] et pour en savoir plus sur l’interface utilisateur de la liste [!UICONTROL Activity].

## Audiences

Cliquez sur l’onglet **[!UICONTROL Audiences]** pour afficher la liste [!UICONTROL Audiences] dans laquelle vous pouvez créer des audiences et gérer les audiences existantes.

![Liste des audiences](/help/main/c-intro/assets/audience-list.png)

Une audience est un groupe de participants à une activité similaire qui voient une activité ciblée. Une audience est un groupe de personnes ayant les mêmes caractéristiques, telles qu’un nouveau visiteur, un visiteur récurrent ou des visiteurs récurrents du Midwest. La fonctionnalité [!UICONTROL Audience] vous permet de cibler différents contenus et expériences selon les audiences, afin d’optimiser votre marketing numérique en affichant les messages adéquats aux personnes appropriées et au moment opportun. Si un visiteur est identifié comme faisant partie d’une audience cible, [!DNL Target] détermine l’expérience à afficher, en fonction des critères définis lors de la création de l’activité.

Voir [Création d’audiences](/help/main/c-target/c-audiences/create-audience.md) pour obtenir des informations détaillées sur les types d’audiences dans [!DNL Target] et pour en savoir plus sur l’interface utilisateur de la liste [!UICONTROL Audience].

## Offres

Cliquez sur l’onglet **[!UICONTROL Offers]** pour afficher la liste [!UICONTROL Offers] dans laquelle vous pouvez créer des expériences et des offres et gérer les expériences et offres existantes.

![Liste des offres](/help/main/c-intro/assets/offers.png)

Une expérience peut être une offre, une image, un texte, un bouton, une vidéo, une combinaison de ces différents éléments sur une page, une page Web entière ou un ensemble de pages qui peut éventuellement former un tunnel de vente ou une autre séquence logique de pages. Il peut également s’agir de la réponse d’un assistant vocal, d’un script de service à la clientèle ou même d’une saveur personnalisée provenant d’un distributeur de boissons. Vous pouvez tester ou personnaliser des expériences dans les activités [!DNL Target].

Consultez [Offres](/help/main/c-experiences/c-manage-content/manage-content.md) pour obtenir des informations détaillées sur les types d’offres dans [!DNL Target] et pour en savoir plus sur l’interface utilisateur de la liste [!UICONTROL Offer].

## Recommendations

Cliquez sur l’onglet **[!UICONTROL Recommendations]** pour accéder aux [!DNL Target Recommendations].

>[!NOTE]
>
>Les activités Recommendations sont disponibles dans le cadre de la solution [!DNL Target Premium]. Elles ne sont pas disponibles dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations, consultez [Target Premium](/help/main/c-intro/intro.md#premium) dans *Présentation de Target*.

![Recommendations](/help/main/c-intro/assets/recommendations.png)

Les activités [!UICONTROL Recommendations] affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes. Recommendations permet d’orienter les clients vers des éléments pertinents qu’ils ne connaîtraient pas autrement.

Consultez [Recommendations](/help/main/c-recommendations/recommendations.md) pour obtenir des informations détaillées sur les [!UICONTROL Recommendations] dans [!DNL Target] et pour en savoir plus sur l’interface utilisateur de [!UICONTROL Recommendations].

## Administration

Cliquez sur l’onglet **[!UICONTROL Administration]** pour accéder aux pages [!UICONTROL Administration].

![Pages Administration](/help/main/c-intro/assets/administration.png)

Les pages [!UICONTROL Administration] vous permettent d’administrer des [!DNL Target], notamment les paramètres de configuration du [!UICONTROL Visual Experience Composer] (VEC), les rapports, la configuration [!DNL Scene7], l’implémentation, les hôtes, les environnements, les jetons de réponse et les utilisateurs.

Consultez [Aperçu de l’administration dans Target](/help/main/administrating-target/administrating-target.md) pour obtenir des informations détaillées et en savoir plus sur l’interface utilisateur.
