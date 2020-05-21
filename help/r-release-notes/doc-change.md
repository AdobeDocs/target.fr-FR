---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: Cette page liste les modifications importantes apportées à la documentation d’Adobe Cible, classées par versions.
title: Modifications apportées à documentation du produit Adobe Target.
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: da102687f5d73813e3670b166eb0e668b96c93b6
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 36%

---


# Modifications de la documentation{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.4.1 (6 mai 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| Mai 21 | [Noeuds de bord de la Cible liste blanche](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Ajout `mboxedge30.tt.omtrdc.net` à la liste. |
| Mai 20 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’informations sur la prochaine version de Cible Standard/Premium 20.6.1 (10 juin 2020). |
|  | [Hôtes](/help/administrating-target/hosts.md) | Ajout d’une note à la section &quot;Meilleures pratiques en matière de sécurité&quot;. |
| Mai 14 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’informations à propos des modifications de l’API v2 d’état du lot de Profils. |
| Mai 13 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Ajout de la section &quot;Limites connues&quot;. |
| Mai 11 | [Hôtes](/help/administrating-target/hosts.md) | Ajout d’informations sur l’utilisation de la fonctionnalité de boîte aux lettres avec redirections et listes blanches. |
|  | [Fonctionnement avec un redirecteur](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Ajout d’informations sur l’utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Intégration de Recommandations dans la messagerie électronique](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Ajout d’informations sur l’utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
|  | [Messagerie électronique : implémentation de Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Ajout d’informations sur l’utilisation des hôtes pour éviter les vulnérabilités de redirection ouverte. |
| Mai 7 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Avec la prochaine désapprobation de mbox.js, le 30 août 2020, David Son, responsable de produit Adobe Cible, a récemment hébergé une discussion pour les développeurs afin de discuter des avantages de la migration de mbox.js vers at.js. Il existe un lien vers lequel vous pouvez regarder le webinaire pendant les 30 prochains jours. |
|  | [AQ d’activité](/help/c-activities/c-activity-qa/activity-qa.md) | Mise à jour de la section &quot;Considérations&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Mise à jour de la ligne &quot;overrideMboxEdgeServer&quot; sous &quot;Paramètres&quot;. |
| Mai 6 | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Ajout d’informations sur ITP 2.3. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.4.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.2.1 (19 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| Mai 4 | [FAQ sur la création de rapports](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Ajout d’une nouvelle FAQ : &quot;Pourquoi la répartition du trafic entre mes expériences est-elle inégale dans mon activité A/B ou MVT ?&quot; |
| Avril 29 | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md) | Ajout d’un problème connu pour les rapports avec des commandes extrêmes. |
| Avril 28 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Suppression des informations sur l’utilisation `user.header('x-forwarded-for')` avec des arêtes AWS plus récentes pour récupérer les adresses IP des utilisateurs. Cette commande fonctionne désormais avec les arêtes AWS les plus récentes. |
|  | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Modification de la date de publication de Cible Standard/Premium (20.4.1) en 6 mai. |
| Avril 23 | [CNAME et Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Mise à jour d’une rubrique. |
| Avril 22 | [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md) | Ajout d’une nouvelle section : *Modifications de l’API v2 de l’état du lot de Profils (4 mai 2020).* |
| Avril 20 | [Notes de mise à jour de Target (actualisées)](/help/r-release-notes/release-notes.md) | Ajout d’une nouvelle section : *Adobe Cible Skill Builder : Chat de développeur, migrez le fichier mbox.js de la Cible Adobe vers at.js.* |
| Avril 14 | [Hôtes Edge de Cible de liste blanche](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Nouvelle rubrique. |
| Avril 10 | [Mise en œuvre d’une application d’une seule page](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Ajout d’une nouvelle section : &quot;Meilleures pratiques d’implémentation.&quot; |
| Avril 7 | [FAQ sur l’effet élévateur et le degré de confiance - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Mise à jour du texte pour &quot;Pourquoi est-ce que je ne vois pas l’effet élévateur et le degré de confiance sur les mesures calculées ?&quot; |
| Avril 2 | [Glossaire des profils et variables](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Ajout d’informations sur l’utilisation `user.header('x-forwarded-for')` avec des arêtes AWS plus récentes pour récupérer les adresses IP des utilisateurs. |
|  | [Mise à niveau d’at.js 1.*x* vers at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Ajout de la remarque suivante :<ul><li>Après avoir installé la bibliothèque ECID v4.3.0+ et at.js 2.*x*, vous pouvez créer des activités qui s’étendent sur des domaines uniques et effectuer le suivi des utilisateurs. Il est important de noter que cette fonctionnalité ne fonctionne qu’après l’expiration de la session.</li></ul> |
| 30 mars | [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Ajout d’un problème connu affectant les versions d’at.js antérieures à at.js 2.2.0. Ce problème empêchait le suivi des clics de signaler les conversions dans Analytics pour la Cible (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout des informations suivantes aux détails de at.js version 2.2.0 :<ul><li>Correction d’un problème en raison duquel le suivi des clics ne signalait pas les conversions dans Analytics pour la Cible (A4T) lorsque le code Adobe Analytics n’était pas présent sur les éléments de page.</li></ul> |
| 25 mars | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Ajout d’informations sur les nouvelles versions suivantes d’at.js :<ul><li>at.js version 2.3.0</li><li>at.js version 1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Ajout des nouvelles lignes suivantes dans la section &quot;Paramètres&quot; :<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Ajout de la nouvelle section suivante :<ul><li>Stratégie de sécurité du contenu</li></ul> |
| 24 mars | [ITP (Intelligent Tracking Prevention) 2.x d’Apple](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Ajout d’informations sur les impacts pour les éléments suivants :<ul><li>Scripts de Profil basés sur 3rdPartyID</li><li>URL de contrôle qualité/Prévisualisation sur les périphériques iOS</li></ul> |
| 20 mars | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Indique que la version de Cible Standard/Premium 20.2.1 sera publiée le 23 mars 2020. |
| 13 mars | [Limites](/help/r-troubleshooting-target/target-limits.md) | Mise à jour du nombre d’Audiences réutilisables par compte. |
| 12 mars | [Notes de mise à jour (en cours)](/help/r-release-notes/release-notes.md#summit) | Ajout d’informations d’inscription pour un accès gratuit à la conférence numérique en ligne du sommet. |
| 9 mars | [Confidentialité](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Ajout d’informations supplémentaires dans la section &quot;Remplacement du dernier octet des adresses IP&quot;. |
|  | [Utilisation d’attributs à plusieurs valeurs](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Mise à jour de l’exemple de code dans *Transmettre un paramètre à plusieurs valeurs dans JavaScript*. |
|  | [Attributs d’entité personnalisés](/help/c-recommendations/c-products/custom-entity-attributes.md) | Ajout d’un exemple de code dans *Utilisation d’API* sous *Implémentation d’attributs*&#x200B;à plusieurs valeurs. |
| 4 mars | [Attributs de profil](/help/c-target/c-visitor-profile/profile-parameters.md) | Mise à jour de la rubrique complète, avec des révisions importantes de la section &quot;Meilleures pratiques&quot;. |
| 21 février | [Notes de mise à jour (actuelles)](/help/r-release-notes/release-notes.md) | Ajout d’informations sur la nouvelle navigation dans Adobe Experience Cloud. |
| 20 février | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. Ajout d’informations pour les paramètres suivants : `pageLoadEnabled` et `viewsEnabled`. |
| 19 février | [Notes de mise à jour](/help/r-release-notes/release-notes.md) | Ajout d’informations à propos de la prochaine désapprobation de la bibliothèque mbox.js. |
|  | [Géo](/help/c-target/c-audiences/c-target-rules/geo.md) | Ajout d’une remarque indiquant que `mboxOverride.browserIp` at.js 1 est pris en charge.*x* uniquement. |
|  | [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Texte clarifié expliquant les versions d’at.js prises en charge par l’équipe de Cible. |
|  | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.2.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |

## Adobe Target Standard/Premium 20.1.1 (4 février 2020)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 4 février | [Notes de mise à jour](/help/r-release-notes/release-notes.md) : 20.1.1 | Cette version comprend des améliorations et des correctifs. Vous pouvez les lire et les lier à la documentation depuis les notes de mise à jour. Cette version inclut également de nombreuses mises à jour de la documentation dans l’ensemble de l’aide. |
