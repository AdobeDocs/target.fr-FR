---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des prochaines versions de l’Adobe Target DNL.
title: Notes de mise à jour des Adobes Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a6bcaac474927ddd0a14d4cb274c0460e6002a9b
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 15%

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 24 juin 2020**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!NOTE]
>
>* **Dépréciation** de mbox.js : Le 30 août 2020, l’Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités de Cible sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir Fonctionnement [d’At.js et Créateur de compétences en](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) [Adobe Target : Chat de développeur, mbox.js d’Adobe Target migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance seront en mesure de vous fournir de nouvelles fonctionnalités et d&#39;offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de Cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d’informations, voir Annonces [de](/help/r-release-notes/target-announcements.md)Cible.


## Target Standard/Premium 20.6.1 (juillet 2020, date exacte à déterminer)

Les améliorations suivantes ont été apportées à cette version :

### Prise en charge d’Analytics pour Cible (A4T) pour les activités de Cible  automatique

[!UICONTROL Les activités de Cible] automatique prennent désormais en charge [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md).

Cette intégration utilise l’apprentissage automatique avancé pour effectuer un choix parmi plusieurs expériences hautement performantes définies par le spécialiste du marketing afin de personnaliser le contenu et de générer des conversions. Le ciblage automatique offre à chaque visiteur l’expérience la plus personnalisée en fonction de son profil individuel et du comportement des visiteurs précédents avec des profils similaires.

Si vous avez déjà [mis en oeuvre A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) pour l’utiliser avec les activités de test A/B, vous êtes prêt !

### [!UICONTROL Actualisation de l’interface utilisateur de la section Administration]

Nous réécrivons progressivement l’ensemble de l’ [!DNL Target] interface utilisateur à l’aide d’une nouvelle pile technologique afin de pouvoir offre des performances améliorées, réduire le temps de maintenance requis lors de la publication de nouvelles fonctionnalités et améliorer l’expérience utilisateur sur l’ensemble du produit. La première section actualisée est la section [!UICONTROL Configuration] , qui a été renommée [!UICONTROL Administration].

Dans le cadre de cette actualisation, vous pourrez exécuter facilement de nombreuses actions à l’aide des pages de la section [!UICONTROL Administration] , telles que :

* Téléchargez le dernier fichier at.js depuis l’onglet [!UICONTROL Implémentation] (**[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**).
* Personnalisez vos paramètres at.js et vérifiez facilement vos modifications (**[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**).
* Modifiez les paramètres de rapports améliorés, tels que la devise et le fuseau horaire par défaut, les adresses IP à exclure du rapports, etc. (**[!UICONTROL Administration]** > **[!UICONTROL Rapports]**)
* Obscurcir les adresses IP du visiteur pour des raisons de confidentialité (**[!UICONTROL Administration]** > **[!UICONTROL Mise en oeuvre]**)
* Vue de la liste existante des utilisateurs par espace de travail et de leurs rôles, avant de les gérer dans Adobe (**[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]**).
* Recherchez et filtrez tous les tableaux de la section [!UICONTROL Administration] .

Les changements importants incluent :

* **[!UICONTROL Page]**du compositeur d’expérience visuelle : Cette nouvelle page (**[!UICONTROL Administration ]**> Compositeur**[!UICONTROL d’expérience ]**visuelle) vous permet d’effectuer les opérations suivantes :

   * Configurez les paramètres généraux du compositeur d’expérience visuelle (spécifiez l’URL par défaut, activez le compositeur [!UICONTROL d’expérience]amélioré, chargez du contenu mixte et générez des instantanés d’expérience dans le diagramme de flux d’activité).
   * Configuration des fenêtres d’affichage mobiles
   * Configuration des sélecteurs CSS

* **[!UICONTROL Page]de Rapports **: Cette nouvelle page (**[!UICONTROL Administration ]**>**[!UICONTROL Rapports ]**) vous permet de configurer les paramètres généraux à utiliser dans les[!DNL Target]rapports qui s’appliquent à l’intégralité de votre[!DNL Target]compte.

   Les paramètres disponibles sont les suivants :

   * La [!DNL Adobe Experience Cloud] solution à utiliser pour le rapports
   * Fuseau horaire à utiliser pour le rapports
   * Devise à utiliser pour le rapports
   * Adresses IP à exclure du rapports
   * Indique si l&#39;effet élévateur estimé des recettes doit être affiché dans le rapports
   * Autoriser ou non des priorités affinées

* La page [!UICONTROL Hôtes] précédente a été fractionnée en deux nouvelles pages :

   * [!UICONTROL Hôtes]
   * [!UICONTROL Environnements]

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
