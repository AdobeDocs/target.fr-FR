---
keywords: target documentation change log;documentation updates;new topics;edits;updates;update
description: Cette page liste les modifications importantes apportées à la documentation Adobe Target, classées par versions.
title: Modifications apportées à documentation du produit Adobe Target.
feature: release notes
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: 9faed3d7fa8659c04059486a23bbb3957a0f5e27
workflow-type: tm+mt
source-wordcount: '1814'
ht-degree: 30%

---


# Modifications de la documentation{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.7.1 (27 juillet 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 14 août | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Problème connu Ajouté concernant l’assurance qualité dans les activités Recommendations. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Texte Ajouté indiquant que si vous utilisez `serverState` et utilisez `<script>` des balises dans le contenu renvoyé, veillez à ce que votre contenu HTML utilise `<\/script>` plutôt que `</script>`. |
| 12 août | [Comprendre l’interface utilisateur de la Cible](/help/c-intro/understand-the-target-ui.md) | Nouvelle rubrique. |
|  | [Présentation de l’API Adobe Target](/help/api/api-overview.md) | Nouvelle rubrique. |
| 10 août | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Texte Ajouté indiquant que la taille de l’en-tête du cookie augmente lors de l’utilisation de CNAME. |
|  | [Intégration de la Cible avec Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) | Nouvelle rubrique. |
|  | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Lien Ajouté vers la vue du webinaire archivé suivant : &quot;Comment HSBC exploite Adobe Target et l&#39;IA pour optimiser rapidement et fournir une personnalisation à grande échelle.&quot; |
| 6 août | [Ciblage automatique](/help/c-activities/auto-target-to-optimize.md#how-long) | Mise à jour du texte de la FAQ suivante : &quot;Combien de temps dois-je attendre que les modèles soient créés ?&quot; |
|  | [FAQ sur les classifications - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-classifications.md) | Mise à jour du texte pour targettype. |
| 5 août | [Suppression du cookie Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md) | Mise à jour de la rubrique entière. |
| 4 août | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations d’enregistrement Ajoutées sur le webinaire &quot;Stratégies de personnalisation utilisant l’intelligence artificielle et Adobe Target&quot; prévu pour le 13 août. |
|  | [Activation du contenu mixte dans votre navigateur](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md) | Mise à jour d’une rubrique. |
| 3 août | [Mesures de succès](/help/c-activities/r-success-metrics/success-metrics.md) | Note Ajoutée expliquant ce que les options [!UICONTROL Incrémenter le décompte] signifient en ce qui concerne les visiteurs par rapport aux visites. |
| 31 juillet | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Nouveau problème connu Ajouté : &quot;Offres d’image présentant l’étiquette &quot;Traitement&quot;.&quot; |
|  | [adobe.target.getOffers(options) - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Exemple de code Ajouté à utiliser `getoffers()` pour effectuer une pageLoad. |
|  | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations d&#39;enregistrement Ajoutées sur la prochaine pause café de la communauté Adobe Target le 5 août. |
| 28 juillet | [Rapports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)d’informations sur la personnalisation, rapport<br>[Segments](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatisés<br>et rapport Attributs [importants](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) | Mise à jour du texte de la note en haut des rubriques. |
|  | [Affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ajout des questions fréquentes suivantes :<ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité d’affectation automatique ?</li><li>Comment l&#39;affectation automatique génère-t-elle des modèles en ce qui concerne les environnements ?</li></ul> |
|  | [Ciblage automatique](/help/c-activities/auto-target-to-optimize.md) | Ajout de la question fréquente suivante :    <ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité d’Cible automatique ?</li></ul>Mise à jour du texte dans la section &quot;Considérations&quot;. |
|  | [FAQ sur Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Ajout des questions fréquentes suivantes :<ul><li>Puis-je utiliser l’option Réinitialiser les données du rapport lors de l’exécution d’une activité Automated Personalization ?</li><li>Comment Automated Personalization construit-t-il des modèles en ce qui concerne les environnements ?</li></ul> |
|  | [Navigateurs pris en charge](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Informations Ajoutées sur Internet Explorer et éléments inconnus. |
|  | [Attributs du client](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Updated following paragraph:<br>[!DNL Adobe] does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. Dans notre conception actuelle, il est possible qu&#39;un petit pourcentage de données (jusqu&#39;à 0,1 % des grands lots de production) ne soient pas intégrées. |
| 27 juillet | [Administration de Target](/help/administrating-target/administrating-target.md) | Mise à jour du texte de toutes les rubriques liées sur cette page afin de refléter les nouvelles modifications apportées à l’interface utilisateur pour les pages [!UICONTROL d’administration] . |
|  | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Les modifications suivantes ont été apportées : <ul><li>Informations d’inscription Ajoutées pour le webinaire suivant : &quot;Comment HSBC exploite Adobe Target et l&#39;IA pour optimiser rapidement et fournir une personnalisation à grande échelle.&quot;</li><li>Informations Ajoutées sur le fait que l&#39;Adobe est à nouveau nommé Leader dans Gartner Magic Quadrant pour les moteurs de personnalisation.</li></ul> |
|  | [Compositeur d’expérience d’après les formulaires](/help/c-experiences/form-experience-composer.md) | Clarification de l&#39;information à l&#39;étape 4 : Sélectionnez un emplacement. |
| 24 juillet | <br>[Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations relatives à at.js 2.3.2. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.7.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.5.1 (17 juin 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 17 juillet | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations Ajoutées sur la pause café Adobe Target du 22 juillet. |
| 15 juillet | [L’affectation automatique peut vous donner des résultats de test plus rapides et des recettes plus élevées qu’un test manuel.](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md) | Nouvelle rubrique. |
| 14 juillet | [FAQ sur l’affectation](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)automatique, la Cible<br>[](/help/c-activities/auto-target-to-optimize.md)<br><br>[automatique et la personnalisation automatisée](/help/c-activities/t-automated-personalization/automated-personalization-faq.md) | Questions fréquentes Ajoutées recommandant de ne pas modifier la mesure d’objectif à mi-chemin d’une activité. |
| 7 juillet | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations Ajoutées sur la pause café Adobe Target du 8 juillet. |
| 25 juin | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la version de Target Standard/Premium 20.6.1 (juillet 2020). |
|  | [Présentation de la documentation de la cible](/help/r-release-notes/target-documentation.md) | Nouvelle rubrique détaillant les différentes sources de [!DNL Target] documentation. |
| 23 juin | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations Ajoutées sur la pause café Adobe Target du 24 juin. |
|  | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Remarque Ajoutée : la création de scripts de profil dépendants qui utilisent le résultat d’un script de profil dans un autre script de profil n’est pas recommandée. |
|  | [Fonctionnement d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | ajouté la vidéo suivante : Heures de bureau : conseils et présentation d’at.js |
| 17 juin | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Mise à jour d’une rubrique. |
|  | [Jetons de réponse](/help/administrating-target/response-tokens.md) | Informations Ajoutées sur les jetons de réponse pour la méthode d’affectation du trafic pour les activités de Cible  automatique et de Automated Personalization  . |
|  | [Création de l’activité](/help/c-integrating-target-with-mac/a4t/campaign-creation.md) | Informations Ajoutées sur la prise en charge d’Analytics pour la Cible (A4T) pour les activités d’affectation automatique. |
|  | [Utilisateurs](/help/administrating-target/c-user-management/c-user-management/user-management.md) | Informations Ajoutées sur le nouveau rôle [!UICONTROL Editeur] sous *Spécifier les rôles et autorisations*. |
|  | [Configuration des autorisations d’Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md) | Informations Ajoutées sur le nouveau rôle [!UICONTROL Editeur] à l’ *étape 6 : Spécifiez les rôles et les autorisations*. |
|  | [Autorisations des utilisateurs d’Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Lien Ajouté vers les heures de *bureau : Session* des espaces de travail cible Premium. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.5.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.4.1 (6 mai 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 15 juin | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Informations Ajoutées sur les versions d’at.js 1.8.2 et d’at.js 2.3.1. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations Ajoutées sur les versions d’at.js 1.8.2 et d’at.js 2.3.1. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Mise à jour des notes de la version [!DNL Target Standard/Premium] 20.5.1 (17 juin 2020) afin d’inclure des informations sur la prise en charge d’A4T dans [!DNL Analysis Workspace]. |
| 12 juin | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout d’informations sur le paramètre `deviceIdLifetime`. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur les versions d’at.js 1.8.2 et d’at.js 2.3.1. |
| 8 juin | [FAQ sur Target pour les applications mobiles](/help/c-target-mobile-app/target-for-mobile-apps-faq.md) | Mise à jour du texte de la FAQ suivante : &quot;Cible Mobile est-elle une fonctionnalité du SKU du produit Adobe Target Premium uniquement ?&quot; |
|  | [FAQ sur l’affichage des rapports - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Mise à jour de la rubrique entière. |
| 5 juin | [Annonces de cible et événements](/help/r-release-notes/target-announcements.md) | Informations Ajoutées sur la pause café Adobe Target du 10 juin. |
|  | [FAQ sur l’effet élévateur et le degré de confiance - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md) | Mise à jour du texte de la FAQ suivante : &quot;Pourquoi est-ce que je ne vois pas l’effet élévateur et le degré de confiance sur les mesures calculées ?&quot; |
| 4 juin | [Rapports A4T](/help/c-integrating-target-with-mac/a4t/reporting.md) | Mise à jour de la section &quot;Rapports dans Analytics&quot;. |
| 1er juin | [Annonces de cible](/help/r-release-notes/target-announcements.md) | Nouvelle page Ajoutée pour annoncer les événements de Cible à venir. |
|  | [Fenêtres d’affichage mobiles pour les expériences réactives](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) | Mise à jour des dimensions et résolutions des fenêtres d’affichage pour les modèles Apple iPhone 11, Apple iPhone SE et Google Pixel 2 XL. |
| Mai 28 | [FAQ sur la création de rapports](/help/c-reports/reporting-frequently-asked-questions.md) | Ajout de la question fréquente suivante : <ul><li>Comment les mesures Nouveaux Visiteurs et Visiteurs récurrents sont-elles comptabilisées ?</li></ul> |
| Mai 27 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la prise en charge d’Analytics pour la Cible (A4T) pour les activités d’affectation automatique. |
| Mai 26 | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Informations Ajoutées : &quot;Le paramètre reste dans le profil après la désactivation du script. Les utilisateurs dont les profils contiennent déjà un paramètre utilisé dans une audience d’activité seront inclus dans cette activité.&quot; |
| Mai 21 | [Liste autorisée des noeuds de bord de Cible](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | ajouté `mboxedge30.tt.omtrdc.net` à la liste. |
| Mai 20 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Informations Ajoutées sur la prochaine version de Target Standard/Premium 20.6.1 (10 juin 2020). |
|  | [Hôtes](/help/administrating-target/hosts.md) | Note Ajoutée à la section &quot;Meilleures pratiques en matière de sécurité&quot;. |
| Mai 14 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Informations Ajoutées sur les modifications de la version 2 de l’API d’état du lot de Profils. |
| Mai 13 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Section &quot;Limites connues&quot; Ajoutée. |
| Mai 11 | [Hôtes](/help/administrating-target/hosts.md) | Informations Ajoutées sur l’utilisation de la fonctionnalité de boîte aux lettres avec redirections et listes autorisées. |
|  | [Fonctionnement avec un redirecteur](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Informations Ajoutées sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Intégration de Recommandations dans la messagerie électronique](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Informations Ajoutées sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Messagerie électronique : implémentation de Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Informations Ajoutées sur l&#39;utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) | Mise à jour de la section &quot;Considérations&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Mise à jour de la ligne &quot;overrideMboxEdgeServer&quot; sous &quot;Paramètres&quot;. |
| Mai 6 | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Informations Ajoutées au sujet du PTI 2.3. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.4.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.2.1 (19 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| Mai 4 | [FAQ sur la création de rapports](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Nouvelle FAQ Ajoutée : &quot;Pourquoi la répartition du trafic entre mes expériences est-elle inégale dans mon activité A/B ou MVT ?&quot; |
| Avril 29 | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Problème connu Ajouté pour les rapports ayant des commandes extrêmes. |
| Avril 28 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Suppression des informations sur l’utilisation `user.header('x-forwarded-for')` avec des arêtes AWS plus récentes pour récupérer les adresses IP des utilisateurs. Cette commande fonctionne désormais avec les arêtes AWS les plus récentes. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Date de publication de Target Standard/Premium (20.4.1) modifiée en 6 mai. |
| Avril 23 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Mise à jour d’une rubrique. |
| Avril 22 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Nouvelle section Ajoutée : *Modifications de l’API v2 de l’état du lot de profils (4 mai 2020).* |
| Avril 14 | [Hôtes du bord de la Cible de Liste autorisée](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Nouvelle rubrique. |
| Avril 10 | [Mise en œuvre d’une application d’une seule page](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Nouvelle section Ajoutée : &quot;Meilleures pratiques d’implémentation.&quot; |
| Avril 7 | [FAQ sur l’effet élévateur et le degré de confiance - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Mise à jour du texte pour &quot;Pourquoi est-ce que je ne vois pas l’effet élévateur et le degré de confiance sur les mesures calculées ?&quot; |
| Avril 2 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Informations Ajoutées sur l’utilisation `user.header('x-forwarded-for')` avec des arêtes AWS plus récentes pour récupérer les adresses IP des utilisateurs. |
|  | [Mise à niveau d’at.js 1.*x* vers at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Ajout de la remarque suivante :<ul><li>Après avoir installé la bibliothèque ECID v4.3.0+ et at.js 2.*x*, vous pouvez créer des activités qui s’étendent sur des domaines uniques et effectuer le suivi des utilisateurs. Il est important de noter que cette fonctionnalité ne fonctionne qu’après l’expiration de la session.</li></ul> |
| 30 mars | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Correction d’un problème connu qui affectait les versions d’at.js antérieures à at.js 2.2.0. Ce problème empêchait le suivi des clics de signaler les conversions dans Analytics pour la Cible (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | ajouté les informations suivantes aux détails de at.js version 2.2.0 :<ul><li>Correction d’un problème en raison duquel le suivi des clics ne signalait pas les conversions dans Analytics pour la Cible (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page.</li></ul> |
| 25 mars | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations Ajoutées sur les nouvelles versions suivantes d’at.js :<ul><li>at.js version 2.3.0</li><li>at.js version 1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | ajoute les nouvelles lignes suivantes dans la section &quot;Paramètres&quot; :<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Ajout de la nouvelle section suivante :<ul><li>Stratégie de sécurité du contenu</li></ul> |
| 24 mars | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Informations Ajoutées sur les impacts pour les éléments suivants :<ul><li>Scripts de profil basés sur 3rdPartyID</li><li>URL de contrôle qualité/Prévisualisation sur les périphériques iOS</li></ul> |
| 20 mars | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Indique que la version de Target Standard/Premium 20.2.1 sera publiée le 23 mars 2020. |
| 13 mars | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour du nombre d’Audiences réutilisables par compte. |
| 12 mars | [Notes de mise à jour (en cours)](/help/r-release-notes/release-notes.md#summit) | Informations d&#39;inscription Ajoutées pour un accès gratuit à la conférence numérique en ligne du sommet. |
| 9 mars | [Confidentialité](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | ajouté plus d’informations dans la section &quot;Remplacement du dernier octet des adresses IP&quot;. |
|  | [Utilisation des attributs à plusieurs valeurs](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Mise à jour de l’exemple de code dans *Transmettre un paramètre à plusieurs valeurs dans JavaScript*. |
|  | [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md) | Exemple de code Ajouté dans *Utilisation d’API* sous *Implémentation d’attributs*&#x200B;à plusieurs valeurs. |
| 4 mars | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Mise à jour de la rubrique complète, avec des révisions importantes de la section &quot;Meilleures pratiques&quot;. |
| 21 février | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Informations Ajoutées sur la nouvelle navigation Adobe Experience Cloud. |
| 20 février | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. Informations Ajoutées pour les paramètres suivants : `pageLoadEnabled` et `viewsEnabled`. |
|  | [Géo](/help/c-target/c-audiences/c-target-rules/geo.md) | Remarque Ajoutée prise en `mboxOverride.browserIp` charge dans at.js 1.*x* uniquement. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Texte clarifié expliquant les versions d’at.js prises en charge par l’équipe de Cible. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.2.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.1.1 (4 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 4 février | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.1.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |
