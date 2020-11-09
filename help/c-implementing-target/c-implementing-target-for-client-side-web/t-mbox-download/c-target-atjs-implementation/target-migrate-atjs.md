---
keywords: Target;at.js;migrate to at.js;readiness;audit at.js;integrate at.js
description: La migration de mbox.js vers at.js est très simple.
title: Comment migrer de mbox.js à at.js
feature: null
topic: Standard
uuid: 45f81fe8-7b04-4a36-931d-bbf03ed6cbb3
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 99%

---


# Comment migrer de mbox.js à at.js{#how-to-migrate-to-at-js-from-mbox-js}

La migration de mbox.js vers at.js dans [!DNL Adobe Target] est très simple.

Procédez comme suit pour migrer de [!DNL mbox.js] vers [!DNL at.js] et vérifier la migration :

1. Déterminez les exigences en matière de [prise en charge des navigateurs](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) de votre entreprise.
1. Dans l’implémentation actuelle du fichier [!DNL mbox.js] du site web, recherchez les fonctionnalités qui ne sont pas prises en charge par [!DNL at.js].

   Lorsque vous contrôlez votre implémentation, recherchez les éléments suivants :

   **Quels types de mbox utilisez-vous actuellement ?**

   | Type | Détails |
   |--- |--- |
   | Mbox globale créée automatiquement | La mbox globale créée automatiquement est créée lorsque la seule ligne de code Target sur le site correspond au fichier mbox.js. Ce fichier génère automatiquement un appel de mbox. |
   | mboxCreate vide global | Il est recommandé de passer à la mbox globale créée automatiquement. |
   | Enveloppement de mboxCreate | La migration doit être simple à condition que `mboxCreate()` soit précédé de `<div class="mboxDefault"></div>`. |
   | mboxUpdate | La migration doit être simple lorsque `mboxUpdate()` est utilisé conjointement avec `mboxDefine()` ou `mboxCreate()`. `mboxUpdate()` ne met pas à jour la mbox globale créée automatiquement ou une mbox créée à l’origine par `getOffer()`. Dans ces cas, une combinaison de `getOffer()` et `applyOffer()` doit être utilisée pour remplacer `mboxUpdate()` lors de la migration vers at.js. |
   | Mbox de suivi de clics personnalisées, notamment mboxTrack | Nous vous recommandons de mettre à jour votre code pour utiliser `trackEvent()`. |

   >[!NOTE]
   >
   >Pour plus d’informations sur les différentes fonctions mentionnées dans le tableau précédent, consultez les [Fonctions at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

   **Le fichier [!DNL mbox.js] contient-il des personnalisations ?**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * Code JavaScript supplémentaire
   * Autres emplacements

   La plupart des [objets et méthodes de mbox.js](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (comme `mbox`,`mboxCurrent`, `mboxFactoryDefault`, `mboxFactories`, etc.) ne sont pas pris en charge. D’autres solutions peuvent exister pour effectuer ce que vous souhaitez faire.

   **[!DNL mbox.js] est-il installé sur l’une ou plusieurs de vos pages web ?**

   Vous ne pouvez pas utiliser [!DNL at.js] et [!DNL mbox.js] sur la même page web. Vous pouvez toutefois utiliser les deux bibliothèques JavaScript sur deux pages différentes du même site web.

   Le cookie de mbox permet à Adobe de suivre le visiteur d’une page à l’autre. Dans le cadre de votre processus d’assurance qualité, vérifiez que le cookie est préservé et correctement lu quand le visiteur passe d’une page avec [!DNL at.js] à l’autre et d’une page avec [!DNL mbox.js] à l’autre. Veillez à ce que les mêmes valeurs `mboxPC` et `mboxSession` soient transmises dans les appels de mbox, quelle que soit la section du site ([!DNL at.js] ou [!DNL mbox.js]) où arrive le visiteur et quelle que soit la section qui définit initialement le cookie. Si vous utilisez des cookies tiers dans votre mise en œuvre, vérifiez que ces valeurs restent inchangées quand vous naviguez sur le site.

   **[!DNL Target] est-il intégré dans d’autres solutions Adobe ?**

   * Analytics (A4T)
   * Analytics (intégration héritée)
   * AAM (principal)
   * AAM (frontal hérité)
   * AEM
   * Data Workbench

   Certaines des intégrations héritées ne sont pas prises en charge par [!DNL at.js]. Pour plus d’informations, consultez la page d’[Intégrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **[!DNL Target] est-il intégré dans des solutions tierces ?**

   * Autres outils d’analyse
   * Autres plates-formes de gestion des données
   * Demandbase
   * Click-tale
   * Les autres

   Il est possible que ces intégrations doivent être ajustées pour fonctionner avec [!DNL at.js]. Pour plus d’informations, consultez la page [Intégration](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **Utilisez-vous un gestionnaire de balises ?**

   * Dynamic Tag Management
   * Ensighten
   * Tealium
   * Signal/BrightTag

   Pour plus d’informations, voir [Intégrations at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   >[!NOTE]
   >
   >Si vous n’utilisez pas encore de gestionnaire de balises pour déployer [!DNL Target], c’est peut-être le moment d’y songer. La fonctionnalité de [Dynamic Tag Management](https://dtm.adobe.com)d’Adobe ( ) est gratuite pour les clients de [!DNL Target]. Il s’agit de la méthode recommandée pour déployer [!DNL Target]. Pour en savoir plus, voir [Bonnes pratiques relatives à la mise en œuvre d’Adobe Target à l’aide de la Dynamic Tag Management](https://experienceleague.adobe.com/docs/dtm/implementing/overview.html).

1. Vérifiez que toutes les activités et intégrations en cours fonctionnent normalement.

   Voici ce que vous pouvez faire lors du test pour vérifier que le fichier [!DNL at.js] génère les résultats escomptés :

   * Vérifiez que toutes les activités en cours fonctionnent avec la nouvelle bibliothèque JavaScript.
   * Vérifiez que l’ensemble des [intégrations](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) et [modules externes](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) fonctionnent comme prévu.
   * Veillez à bien [effectuer le débogage](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) à l’aide des approches disponibles [!DNL at.js].

**Problèmes possibles lors de la migration vers at.js** Certains utilisateurs ont signalé les problèmes suivants après avoir effectué la migration vers at.js :

* Certaines activités du compositeur d’expérience visuelle qui ont été créées sur une page avec [!DNL mbox.js] peuvent nécessiter une mise à jour pour fonctionner avec [!DNL at.js].

   Ce problème survient le plus souvent sur les sites web qui n’utilisent pas de nombreux attributs d’identifiant ou de classe dans les éléments HTML. Vérifiez si vous êtes confronté à ce problème en chargeant la page, et déterminez si l’expérience est diffusée comme prévu en chargeant la page avec `?mboxDebug=true` puis en examinant les instructions de console.

   ![](assets/mboxdebug.png)
Dans les cas qui nous intéressent, les sélecteurs d’éléments peuvent commencer par quelque chose comme

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   et ont été créés en partant du principe que [!DNL mbox.js] ajoute un élément `<div>` supplémentaire en haut de la page. Comme [!DNL at.js] n’ajoute pas d’élément `<div>` en haut de la page, ce sélecteur ne fonctionne plus avec [!DNL at.js].

   Ce problème peut être résolu en recréant l’activité à l’URL concernée avec [!DNL at.js] dans le compositeur d’expérience visuelle ou en mettant manuellement à jour le sélecteur à l’aide de l’option **[!UICONTROL &lt;/> Code]** > **[!UICONTROL Modifications]** dans le compositeur d’expérience visuelle.

   Pour remédier à ce problème, soustrayez 1 de l’attribut nth-of-type dans le premier élément DIV après BODY. Dans l’exemple ci-dessus, le code modifié sera :

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   Pour en savoir plus sur l’utilisation de l’éditeur de code dans ce contexte, voir [Éditeur de code](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5).

* Étant donné que toutes les mbox sont désormais asynchrones, elles ne bloquent pas le rendu des pages et ne sont pas renvoyées dans l’ordre dans lequel elles sont déclenchées. Pour en savoir plus, voir « Points à prendre en compte concernant le caractère asynchrone des mbox » dans [Limites d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE).
