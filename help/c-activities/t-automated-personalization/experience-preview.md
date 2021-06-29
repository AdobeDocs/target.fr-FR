---
keywords: prévisualiser une expérience;url d’expérience;générer des url;afficher les url d’expérience
description: Découvrez comment utiliser les URL d’aperçu de l’expérience pour les activités Adobe [!DNL Target] Automated Personalization afin d’afficher le contenu de l’expérience directement sur votre site avant que l’activité ne soit activée.
title: Comment utiliser les URL d’aperçu d’expérience dans les activités Automated Personalization ?
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: 0d24bcf335980291891e3198a13ec283d1dd325f
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 50%

---

# ![](/help/assets/premium.png) PREMIUMPreview activités Automated Personalization avec URL d’aperçu de l’expérience

Les URL d’aperçu de l’expérience peuvent être générées pour les activités [!DNL Target] [!UICONTROL Automated Personalization] afin d’afficher le contenu de l’expérience directement sur votre site avant que l’activité ne soit activée à des fins d’aperçu et d’assurance qualité. Les URL d’aperçu de l’expérience contournent le ciblage pour forcer l’affichage d’une expérience particulière.

>[!NOTE]
>
>Vous pouvez créer des URL d’aperçu d’expérience pour d’autres types d’activités [!DNL Target]. Cependant, le processus est légèrement différent. Pour plus d’informations, voir [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md#preview)..

Utilisez les URL d’aperçu de l’expérience pour partager des expériences avec les membres de l’équipe et pour contrôler la qualité des expériences dans les navigateurs et les environnements, sans créer d’activité d’assurance qualité distincte. Cette fonctionnalité s’avère particulièrement utile en cas de site complexe ou lorsque les stratégies de sécurité n’autorisent pas l’affichage du site dans un simulateur.

1. Créer une [activité Automated Personalization](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou cliquez sur l’activité pour l’ouvrir.

   Il n’est pas nécessaire qu’une activité soit active pour prévisualiser une expérience.

1. Sur la page Aperçu de l’activité, cliquez sur les trois points verticaux, puis sur **[!UICONTROL Afficher les URL d’expérience]**.

1. Passez en revue et/ou spécifiez vos adresses URL.

   * Si vous utilisez le [!UICONTROL compositeur d’expérience visuelle] (VEC), l’URL par défaut que vous avez spécifiée pour l’activité est automatiquement saisie et un lien est généré pour chaque expérience de votre activité. Vous pouvez modifier cette URL et en ajouter d’autres si vous le souhaitez.
   * Si vous utilisez le [!UICONTROL compositeur d’expérience d’après les formulaires], aucune URL par défaut n’est saisie automatiquement. Si vous n’avez pas encore créé d’URL d’aperçu d’expérience, cliquez sur **Ajouter une nouvelle URL**. Vous devez spécifier toutes les URL que vous souhaitez prévisualiser, ainsi qu’un nom pour chacune d’elles.

   Vous pouvez ajouter plusieurs URL, ce qui s’avère utile lorsque vous effectuez un test multi-page ou de modèle et que vous souhaitez prévisualiser l’activité de plusieurs pages.

   Une fenêtre modale affiche des liens vers vos expériences sur votre site pour obtenir un &quot;véritable aperçu&quot; des expériences en dehors du [!DNL Target] VEC. Vous devez partager les liens provenant du message pour partager l’aperçu. Le fait de cliquer sur un lien, puis de copier l’URL qui en résulte depuis la page ne fonctionnera pas car l’URL contient un paramètre qui n’affiche la page correctement que lorsque vous accédez à la page depuis le lien contenu dans le message. Copiez plutôt le texte dans la fenêtre modale et envoyez l’ensemble du texte à votre équipe par courrier électronique.

1. Cliquez sur **[!UICONTROL Générer tout]**, puis cliquez sur chaque expérience pour la prévisualiser.

   Si vous apportez ensuite des modifications à l’expérience, veillez à générer de nouveaux liens d’aperçu pour votre équipe en revenant à la fenêtre modale et en cliquant sur **Renouveler les liens** pour obtenir de nouveaux liens.

   >[!NOTE]
   >
   >Les liens d’aperçu s’ouvrent dans de nouveaux onglets et nécessitent que le bloqueur de fenêtres contextuelles de votre navigateur soit désactivé.

1. Cliquez sur le nom de chaque expérience pour prévisualiser l’activité.

   La page s’ouvre, affichant l’activité.

1. Cliquez sur **[!UICONTROL Terminé]** pour revenir au récapitulatif de l’activité.

## Considérations {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Génération des URL d’aperçu de l’expérience**

* L’URL d’aperçu de l’expérience n’est pas affectée par la division du trafic entre les expériences.
* Le ciblage au niveau des audiences n’affecte pas l’aperçu.
* Vous pouvez générer automatiquement un maximum de 300 URL d’expérience par activité. Au-delà, vous devez générer les URL manuellement.
* Selon le nombre d’expériences, la génération des URL peut prendre jusqu’à cinq minutes. Ne fermez pas la boîte de dialogue ou les URL générées sont perdues.
* Les liens d’aperçu générés sont valides pendant deux mois. Au-delà, vous devez les générer à nouveau.
* Vous devez générer à nouveau les liens à chaque modification d’expérience.

**Partage des URL d’aperçu de l’expérience**

* Vous pouvez prévisualiser une expérience même si vous n’appartenez pas à l’audience ciblée.
* Vous pouvez partager des URL d’aperçu de l’expérience avec des collègues qui n’ont pas accès à [!DNL Adobe Target].

**Affichage d’expériences avec des URL d’aperçu d’expérience**

* L’aperçu peut être utilisé pour les activités enregistrées tant que la page n’a pas été modifiée.
* L’URL de prévisualisation de l’expérience est disponible que l’activité soit principale ou inactive.
* Vous ne pouvez pas prévisualiser une expérience dont l’état est [!UICONTROL Brouillon].
* La création de rapports n’est pas affectée par l’affichage des URL d’aperçu de l’expérience.

**Dépannage des URL d’aperçu d’expérience**

* Si vous ne parvenez pas à accéder à l’aperçu dans le nouvel onglet (en raison du cache du navigateur), essayez d’actualiser la page deux ou trois fois ou copiez le lien et ouvrez-le dans un nouveau navigateur, une nouvelle session ou un mode de navigation privé.
