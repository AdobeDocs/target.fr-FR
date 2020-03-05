---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 336726bef7a8a3a8cf4abed37ccdeb63b8efa369

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour pour les API Target, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plateformes sont également incluses, le cas échéant.

>[!NOTE]
>
>* **Modifications** de la prise en charge TLS : À compter du 1er mars 2020, Target désactivera la prise en charge du chiffrement TLS 1.1 et TLS 1.0. Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. Ce changement est nécessaire pour répondre à la norme de conformité de sécurité généralement acceptée de TLS 1.2 ou version ultérieure. Vérifiez la version TLS que vous utilisez actuellement. Si votre version est inférieure à 1.2, implémentez les modifications requises avant le 1er mars 2020 afin de continuer à utiliser Target comme prévu.
   >
   >   
   Pour plus d’informations sur l’impact possible et sur les étapes à suivre pour mettre à jour votre implémentation, voir Modifications [du chiffrement](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **dépréciation** de mbox.js : Le 30 août 2020, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités Target sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons pas fourni de mises à jour de fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et vous offrir le support auquel vous vous attendez d’Adobe.
   >
   >
* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].


## Target Standard/Premium 20.2.1 (3 mars 2020)

>[!IMPORTANT]
>
>Consultez les informations ci-dessus à propos de la désapprobation de mbox.js.

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait les clients de sélectionner une collection lors de l’exécution d’une recherche de catalogue. (TGT-36230)
* Correction d’un problème suite auquel un critère créé via l’API, mais non référencé par une activité créée dans l’interface utilisateur de Target, pouvait être supprimé par erreur de l’interface utilisateur. (TGT-35917)
* Amélioration de la sécurité mise en oeuvre dans la stratégie de sécurité du contenu (CSP). (TGT-36190)
* Correction d’un problème en raison duquel &quot;NaN%&quot; s’affichait lors du glissement de la barre de pourcentage Pondération d’attribut vers l’extrême gauche. (TGT-36211)
* Correction de problèmes de localisation afin que le texte de l’interface utilisateur s’affiche correctement dans différentes langues.
* Les mesures Adobe Analytics suivantes ne sont plus prises en charge pour Analytics pour Target (A4T) à compter de la version de Target de mars 2020 :
   * moyenne visitdepth
   * bots
* Les mesures suivantes ne sont plus prises en charge et sont automatiquement converties en nouvelles versions de la mesure lorsqu’un utilisateur modifie une activité contenant la mesure pour la première fois :

   | Mesure obsolète | Nouvelle mesure |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (remarque : mesuré en minutes plutôt qu’en secondes) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Navigation dans Adobe Experience Cloud (22 février 2019)

* Lorsque vous vous connectez au [!DNL Adobe Experience Cloud], vous accédez au nouvel en-tête de navigation. Il ressemble beaucoup à la navigation précédente avec la barre noire en haut, mais il apporte les améliorations suivantes :

   * Il est plus facile de passer d&#39;une organisation [!DNL Identity Management System] (IMS) à une autre solution.
   * Amélioration de l’aide à l’utilisateur : Les résultats de la recherche incluent les résultats de la documentation du [!DNL Target] produit, ainsi que des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d&#39;accéder plus facilement à un plus grand nombre de contenus pour vous aider à tirer le meilleur parti [!DNL Target]. Nous avons également ajouté un mécanisme de rétroaction directement dans le menu [!UICONTROL Aide] , ce qui facilite la création de rapports sur les problèmes ou le partage de vos idées.

   * Amélioration de la fonctionnalité de rétroaction de Net Promoter Score (NPS), de sorte que le module de l&#39;enquête ne perturbe pas votre flux de travail.
   * Amélioration du flux de connexion. Auparavant, tous les [!DNL Target] clients accédaient à la page d’entrée Target après avoir cliqué sur l’ [!DNL Target] icône dans l’en-tête. Cette page a ensuite permis aux clients de continuer avec [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], comme illustré ci-dessous :

      ![Landing page](/help/r-release-notes/assets/landing.png)

      Nous avons éliminé cette page d&#39;entrée pour tous nos clients. Vous êtes désormais toujours dirigé directement vers la page Liste [!UICONTROL des] activités en cliquant sur l’ [!DNL Target] icône dans la nouvelle barre de navigation de l’en-tête.

      Si vous utilisez [!DNL Recommendations Classic], vous pouvez soit accéder directement à la solution, soit accéder au lien court créé dans l’onglet [!UICONTROL Recommandations] , comme illustré ci-dessous :

      ![Lien profond Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si vous utilisez [!DNL Search&Promote], vous devez accéder directement à l’URL [](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). Le chemin à atteindre [!DNL Search&Promote] de l&#39;intérieur de [!DNL Adobe Target] a été complètement supprimé.

   * Les notifications pour [!DNL Target] ne sont actuellement pas disponibles dans la liste déroulante [!UICONTROL Notifications] de l’en-tête.
   >[!NOTE]
   >
   >Dans le cadre du déploiement de la nouvelle barre de navigation, vous remarquerez également des changements d’URL. Tous les liens précédemment mis en signet continuent de fonctionner, mais nous vous encourageons à mettre en signet de nouveaux liens pour une ouverture plus rapide.

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur d’Adobe Target. |
| [Notes de mise à jour - SDK de Noeud.js Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js d’Adobe Target. |
| [Notes de mise à jour - SDK Java Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe Target. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js d’Adobe Target. |
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
