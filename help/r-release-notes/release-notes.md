---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 21%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!NOTE]
>
>* **Dépréciation** de mbox.js : Le 30 août 2020, Adobe Cible ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités de Cible sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Voir *Adobe Cible Skill Builder : Chat de développeur, migrez le fichier mbox.js de la Cible Adobe vers at.js* ci-dessous pour plus d’informations.
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et le personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et offre l’assistance qu’Adobe vous a proposée.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Adobe Cible Skill Builder : Chat de développeur, migrer le fichier mbox.js de la Cible Adobe vers at.js {#skill-builder}

Avec la prochaine désapprobation de mbox.js, le 30 août 2020, David Son, responsable de produit Adobe Cible, a récemment hébergé une discussion pour les développeurs afin de discuter des avantages de la migration de mbox.js vers at.js. Pendant les 30 prochains jours, vous pouvez [vue l’enregistrement](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)du webinaire.

## Cible d’at.js (25 mars 2020)

Les nouvelles versions suivantes des bibliothèques JavaScript at.js de Cible sont disponibles :

* at.js version 2.3.0
* at.js version 1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 mars 2020)

>[!IMPORTANT]
>
>Reportez-vous aux informations ci-dessus sur la désapprobation de mbox.js.

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait les clients de sélectionner une collection lors de l’exécution d’une recherche de catalogue. (TGT-36230)
* Correction d’un problème en raison duquel un critère créé via l’API, mais non référencé par une activité créée dans l’interface utilisateur de la Cible, pouvait être supprimé par erreur de l’interface utilisateur. (TGT-35917)
* Amélioration de la sécurité mise en oeuvre de la stratégie de sécurité de contenu (CSP). (TGT-36190)
* Correction d’un problème en raison duquel &quot;NaN%&quot; s’affichait lors du glissement de la barre de pourcentage de pondération d’attribut à l’extrémité gauche. (TGT-36211)
* Correction de problèmes de localisation afin que le texte de l’interface utilisateur s’affiche correctement dans différentes langues.
* Nous avons normalisé la liste des mesures disponibles provenant des activités Adobe Analytics pour la Cible (A4T) en abandonnant les mesures Adobe Analytics qui ne sont pas prises en charge dans la version actuelle des API Adobe Analytics. Cela nous permettra d’étendre la prise en charge d’A4T dans les prochaines versions d’Adobe Cible.

   Les modifications suivantes ont été apportées :

   * &quot;Durée moyenne de consultation de la page&quot; a été remplacé par &quot;Durée moyenne de consultation du site&quot;. Toute activité utilisant cette mesure comme mesure de la mesure Objectif principal aura &quot;Durée moyenne de la visite du site&quot; (remarque : mesurée en minutes plutôt qu’en secondes) sélectionnée comme mesure principale d’objectif la prochaine fois que l’activité sera modifiée.
   * &quot;Visiteur&quot; a été remplacé par &quot;Visiteurs uniques&quot;. Pour toute activité utilisant cette mesure comme mesure principale d’objectif, &quot;Visiteurs uniques&quot; sera sélectionné comme mesure principale d’objectif lors de la prochaine modification de l’activité.

* Les mesures suivantes ont été abandonnées et ne peuvent plus être sélectionnées en tant que mesure d’objectif principal lors de la création d’une activité A4T.

   | Mesure(s) obsolète(s) | Mesure(s) de remplacement suggérée(s) |
   |--- |--- |
   | Visiteurs quotidiens, Visiteurs horaires, Visiteurs mensuels, Visiteurs trimestriels, Visiteurs hebdomadaires, Visiteurs annuels | Visiteurs uniques |
   | Profondeur de visite moyenne | n/d. Non suggéré comme mesure d’objectif principale |
   | Robots | n/d. Non suggéré comme mesure d’objectif principale |
   | Taux de plantage des applications mobiles, Durée de session de prévisualisation moyenne mobile, Classement moyen de la boutique d’applications mobiles, Taux de plantage des performances des applications mobiles, Note moyenne de la boutique d’applications mobiles | n/d. Non suggéré comme mesure d’objectif principale |

## Navigation dans Adobe Experience Cloud (22 février 2019)

* Lorsque vous vous connectez au [!DNL Adobe Experience Cloud], vous accédez au nouveau volet de navigation de l’en-tête. Il ressemble beaucoup à la navigation précédente avec la barre noire en haut, mais il apporte les améliorations suivantes :

   * Il est plus facile de passer d&#39;une organisation [!DNL Identity Management System] (IMS) à une autre solution.
   * Amélioration de l&#39;aide utilisateur : Les résultats de la recherche incluent les résultats de la documentation du [!DNL Target] produit, ainsi que des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d&#39;accéder plus facilement à un plus grand nombre de contenus pour vous aider à tirer le meilleur parti [!DNL Target]. Nous avons également ajouté un mécanisme de rétroaction directement dans le menu [!UICONTROL Aide] , ce qui vous permet de signaler plus facilement les problèmes ou de partager vos idées.

   * Amélioration de la fonctionnalité de rétroaction de Net Promoter Score (NPS), de sorte que le module de questionnaire ne perturbe pas votre flux de travail.
   * Amélioration du flux de connexion. Auparavant, tous les [!DNL Target] clients se retrouvaient sur le landing page de la Cible après avoir cliqué sur l’ [!DNL Target] icône de l’en-tête. Cette page a ensuite permis aux clients de continuer avec [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], comme indiqué ci-dessous :

      ![Landing page](/help/r-release-notes/assets/landing.png)

      Nous avons éliminé ce landing page pour tous nos clients. Vous accédez désormais toujours directement à la page [!UICONTROL Activités Liste] en cliquant sur l’ [!DNL Target] icône dans la nouvelle barre de navigation de l’en-tête.

      Si vous utilisez [!DNL Recommendations Classic], vous pouvez soit accéder directement à la solution, soit accéder au lien court créé dans l’onglet [!UICONTROL Recommandations] , comme indiqué ci-dessous :

      ![Lien profond Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si vous utilisez [!DNL Search&Promote], vous devez accéder directement à l’URL [](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). Le chemin à atteindre [!DNL Search&Promote] de l&#39;intérieur de [!DNL Adobe Target] a été complètement supprimé.

   * Les notifications pour [!DNL Target] le moment ne sont pas disponibles dans la liste déroulante [!UICONTROL Notifications] de l’en-tête.
   >[!NOTE]
   >
   >Dans le cadre du déploiement de la nouvelle barre de navigation, vous remarquerez également certains changements d’URL. Tous les liens précédemment mis en signet continuent de fonctionner, mais nous vous encourageons à mettre en signet de nouveaux liens pour une ouverture plus rapide.

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur de Cible](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur d’Adobe Cible. |
| [Notes de mise à jour - SDK Node.js Cible](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js de la Cible Adobe. |
| [Notes de mise à jour - Cible Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe Cible. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js d’Adobe Cible. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour d’](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
