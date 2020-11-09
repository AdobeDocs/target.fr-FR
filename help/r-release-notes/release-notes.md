---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 27%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>* **Fin de vie** de mbox.js : Le 18 janvier 2021, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 18 janvier 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages dont les activités de Cible s’exécutent en diffusant le contenu par défaut. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir [Fonctionnement d’At.js et](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) [Adobe Target Skill Builder : Messagerie instantanée des développeurs, mbox.js Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance pourront vous fournir de nouvelles fonctionnalités et offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d’informations, voir Annonces [de](/help/r-release-notes/target-announcements.md)Cible.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## Target Standard/Premium 20.10.1 (27 octobre 2020)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| [Prise de décision sur périphérique](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | La prise de décision sur périphérique permet à la fois aux marketeurs et aux développeurs de produits de proposer des expériences et une personnalisation pilotée par l’apprentissage automatique depuis l’appareil d’un utilisateur, d’un canal à l’autre, à une latence proche de zéro.<br>La vitesse et les performances sont importantes, en ce qui concerne les connaissances des clients et la satisfaction des utilisateurs.<br>La prise de décision sur périphérique vous permet de compiler les instructions de personnalisation et d’expérimentation clés dans les activités A/B Test and Experience Targeting (XT) en &quot;artefacts d’optimisation :&quot; objets JSON chargés sur les périphériques client via le CDN. Et comme la prise de décision sur le périphérique se connecte nativement à [!DNL Adobe Experience Cloud] des produits, [!DNL Target] les utilisateurs obtiennent une analyse rapide et des itérations d’expérience plus rapides.<br>Pour plus d’informations, voir *[Présentation de la prise de décision](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)* sur périphérique dans le Guide *des SDK* Adobe Target.<br>**Inscrivez-vous dès maintenant à un webinaire en direct.** Rejoignez les experts du produit Adobe Target pour découvrir comment le déplacement des décisions d’optimisation d’expérience critiques sur le périphérique pour s’exécuter localement sans latence peut ouvrir la porte à de nouveaux cas d’utilisation intéressants tout en améliorant les performances du site pour vos clients.<ul><li>10 novembre 2020</li><li>10 heures PT / 12 heures CT / 13 heures ET</li><li>[Inscrivez-vous ici](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème qui empêchait l’affichage en [!UICONTROL rapports de l’Intervalle] de fiabilité de l’effet élévateur [!UICONTROL moyen et de la] fiabilité [!DNL Auto-Target] pour la ligne [!UICONTROL Total] . Les mesures s’affichaient correctement pour toutes les expériences individuelles. (TGT-37301)
* Correction d’un problème qui affectait le rapports de Cible [!DNL Adobe Target Premium]  automatique des utilisateurs à partir du 15 septembre à 14 h 30. (HAP) au 6 octobre, de 9 h 25 (PDT). Lors de l’affichage de rapports pour les mesures de conversion affectées (configurées à l’aide de l’option &quot;[!UICONTROL Consulté une page]&quot; ou &quot;[!UICONTROL Cliqué sur la mbox]&quot;), les taux de conversion sont incorrectement signalés. Il n&#39;y a pas de problème de diffusion connu pour le moment. Pour plus d’informations sur la resynchronisation et la correction de votre rapports, voir rapports [de Cible](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) automatique sous Problèmes *résolus dans Problèmes* *connus et Problèmes* résolus.
* Ajoute une colonne [!UICONTROL Dernière mise à jour] sélectionnable dans le tableau Recherche [!UICONTROL de catalogue et un filtre] Dernière mise à jour à  . Cette amélioration vous permet de gagner du temps et d’obtenir des efforts car vous n’avez pas à ouvrir chaque élément pour savoir quand il a été mis à jour pour la dernière fois et vous pouvez filtrer par date la dernière mise à jour des éléments.

   ![Illustration Dernière mise à jour à la colonne et au filtre](/help/r-release-notes/assets/column-and-filter.png)

* Des mises à jour ont été apportées pour aider à rendre l&#39;interface utilisateur de la Cible conforme aux directives [sur l&#39;accessibilité du contenu](https://www.w3.org/WAI/standards-guidelines/wcag/) Web 2.0 Niveau A et aux critères de réussite AA (WCAG 2.0 AA). (TGT-34384 et TGT-24679)
* Amélioration de la stratégie de sécurité de contenu (CSP). (TGT-37035)
* Ajout d’un moyen de spécifier le code client en tant que paramètre pour les clients utilisant CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] la documentation se déplace vers [!DNL Experience League]. En octobre, toutes les notes de mise à jour, articles, vidéos et didacticiels passeront de leur emplacement actuel `docs.adobe.com` à [!DNL Experience League]. Ce déplacement permet de s’assurer que tous les contenus d’apprentissage, d’auto-assistance, d’activation et de communauté sont diffusés à partir d’un seul emplacement. Lorsque ce changement se produit, il n’y a rien à faire, car tous les liens seront redirigés vers [!DNL Experience League]. Nous mettrons à jour les notes de mise à jour au début du découpage.

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la Bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour des](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
