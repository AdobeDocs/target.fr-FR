---
keywords: prévisualiser une expérience;url d’expérience;générer des url;afficher les url d’expérience
description: Découvrez comment utiliser les URL de prévisualisation d’expérience pour les activités Automated Personalization Adobe Target pour afficher le contenu d’expérience directement sur votre site avant que l’activité ne soit activée.
title: Comment puis-je utiliser les URL de la Prévisualisation d’expériences dans les Activités Automated Personalization ?
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 65%

---


# ![](/help/assets/premium.png) PREMIUMPrévision des activités Automated Personalization avec des URL de prévisualisation d’expérience

Des URL de prévisualisation d’expérience peuvent être générées pour les activités Automated Personalization de Cible afin d’afficher le contenu d’expérience directement sur votre site avant que l’activité ne soit activée à des fins de prévisualisation et d’assurance qualité. Les URL de la prévisualisation d’expérience contournent le ciblage pour forcer l’affichage d’une expérience particulière.

>[!NOTE]
>
>Les URL de prévisualisation d’expérience pour Automated Personalization diffèrent du mode d’assurance qualité de l’Activité. Le mode AQ de l’activité permet de créer des URL d’activité pour d’autres types d’activités. Pour plus d’informations, voir [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md)..
>
>Les URL de prévisualisation d’expérience pour les activités AP ne sont disponibles que lors de l’utilisation d’at.js 1.x. Les URL de prévisualisation d’expérience pour les activités AP ne sont actuellement pas prises en charge pour at.js 2.x.

Utilisez les URL de prévisualisation d’expérience pour partager des expériences avec les membres de l’équipe et pour effectuer un contrôle qualité des expériences sur les navigateurs et les environnements, sans créer d’activité d’assurance qualité distincte. Cette fonctionnalité s’avère particulièrement utile en cas de site complexe ou lorsque les stratégies de sécurité n’autorisent pas l’affichage du site dans un simulateur.

1. Créer une [activité Automated Personalization](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou cliquez sur l’activité pour l’ouvrir.

   Il n’est pas nécessaire qu’une activité soit active pour prévisualiser une expérience.
1. Sur la page récapitulative de l’activité, cliquez sur les trois points alignés verticalement, puis sur **[!UICONTROL Afficher les URL d’Experience]**.
1. Passez en revue et/ou spécifiez vos adresses URL.

   * Si vous utilisez le compositeur d’expérience visuelle, l’URL par défaut spécifiée pour l’activité est entrée automatiquement et un lien est généré pour chaque expérience contenue dans votre activité. Vous pouvez modifier cette URL et en ajouter d’autres si vous le souhaitez.
   * Si vous utilisez le compositeur d’expérience d’après les formulaires, aucune URL par défaut ne sera automatiquement renseignée. Si vous n’avez pas encore créé d’URL de prévisualisation d’expérience, cliquez sur **Ajouter une URL**. Vous devez spécifier toutes les URL que vous souhaitez prévisualiser, ainsi qu’un nom pour chacune d’elles.

   Vous pouvez ajouter plusieurs URL, ce qui s’avère utile lorsque vous effectuez un test multi-page ou de modèle et que vous souhaitez prévisualiser l’activité de plusieurs pages.

   Une fenêtre modale affiche des liens vers les expériences de votre site pour obtenir un « véritable aperçu » des expériences en dehors du compositeur d’expérience visuelle de Target. Vous devez partager les liens provenant du message pour partager l’aperçu. Le fait de cliquer sur un lien, puis de copier l’URL qui en résulte depuis la page ne fonctionnera pas car l’URL contient un paramètre qui n’affiche la page correctement que lorsque vous accédez à la page depuis le lien contenu dans le message. Copiez plutôt le texte dans la fenêtre modale et envoyez l’ensemble du texte à votre équipe par courrier électronique.
1. Cliquez sur **[!UICONTROL Générer tout]**, puis cliquez sur chaque expérience pour la prévisualiser.

   Si vous apportez ensuite des modifications à l’expérience, veillez à générer de nouveaux liens de prévisualisation pour votre équipe en revenant à la fenêtre modale et en cliquant sur **Renouveler les liens** pour obtenir de nouveaux liens.

   **Remarque :** Les liens d’aperçu s’ouvrent dans de nouveaux onglets et nécessitent la désactivation du bloqueur de fenêtres contextuelles dans votre navigateur.

1. Cliquez sur le nom de chaque expérience pour prévisualiser l’activité.

   La page s’ouvre, affichant l’activité.
1. Cliquez sur **[!UICONTROL Terminé]** pour revenir au récapitulatif de l’activité.

## Considérations {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Génération d’URL de Prévisualisation d’expérience**

* L’URL de la prévisualisation d’expériences n’est pas affectée par la division du trafic entre les expériences.
* Le ciblage au niveau des audiences n’affecte pas l’aperçu.
* Vous pouvez générer automatiquement un maximum de 300 URL d’expérience par activité. Au-delà, vous devez générer les URL manuellement.
* Vous pouvez générer automatiquement un maximum de 300 URL d’expérience par activité. Au-delà, vous devez générer les URL manuellement.
* Selon le nombre d’expériences, la génération des URL peut prendre jusqu’à cinq minutes. Ne fermez pas la boîte de dialogue, sinon les URL générées seront perdues.
* Les liens d’aperçu générés sont valides pendant deux mois. Au-delà, vous devez les générer à nouveau.
* Vous devez générer à nouveau les liens à chaque modification d’expérience.

**Partage des URL de la Prévisualisation d’expériences**

* Vous pouvez prévisualiser une expérience même si vous n’appartenez pas à l’audience ciblée.
* Vous pouvez partager des URL de prévisualisation d’expérience avec des collègues qui n’ont pas accès à Adobe Target.

**Affichage d’expériences avec des URL de Prévisualisation d’expérience**

* L’aperçu peut être utilisé pour les activités enregistrées tant que la page n’a pas été modifiée.
* L’URL de la prévisualisation d’expériences est disponible que l’activité soit principale ou inactive.
* Vous ne pouvez pas prévisualisation une expérience dont l’état est Brouillon.
* Le rapports n’est pas affecté par l’affichage des URL de prévisualisation d’expérience.

**Dépannage des URL d’Experience Prévisualisation**

* Si vous ne parvenez pas à accéder à l’aperçu dans le nouvel onglet (en raison du cache du navigateur), essayez d’actualiser la page deux ou trois fois ou copiez le lien et ouvrez-le dans un nouveau navigateur, une nouvelle session ou un mode de navigation privé.
