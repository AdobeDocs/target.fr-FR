---
keywords: journal des modifications de la documentation de Target;mises à jour de la documentation;nouvelles rubriques;modifications;mises à jour;mise à jour
description: Tenez-vous au courant des ajouts et modifications importants apportés à la documentation du produit  [!DNL Target] Adobe.
title: Où puis-je consulter les mises à jour de la documentation de Target ?
feature: Notes de mise à jour
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
translation-type: tm+mt
source-git-commit: 0fd1f43f7cd48123eab7d6f412babb7a670398c7
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 62%

---

# Modifications de la documentation

Cette rubrique répertorie les modifications importantes apportées à la documentation d’[!DNL Adobe Target].

## Adobe [!DNL Target] Standard/Premium 21.4.1 (19 avril 2021)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 6 mai | [Questions fréquentes relatives aux recommandations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Ajout des questions fréquentes suivantes :<ul><li>Combien de temps faut-il pour qu&#39;une modification de la configuration de mes paramètres d&#39;activité, d&#39;offre, de promotions ou de critères [!UICONTROL Recommendations] soit répercutée sur mon site ?</li><li>Combien de temps faut-il pour que le comportement d’un utilisateur (par exemple, cliquer sur le produit A et acheter le produit B) se reflète dans les recommandations *que reçoit* l’utilisateur ?</li><li>Combien de temps faut-il pour que le comportement d&#39;un utilisateur (par exemple, cliquer sur le produit A et acheter le produit B) soit reflété dans les recommandations *que les autres* utilisateurs reçoivent ?</li></ul> |
|  | [Prise de décision sur l’appareil](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Lien Ajouté vers l&#39;article de blog suivant sur le blog Adobe Tech :<ul><li>Partie 1 : Exécution du SDK Adobe Target NodeJS pour l’expérimentation et la personnalisation sur les plateformes Edge (Akamai Edge Workers)</li></ul> |
| 5 mai | [Annonces et événements Target](/help/r-release-notes/target-announcements.md) | Information Ajoutée au sujet de la pause-café de la communauté Adobe Target qui se tiendra le mercredi 12 mai 2021 à 8 h. (PDT, GMT-7). |
| 27 avril | [Paramétrage des cookies](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | Mise à jour de la rubrique afin d’indiquer que la durée du cookie (`deviceIdLifetime` paramètre) est remplaçable dans at.js version 2.3.1 ou ultérieure. |
|  | [Guide Adobe Target](/help/target-home.md) | Informations Ajoutées sur le Sommet Adobe. |
| 26 avril | [Dépannage de la prise de décision sur périphérique pour at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | Nouvelle rubrique. |
| 19 avril | [Prise de décision sur l’appareil](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | Ajouté les nouveaux articles suivants :<ul><li>[Prise de décision sur l’appareil](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>[Fonctionnalités prises en charge pour la prise de décision sur périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[Artefact de règle de prise de décision sur périphérique](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | Informations Ajoutées sur `decisioningMethod`. |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Ajouté les éléments suivants :<ul><li>Informations sur la clé `decisioningMethod`.</li><li>Exemple de &quot;getCallOffers() pour prendre une décision sur le périphérique&quot;.</li></ul> |
|  | [événements personnalisés at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Ajout des informations suivantes :<ul><li>Artefact de prise de décision sur périphérique réussi</li><li>Échec de l&#39;artefact de prise de décision sur le périphérique</li></ul> |
|  | [Activités](/help/c-activities/activities.md) | Informations Ajoutées sur la prise de décision sur le périphérique. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations relatives à at.js 2.5.0. |
|  | [Implémentation de Target sans gestionnaire de balises](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | Informations Ajoutées sur la prise de décision sur le périphérique. |
|  | [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) | La prise en charge des liens de prévisualisation pour les activités [!UICONTROL Automated Personalization] a été ajoutée avec [at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
|  | [Utilisation de règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | Informations Ajoutées sur les nouveaux opérateurs suivants :<ul><li>Contient Dans La Liste</li><li> N’est pas contenu dans la Liste</li><li>La liste Contient Un Élément Dans</li><li>La liste Ne Contient Pas D&#39;Élément Dans</li><li>La liste Contient Tous Les Éléments Dans</li><li>La liste Ne Contient Pas Tous Les Éléments Dans</li></ul> |
|  | [Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)<br> Adobe Target (*Experience Cloud Services and* Administration Guide) | Informations supplémentaires Ajoutées sur &quot;ID de session&quot;. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.4.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe [!DNL Target] Standard/Premium 21.2.1 (9 mars 2021)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 9 avril | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations de pré-version Ajoutées pour la version 2.5.0 d’at.js (19 avril 2021) |
| 9 avril | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version bêta de Target Standard/Premium 21.4.1 (19 avril 2021) |
|  | [Intégration de Recommandations dans la messagerie électronique](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Note Ajoutée décrivant les directives de capacité pour les options 1 et 2. |
| 29 mars | [Questions fréquentes relatives aux recommandations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | Nouvelle FAQ Ajoutée :<ul><li>Les recommandations basées sur les éléments récemment consultés persistent-elles sur plusieurs périphériques pour un seul visiteur ?</li></ul> |
| 23 mars | [Notes de mise à jour](/help/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 2.4.1 d’at.js. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout de notes de mise à jour pour la version 2.4.1 d’at.js. |
|  | [Questions fréquentes relatives aux recommandations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Mise à jour des questions fréquentes suivantes :<ul><li>Combien de temps faut-il pour que les mises à jour des éléments de mon catalogue soient répercutées sur mon site ?</li></ul> |
| 22 mars | [Adresses IP utilisées par les serveurs de traitement de flux de Recommandations](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | Mise à jour de la liste des adresses IP. |
|  | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour de la section &quot;Nombre d’entités&quot; sous &quot;Entités&quot;. |
|  | [Géo](/help/c-target/c-audiences/c-target-rules/geo.md) | Ajout d’informations relatives à at.js 2.** xunder &quot;Comment puis-je tester mes activités comme si je venais d’un autre endroit ?&quot; |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.2.1 | Ajouté dans la section suivante : <ul><li>Modifications de l’adresse IP pour les serveurs de traitement des flux Recommendations (16 mars 2021)</li></ul> |
| 19 mars | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | Ajout de la question fréquente suivante :<ul><li>Pourquoi est-ce que je continue à voir plus d’impressions après la désactivation de mon activité ?</li></ul> |
| 12 mars | [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | Ajout du nouveau tutoriel suivant :<ul><li>Comment configurer les rapports A4T dans Analysis Workspace pour les activités de ciblage automatique ?</li></ul> |
| 9 mars | [Limites](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>Mise à jour des limites de taille d’offre autorisées.</li><li>Correction de la limite de caractères pour le paramètre categoryId.</li></ul> |
|  | [Ajout des nœuds Edge de Target sur liste autorisée](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Mise à jour des adresses IP Edge de [!DNL Target]. |
|  | [Attributs d’entité](/help/c-recommendations/c-products/entity-attributes.md) | Ajout de texte pour indiquer que entity.value doit être au format décimal (par exemple 15,99 au lieu de 15.99). |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.2.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe [!DNL Target] Standard/Premium 21.1.1 (19 janvier 2021)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 22 février | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour des questions fréquentes suivantes :<ul><li>Où les segments peuvent-ils être appliqués dans Analysis Workspace ?</li></ul> |
| 16 février | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Mise à jour du texte concernant la taille limite des offres dans les notes de mise à jour. |
| 11 février | [Fonctionnement de Target](/help/c-intro/how-target-works.md) | Mise à jour de la section « Robots ». |
| 10 février | [Annonces et événements Target](/help/r-release-notes/target-announcements.md) | Ajout d’informations à propos de la pause-café questions/réponses de la communauté Adobe Target du mercredi 24 février 2021. |
| 8 février | [Aperçu de Target Mobile](/help/c-target-mobile-app/target-mobile-preview.md) | Ajout du fragment de code à rajouter au fichier AndroidManifest.xml pour la version 4 du SDK Adobe Mobile. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Clarification du problème connu suivant :<ul><li>Les collections, exclusions, critères et conceptions créés par le biais de l’API ne sont pas visibles dans l’interface utilisateur de Target et ne peuvent être modifiés que par le biais de l’API. De même, si vous créez l’un de ces éléments dans l’interface utilisateur de Target et que vous le modifiez ultérieurement par le biais de l’API, ces modifications ne seront pas répercutées dans l’interface utilisateur de Target. Les éléments modifiés par le biais de l’API doivent continuer à l’être par ce même biais afin d’éviter toute perte de modifications.</li></ul> |
| 1er février | [Rapports de synthèse d’Automated Personalization](/help/c-reports/reports-ap.md) | Ajout de la section « Questions fréquentes ». |
| 27 janvier | [Création d’offres de redirection](/help/c-experiences/c-manage-content/offer-redirect.md) | Mise à jour de la rubrique. |
|  | [Création d’offres distantes](/help/c-experiences/c-manage-content/about-remote-offers.md) | Mise à jour de la rubrique. |
| 26 janvier | [Taux de conversion](/help/c-reports/conversion-rate.md) | Clarification de la façon dont Target utilise la « somme des carrés » dans les tests en t. |
| 22 janvier | [Taux de conversion](/help/c-reports/conversion-rate.md#t-test) | Ajout de la section suivante : « Pourquoi Target recommande-t-il d’utiliser des tests en t ? » |
| 21 janvier | [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | Ajout de la section « Les rapports d’activité d’A4T incluent une ligne avec un grand nombre d’événements &quot;non spécifiés&quot; ». |
|  | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour de la section suivante : « Pourquoi est-ce que je vois &quot;non spécifié&quot; dans les rapports Analytics ? Qu’est-ce que cela signifie ? ». |
| 20 janvier | [SDK web Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Nouvelle rubrique. |
| 19 janvier | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur la version Target 21.1.1 (19 janvier 2021). |
|  | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour du texte du paramètre `productPurchasedID`. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un problème connu lors de la copie d’une activité de [!UICONTROL Recommandations] avec une promotion active. Toute modification de l’activité dupliquée affecte également l’activité d’origine, et vice versa. Une solution temporaire est incluse. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.1.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |
