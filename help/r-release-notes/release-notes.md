---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour pour les API de , les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plateformes sont également incluses, le cas échéant.

>[!NOTE]
>
>* **Modifications** de la prise en charge TLS : À compter du 1er mars 2020, les  de désactiveront la prise en charge du chiffrement TLS 1.1 et TLS 1.0. Transport Layer Security (TLS) est le protocole de sécurité le plus répandu utilisé aujourd’hui pour les navigateurs web et autres applications exigeant que les données soient échangées en toute sécurité sur un réseau. Ce changement est nécessaire pour répondre à la norme de conformité de sécurité généralement acceptée de TLS 1.2 ou version ultérieure. Vérifiez la version TLS que vous utilisez actuellement. Si votre version est antérieure à la version 1.2, implémentez les modifications requises avant le 1er mars 2020 afin de continuer à utiliser les  comme prévu.
   >
   >   
   Pour plus d’informations sur l’impact possible et sur les étapes à suivre pour mettre à jour votre implémentation, voir Modifications [du chiffrement](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **dépréciation** de mbox.js : Le 30 août 2020, le Adobe  ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles le   l’exécution de . Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons pas fourni de mises à jour de fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d’assistance pourront vous fournir de nouvelles fonctionnalités et  les  l’assistance que vous attendez d’Adobe.
   >
   >
* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].


## Summit Live : Digital Experience Conference {#summit}

Adobe Summit est devenu un  virtuel ! Adobe s’en sort avec une expérience numérique en direct à partir du 31 mars 2020. Cette expérience en direct comprendra notre discours d’ouverture, des mini-notes-clés présentant les dernières tendances et les dernières avancées, des informations sur la réussite des leaders du secteur et des séances de formation.

* **Regardez le discours en direct**: Écoutez les tendances et les nouveaux produits qui transforment les industries du confort de votre lieu de travail.
* **Explorez plus de 100 ventilations sur demande :** Bénéficiez d&#39;un accès gratuit à plus d&#39;une centaine de sessions de sous-traitance à la demande d&#39;Adobe, de clients et de partenaires.
* **Jetez un coup d&#39;oeil à l&#39;avenir**: Rejoignez l&#39;invité Chelsea Handler pour découvrir les dernières technologies expérimentales de nos laboratoires... dans Adobe Sneaks.

Pour vous inscrire pour accéder gratuitement à l’intégralité du  de numérique, rendez-vous sur [The Digital Experience Conference : Page Sommet](https://www.adobe.com/summit.html) .

##  d’at.js (25 mars 2020)

Les nouvelles versions suivantes des bibliothèques JavaScript at.js du sont disponibles :

* at.js version 2.3.0
* at.js version 1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 mars 2020)

>[!IMPORTANT]
>
>Consultez les informations ci-dessus à propos de la désapprobation de mbox.js.

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait les clients de sélectionner une collection lors de l’exécution d’une recherche de catalogue. (TGT-36230)
* Correction d’un problème suite auquel un critère créé via l’API, mais non référencé par un  créé dans l’interface utilisateur de l’, pouvait être supprimé par erreur de l’interface utilisateur. (TGT-35917)
* Amélioration de la sécurité mise en oeuvre dans la stratégie de sécurité du contenu (CSP). (TGT-36190)
* Correction d’un problème en raison duquel &quot;NaN%&quot; s’affichait lors du glissement de la barre de pourcentage Pondération d’attribut vers l’extrême gauche. (TGT-36211)
* Correction de problèmes  d’interface utilisateur afin que le texte de l’interface dans différentes langues s’affiche correctement.
* Nous avons normalisé le  des mesures disponibles d’Adobe Analytics pour les  de (A4T) en abandonnant les mesures d’Adobe Analytics qui ne sont pas prises en charge dans la version actuelle des API d’Adobe Analytics. Cela nous permettra d’étendre la prise en charge d’A4T dans les prochaines versions des  d’Adobe.

   Les modifications suivantes ont été apportées :

   * &quot;Durée moyenne de consultation de la page&quot; a été remplacé par &quot;Durée moyenne de consultation du site&quot;. Tout   utilisant cette mesure comme mesure de la mesure Objectif principal aura &quot;Durée moyenne de la visite du site&quot; (remarque : mesurée en minutes plutôt qu’en secondes) sélectionnée comme mesure principale de l’objectif lors de la prochaine modification de l’ de .
   * &quot;&quot; a été remplacé par &quot;uniques&quot;. Tout   utilisant cette mesure comme mesure d’objectif principal aura &quot;uniques&quot; sélectionné comme mesure d’objectif principal lors de la prochaine modification du  principal.

* Les mesures suivantes ont été abandonnées et ne peuvent plus être sélectionnées comme mesure d’objectif principal lors de la création d’un nouvel   A4T.

   | Mesure(s) obsolète(s) | Mesure(s) de remplacement suggérée(s) |
   |--- |--- |
   | quotidiens, horaires, mensuels, trimestriels, hebdomadaires, annuels | Visiteurs uniques |
   | Profondeur de visite moyenne | n/d. Non suggéré comme mesure d’objectif principal |
   | Robots | n/d. Non suggéré comme mesure d’objectif principal |
   | Taux de plantage mobile, Durée de session antérieure moyenne mobile, Classement moyen de la boutique d’applications mobiles, Taux de plantage des performances des applications mobiles, Note moyenne de la boutique d’applications mobiles | n/d. Non suggéré comme mesure d’objectif principal |

## Navigation dans Adobe Experience Cloud (22 février 2019)

* Lorsque vous vous connectez au [!DNL Adobe Experience Cloud], vous accédez au nouveau volet de navigation de l’en-tête. Il ressemble beaucoup à la navigation précédente avec la barre noire en haut, mais il apporte les améliorations suivantes :

   * Il est plus facile de passer d&#39;une organisation [!DNL Identity Management System] (IMS) à une autre solution.
   * Amélioration de l’aide à l’utilisateur : Les résultats de la recherche incluent les résultats de la documentation du [!DNL Target] produit, ainsi que des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d&#39;accéder plus facilement à un plus grand nombre de contenus pour vous aider à tirer le meilleur parti [!DNL Target]. Nous avons également ajouté un mécanisme de rétroaction directement dans le menu [!UICONTROL Aide] , ce qui facilite la création de rapports sur les problèmes ou le partage de vos idées.

   * Amélioration de la fonctionnalité de rétroaction de Net Promoter Score (NPS), de sorte que le module  ne perturbe pas votre flux de travail.
   * Amélioration du flux de connexion. Auparavant, tous les [!DNL Target] clients se retrouvaient sur le  de  de après avoir cliqué sur l’ [!DNL Target] icône dans l’en-tête. Cette page a ensuite permis aux clients de continuer avec [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], comme illustré ci-dessous :

      ![Landing page](/help/r-release-notes/assets/landing.png)

      Nous avons éliminé ce  pour tous nos clients. Vous êtes désormais toujours dirigé directement vers la page   [!UICONTROL en cliquant sur l’] [!DNL Target] icône dans la nouvelle barre de navigation de l’en-tête.

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
| [Notes de mise à jour -  API côté serveur côté](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur  Adobe. |
| [Notes de mise à jour -  SDK Node.js du](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js du Adobe. |
| [Notes de mise à jour - SDK Java](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe . |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js du Adobe. |
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
