---
keywords: experience preview;experience urls;generate urls;view experience urls
description: Les URL d’expérience peuvent être générées pour chaque activité Automated Personalization de Target et permettent d’afficher le contenu de l’expérience directement sur votre site avant que l’activité ne soit activée à des fins d’aperçu et d’assurance qualité (AQ). Les URL d’Experience contournent le ciblage afin de forcer l’affichage d’une expérience spécifique.
title: Partage des URL d’Experience pour la prévisualisation d’Automated Personalization en dehors de Target
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
translation-type: tm+mt
source-git-commit: 533a2aac50ceb085b090ad5f9d7b1fff396c2de4

---


# ![PREMIUM](/help/assets/premium.png) Partage des URL d’Expérience pour la prévisualisation de la personnalisation automatisée en dehors de Target{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

Les URL d’expérience peuvent être générées pour chaque activité Automated Personalization de Target et permettent d’afficher le contenu de l’expérience directement sur votre site avant que l’activité ne soit activée à des fins d’aperçu et d’assurance qualité (AQ). Les URL d’Experience contournent le ciblage afin de forcer l’affichage d’une expérience spécifique.

>[!NOTE]
>
>Le mode AQ de l’activité permet de créer des URL d’activité pour d’autres types d’activités. Pour plus d’informations, voir [AQ d’activité](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40).

.

Pour utiliser les URL d’Experience, vous devez partager les liens générés dans Target, et non l’URL finale sur laquelle vous débouchez lors de l’affichage de l’expérience. D’autre part, lorsque le contenu est modifié, de nouvelles URL doivent être générées. La génération de nouvelles URL peut mettre fin au fonctionnement des anciennes URL.

Utilisez les URL d’expérience pour partager des expériences avec les membres de votre équipe et contrôler la qualité de celles-ci au niveau des navigateurs et des environnements, sans même devoir créer d’activité de contrôle qualité indépendante. Cette fonctionnalité s’avère particulièrement utile en cas de site complexe ou lorsque les stratégies de sécurité n’autorisent pas l’affichage du site dans un simulateur.

1. Créer une [activité Automated Personalization](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou cliquez sur l’activité pour l’ouvrir.

   Il n’est pas nécessaire qu’une activité soit active pour prévisualiser une expérience.
1. Sur la page récapitulative de l’activité, cliquez sur les trois points alignés verticalement, puis sur **[!UICONTROL Afficher les URL d’Experience]**.
1. Passez en revue et/ou spécifiez vos adresses URL.

   * Si vous utilisez le compositeur d’expérience visuelle, l’URL par défaut spécifiée pour l’activité est entrée automatiquement et un lien est généré pour chaque expérience contenue dans votre activité. Vous pouvez modifier cette URL et en ajouter d’autres si vous le souhaitez.
   * Si vous utilisez le compositeur d’expérience d’après les formulaires, aucune URL par défaut ne sera automatiquement renseignée. Si vous n’avez encore créé aucune URL d’Experience, cliquez sur **Ajouter une nouvelle URL**. Vous devez spécifier toutes les URL que vous souhaitez prévisualiser, ainsi qu’un nom pour chacune d’elles.
   Vous pouvez ajouter plusieurs URL, ce qui s’avère utile lorsque vous effectuez un test multi-page ou de modèle et que vous souhaitez prévisualiser l’activité de plusieurs pages.

   Une fenêtre modale affiche des liens vers les expériences de votre site pour obtenir un « véritable aperçu » des expériences en dehors du compositeur d’expérience visuelle de Target. Vous devez partager les liens provenant du message pour partager l’aperçu. Le fait de cliquer sur un lien, puis de copier l’URL qui en résulte depuis la page ne fonctionnera pas car l’URL contient un paramètre qui n’affiche la page correctement que lorsque vous accédez à la page depuis le lien contenu dans le message. Copiez plutôt le texte dans la fenêtre modale et envoyez l’ensemble du texte à votre équipe par courrier électronique.
1. Cliquez sur **[!UICONTROL Générer tout]**, puis cliquez sur chaque expérience pour la prévisualiser.

   If you then make changes to the experience, make sure to generate new preview links for your team by returning to the modal window and clicking **Renew Links** to get new links.

   **Remarque :** Les liens d’aperçu s’ouvrent dans de nouveaux onglets et nécessitent la désactivation du bloqueur de fenêtres contextuelles dans votre navigateur.

1. Cliquez sur le nom de chaque expérience pour prévisualiser l’activité.

   La page s’ouvre, affichant l’activité.
1. Cliquez sur **[!UICONTROL Terminé]** pour revenir au récapitulatif de l’activité.

## Considérations {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Génération des URL d’expérience**

* L’URL d’expérience n’est pas affectée par la répartition du trafic entre les expériences.
* Le ciblage au niveau des audiences n’affecte pas l’aperçu.
* Vous pouvez générer automatiquement un maximum de 300 URL d’expérience par activité. Au-delà, vous devez générer les URL manuellement.
* Vous pouvez générer automatiquement un maximum de 300 URL d’expérience par activité. Au-delà, vous devez générer les URL manuellement.
* Selon le nombre d’expériences, la génération des URL peut prendre jusqu’à cinq minutes. Ne fermez pas la boîte de dialogue, sinon les URL générées seront perdues.
* Les liens d’aperçu générés sont valides pendant deux mois. Au-delà, vous devez les générer à nouveau.
* Vous devez générer à nouveau les liens à chaque modification d’expérience.

**Partage des URL d’expérience**

* Vous pouvez prévisualiser une expérience même si vous n’appartenez pas à l’audience ciblée.
* Vous pouvez partager les URL d’Experience avec ceux de vos collègues qui n’ont pas accès à Adobe Target.

**Affichage des expériences via leur URL d’expérience**

* L’aperçu peut être utilisé pour les activités enregistrées tant que la page n’a pas été modifiée.
* L’URL d’expérience est disponible que l’activité soit active ou inactive.
* Il n’est pas possible d’afficher l’aperçu d’une expérience ayant un état Brouillon
* La génération de rapports n’est pas affectée par la prévisualisation des URL d’Experience.

**Résolution des problèmes des URL d’Experience**

* Si vous ne parvenez pas à accéder à l’aperçu dans le nouvel onglet (en raison du cache du navigateur), essayez d’actualiser la page deux ou trois fois ou copiez le lien et ouvrez-le dans un nouveau navigateur, une nouvelle session ou un mode de navigation privé.
* Que vous effectuiez votre propre contrôle qualité de l’activité ou que vous transfériez ces liens vers une autre équipe, vous pouvez facilement afficher un aperçu d’expériences spécifiques sans configurer de tests distincts.

