---
keywords: journal des modifications de la documentation de Target;mises à jour de la documentation;nouvelles rubriques;modifications;mises à jour;mise à jour
description: Tenez-vous informé des modifications et des ajouts importants apportés à la documentation d’ [!DNL Adobe Target] .
title: Où puis-je consulter les mises à jour de la documentation de  [!DNL Target] ?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7d84ce530081c20f7cdcb6e89010baef6f638647
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 97%

---

# Modifications de la documentation

Cette rubrique répertorie les modifications importantes apportées à la documentation d’[!DNL Adobe Target].

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 et 25 janvier 2024)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 8 février | [Prérécupération](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html){target=_blank} | Ajout d’une nouvelle section : &quot;Prérécupération des mbox avec des mesures de suivi des clics lors de l’utilisation d’Analytics for Target (A4T)&quot; |
| 5 février | [Création d’une activité utilisant Analytics en tant que source de rapports](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | Ajout d’un texte spécifiant que vous ne pouvez pas utiliser le même nom pour deux activités provenant d’espaces de travail distincts lors de l’utilisation d’[!UICONTROL Analytics for Target] (A4T) comme source des rapports. |
|  | [Questions fréquentes sur le paramétrage des activités - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | Ajout d’un texte spécifiant que vous ne pouvez pas utiliser le même nom pour deux activités provenant d’espaces de travail distincts lors de l’utilisation d’[!UICONTROL Analytics for Target] (A4T) comme source des rapports. |
|  | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations à propos de la pause de café de la communauté Adobe Target prévue pour le 7 février 2024. |
| 24 janvier | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Ajout de notes de mise à jour pour la version 2.11.4 d’at.js. |
|  | [Navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | Annonce que les deux nouveaux profils ne sont pas encore disponibles. Ces notes seront mises à jour lorsque ces profils seront disponibles. |
|  | [Questions fréquentes sur at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html?lang=fr){target=_blank} | Ajout de questions fréquentes relatives à at.js dans un environnement d’application Ionic. Cette implémentation n’est ni testée ni recommandée. |
| 22 janvier | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations importantes sur l’obsolescence de l’iPad et de l’iPhone dans l’attribut d’audience [!UICONTROL Navigateur] qui nécessite des modifications de votre part avant le 30 avril 2024. |
|  | [Navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | Ajout d’une nouvelle section : <ul><li>Obsolescence de l’iPad et de l’iPhone dans l’attribut d’audience Navigateur (30 avril 2024)</li></ul> |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 24.1.1 de [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.11.1 (13 et 14 novembre 2023)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 18 janvier | Notes de mise à jour de [[!DNL Target]  (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout de notes de mise à jour préliminaires relatives à la version 24.1.1 de [!DNL Target Standard/Premium] à venir. |
| 13 décembre | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations à propos de la Série de webinaires d’[!DNL Adobe Target] sur la maturité de personnalisation de 2024. |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=fr){target=_blank} | Ajout de deux nouveaux paramètres facultatifs : <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 4 décembre | Annonces et événements [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations d’enregistrement à propos de la pause café « Machine learning, rapports et analyses basés sur l’IA » [!DNL Adobe Target Community] : mercredi 6 décembre 2023. |
| 1er décembre | [API de mise à jour du profil Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank} | Déplacement de la documentation héritée de l’API vers les articles suivants :<ul><li>[Vue d’ensemble des API de profil Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html){target=_blank}</li><li>[API de mise à jour de profil unique Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html){target=_blank}</li><li>[API de mise à jour du profil en bloc Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?){target=_blank}</li></ul> |
| 29 novembre | [API de mise à jour des profils en bloc](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=fr){target=_blank} | Clarification des différences sur la manière dont [!DNL Target] gère les attributs des clientes et clients lors de la création d’un profil pour un utilisateur ou une utilisatrice que [!DNL Target] n’a pas encore vu lors de l’utilisation de l’[!UICONTROL API de mise à jour des profils en bloc] v2 plutôt que v1. |
| 21 novembre | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Ajout de notes de mise à jour pour at.js 2.11.3 |
| 17 novembre | [Premières étapes pour l’administrateur ou l’administratrice](/help/main/administrating-target/start-target.md) | Ajout de la remarque importante suivante :<ul><li>Les personnes avec des droits d’[!UICONTROL administration de produit] ou d’[!UICONTROL administration système] dans [!DNL Adobe Admin Console] peuvent modifier tous les paramètres de la page [!UICONTROL Administration] de [!DNL Target], quel que soit leur rôle [!DNL Target]. Les personnes ne possédant pas les droits d’[!UICONTROL administration de produit] ou d’[!UICONTROL administration système] dans [!DNL Adobe Admin Console] doivent avoir le rôle [!DNL Target] spécifique afin d’effectuer ces modifications.1</li></ul> |
|  | [Limites](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | Mise à jour de la section contenant des informations sur la manière dont [!DNL Target] gère la troncation dans at.js 2.*x* et le [!DNL Adobe Experience Platform Web SDK]. |
|  | [API de diffusion](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=fr){target=_blank} | Ajout de redirections vers la documentation actuelle de l’API de diffusion et obsolescence de la documentation héritée (`http://developers.adobetarget.com/api/delivery-api/`). Mettez vos signets à jour si nécessaire. |
| 16 novembre | [API de mise à jour des profils en bloc](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=fr){target=_blank} | Ajout de l’avertissement suivant : « Les mises à jour surviennent généralement en moins d’une heure, mais peuvent prendre jusqu’à 24 heures pour être répercutées. » |
| 13 novembre | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.11.1 de [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.10.2 (24 octobre 2023)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 10 novembre | [Référence de l’API Recommendations](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | L’API [!DNL Recommendations] d’[!DNL Adobe Target] a été déplacée vers le site web [!DNL Adobe Developer]. Mettez à jour vos signets si nécessaire. |
|  | [Période](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Ajout d’une remarque selon laquelle les audiences horaires [!DNL Target] ne prennent pas en compte les modifications de l’heure d’été. Vous devez mettre à jour manuellement les audiences afin de les prendre en compte. |
| 8 novembre | Notes de mise à jour de [[!DNL Target]  (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 23.11.1 de [!DNL Target Standard/Premium] à venir |
| 28 octobre | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Ajout d’informations relatives à la version 2.11.2 d’at.js. |
| 25 octobre | [[!DNL Target] Notes de mise à jour (actuelles)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations à propos de l’actualisation de l’interface utilisateur de la page [!UICONTROL Activités] (25 octobre 2023) |
| 24 octobre | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.10.2 de [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.9.1 (du 6 au 11 septembre 2023)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 17 octobre | [FAQ sur la création de rapports](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | Mise à jour de la FAQ suivante : « Pourquoi n’existe-t-il aucune donnée disponible pour le rapport de mon activité ?  » |
| 11 octobre | [[!DNL Adobe Analytics]  comme source de création de rapports pour  [!DNL Adobe Target]  (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) | Mise à jour des informations sur la prise en charge d’A4T pour [!DNL Adobe Experience Platform Web SDK]. |
| 10 octobre | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Ajout de notes de mise à jour pour la version 2.11.0 d’at.js. |
| 6 octobre | [Jetons de réponse](/help/main/administrating-target/response-tokens.md) | Mise à jour de tous les exemples de code. |
|  | [Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités d’[!UICONTROL affectation automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank} | Mise à jour complète du tutoriel dans le guide *[!UICONTROL Tutoriels d’Adobe Target]*. |
| 4 octobre | [Activités](/help/main/c-activities/activities.md) | Mise à jour du texte et des images, de sorte à refléter l’actualisation de l’interface utilisateur incluse dans la version 23.9.4 de [!DNL Target]. |
|  | [Flux](/help/main/c-recommendations/c-products/feeds.md) | Mise à jour du texte et des images, de sorte à refléter l’actualisation de l’interface utilisateur incluse dans la version 23.9.4 de [!DNL Target]. |
| 2 octobre | [[!DNL Target] Notes de mise à jour (actuelles)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.9.3 de [!DNL Target Standard/Premium]. |
|  | Modèle d’implémentation de [[!DNL Recommendations] ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=fr){target=_blank} | Les nouveaux articles *Modèle d’implémentation de Recommendations à l’aide d’at.js* permettent de comprendre et de créer votre implémentation de [!DNL Adobe Target Recommendations] lors de l’utilisation de la bibliothèque JavaScript at.js.<P>Pour obtenir des informations générales sur les modèles de [!DNL Target], voir [Vue d’ensemble des modèles d’implémentation](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html?lang=fr){target=_blank} dans le *Guide du développement d’Adobe Target*.<P>Le nouveau modèle d’implémentation de Recommendations se compose des articles suivants :<ul><li>[Vue d’ensemble du modèle d’implémentation de Recommendations à l’aide d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=fr){target=_blank}</li><ul><li>[Initialiser les SDK](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html?lang=fr){target=_blank}</li><li>[Configurer la collecte de données](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html?lang=fr){target=_blank}</li><li>[Effectuer le rendu d’expériences](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=fr){target=_blank}</li><li>[Notifier [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=fr){target=_blank}</li></ul></ul> |
| 29 septembre | Notes de mise à jour de [[!DNL Target] (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 23.9.3 de [!DNL Target Standard/Premium] |
|  | [Initialiser le SDK Java](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html?lang=fr){target=_blank} | Ajout des nouveaux paramètres suivants dans le tableau :<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 22 septembre | [Résolution des problèmes liés au [!UICONTROL Compositeur d’expérience avancé]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | Mise à jour de la liste d’adresses IP dans la liste autorisée. |
| 18 septembre | [[!DNL Target] Notes de mise à jour (actuelles)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.9.3 de [!DNL Target Standard/Premium]. |
| 15 septembre | Notes de mise à jour de [[!DNL Target] (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 23.9.3 de [!DNL Target Standard/Premium] |
| 12 septembre | [[!DNL Target] Notes de mise à jour (actuelles)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.9.2 de [!DNL Target Standard/Premium]. |
|  | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Ajout de notes de mise à jour pour la version 2.10.3 d’at.js. |
| 11 septembre | Notes de mise à jour de [[!DNL Target] (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 23.9.2 de [!DNL Target Standard/Premium] |
| 6 septembre | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.9.1 de [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.8.1 (9 août 2023)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 1 septembre | [Environnements](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | Mise à jour de la note sous « Définition de l’environnement par défaut pour la création de rapports ». |
| 30 août | [Confidentialité](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html?lang=fr#aep){target=_blank} | Ajout d’une nouvelle section : « Obscurcissement d’IP au niveau du train de données lors de l’utilisation du SDK web Adobe Experience Platform » |
|  | [Questions fréquentes sur le paramétrage des activités - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | Correction de la période d’attente d’affichage des données dans les rapports des questions fréquentes suivantes : « Je viens de créer une activité. Pourquoi les données ne s’affichent-elles pas ? » |
| 29 août | [Fonctionnalités prises en charge pour la prise de décision sur l’appareil](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html?lang=fr){target=_blank} | Ajout de la liste des attributs de géolocalisation pris en charge pour le ciblage lors de l’utilisation de la prise de décision sur l’appareil (ODD) côté client. |
|  | [Vue d’ensemble de la prise de décision sur l’appareil](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=fr){target=_blank} | Ajout de la liste des attributs de géolocalisation pris en charge pour le ciblage lors de l’utilisation de la prise de décision sur l’appareil (ODD) côté serveur. |
|  | [Mise en œuvre de Target avec le SDK mobile AEP dans une application native avec des vues web](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html?lang=fr){target=_blank} | Nouvel article. |
|  | Annonces et événements [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations sur la prochaine session Pause-café de la communauté Adobe Target (30 août 2023) : suivi du webinaire « Stratégie pour un impact maximal du retour sur investissement grâce à la préparation à la haute saison ». |
| 14 août | [QA d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md) | Information ajoutée éclaircissant le fait que le chargement d’une page de votre site avec une valeur vide ne supprime *pas* le cookie QA du navigateur lorsque at.js 2.*x* est déployé. |
|  | [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | Mise à jour de la définition de « Confiance ». |
|  | [Offres](/help/main/c-experiences/c-manage-content/manage-content.md) | Note ajoutée expliquant que les offres d’image ne font pas partie du modèle [!UICONTROL Autorisations des utilisateurs d’Enterprise]. |
| 9 août | [Aperçu de Target Mobile](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=fr){target=_blank} | Mise à jour de la rubrique avec des informations sur les versions actuelles d’[!DNL Adobe Experience Platform Mobile SDK]. |
| 9 août | [Aperçu de Target Mobile](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=fr){target=_blank} | Mise à jour de la rubrique avec des informations sur les versions actuelles d’[!DNL Adobe Experience Platform Mobile SDK]. |
|  | Annonces et événements [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations à propos du prochain webinaire programmé pour le 17 août 2023 : *Stratégie pour un impact maximal du retour sur investissement grâce à la préparation à la haute saison*. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.8.1 de [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.7.1 (24 au 26 juillet 2023)

| Date | Rubrique | Modifications |
| --- | --- | --- |
|  | Annonces et événements [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations à propos du webinaire suivant programmé pour le 17 août 2023 : *Stratégie pour un impact maximal du retour sur investissement grâce à la préparation à la haute saison*. |
| 7 août | [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Clarification des informations sur les versions prises en charge d’at.js. |
| 25 juillet | [[!DNL Target] Notes de mise à jour (actuelles)](/help/main/r-release-notes/release-notes.md#edge) | Ajout d’informations sur la mise à niveau de l’infrastructure Edge prévue pour le 9 août 2023. |
|  | [Ajout des nœuds Edge de Target sur liste autorisée](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=fr){target=_blank} | Mise à jour des domaines NAT et IP pour les déploiements Edge 41-48. |
| 24 juillet | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 23.7.1 de [!DNL Target Standard/Premium]. |
