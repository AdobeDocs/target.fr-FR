---
keywords: notes de mise à jour;notes de version préliminaire;améliorations futures;correctifs futurs;fonctionnalités futures;version à venir
description: Consultez une liste des fonctionnalités, améliorations et correctifs inclus dans les versions antérieures d’Adobe Target.
title: Quelles sont les fonctionnalités incluses dans les versions précédentes ?
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 32%
---
# Notes de mise à jour pour les versions antérieures

Notes de mise à jour pour les versions antérieures dʼ[!DNL Adobe Target], comprenant des notes de mise à jour de [!DNL Target Standard/Premium], la plateforme [!DNL Target] et la bibliothèque JavaScript [!DNL Target] (at.js).

Les notes de mise à jour sont répertoriées dans l’ordre décroissant de leur date (mois et année) de publication.

>[!NOTE]
>
>Consultez les [Notes de mise à jour Target (actualisées)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) pour plus d’informations sur les versions de Target du mois en cours (plateforme et Target Standard/Premium).

## Notes de mise à jour - 2024

### Optimisation de la portée de la `__view__` [!DNL Adobe Experience Platform Web SDK] (22 octobre 2024)

Entre le 22 juillet 2024 et le 15 août 2024, l’équipe [!DNL Target] a optimisé la portée du `__view__`, améliorant la précision des impressions d’activité, des visites et des rapports des visiteurs. Cette optimisation vise à capturer automatiquement les données de rapport pour les propositions générées automatiquement et doit être transparente pour la plupart des comptes.

Cette optimisation sera activée pour tous les nouveaux clients [!DNL Adobe Experience Platform Web SDK]. Toutefois, l’optimisation est désactivée pour les clients qui ont migré depuis at.js et n’ont pas suivi les étapes d’implémentation ci-dessous. Nous recommandons vivement à ces clients de passer en revue leurs mises en œuvre d’ici le 3 février 2025. Passée cette date, nous activerons l’optimisation pour tous les clients. Si vous ne révisez pas et n’ajustez pas les implémentations d’ici là, les rapports peuvent être affectés, comme mentionné ci-dessous. Contactez [!DNL Adobe Customer Care] si vous devez confirmer si votre implémentation est affectée ou si vous avez besoin de plus de temps pour ajuster votre implémentation.

>[!IMPORTANT]
>
>Si vous ne parvenez pas à terminer l’examen de votre mise en œuvre et à résoudre les problèmes d’ici le 3 février 2025, vous pouvez demander une prolongation unique de six mois. Assurez-vous que votre demande a été soumise au plus tard le 31 janvier 2025. Adobe examinera votre demande et prendra une décision à ce sujet.

Pour bénéficier de cette optimisation en cas de rendu manuel des propositions, passez en revue votre [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/fr/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} pour vous assurer que vous envoyez des notifications après avoir effectué manuellement le rendu des expériences ou lors de l’utilisation de la méthode `applyPropositions` (ou de l’action [!DNL Launch] correspondante en tant qu’assistant) pour effectuer le rendu des expériences.

Les scénarios les plus courants lorsque les expériences sont rendues manuellement incluent :

* Utilisation des offres JSON
* Utilisation d’une portée de décision personnalisée dans une activité créée dans le [[!UICONTROL Compositeur d’expérience d’après les formulaires]](/help/main/c-experiences/form-experience-composer.md)
* Ne pas utiliser `renderDecisions: true` lors de la récupération d’une activité créée à l’aide du [!UICONTROL compositeur d’expérience d’après les formulaires] qui utilise la portée de `__view__` globale

