---
keywords: Journal des modifications de la documentation de la cible ; mises à jour de la documentation ; nouvelles rubriques ; modifications ; mises à jour ; mise à jour
description: Tenez-vous au courant des ajouts et modifications importants apportés à la documentation du produit Adobe Target.
title: Où puis-je Vue les mises à jour de la documentation pour la Cible ?
feature: Notes de mise à jour
translation-type: tm+mt
source-git-commit: 6a1f51cba34038abc3c73fa5cf88bfab183dfb28
workflow-type: tm+mt
source-wordcount: '3767'
ht-degree: 28%

---


# Modifications de la documentation

Cette page liste les modifications importantes apportées à la documentation du produit [!DNL Adobe Target].

## Adobe Target Standard/Premium 21.2.1 (9 mars 2021)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 12 mars 2021 | [Prise en charge d’A4T pour les activités d’affectation automatique et de Cible automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | Ajouté le nouveau didacticiel suivant :<ul><li>Configuration de rapports A4T en Analysis Workspace pour les activités à Cible automatique</li></ul> |
| 9 mars | [Limites](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>Mise à jour des limites de taille d’offre autorisées.</li><li>Correction de la limite de caractères pour le paramètre categoryId.</li></ul> |
|  | [Liste autorisée des noeuds de bord de Cible](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Mise à jour des adresses IP de périphérie [!DNL Target]. |
|  | [Attributs d’entité](/help/c-recommendations/c-products/entity-attributes.md) | Texte Ajouté pour indiquer que entity.value doit être au format décimal (par exemple 15,99 au lieu de 15,99). |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.2.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 21.1.1 (19 janvier 2021)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 22 février | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour du FAQ suivant :<ul><li>Où les segments peuvent-ils être appliqués en Analysis Workspace ?</li></ul> |
| 16 février | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Mise à jour du texte pour la taille limite des offres dans les notes de mise à jour. |
| 11 février | [Fonctionnement de Target](/help/c-intro/how-target-works.md) | Mise à jour de la section &quot;Robots&quot;. |
| 10 février | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations Ajoutées sur la pause café de la communauté Adobe Target le mercredi 24 février 2021. |
| 8 février | [Aperçu de Target Mobile](/help/c-target-mobile-app/target-mobile-preview.md) | Ajouté le fragment de code à ajouter au fichier AndroidManifest.xml pour la version 4 du kit SDK Mobile Adobe. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Clarification du problème connu suivant :<ul><li>Les collections, exclusions, critères et conceptions créés via l’API ne sont pas visibles dans l’interface utilisateur de la Cible et ne peuvent être modifiés que par le biais de l’API. De même, si vous créez l’un de ces éléments dans l’interface utilisateur de la Cible et que vous les modifiez ultérieurement au moyen de l’API, ces modifications ne seront pas répercutées dans l’interface utilisateur de la Cible. Les éléments modifiés via l’API doivent continuer à être modifiés via l’API afin d’éviter toute perte de modifications.</li></ul> |
| 1er février | [Rapports de synthèse d’Automated Personalization](/help/c-reports/reports-ap.md) | Nouvelle section Ajoutée : &quot;Questions fréquentes&quot;. |
| Janvier 27 | [Création d’offres de redirection](/help/c-experiences/c-manage-content/offer-redirect.md) | Mise à jour d’une rubrique. |
|  | [Créer des offres distantes](/help/c-experiences/c-manage-content/about-remote-offers.md) | Mise à jour d’une rubrique. |
| Janvier 26 | [Taux de conversion](/help/c-reports/conversion-rate.md) | Clarification de la façon dont la Cible utilise la &quot;somme des carrés&quot; dans les tests en t de Student. |
| Janvier 22 | [Taux de conversion](/help/c-reports/conversion-rate.md#t-test) | Ajouté dans la section suivante : &quot;Pourquoi la Cible recommande-t-elle d&#39;utiliser les tests en t-test de Student ?&quot; |
| Janvier 21 | [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | Nouvelle section Ajoutée : &quot;Les rapports d’Activité A4T incluent une ligne avec un grand nombre de événements &quot;non spécifiés&quot;.&quot; |
|  | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour de la section suivante : &quot;Pourquoi est-ce que je vois &quot;non spécifié&quot; dans les rapports Analytics ? Qu&#39;est-ce que ça veut dire ?&quot; |
| Janvier 20 | [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Nouvelle rubrique. |
| Janvier 19 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Informations Ajoutées sur la version 21.1.1 de la Cible (19 janvier 2021). |
|  | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour du texte du paramètre `productPurchasedID`. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un problème connu lors de la copie d’une activité [!UICONTROL Recommandation] avec une promotion active. Toute modification de l’activité dupliquée affecte également l’activité d’origine, et inversement. Une solution temporaire est incluse. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 21.1.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.10.1 (28 octobre 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| Janvier 14 | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations relatives à at.js version 2.4.0. |
| Janvier 12 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’informations de version préliminaire sur la version Target Standard/Premium 21.1.1 (19 janvier 2021). |
| Janvier 11 | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d’informations et d’informations d’enregistrement pour la pause café de la communauté Adobe Target du 13 janvier. |
| Janvier 6 | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d’informations et d’informations d’enregistrement pour le webinaire en direct suivant :<ul><li>Personnalisation réussie à l’échelle : Principales conclusions de Forrester Wave, Experience Optimization Platforms.</li></ul> |
| 4 janvier | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Changement de la date à laquelle Target ne prendra plus en charge mbox.js du 18 janvier 2021 au 31 mars 2021. |
| Décembre 18 | [Test A/A](/help/c-activities/t-test-ab/aa-testing.md) | Nouvelle rubrique. |
| Décembre 17 | [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Tableau mis à jour pour indiquer que le SDK Java prend en charge A4T. |
| Décembre 16 | [Résolution des problèmes de cible automatique et FAQ](/help/c-activities/auto-target/auto-target-troubleshooting-faqs.md) | Ajout de la FAQ suivante : &quot;Que se passe-t-il si je supprime une expérience unique d’une activité Cible automatique ?&quot; |
| Décembre 9 | [Décision sur l’appareil](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Nouvelle rubrique. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Le problème suivant a été déplacé de la section Problèmes connus vers la section Problèmes résolus : &quot;Offres d&#39;image avec l&#39;étiquette &quot;Traitement&quot;.&quot; |
| Décembre 1 | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Intégration de l’enregistrement du webinaire pour &quot;Personnaliser et tester à zéro latence avec les décisions sur l’appareil d’Adobe Target&quot;. |
| 24 novembre | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Problème connu Ajouté :<ul><li>[Rapports : données incohérentes dans le rapport .csv téléchargeable par rapport au rapport affiché dans l’interface utilisateur cible.](/help/r-release-notes/known-issues-resolved-issues.md#csv)</li></ul>Problème résolu Ajouté :<ul><li>[Rapports Analytics for Target (A4T)](/help/r-release-notes/known-issues-resolved-issues.md#section_FD2FC86E7C734D60B1EDC9DEF60E1014)</li></ul> |
|  | [FAQ sur les définitions de mesures - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md) | Ajout de la FAQ suivante : &quot;Lors de la configuration de mes mesures d’objectif, pourquoi ne puis-je pas accéder aux options Paramètres avancés ?&quot; |
|  | [Mesures de succès](/help/c-activities/r-success-metrics/success-metrics.md) | Texte ajusté dans la note sur les activités qui utilisent A4T. |
| 17 novembre | [FAQ sur le paramétrage des activités - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | Ajout de la FAQ suivante : &quot;Un visiteur peut-il basculer entre des expériences ciblées et contrôlées lors de différentes visites dans une activité Cible automatique qui utilise A4T ?&quot; |
|  | [Résolution des problèmes de cible automatique et FAQ](/help/c-activities/auto-target/auto-target-troubleshooting-faqs.md) | Ajout de la FAQ suivante : &quot;Recommandez-vous d’utiliser la Cible Auto avec un fractionnement 90 (Contrôle)/10 (Ciblé) jusqu’à ce que les modèles soient construits ?&quot; |
|  | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Ajout de la FAQ suivante : &quot;Comment les visites comptabilisées dans Analytics et le crédit de conversion sont-elles allouées dans une activité Cible automatique qui utilise A4T ?&quot; |
| 13 novembre | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations relatives à at.js 2.3.3. |
| 10 novembre | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations sur la pause café de la communauté Adobe Target prévue pour le 11 novembre. |
| 3 novembre | [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | Mise à jour de la rubrique de dépannage suivante : &quot;La suite de rapports dont j&#39;ai besoin ne s&#39;affiche pas.&quot; |
| 28 octobre | [Côté serveur : implémentation de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | Notez que les nouveaux visiteurs peuvent être initialisés uniquement côté client, et non côté serveur. |
| 27 octobre | [Côté serveur : implémentation de Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) | Ajout d’un lien vers le nouveau portail *[Adobe Target SDKs](https://adobetarget-sdks.gitbook.io/docs/)*. |
|  | [Créer une activité qui utilise Analytics comme source de rapport](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | Ajout d’informations indiquant que si vous utilisez `analyticsLogging = client_side`, vous devez transmettre la valeur `sessionId` à [!DNL Analytics] lors de l’utilisation d’Analytics en tant que source de rapport (A4T) avec les activités Cible automatique. |
|  | [Implémentation d’Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) | Ajout d’informations indiquant que pour les activités [!UICONTROL Auto-Allocation] et [!UICONTROL Auto-Target] utilisant `analyticsLogging = client_side`, vous devez également transférer l’ID de session. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.10.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.9.1 (30 septembre 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 26 octobre | [Présentation de la sécurité de Target](/help/c-implementing-target/c-considerations-before-you-implement-target/target-security-overview.md) | Mise à jour du livre blanc *Présentation de la sécurité d&#39;Adobe Target*. |
| 22 octobre | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Ajout d’informations sur un correctif pour la prise en charge de CNAME dans les versions 1.8.2 et 2.3.1 d’at.js |
|  | [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout d’informations sur un correctif pour la prise en charge de CNAME dans les versions 1.8.2 et 2.3.1 d’at.js |
| 15 octobre | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Mise à jour des notes de version préliminaire pour la version 20.10.1 de Target Standard/Premium (27 octobre 2020). |
| 14 octobre | [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ajout d’une note sur l’affectation du trafic pour une activité d’affectation automatique avec seulement deux expériences. |
| 13 octobre | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d’informations sur le webinaire en direct suivant prévu pour le 10 novembre 2020 :<ul><li>Personnalisez et testez avec une latence nulle grâce aux décisions prises sur l’appareil à partir d’Adobe Target</li></ul> |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’informations sur le webinaire en direct suivant prévu pour le 10 novembre 2020 :<ul><li>Personnalisez et testez avec une latence nulle grâce aux décisions prises sur l’appareil à partir d’Adobe Target</li></ul> |
| 12 octobre | [Résolution des problèmes liés à la diffusion de contenu](/help/c-activities/c-troubleshooting-activities/content-trouble.md) | Mise à jour de [Récupérez le jeton d&#39;autorisation à utiliser avec les outils de débogage](/help/c-activities/c-troubleshooting-activities/content-trouble.md#section_BED130298E794D1FA229DB7C3358BA54) pour indiquer le niveau d&#39;autorisation dont vous devez générer un jeton d&#39;authentification. |
|  | [Paramètres de l’API de profil](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md) | Rubrique mise à jour pour indiquer le niveau d’autorisation que vous devez générer un jeton d’authentification. |
|  | [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) | Ajout d’un récit de réussite réel à l’aide de la fonction Cible automatique. |
|  | [Inclure la même expérience sur des pages similaires](/help/c-experiences/c-visual-experience-composer/temtest.md) | Ajout d’une section pour expliquer comment effectuer le rendu d’une même activité sur l’ensemble du domaine. |
|  | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Problème connu Ajouté :<ul><li>Analytics pour les mesures Cible (A4T) pour les activités d’affectation automatique et de cible automatique</li></ul> |
| 8 octobre | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) | Problème résolu Ajouté :<ul><li>[Rapports de cible automatique](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics)</li></ul>Déplacement du problème suivant de la section Problèmes connus vers la section Problèmes résolus :<ul><li>[Création de rapports](/help/r-release-notes/known-issues-resolved-issues.md#conversions-audiences)</li></ul> |
|  | [Mise en oeuvre hybride](/help/c-implementing-target/hybrid-implementation.md) | Nouvelle rubrique. |
| 7 octobre | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version de Target Standard/Premium 20.10.1. |
| 1er octobre | [Estimation du trafic requis pour réussir un test](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md) | Ajout de la section FAQ. |
| 30 septembre | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d’informations sur le webinaire en direct suivant :<ul><li>Personnalisation adaptée et affinée à l’échelle avec Adobe Target et Analytics</li></ul> |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.9.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.8.1 (2 septembre 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 29 septembre | [Résolution des problèmes d’intégration d’Analytics et de Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md#section_75002584FA63456D8D9086172925DD8D) | Ajout d’informations sur la façon d’inspecter l’ID supplémentaire dans at.js 1.x et at.js 2.x. |
| 24 septembre | [Signet d’applet de l’AQ d’activité](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | Mise à jour du code du signet d&#39;assurance qualité de l&#39;activité pour at.js 2.*x*. |
|  | [Recherche catalogue](/help/c-recommendations/c-products/catalog-search.md#faq) | Ajout d’une note sur la recherche sur un attribut personnalisé avec une valeur numérique. |
|  | [Questions fréquentes relatives aux recommandations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Ajout de la FAQ suivante : &quot;Pourquoi la recherche de catalogue n’affiche-t-elle pas les bons résultats lorsque je recherche sur un attribut personnalisé avec une valeur numérique ?&quot; |
|  | [Fonctionnement de Target](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) | Mise à jour des emplacements de cluster cible et de cluster central cible répertoriés dans &quot;The edge network&quot; (Le réseau de bord). |
| 23 septembre | [Utilisation d’un serveur de suivi Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md) | Mise à jour de la rubrique complète avec les informations de [!DNL Adobe Experience Platform Debugger] et des outils de développement du navigateur. |
|  | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Mise à jour de la ligne &quot;user.header(&#39;x-send-for&#39;)&quot; pour indiquer que &quot;user.header(&#39;x-cluster-client-ip&#39;)&quot; a été abandonné. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version de Target Standard/Premium 20.9.1 (30 septembre 2020). |
| 15 septembre | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur la version 20.8.3 de Target Standard/Premium, qui inclut la prise en charge d’Analytics pour Target (A4T) pour les activités de ciblage automatique. La prise en charge des activités d’affectation automatique a été ajoutée dans une version précédente. |
|  | [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | Ajout d’informations sur la prise en charge d’A4T dans les activités de ciblage automatique. |
|  | [Signet d’applet de l’AQ d’activité](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | Texte mis à jour pour indiquer que la méthode pour vous forcer manuellement à quitter le mode QA en chargeant une page sur votre site avec le paramètre `at_preview_token` avec une valeur vide s&#39;applique à at.js 1.*x* uniquement. |
|  | [Recherche catalogue](/help/c-recommendations/c-products/catalog-search.md) | Mise à jour de la rubrique entière. |
| 10 septembre | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur la version Target Standard/Premium 20.9.2 qui inclut la nouvelle fonctionnalité suivante : Contrôler les emplacements de recommandations dans les séquences de critères. |
|  | [Création d’une séquence de critères](/help/c-recommendations/c-algorithms/create-criteria-sequence.md) | Ajout d’informations sur la fonction &quot;Limiter le nombre d’éléments renvoyés&quot;. |
| 9 septembre | [Signet d’applet de l’AQ d’activité](/help/c-activities/c-activity-qa/activity-qa-bookmark.md) | Ajout de code JavaScript pour une utilisation avec at.js 2.*x*. |
| 3 septembre | [Extension d’assistance du Compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Mise à jour de la section &quot;Obtenir et installer l&#39;extension du navigateur de l&#39;assistance VEC&quot; avec des informations sur le nom du cookie et le domaine. |
|  | [Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | Mise à jour de la section &quot;Comment les politiques d’application des cookies Google Chrome SameSite annoncées récemment ont-elles un impact sur la CVE et la CEE ?&quot; avec des informations sur le nom et le domaine du cookie. |
| 2 septembre | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.8.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.7.1 (27 juillet 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 31 août | [Utiliser Adobe Analytics avec Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md) | Ajout de la section FAQ. |
| 28 août | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Mise à jour des éléments suivants :<ul><li>Ajouté à la section Problèmes connus : &quot;Rapports : les conversions s’incrémentent actuellement différemment en fonction du public utilisé.&quot;</li><li>Ajout à la section Problèmes résolus : &quot;Pages non chargées dans Visual Experience Composer (VEC) ou Enhanced Experience Composer (EEC) lors de l’utilisation de Google Chrome version 80+.&quot;</li></ul> |
|  | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | La date d’abandon du fichier mbox.js a été changée du 30 août 2020 au 18 janvier 2021. La date de modification est maintenant le 31 mars 2020. |
| 26 août | [Utiliser Adobe Analytics avec Target Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md) | Nouvelle rubrique. |
| 24 août | [Mesures de succès](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) | Mise à jour de la section &quot;Paramètres avancés&quot;. |
| 21 août | [Présentation du kit de bienvenue d’Adobe Target](/help/c-intro/target-welcome-kit.md) | Nouvel article et sous-rubriques. |
| 20 août | [Résolution des problèmes liés au compositeur d’expérience visuelle et au compositeur d’expérience avancé](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md) | Ajout de la section suivante : &quot;Comment les politiques récemment annoncées en matière d&#39;application des cookies Google Chrome SameSite ont-elles une incidence sur la CVE et la CEE ?&quot; |
|  | [Suivi des clics](/help/c-activities/r-success-metrics/click-tracking.md) | Mise à jour du texte suivant : &quot;Si vous sélectionnez plusieurs éléments, si un participant clique sur l’un des éléments sélectionnés, le clic est comptabilisé. Pour comptabiliser séparément chaque élément, configurez des mesures de succès distinctes pour chacun d’entre eux. Pour compter un élément en cliquant sur plusieurs éléments d’une page, modifiez le sélecteur d’éléments CSS pour qu’il corresponde à plusieurs éléments.&quot; |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version de Target Standard/Premium 20.9.1 (2 septembre 2020). |
| 14 août | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un problème connu concernant l’assurance qualité dans les activités Recommendations. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout de texte indiquant que si vous utilisez des balises `serverState` et `<script>` dans le contenu renvoyé, assurez-vous que votre contenu HTML utilise `<\/script>` au lieu de `</script>`. |
| 12 août | [Présentation de l’interface utilisateur cible](/help/c-intro/understand-the-target-ui.md) | Nouvelle rubrique. |
|  | [Présentation de l’API Adobe Target](/help/api/api-overview.md) | Nouvelle rubrique. |
| 10 août | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Ajout de texte indiquant que la taille de l&#39;en-tête de cookie augmentera lors de l&#39;utilisation de CNAME. |
|  | [Intégration de Target avec Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | Nouvelle rubrique. |
|  | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d’un lien pour afficher le webinaire archivé suivant : &quot;Comment HSBC exploite Adobe Target et l&#39;IA pour optimiser rapidement et offrir une personnalisation à grande échelle.&quot; |
| 6 août | [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md#how-long) | Texte mis à jour pour la FAQ suivante : &quot;Combien de temps dois-je attendre que les modèles soient construits ?&quot; |
|  | [FAQ sur les classifications - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | Mise à jour du texte pour le type cible. |
| 5 août | [Suppression du cookie Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | Mise à jour de la rubrique entière. |
| 4 août | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations d&#39;inscription sur le webinaire &quot;Stratégies de personnalisation à l&#39;aide de l&#39;intelligence artificielle et de Adobe Target&quot; prévu pour le 13 août. |
|  | [Activation du contenu mixte dans votre navigateur](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | Mise à jour d’une rubrique. |
| 3 août | [Mesures de succès](/help/c-activities/r-success-metrics/success-metrics.md) | Ajout d’une note expliquant ce que les options [!UICONTROL Nombre d’incréments] signifient en ce qui concerne les visiteurs par rapport aux visites. |
| 31 juillet | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un nouveau problème connu : &quot;Offres d’image avec le libellé &quot;Traitement&quot;.&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Exemple de code ajouté pour utiliser `getoffers()` pour exécuter une commande pageLoad. |
|  | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations d&#39;inscription sur la prochaine pause café de la communauté Adobe Target le 5 août. |
| 28 juillet | [Rapports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) d’analyse de personnalisation, Rapport<br>[ de segments ](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatisés <br>et Rapport d’attributs  [importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | Texte mis à jour dans la note en haut des rubriques. |
|  | [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ajout des questions fréquentes suivantes :<ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité d’affectation automatique ?</li><li>Comment l&#39;affectation automatique génère-t-elle des modèles en ce qui concerne les environnements ?</li></ul> |
|  | [Ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) | Ajout de la question fréquente suivante :    <ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité Cible automatique ?</li></ul>Texte mis à jour dans la section &quot;Considérations&quot;. |
|  | [FAQ sur Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Ajout des questions fréquentes suivantes :<ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité Automated Personalization ?</li><li>Comment Automated Personalization construit-il des modèles en ce qui concerne les environnements ?</li></ul> |
|  | [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Ajout d’informations sur Internet Explorer et des éléments inconnus. |
|  | [Attributs du client](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Mise à jour du paragraphe suivant : <br>[!DNL Adobe] ne garantit pas que 100 % des données d’attributs du client (profil visiteur) provenant des bases de données de gestion de la relation client seront intégrées à [!DNL Experience Cloud] et, par conséquent, seront disponibles pour le ciblage dans [!DNL Target]. Dans notre conception actuelle, il est possible qu&#39;un petit pourcentage de données (jusqu&#39;à 0,1 % des grands lots de production) ne soient pas embarquées. |
| 27 juillet | [Administration de Target](/help/administrating-target/administrating-target.md) | Texte mis à jour dans toutes les rubriques liées de cette page pour refléter les nouvelles modifications de l&#39;interface utilisateur pour les pages [!UICONTROL Administration]. |
|  | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Les modifications suivantes ont été apportées : <ul><li>Ajout des informations d’inscription pour le webinaire suivant : &quot;Comment HSBC exploite Adobe Target et l&#39;IA pour optimiser rapidement et offrir une personnalisation à grande échelle.&quot;</li><li>Ajout d&#39;informations sur le fait que l&#39;Adobe est à nouveau nommé Leader dans Gartner Magic Quadrant pour les moteurs de personnalisation.</li></ul> |
|  | [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) | Informations clarifiées au titre de l&#39;étape 4 : Sélectionnez un emplacement. |
| 24 juillet | <br>[Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations relatives à at.js 2.3.2. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.7.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.5.1 (17 juin 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 17 juillet | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations sur la pause café Adobe Target du 22 juillet. |
| 15 juillet | [L’affectation automatique peut vous donner des résultats de test plus rapides et des revenus plus élevés qu’un test manuel.](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | Nouvelle rubrique. |
| 14 juillet | [FAQ sur l’affectation](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) automatique, la cible<br>[ automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) <br><br>[et la personnalisation automatisée](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Ajout d’une FAQ recommandant de ne pas modifier la mesure d’objectif à mi-chemin d’une activité. |
| 7 juillet | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations sur la pause café du 8 juillet à l&#39;Adobe Target. |
| 25 juin | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version de Target Standard/Premium 20.6.1 (juillet 2020). |
|  | [Présentation de la documentation cible](/help/r-release-notes/target-documentation.md) | Nouvelle rubrique détaillant les différentes sources de la documentation [!DNL Target]. |
| 23 juin | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations sur la pause café Adobe Target du 24 juin. |
|  | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Ajout d’une note indiquant que la création de scripts de profil dépendants qui utilisent le résultat d’un script de profil dans un autre script de profil n’est pas recommandée. |
|  | [Fonctionnement d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Ajout de la vidéo suivante : Heures de bureau : Conseils et présentation d’at.js |
| 17 juin | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Mise à jour d’une rubrique. |
|  | [Jetons de réponse](/help/administrating-target/response-tokens.md) | Ajout d’informations sur les jetons de réponse pour la méthode d’allocation du trafic pour les activités [!UICONTROL Ciblage automatique] et [!UICONTROL Automated Personalization]. |
|  | [Création de l’activité](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | Ajout d’informations sur la prise en charge d’Analytics pour Target (A4T) pour les activités d’affectation automatique. |
|  | [Utilisateurs](/help/administrating-target/c-user-management/c-user-management/user-management.md) | Ajout d&#39;informations sur le nouveau rôle [!UICONTROL Éditeur] sous *Spécifier les rôles et les autorisations*. |
|  | [Configuration des autorisations d’Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | Ajout d&#39;informations sur le nouveau rôle [!UICONTROL Éditeur] sous *Étape 6 : Spécifiez les rôles et les autorisations*. |
|  | [Autorisations des utilisateurs d’Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Ajout du lien vers les *heures de bureau : Session Target Premium Workspaces*. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.5.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.4.1 (6 mai 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 15 juin | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur les versions at.js 1.8.2 et at.js 2.3.1. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations sur les versions at.js 1.8.2 et at.js 2.3.1. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Mise à jour des notes relatives à la version [!DNL Target Standard/Premium] 20.5.1 (17 juin 2020) afin d’inclure des informations sur la prise en charge d’A4T dans [!DNL Analysis Workspace]. |
| 12 juin | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout d’informations sur le paramètre `deviceIdLifetime`. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’informations sur les versions at.js 1.8.2 et at.js 2.3.1. |
| 8 juin | [FAQ sur Target pour les applications mobiles](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | Texte mis à jour pour la FAQ suivante : &quot;Target Mobile est-il une fonctionnalité de la référence SKU de produit Premium d’Adobe Target uniquement ?&quot; |
|  | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour de la rubrique entière. |
| 5 juin | [Annonces et événements cibles](/help/r-release-notes/target-announcements.md) | Ajout d&#39;informations sur la pause café Adobe Target du 10 juin. |
|  | [FAQ sur l’effet élévateur et le degré de confiance - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | Texte mis à jour pour la FAQ suivante : &quot;Pourquoi est-ce que je ne vois pas l&#39;effet de levier et la confiance sur les mesures calculées ?&quot; |
| 4 juin | [Rapports A4T](/help/c-integrating-target-with-mac/a4t/reporting.md) | Mise à jour de la section &quot;Rapports dans Analytics&quot;. |
| 1er juin | [Annonces cibles](/help/r-release-notes/target-announcements.md) | Ajout d’une nouvelle page pour annoncer les prochains événements Target. |
|  | [Fenêtres d’affichage mobiles pour les expériences réactives](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | Dimensions et résolutions de la fenêtre d’affichage mises à jour pour l’iPhone 11 d’Apple, l’iPhone SE d’Apple et les modèles XL de Google Pixel 2. |
| Mai 28 | [FAQ sur la création de rapports](/help/c-reports/reporting-frequently-asked-questions.md) | Ajout de la question fréquente suivante : <ul><li>Comment les mesures Nouveaux visiteurs et Visiteurs de retour sont-elles comptabilisées ?</li></ul> |
| Mai 27 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’informations sur la prise en charge d’Analytics pour Target (A4T) pour les activités d’affectation automatique. |
| Mai 26 | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Ajout des informations suivantes : &quot;Le paramètre reste dans le profil après avoir désactivé le script. Les utilisateurs dont les profils contiennent déjà un paramètre qui est utilisé dans le public d&#39;une activité sont admissibles dans cette activité.&quot; |
| Mai 21 | [Liste autorisée des noeuds de bord de Cible](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Ajout de `mboxedge30.tt.omtrdc.net` à la liste. |
| Mai 20 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la prochaine version de Target Standard/Premium 20.6.1 (10 juin 2020). |
|  | [Hôtes](/help/administrating-target/hosts.md) | Ajout d’une note à la section &quot;Meilleures pratiques en matière de sécurité&quot;. |
| Mai 14 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur les modifications de l’API v2 de statut du lot de profils. |
| Mai 13 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Ajout de la section &quot;Restrictions connues&quot;. |
| Mai 11 | [Hôtes](/help/administrating-target/hosts.md) | Ajout d’informations sur l’utilisation de la fonctionnalité ubox avec les redirections et les listes d’autorisations. |
|  | [Fonctionnement avec un redirecteur](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Ajout d&#39;informations sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Intégration de Recommandations dans la messagerie électronique](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Ajout d&#39;informations sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Messagerie électronique : implémentation de Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Ajout d&#39;informations sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) | Mise à jour de la section &quot;Considérations&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Mise à jour de la ligne &quot;overrideMboxEdgeServer&quot; sous &quot;Paramètres&quot;. |
| Mai 6 | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Ajout d&#39;informations sur ITP 2.3. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.4.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.2.1 (19 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| Mai 4 | [FAQ sur la création de rapports](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Ajout d’une nouvelle FAQ : &quot;Pourquoi la répartition du trafic entre mes expériences est-elle inégale dans mon activité A/B ou MVT ?&quot; |
| Avril 29 | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un problème connu pour la génération de rapports avec des commandes extrêmes. |
| Avril 28 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Suppression des informations sur l&#39;utilisation de `user.header('x-forwarded-for')` avec des bords AWS plus récents pour récupérer les adresses IP des utilisateurs. Cette commande fonctionne désormais avec les bords AWS plus récents. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Date de publication de Target Standard/Premium (20.4.1) modifiée en 6 mai. |
| Avril 23 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Mise à jour d’une rubrique. |
| Avril 22 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Nouvelle section ajoutée : *Modifications de l&#39;API v2 d&#39;état du lot de profils (4 mai 2020).* |
| Avril 14 | [Hôtes de bord cible autorisés](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Nouvelle rubrique. |
| Avril 10 | [Mise en œuvre d’une application d’une seule page](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Nouvelle section ajoutée : &quot;Meilleures pratiques de mise en oeuvre.&quot; |
| Avril 7 | [FAQ sur l’effet élévateur et le degré de confiance - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Mise à jour du texte pour &quot;Pourquoi est-ce que je ne vois pas l’effet élévateur et le degré de confiance sur les mesures calculées ?&quot; |
| Avril 2 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Ajout d’informations sur l’utilisation de `user.header('x-forwarded-for')` avec des bords AWS plus récents pour récupérer les adresses IP des utilisateurs. |
|  | [Mise à niveau d’at.js 1.*x* vers at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Ajout de la remarque suivante :<ul><li>Après avoir installé la bibliothèque ECID v4.3.0+ et at.js 2.*x*, vous pouvez créer des activités qui s’étendent sur des domaines uniques et effectuer le suivi des utilisateurs. Il est important de noter que cette fonctionnalité ne fonctionne qu’après l’expiration de la session.</li></ul> |
| 30 mars | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Ajout d’un problème connu qui affectait les versions at.js antérieures à at.js 2.2.0. Ce problème entraînait le suivi des clics à ne pas signaler les conversions dans Analytics pour Target (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout des informations suivantes aux détails de at.js version 2.2.0 :<ul><li>Correction d’un problème en raison duquel le suivi des clics ne signalait pas les conversions dans Analytics pour Target (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page.</li></ul> |
| 25 mars | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations sur les nouvelles versions suivantes d’at.js :<ul><li>at.js version 2.3.0</li><li>at.js version 1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout des nouvelles lignes suivantes dans la section &quot;Paramètres&quot; :<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Ajout de la nouvelle section suivante :<ul><li>Stratégie de sécurité du contenu</li></ul> |
| 24 mars | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Ajout d’informations sur les impacts pour les éléments suivants :<ul><li>Scripts de profil basés sur 3rdPartyID</li><li>URL QA/Preview dans les appareils iOS</li></ul> |
| 20 mars | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Indique que la version Target Standard/Premium 20.2.1 sera publiée le 23 mars 2020. |
| 13 mars | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour du nombre de &quot;Audiences, réutilisables par compte.&quot; |
| 12 mars | [Notes de mise à jour (en cours)](/help/r-release-notes/release-notes.md#summit) | Ajout d’informations d’inscription pour un accès gratuit à la conférence numérique en ligne. |
| 9 mars | [Confidentialité](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Ajout d’informations supplémentaires dans la section &quot;Remplacement du dernier octet d’adresses IP&quot;. |
|  | [Utilisation des attributs à plusieurs valeurs](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Exemple de code mis à jour dans *Passer un paramètre à plusieurs valeurs dans JavaScript*. |
|  | [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md) | Exemple de code ajouté dans *Utilisation d&#39;API* sous *Implémentation d&#39;attributs à plusieurs valeurs*. |
| 4 mars | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Mise à jour de la rubrique entière, avec des révisions approfondies de la section &quot;Meilleures pratiques&quot;. |
| 21 février | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur la nouvelle navigation Adobe Experience Cloud. |
| 20 février | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Mise à jour de la description du paramètre `enabled`. Ajout d’informations pour les paramètres suivants : `pageLoadEnabled` et `viewsEnabled`. |
|  | [Géo](/help/c-target/c-audiences/c-target-rules/geo.md) | Ajout d’une note indiquant que `mboxOverride.browserIp` est pris en charge dans at.js 1.*x* uniquement. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Texte clarifié expliquant les versions d’at.js prises en charge par l’équipe cible. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.2.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.1.1 (4 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 4 février | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.1.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |
