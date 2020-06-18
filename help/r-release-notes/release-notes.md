---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: b25108284abbc44320fdceddd8ca155e2b800b3c
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 29%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

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


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Target Standard/Premium 20.5.1 (17 juin 2020)

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Analytics for Target (A4T) prise en charge des activités d’affectation  automatique | [!UICONTROL Les activités d’affectation] automatique prennent désormais en charge [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Cette intégration vous permet d’utiliser la fonctionnalité d’affectation  automatique de bandit à plusieurs bras pour diriger le trafic vers des expériences gagnantes, tout en utilisant une mesure d’objectif Analytics  Adobe [!UICONTROL et/ou des fonctionnalités d’analyse et de rapports] Adobe Analytics.<br>Si vous avez déjà [mis en oeuvre A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) pour l’utiliser avec les activités de test A/B et de ciblage d’expérience, vous êtes prêt à le faire !<br>Pour plus d’informations, voir Prise en charge des activités [d’affectation](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) automatique dans la création *d’* Activités dans Analytics for Cible (A4T). |
| Jetons de réponse pour la méthode d’affectation du trafic pour les activités de Cible automatique et de personnalisation automatisée | Deux jetons [de](/help/administrating-target/response-tokens.md) réponse ont été ajoutés aux activités de la Cible  automatique et de la personnalisation  automatisée pour permettre de déterminer si un visiteur a reçu une expérience particulière du fait d’avoir été affecté au &quot;contrôle&quot; ou au trafic &quot;ciblé&quot;.<ul><li>`experience.trafficAllocationId` renvoie 0 si un visiteur a reçu une expérience provenant d’un trafic de &quot;contrôle&quot; et 1 si un visiteur a reçu une expérience provenant de la distribution de trafic &quot;ciblée&quot;.</li><li>`experience.trafficAllocationType` renverra respectivement &quot;contrôle&quot; et &quot;ciblé&quot;.</li></ul>Pour plus d’informations sur le contrôle par rapport au trafic ciblé, voir [Sélectionner le contrôle pour votre personnalisation automatisée ou votre activité](/help/c-activities/t-automated-personalization/experience-as-control.md)d’Cible automatique. |
| [!UICONTROL Rôle Editeur] | Ce nouveau rôle est similaire au rôle actuel d’ [!UICONTROL observateur] (peut vue des activités, mais ne peut pas les créer ni les modifier). Toutefois, le rôle [!UICONTROL Editeur] dispose des autorisations supplémentaires nécessaires pour activer les activités.<br>Pour plus d’informations, voir : <ul><li>**utilisateurs** Target Standards : [Spécifiez des rôles et des autorisations](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*.</li><li>**Utilisateurs** de Cible Premium : [Étape 6 : Spécifiez les rôles et les autorisations](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) dans *Configuration des autorisations* d’entreprise.</li></ul> |
| Prise en charge d’A4T le 25 [!DNL Analysis Workspace]<br>juin 2020 | [!UICONTROL Les analyses pour la Cible] (A4T) sont désormais prises en charge dans [!DNL Analysis Workspace]. Le panneau  Analytics for Cible (A4T) vous permet d’analyser vos [!DNL Adobe Target] activités et expériences dans [!DNL Analysis Workspace].<br>Pour plus d’informations, reportez-vous à la section [Rapports en Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) dans le rapports ** A4T et dans le panneau [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics for Cible (A4T) du *Analytics Tools Guide.* |

### Améliorations, correctifs et modifications

* Correction d’un problème en raison duquel la mesure &quot;visiteurs&quot; était stockée dans la définition de la activité au lieu de &quot;Visiteurs uniques&quot;. (TGT-37098)
* Correction d’un problème dans l’ [!DNL Target] interface utilisateur en raison duquel la barre de défilement verticale ne fonctionnait pas correctement sur la page [!UICONTROL Audiences] . (TGT-36968)

## versions d’at.js 1.8.2 et d’at.js 2.3.1 (15 juin 2020)

Les améliorations et correctifs suivants ont été apportés aux bibliothèques [!DNL Target] at.js :

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Paramètres at.js 1.8.2 | Cette version d’at.js est une version de maintenance et comprend les correctifs suivants :<ul><li>Correction d’un problème lors de l’utilisation de CNAME et du remplacement de bord, at.js 1.*x* peut créer de manière incorrecte le domaine du serveur, ce qui entraîne l’échec de la [!DNL Target] demande. (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| Paramètres at.js 2.3.1 | Cette version d’at.js est une version de maintenance qui comprend les améliorations et correctifs suivants :<ul><li>Possibilité de remplacer le `deviceIdLifetime` paramètre par [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)</li><li>Correction d’un problème lors de l’utilisation de CNAME et du remplacement de bord, at.js 2.*x* peut créer de manière incorrecte le domaine du serveur, ce qui entraîne l’échec de la [!DNL Target] demande. (TNT-35065)</li><li>Correction d’un problème lors de l’utilisation de l’ [!DNL Target] extension v2 et de l’ [!DNL Launch] extension, qui entraînait [!DNL Adobe Analytics] le report de l’ [!DNL Launch][!DNL Target] [!DNL Analytics] `sendBeacon` appel. (TNT-36407, TNT-35990, TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur du Adobe Target. |
| [Notes de mise à jour - SDK Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js Adobe Target. |
| [Notes de mise à jour - Cible Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java de l’Adobe Target. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js de l’Adobe Target. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour des](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