Si les notifications ne sont pas implémentées comme indiqué dans la section [Rendu de contenu personnalisé](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} du guide *Collecte de données*, les données de rapport peuvent être manquantes dans les rapports [!DNL Target] et [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Dans certains scénarios, vous remarquerez peut-être une répartition incorrecte du trafic, car les données des rapports ne sont pas capturées. Ou, dans d’autres scénarios, signaler le même événement à plusieurs reprises.

Selon votre implémentation, vérifiez l’impact des rapports [!DNL Analytics] et A4T.

Le [!DNL Platform Web SDK] prend en charge deux types d’implémentation pour le rendu des expériences et des personnalisations :

* **Appel unique pour la personnalisation et la mesure.**

  Initialement recommandée, l’approche par appel unique pour le [!DNL Platform Web SDK] devrait être abandonnée au profit de l’approche par appel partagé. Adobe conseille à toutes les nouvelles mises en œuvre d’utiliser la nouvelle approche d’appel partagé et recommande aux clients existants d’adopter également la méthode d’appel partagé.

  Si vous continuez à utiliser l’approche d’appel unique, vous remarquerez peut-être les modifications inattendues suivantes dans vos rapports [!DNL Analytics] :

  * Baisse des bounces.
  * Les accès A4T et [!UICONTROL Page vue] ne sont pas regroupés, ce qui rend difficile l’exécution de certaines répartitions et corrélations de vos rapports A4T à l’aide d’eVars et d’événements [!DNL Analytics].

* **Appels fractionnés (également appelés événements en haut et en bas de page).**

  Ce type d’implémentation est la nouvelle approche d’implémentation [appel fractionné](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recommandée par [!DNL Adobe]. Avec cette approche, la nouvelle optimisation n’a aucune incidence sur les rapports [!DNL Analytics] ou A4T.

Si vous avez des questions, contactez l’[Assistance clientèle &#x200B;](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

### at.js version 2.11.6 (29 septembre 2024)

* Correction d’un problème qui empêchait le bon fonctionnement des [!DNL Target] avec les offres de redirection dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) ou le [!UICONTROL Compositeur d’expérience d’après les formulaires].

Pour plus d’informations sur les versions d’at.js, voir [informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank} dans le *Guide du développeur d’Adobe Target*.

### Création de rapports [!DNL Target] dans [!DNL Adobe Customer Journey Analytics] (8 mai 2024)

L’intégration entre [&#128279;](https://experienceleague.adobe.com/fr/docs/customer-journey-analytics){target=_blank} et [!DNL Target] fournit de puissants outils d’analyse et de gain de temps pour votre programme d’optimisation.

Les principaux avantages de l’utilisation de [!DNL Customer Journey Analytics] comme source de création de rapports pour [!DNL Target] sont les suivants :

* Les personnes spécialisées dans le marketing peuvent appliquer dynamiquement les mesures de succès de [!DNL Customer Journey Analytics] aux rapports d’activités de [!DNL Target], à tout moment. Il n’est pas nécessaire de spécifier tous les éléments avant d’exécuter l’activité.
* Les marketeurs peuvent tirer parti de [!DNL Customer Journey Analytics] fonctionnalités, telles que le [Panneau d’expérimentation](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank} pour analyser plus en détail la personnalisation de leur site web.

Pour plus d’informations, voir [Créer des rapports Target dans Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

### [!UICONTROL Compositeur d’expérience visuelle] extension d’assistance (23 avril 2024)

L’extension héritée Assistant du compositeur d’expérience visuelle [!DNL Target] a été créée à l’aide de Manifest V2. [!DNL Google] a annoncé qu’il n’autoriserait plus les extensions créées à l’aide de Manifest V2 à compter de juin 2024. Pour plus d’informations, voir Extension d’assistance [[!UICONTROL Compositeur d’expérience visuelle]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] recommande à la clientèle de passer à la version la plus récente de l’[extension Assistant d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) dès que possible.

### Mises à jour pour `Browser:iPad` et `Browser:iPhone` dans les attributs d’audience [!UICONTROL navigateur] (30 avril 2024)

| Mises à jour | Détails |
|--- |--- |
| [!UICONTROL Browser:iPad] et [!UICONTROL Browser:iPhone] mis à jour dans [Browser attributes](/help/main/c-target/c-audiences/c-target-rules/browser.md) utilisé lors de la création d’audiences. | [!DNL Adobe Target] vous permet de [cibler n’importe quel attribut de catégorie](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les personnes qui utilisent un [navigateur ou des options de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) spécifiques lorsqu’elles consultent votre page.<P>À partir de la version Standard/Premium 24.3.1 de [!DNL Target] (4-6 mars 2024), les audiences intégrées créées à l’aide de l’interface d’utilisation de Target, telles que `Browser:iPad` et `Browser:iPhone`, seront mises à jour afin d’effectuer un ciblage correct pour [!DNL iPad] et [!DNL iPhone] avec `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` et `profile.mobile.isTablet`.<P>Cette mise à jour ne nécessite aucune action du côté de la clientèle.<p><B>Important</b> : pour que la clientèle effectue un ciblage correct de [!DNL iPad] et [!DNL iPhone] dans les scripts de profil (et les segments JavaScript), les modifications manuelles doivent être effectuées par la clientèle avant le **30 avril 2024**. Pour obtenir des exemples d’autres paramètres qui doivent être modifiés manuellement, consultez [Mises à jour pour [!DNL iPad] et [!DNL iPhone] dans [!UICONTROL Navigateur] les attributs d’audience](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

### Extension [!UICONTROL &#x200B; Visual Editing Helper &#x200B;] (14 mars 2024)

Cette version comprend les améliorations et correctifs suivants pour l’extension [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) pour [!DNL Google Chrome] :

* Amélioration du mécanisme de chargement iFrame lors de la création sur les sites web des clients.
* Correction d’un problème en raison duquel l’extension dupliquait des cookies lors de la création dans le [!UICONTROL compositeur d’expérience visuelle] (VEC).

### [!DNL Target] Standard/Premium 24.3.1 (4 et 6 mars 2024)

Cette version comprend les améliorations et correctifs suivants :

* Correction de la logique qui calcule le nombre de sélecteurs uniques dans une activité. (TGT-47878)
* Correction d’un problème en raison duquel les activités [!UICONTROL Multivariate] (MVT) configurées avec les rapports [!UICONTROL Analytics for Target] (A4T) ne s’affichaient pas correctement. (TGT-47490)
* Amélioration du message d’avertissement affiché dans le rapport lorsqu’une expérience sans trafic est utilisée comme expérience de contrôle. (TGT-47537)
* Ajout de nombreuses corrections au niveau du serveur principal et de la localisation.

### [!DNL Target] Standard/Premium 24.1.1 (22, 23 et 25 janvier 2024)

Cette version comprend les améliorations et correctifs suivants :

* Les activités [!UICONTROL Analytics for Target] (A4T) avec les mesures d’objectif de chiffre d’affaires n’affichaient pas « Chiffre d’affaires » comme nom de colonne et la mesure de chiffre d’affaires ne s’affichait pas au format ($) dans les rapports. Il s’agissait d’un problème d’ordre cosmétique qui a été corrigé. (TGT-46995)
* Correction d’un problème en raison duquel les périodes des rapports ne fonctionnaient pas correctement. (TGT-47396)
* Correction d’un problème en raison duquel le statut incorrect s’affichait sur la page [!UICONTROL Toutes les activités] une fois que les clients et clientes activaient ou désactivaient une activité à l’aide de l’icône [!UICONTROL Plus d’actions]. (TGT-47367)
* Correction d’un problème en raison duquel le rapport [!UICONTROL &#x200B; Attributs importants &#x200B;] ne s’affichait pas pour un seul client. (TGT-47272)
* Correction d’un problème en raison duquel le message « Payload non valide » s’affichait lorsqu’un seul client ou une seule cliente tentait d’activer l’option « Authentification obligatoire ». (TGT-47195)
* Mise à jour de plusieurs chaînes localisées dans l’interface utilisateur de [!DNL Target].
