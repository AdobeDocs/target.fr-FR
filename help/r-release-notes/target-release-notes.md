---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs des dernières versions ou des prochaines versions de l’Adobe Target DNL.
title: Notes de mise à jour des Adobes Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a55aeb18e86a4428187faa5ecba6c66d11feda6d
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 14%

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 17 juin 2020**

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


## Target Standard/Premium 20.5.1 (17 juin 2020)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Analytics for Target (A4T) prise en charge des activités d’affectation  automatique | [!UICONTROL Les activités d’affectation] automatique prennent désormais en charge [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Cette intégration vous permet d’utiliser la fonctionnalité d’affectation  automatique de bandit à plusieurs bras pour diriger le trafic vers des expériences gagnantes, tout en utilisant une mesure d’objectif Analytics  Adobe [!UICONTROL et/ou des fonctionnalités d’analyse et de rapports] Adobe Analytics.<br>Si vous avez déjà [mis en oeuvre A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) pour l’utiliser avec les activités de test A/B et de ciblage d’expérience, vous êtes prêt à le faire !<br>Pour plus d’informations, voir Prise en charge des activités [d’affectation](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) automatique dans la création *d’* Activités dans Analytics for Cible (A4T). |
| Jetons de réponse pour la méthode d’affectation du trafic pour les activités de Cible automatique et de personnalisation automatisée | Deux jetons [de](/help/administrating-target/response-tokens.md) réponse ont été ajoutés aux activités de la Cible  automatique et de la personnalisation  automatisée pour permettre de déterminer si un visiteur a reçu une expérience particulière du fait d’avoir été affecté au &quot;contrôle&quot; ou au trafic &quot;ciblé&quot;.<ul><li>`experience.trafficAllocationId` renvoie 0 si un visiteur a reçu une expérience provenant d’un trafic de &quot;contrôle&quot; et 1 si un visiteur a reçu une expérience provenant de la distribution de trafic &quot;ciblée&quot;.</li><li>`experience.trafficAllocationType` renverra &quot;contrôle&quot; ou &quot;ciblé&quot;.</li></ul>Pour plus d’informations sur le contrôle par rapport au trafic ciblé, voir [Sélectionner le contrôle pour votre personnalisation automatisée ou votre activité](/help/c-activities/t-automated-personalization/experience-as-control.md)d’Cible automatique. |
| [!UICONTROL Rôle Editeur] | Ce nouveau rôle est similaire au rôle actuel d’ [!UICONTROL observateur] (peut vue des activités, mais ne peut pas les créer ni les modifier). Toutefois, le rôle [!UICONTROL Editeur] dispose des autorisations supplémentaires nécessaires pour activer les activités.<br>Pour plus d’informations, voir : <ul><li>**utilisateurs** Target Standards : [Spécifiez des rôles et des autorisations](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*.</li><li>**Utilisateurs** de Cible Premium : [Étape 6 : Spécifiez les rôles et les autorisations](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) dans *Configuration des autorisations* d’entreprise.</li></ul> |
| Prise en charge d’A4T le 25 [!DNL Analysis Workspace]<br>juin 2020 | [!UICONTROL Les analyses pour la Cible] (A4T) sont désormais prises en charge dans [!DNL Analysis Workspace]. Le panneau  Analytics for Cible (A4T) vous permet d’analyser vos [!DNL Adobe Target] activités et expériences dans [!DNL Analysis Workspace].<br>Pour plus d’informations, reportez-vous à la section [Rapports en Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) dans le rapports ** A4T et dans le panneau [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics for Cible (A4T) du *Analytics Tools Guide.* |

### Améliorations, correctifs et modifications

* Correction d’un problème en raison duquel la mesure &quot;visiteurs&quot; était stockée dans la définition de la activité au lieu de &quot;Visiteurs uniques&quot;. (TGT-37098)
* Correction d’un problème dans l’ [!DNL Target] interface utilisateur en raison duquel la barre de défilement verticale ne fonctionnait pas correctement sur la page [!UICONTROL Audiences] . (TGT-36968)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
