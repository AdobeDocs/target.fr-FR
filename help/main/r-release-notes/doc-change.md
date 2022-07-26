---
keywords: journal des modifications de la documentation de Target;mises à jour de la documentation;nouvelles rubriques;modifications;mises à jour;mise à jour
description: Tenez-vous informé des modifications et des ajouts importants apportés à la documentation d’ [!DNL Adobe Target] .
title: Où puis-je consulter les mises à jour de la documentation de  [!DNL Target] ?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 99%

---

# Modifications de la documentation

Cette rubrique répertorie les modifications importantes apportées à la documentation d’[!DNL Adobe Target].

## [!DNL Adobe Target] Standard/Premium 22.10.1 (version échelonnée : 10 - 13 octobre 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 14 décembre | [Paramètres des rapports](/help/main/c-reports/c-report-settings/report-settings.md#environment) | Ajout d’une remarque sous la section &quot;Environnement&quot; à propos de l’utilisation de la fonction [!DNL Adobe Experience Platform] (AEP) pour envoyer des données de mesure à [!DNL Target]. |
| 29 novembre | [Géo](/help/main/c-target/c-audiences/c-target-rules/geo.md) | Clarification du texte avec l’ajout du paragraphe suivant :<ul><li>Les informations géographiques d’un visiteur ou d’une visiteuse sont déterminées à partir de l’adresse IP d’origine d’une requête d’emplacement [!DNL Target] (requête de mbox). La résolution IP/zone géographique est effectuée pour le premier appel d’une nouvelle session. En d’autres termes, si l’adresse IP d’un visiteur ou d’une visiteuse change en milieu de session d’une visite, les informations géographiques sont toujours basées sur l’adresse IP du premier appel.</li></ul> |
| 28 novembre | [Présentation de l’API Modèles (liste bloquée)](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} dans le *Guide du développeur d’Adobe Target*. | Nouvelle API Modèles.<br>Les fonctionnalités peuvent être bloquées à partir des algorithmes de machine learning [!DNL Target], qui empêchent leur utilisation dans n’importe quel modèle ou activité [!UICONTROL Ciblage automatique] ou [!UICONTROL Automated Personalization]. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations à propos de la version de l’API Modèles (23 novembre 2022). |
| 23 novembre | [Avant la mise en œuvre dʼAnalytics for Target (A4T) avec at.js](/help/main/c-integrating-target-with-mac/a4t/before-implement.md) | Mise à jour du lien vers le [Formulaire de configuration des intégrations Experience Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}. |
| 16 novembre | [Annonces et événements Adobe Target](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations d’enregistrement pour l’événement suivant :<ul><li>Pause-café Questions/réponses de la communauté [!DNL Adobe Target] (29 novembre)</li></ul> |
| 8 novembre | [Quelle doit être la durée d’exécution d’un test A/B ?](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) | Ajout d’une note importante indiquant que pour obtenir des résultats précis, vous devez recharger la page avant de modifier les numéros de paramètre dans la variable [!DNL Adobe Target] [!UICONTROL Calculateur de taille d’échantillon]. Ajout également d’une note dans le [calculateur](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=fr){target=_blank}. |
|  | [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682) | Mise à jour de la description du paramètre `adobe_mc_sdid` dans le tableau. |
|  | [Résolution des problèmes liés aux activités](/help/main/c-activities/c-troubleshooting-activities/troubleshooting-activities.md) | Ajout d’une nouvelle section : « Après la conversion de l’activité, le visiteur ne fait partie d’aucune expérience. » |
|  | [Paramètres personnalisés](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Ajout d’une note indiquant que la mbox que vous sélectionnez dans la liste déroulante [!UICONTROL Filtrer par] n’est pas enregistrée lors de la création de l’activité. Cette option permet de filtrer les paramètres en fonction de la mbox sélectionnée. |
| 2 novembre | Problèmes connus et problèmes résolus | Suppression de la page et déplacement des problèmes pertinents vers les pages appropriées afin que les informations soient contextuelles. |
| 25 octobre | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.10.3 de [!DNL Target Standard/Premium]. |
| 19 octobre | [Affinité catégorielle](/help/main/c-target/c-visitor-profile/category-affinity.md#section_8B86C7FF50294208866ABF16F07D5EB9) | Ajout d’une note expliquant la notation lorsque plusieurs catégories sont transmises au cours d’un seul appel de mbox. |
| 18 octobre | [Créer une activité [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) | Mise à jour du texte qui indique que bien que vous puissiez créer jusqu’à 30 000 expériences dans un test AP, l’algorithme fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont utilisées. Cette même limite est appliquée même si l’activité a activé l’option [!UICONTROL Refuser les doublons]. |
|  | [FAQ sur Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization-faq.md) | Mise à jour du texte qui indique que bien que vous puissiez créer jusqu’à 30 000 expériences dans un test AP, l’algorithme fonctionne à son meilleur niveau lorsque moins de 10 000 expériences sont utilisées. Cette même limite est appliquée même si l’activité a activé l’option [!UICONTROL Refuser les doublons]. |
| 14 octobre | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations d’enregistrement sur l’événement Pause-café questions/réponses de la communauté [!DNL Adobe Target] (26 octobre 2022). |
| 10 octobre | Extension [[!UICONTROL Visual Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) | Nouvel article. |
|  | [Résolution des problèmes liés au compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md) | Mise à jour de la section « [Ma page ne s’affiche pas dans le compositeur d’expérience visuelle (compositeur d’expérience visuelle uniquement)](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#does-not-load) ». |
| 4 octobre | [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | Nouvelle rubrique.<br>Les informations de cet article remplacent le fichier PDF *Calculs Adobe Target pour les tests A/B*, auparavant disponible en téléchargement sur ce site. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.10.1 de [!DNL Target Standard/Premium]. |

## [!DNL Adobe Target] Standard/Premium 22.9.1 (version échelonnée : 13 - 15 septembre 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 3 octobre | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Mise à jour des dates pour la version 22.10.1. de [!DNL Target Standard/Premium] |
| 22 septembre | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations relatives à l’événement suivant :<ul><li>Pause-café Questions/réponses de la communauté [!DNL Adobe Target] (28 septembre 2022)</li></ul> |
| 15 septembre | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations sur le webinaire suivant :<ul><li>Perfectionnement de la personnalisation basée sur l’IA : nouvelles fonctionnalités d’[!DNL Adobe Target] (11 octobre 2022)</li></ul> |
| 13 septembre | [Présentation de l’ [!DNL Target] interface utilisateur](/help/main/c-intro/understand-the-target-ui.md) | Ajout d’informations sur les notifications lors de l’échec d’un flux [!DNL Recommendations]. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.9.1 de [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.8.1 (sortie échelonnée : 17-18 août 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 22 août | [[!DNL Adobe Target] Annonces et événements](/help/main/r-release-notes/target-announcements.md) | Ajout des informations concernant l’annonce suivante :<ul><li>[!DNL Target] nommé leader dans le Gartner Magic Quadrant pour les moteurs de personnalisation (2022)</li></ul>Ajout d’informations relatives aux événements prochains suivants :<ul><li>[!DNL Adobe Target] Pause-café Questions/réponses de la communauté Adobe Target (31 août 2022)</li><li>Collection du chef : recettes pour une personnalisation réussie (30 août 2022)</li><li>Développeurs de compétences [!DNL Adobe Target] - Optimisation de l’expérience mobile (6 septembre 2022)</li><li>Développeurs de compétences [!DNL Adobe Target] - Personnalisation et recommandations pilotées par l’IA (15 septembre 2022)</li></ul>Ajout d’un lien d’enregistrement pour la session de webinaire suivante :<ul><li>Adobe : acteur du secteur de la personnalisation - vente au détail (11 août 2022)</li></ul> |
| 22 août | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.8.1 de [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.6.1 (sortie échelonnée : 7-9 juin 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 30 juin | [Guide du développeur Adobe Target](https://developer.adobe.com/target/){target=_blank} | Lancez le *Guide du développeur Adobe Target* pour consolider tout le contenu développeur [!DNL Target] dans un portail pratique. Ce portail contient des informations sur l’implémentation de [!DNL Target] et [!DNL Recommendations], des SDK [!DNL Target] et des API [!DNL Target]. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.6.2 de [!DNL Target Standard/Premium]. |
|  | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md) | Ajout de liens d’enregistrement pour les sessions de webinaires précédentes. |
| 14 juin | [Planifier et implémenter les recommendations](https://developer.adobe.com/target/implement/recommendations/){target=_blank} | Mise à jour des exemples de code dans les sections suivantes :<ul><li>Pages Ajouts au panier/consultations de panier/passage en caisse</li><li>Exclure des éléments déjà présents dans le panier du visiteur</li></ul> |
| 7 juin | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout de notes de mise à jour pour la version 22.6.1 de [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.5.1 (sortie échelonnée ; 11-13 mai 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 7 juin | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 22.6.1 de [!DNL Target Standard/Premium]. |
| 31 mai | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Ajout d’informations sur la prochaine pause café de la communauté [!DNL Adobe Target] (29 juin 2022) |
| 25 mai | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations sur la mise à jour de la plateforme [!DNL Target] (25 mai 2022) et sur la version 2.9.0 d’at.js (27 mai 2022). |
|  | [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Ajout d’informations relatives à la version 2.9.0 d’at.js. |
|  | [User-agent et Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} | Nouvelle rubrique. |
|  | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Ajout d’un lien pour l’enregistrement du webinaire suivant : Dick’s Sporting Goods : personnalisation et changement du paysage de la vente au détail (19 mai 2022) |
| 23 mai | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout de notes préliminaires pour at.js version 2.9.0 (25 mai 2022). |
| 11 mai | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Ajout d’informations et de liens d’enregistrement pour les webinaires suivants :<ul><li>Dick’s Sporting Goods : Personnalisation et changement du paysage de la vente au détail</li><li>Adobe : Insider du secteur de la personnalisation - Services financiers et assurance</li><li>City National Bank : Comment faire partie du top des 1 % les meilleurs dans le domaine de l’optimisation numérique</li><li>Adobe : Personnalisation et précision - [!DNL Adobe Analytics] et [!DNL Target]</li><li>City National Bank : De zéro à héros - Démarrage et mise à l’échelle d’un programme de personnalisation</li><li>Adobe : Découvrir les opportunités d’optimisation à fort impact</li><li>Adobe : Insider du secteur de la personnalisation - Vente au détail</li></ul>Ajout de l’enregistrement pour le webinaire suivant :<ul><li>Personnalisation en temps réel avec [!DNL Adobe Target]</li></ul> |
|  | [Directives relatives aux CSP (Content Security Policy, politique de sécurité du contenu)](https://developer.adobe.com/target/before-implement/privacy/content-security-policy/){target=_blank} | Ajout d’une section de questions fréquentes. |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations à propos de [!DNL Target Standard/Premium] 22.5.1 et de la plateforme Target (11-13 mai 2022). |

## Adobe Target Standard/Premium 22.4.1 (avril 28)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 10 mai | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 22.5.1 de [!DNL Target Standard/Premium]. |
| 28 avril | [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#move-audience) | Ajout de la question fréquente suivante :<ul><li>Puis-je déplacer une audience d’un espace de travail à un autre ?</li></ul> |
|  | Aperçu de l’[[!UICONTROL affectation automatique]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#section_0E72C1D72DE74F589F965D4B1763E5C3) | Ajout des questions fréquentes suivantes :<ul><li>Une activité [!UICONTROL Affectation automatique] peut-elle ajuster l’intervalle de recherche arrière au cours d’un test pour prendre en compte les modifications de tendances au fil du temps ?</li><li>Une activité [!UICONTROL Affectation automatique] présente-t-elle une expérience gagnante à un visiteur récurrent si l’expérience gagnante est différente de ce que le visiteur a vu lors de la qualification pour l’activité ?</li></ul> |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations à propos des versions de [!DNL Target Standard/Premium] 22.4.1 et de la plateforme Target (27 avril 2022). |

## Adobe Target Standard/Premium 22.3.1 (avril 5)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 26 avril | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations relatives aux événements suivants :<ul><li>Webinaire : Personnalisation en temps réel avec Adobe Target (28 avril 2022)</li><li>Pause-café Questions/réponses de la communauté [!DNL Adobe Target] (25 mai 2022)</li></ul> |
|  | [FAQ sur les offres de redirection - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#discrepancies) | Ajout de la question fréquente suivante :<ul><li>Comment puis-je réduire les incohérences de distribution du trafic lors de l’utilisation des offres de redirection dans les activités A4T ?</li></ul> |
|  | [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Ajout de la section suivante :<ul><li>Supprimer les bibliothèques clientes et des HTML superflus dans les Fragments d’expérience exportés vers Target</li></ul> |
| 21 avril | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires sur la mise à jour de [!DNL Target] Platform, prévue pour le 17 avril 2022. |
| 20 avril | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 22.4.1 de [!DNL Target Standard/Premium]. |
| 14 avril | [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | Ajout d’informations dans la section « Réorganiser » pour expliquer comment gérer le comportement incohérent du VEC avec les actions [!UICONTROL Déplacer] et [!UICONTROL Réorganiser] du au chargement différé des éléments DOM. |
| 13 avril | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations relatives à l’événement suivant :<ul><li>Session Community Q&amp;A Coffee Break [!DNL Adobe Target] (Pause-café Questions/réponses de la communauté Adobe Target)  (27 avril 2022)</li></ul> |
|  | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations sur la mise à jour de [!DNL Target] Platform. |
| 4 avril | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Mise à jour des informations relatives à la version 22.3.1 de [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.2.1 (1er février 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 30 mars | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations sur la mise à jour de [!DNL Target] Platform. |
| 28 mars | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires sur la mise à jour de [!DNL Target] Platform. |
| 22 mars | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations sur la mise à jour des correctifs d’ingénierie client [!DNL Target Standard/Premium]. |
|  | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 22.3.1 de [!DNL Target Standard/Premium]. |
| 17 mars | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires sur la mise à jour des correctifs d’ingénierie client [!DNL Target Standard/Premium]. |
|  | [Synchronisation des profils en temps réel pour mbox3rdPartyId](/help/main/c-target/c-visitor-profile/3rd-party-id.md) | Mise à jour de la phrase suivante concernant la synchronisation des profils : « Les mises à jour sont synchronisées avec le magasin de profils toutes les 5 à 10 minutes. » |
| 8 mars | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations relatives à l’événement suivant :<ul><li>Session Community Q&amp;A Coffee Break [!DNL Adobe Target] (Pause-café Questions/réponses de la communauté Adobe Target)  (30 mars 2022)</li></ul> |
| 7 mars | [Création dʼaudiences](/help/main/c-target/c-audiences/audiences.md#aep) | Ajout d’une nouvelle section sous « Utiliser les audiences d’[!DNL Adobe Experience Platform] : »<ul><li>Cas d’utilisation de la personnalisation</li></ul> |
| 25 février | [Prise en charge d’A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | Mise à jour des sections suivantes :<ul><li>[Affectation automatique et ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#both)</li><li>[Affectation automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)</li></ul> |
|  | [Interprétation des rapports d’affectation automatique](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Ajout d’une nouvelle FAQ :<ul><li>Les badges « Aucun gagnant », « Gagnant » et « étoile » sont-ils disponibles pour les activités dʼ[!UICONTROL Affectation automatique] qui utilisent [!UICONTROL Analytics comme source de création de rapports] (A4T) ?</li></ul> |
|  | [Créer une audience d’activité unique](/help/main/c-target/creating-activity-only-audience.md) | Ajout d’informations à la section « Considérations » concernant les règles d’exclusion. |
| 10 février | [Extension d’assistance du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Ajout d’informations sur le chargement de sites web avec Service Workers dans le compositeur d’expérience visuelle (VEC). |
| 7 février | [Annonces et événements Target](/help/main/r-release-notes/target-announcements.md) | Ajout d’informations relatives à l’événement suivant :<ul><li>Session Community Q&amp;A Coffee Break [!DNL Adobe Target] (Pause-café Questions/réponses de la communauté Adobe Target)  (23 février 2022)</li></ul> |
| 3 février | [Création dʼaudiences](/help/main/c-target/c-audiences/audiences.md#RTCDP) | Ajout d’une nouvelle section et d’une nouvelle vidéo : « Vidéo : personnalisation des accès suivants avec Real-time CDP et [!DNL Adobe Target] ». |
| 2 février | [Résolution des problèmes liés à la diffusion de contenu](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#escape) | Ajout de la section suivante : « L’échappement des guillemets doubles dans la valeur d’attribut de profil de [!DNL Target] ne fonctionne pas comme prévu ». |
| 1er février | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations relatives à la version 22.2.1 de [!DNL Target Standard/Premium]. |

## [!DNL Adobe Target Standard/Premium] 22.1.1 (12 janvier 2022)

| Date | Rubrique | Modifications |
| --- | --- | --- |
| 31 janvier | [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md) | Ajout d’informations préliminaires relatives à la version 22.2.1 de [!DNL Target Standard/Premium]. |
| 28 janvier | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations relatives à la version 2.8.1 d’at.js. |
|  | [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Ajout d’informations relatives à la version 2.8.1 d’at.js. |
| 27 janvier | [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Mise à jour de la rubrique et ajout d’informations sur [!DNL AEM as a Cloud Service] et [!DNL Adobe I/0]. |
| 26 janvier | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations relatives à la version 22.1.2 de [!DNL Target Standard/Premium]. |
|  | [Création dʼaudiences](/help/main/c-target/c-audiences/audiences.md) | Ajout d’informations relatives aux audiences [!DNL Adobe Experience Platform]. |
|  | [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md) | Ajout d’informations relatives aux audiences [!DNL Adobe Experience Platform]. |
| 21 janvier | [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Ajout d’informations relatives à la version 1.8.3 d’at.js. |
| 19 janvier | [Mise à niveau d’at.js 1.*x* vers at.js 2.x *x*](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Ajout de la section suivante : « at.js 2.*x* ne prend pas en charge la création d’audiences à l’aide de paramètres vst.* » |
| 12 janvier | [Notes de mise à jour de Target (actualisées)](/help/main/r-release-notes/release-notes.md) | Ajout d’informations relatives à la version 22.1.1 de [!DNL Target Standard/Premium]. |
|  | [SDK Web Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | Ajout d’un lien vers un tutoriel contenant des instructions d’implémentation d’[!DNL Adobe Experience Cloud] dans le SDK Web. |
