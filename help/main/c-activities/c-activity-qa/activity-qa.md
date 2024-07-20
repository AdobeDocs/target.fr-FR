---
keywords: qa;mode qa;activité qa;url qa;url qa;url d’aperçu;url d’aperçu;url d’aperçu
description: Découvrez comment utiliser les URL AQ d’Adobe [!DNL Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et des rapports AQ qui restent segmentés à partir des données d’activité actives.
title: Comment vérifier la qualité des activités ?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 4b7c6d82e6988c64ace401d8f749b181b8dc1866
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 27%

---

# AQ d’activité

Utilisez les URL AQ dans [!DNL Adobe Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives.

[!UICONTROL Activity QA] vous permet de tester entièrement vos activités [!DNL Target] avant de les lancer en ligne. La fonctionnalité [!UICONTROL Activity QA] comprend :

* Liens à partager avec les membres de l’équipe qui ne changent jamais ou ne nécessitent aucune régénération, quelles que soient les mises à jour apportées aux expériences ou aux activités. Cette fonctionnalité vous permet de tester entièrement vos activités sur l’ensemble du parcours d’utilisateurs.
* Des conditions d’audience facultatives afin que les responsables du marketing puissent tester les critères de ciblage ou les ignorer pour soumettre à l’assurance qualité (QA) l’aspect des expériences sans avoir à respecter les conditions d’audience.
* La création de rapports QA est capturée afin que les responsables du marketing puissent confirmer que les mesures s’incrémentent comme prévu et que les données des rapports QA sont conservées indépendamment des rapports de production (pour les rapports non-A4T).
* La possibilité de prévisualiser une expérience seule ou avec d’autres activités actives satisfaisant les critères de diffusion (requête/audience page/[!DNL Target]).
* La capacité à vérifier la qualité de l’ensemble du parcours de l’utilisateur. Vous avez accès à votre site une fois avec le lien AQ et vous parcourez ensuite le site entier en mode AQ d’activité. Vous restez dans l’AQ d’activité jusqu’à la fin de la session ou jusqu’à ce que vous utilisiez le [signet d’applet AQ Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) pour vous libérer de [!UICONTROL Activity QA]. Cette fonctionnalité est utile si vous avez une activité qui s’étend sur plusieurs pages web.

  >[!NOTE]
  >
  >Cette fonctionnalité est vraie pour les implémentations d’at.js avec la version 2.*x* ou version ultérieure. Pour at.js 1.Implémentations de *x*, cette fonctionnalité est vraie uniquement si le navigateur du visiteur ne bloque pas les cookies tiers.

## Accès et partage d’une URL AQ {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. Sur la page [!UICONTROL Overview] d’une activité, cliquez sur **[!UICONTROL Activity QA]**.

   ![Liens de l’AQ d’activité](assets/qa_link.png)

1. Configurez les paramètres suivants :

   ![Options de configuration des liens d’assurance qualité](assets/qa_link_config.png)

   * **[!UICONTROL Match audience rules to see experiences]:** Parfois, vous souhaitez confirmer que la correspondance de l’audience fonctionne. D’autres fois, vous souhaitez vérifier l’aspect de l’activité. Si ce paramètre est activé, les testeurs doivent satisfaire aux exigences de ciblage pour pouvoir voir les expériences. Pour les activités de ciblage d’expérience (XT), une seule URL d’activité est fournie. L’expérience que vous voyez est déterminée par le fait que vous vous qualifiez pour l’une des règles de ciblage.

     Si ce paramètre est désactivé, le fait de cliquer sur les liens vous montre les expériences, que vous vous qualifiez ou non. Lors de l’exécution de l’AQ, vous pouvez basculer entre la nécessité ou non de respecter le ciblage d’audience.

   * **Afficher le contenu par défaut pour toutes les autres activités :** Si cette option est activée, le contenu par défaut s’affiche pour toutes les autres activités. Par exemple, l’aperçu s’affiche de manière isolée sans tenir compte de toutes les autres activités actives sur la même requête de page/[!DNL Target].

     Si ce paramètre est désactivé, considérez ce qui suit :

      * S’il existe des collisions entre l’activité que vous testez et d’autres activités actives, les [règles de priorité normale](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) s’appliquent. En raison des collisions, il est possible que vous ne puissiez pas voir l’activité que vous avez l’intention de vérifier la qualité.
      * Les mesures s’incrémentent pour les activités vues, mais uniquement dans l’environnement de création de rapports d’AQ.

1. Cliquez sur **[!UICONTROL Done]** pour enregistrer vos modifications.
1. Partagez les URL de lien d’activité avec les membres de votre organisation pour les tests.

   Les liens d’activité n’expirent jamais et vous n’avez pas besoin de renvoyer les liens si quelqu’un modifie une activité ou une expérience. Cependant, si vous appliquez une audience différente de [!UICONTROL Audience Library], au lieu de simplement modifier l’activité, un nouveau lien est généré que vous devez partager à nouveau.

   Chaque URL de lien d’activité (pour l’expérience A, l’expérience B, etc.) vous permet de démarrer le parcours utilisateur à partir de l’expérience correspondante. Cliquez sur l’URL générée pour une expérience, puis passez à la navigation normale sur le site pour afficher les expériences sur plusieurs pages (s’il existe plusieurs pages). Une seule URL est générée par expérience, même si l’expérience s’étend sur plusieurs pages (tests de modèle ou tests de plusieurs pages).

   Vous pouvez parcourir le site pour afficher les autres pages, car le mode [!UICONTROL Activity QA] est attractif. Cette situation est vraie pour les implémentations d’at.js avec la version 2.*x* ou version ultérieure. Pour at.js 1.Implémentations *x*, cette situation n’est vraie que si le navigateur du visiteur ne bloque pas les cookies tiers.

1. Pour afficher les rapports générés à partir des URL de lien d’activité, cliquez sur la page **[!UICONTROL Reports]** de l’activité, cliquez sur l’icône **[!UICONTROL Settings]** ( ![ image_engrenage_icône](assets/icon_gear.png) ), puis sélectionnez **[!UICONTROL QA Mode Traffic]** dans la liste déroulante **[!UICONTROL Environment]**.

## Se libérer du mode AQ

[!UICONTROL Activity QA] est collant. Une fois que vous avez parcouru un site web dans [!UICONTROL Activity QA], votre session [!DNL Target] doit expirer ou [!DNL Target] vous libérer de [!UICONTROL Activity QA] avant de pouvoir afficher votre site comme un visiteur type.

### at.js 2.*x*

Si votre site comporte at.js 2.*x* déployé, utilisez le [signet d’applet AQ de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) pour vous libérer de [!UICONTROL Activity QA]. Le chargement d’une page de votre site avec une valeur vide, comme décrit à l’étape suivante, *not* supprime le cookie AQ du navigateur lorsque at.js 2.*x* est déployé.

### Paramètres at.js 1.*x*

Si votre site comporte at.js 1.*x* déployé, en plus d’utiliser le [signet d’applet AQ de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879), vous pouvez également vous libérer manuellement en chargeant une page de votre site avec le paramètre `at_preview_token` avec une valeur vide. Par exemple :

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

Si [[!UICONTROL Platform Web SDK]](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank} est déployé sur votre site, vous pouvez vous libérer manuellement en chargeant une page de votre site avec le paramètre `at_qa_mode` avec une valeur vide. Par exemple :

`https://www.mysite.com/?at_qa_mode=`

## Considérations {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Comme l’AQ d’activité est désormais disponible pour tous les types d’activité [!DNL Target], la fonction &quot;Prévisualiser les activités Automated Personalization avec les URL d’aperçu de l’expérience&quot; n’est plus nécessaire.
* Les liens d’aperçu [!UICONTROL Activity QA] pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. La nouvelle tentative des liens d’aperçu doit fonctionner. Pour éviter que cette situation ne se reproduise, archivez les activités enregistrées qui ne sont plus utilisées de manière active.
* [!UICONTROL Activity QA] Les URL sont disponibles avec des activités avec [Analytics comme source des rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Les accès générés lors de l’exécution de l’AQ à l’aide de [!UICONTROL Activity QA] se déplacent vers la même suite de rapports que celle où les données de l’activité sont transmises même après la mise en service de l’activité.
* [!UICONTROL Activity QA] n’affiche pas de contenu pour les activités archivées ou les activités dont la date de fin est dépassée. Si vous désactivez une activité terminée, vous devez enregistrer à nouveau l’activité pour que [!UICONTROL Activity QA] fonctionne.
* Les activités importées dans [!DNL Target Standard/Premium] (depuis [!DNL Target Classic], par exemple) ne prennent pas en charge les URL d’assurance qualité.
* Dans les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Recommendations], le modèle n’est pas affecté par les visites capturées dans [!UICONTROL Activity QA].
* Si vous avez spécifié &quot;URL&quot; lors de la création de l’activité [améliorations dans le compositeur d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [options de remise de page dans le compositeur d’expérience visuelle)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), l’URL d’assurance qualité ne fonctionne pas car [!UICONTROL Activity QA] ajoute des paramètres d’URL. Pour résoudre ce problème, cliquez sur l’URL AQ pour accéder à votre site, supprimez les paramètres ajoutés depuis l’URL, puis chargez la nouvelle URL.
* Si vous disposez d’at.js 1.*x*, le mode [!UICONTROL Activity QA] n’est pas attractif si vous utilisez Safari ou un autre navigateur qui bloque les cookies tiers. Dans ce cas, vous devez ajouter les paramètres d’aperçu à chaque URL à laquelle vous accédez. La même chose est vraie si vous avez implémenté [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* Si une activité utilise plusieurs audiences d’expérience (par exemple, un site des États-Unis et du Royaume-Uni inclus dans la même activité), les liens QA ne sont pas générés pour les quatre combinaisons (Expérience A/US Site, Expérience A/Royaume-Uni Site, Expérience B/US Site, Expérience B/Royaume-Uni Site). Seuls deux liens AQ (Expérience A et Expérience B) sont créés et les utilisateurs doivent se qualifier pour l’audience appropriée pour voir la page. Une personne chargée de l’assurance qualité au Royaume-Uni ne peut pas consulter le site des États-Unis.
* Tous les paramètres et toutes les valeurs `at_preview` sont déjà encodés sous forme d’URL. La plupart du temps, tout fonctionne comme prévu. Certains clients doivent toutefois charger des équilibreurs ou des serveurs Web qui tentent de coder à nouveau les paramètres de chaîne de requête.

  En raison de ce double encodage, lorsque [!DNL Target] tente de décoder le `at_preview_token`, [!DNL Target] ne parvient pas à extraire la valeur de jeton correcte, ce qui entraîne un mauvais aperçu.

  [!DNL Adobe] recommande de discuter avec votre équipe informatique pour vous assurer que tous les paramètres d’aperçu sont placés sur la liste autorisée afin que ces valeurs ne soient jamais transformées.

  Le tableau suivant répertorie les paramètres qui peuvent être placés sur la liste autorisée dans votre domaine :

  | Paramètre | Type | Valeur | Description |
  |--- |--- |--- |--- |
  | `at_preview_token` | Chaîne chiffrée | Obligatoire ; aucune valeur par défaut | Entité chiffrée qui contient la liste des identifiants de campagne pouvant être exécutés en mode AQ. |
  | `at_preview_index` | Chaîne | Vide | Le format du paramètre est `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>Les deux index commencent par 1. |
  | `at_preview_listed_activities_only` | Booléen (true/false) | Valeur par défaut : false | Si la valeur est définie sur « true », toutes les campagnes spécifiées dans les paramètres `at_preview_index` seront traitées.<br>Si « false », toutes les campagnes de la page sont traitées, même si elles n’ont pas été spécifiées dans le jeton d’aperçu. |
  | `at_preview_evaluate_as_true_audience_ids` | Chaîne | Vide | Liste de segmentId-s séparés par des traits de soulignement (&quot;_&quot;) qui doivent toujours (au niveau du ciblage et de la création de rapports) être évalués comme &quot;true&quot; dans la portée de la requête [!DNL Target]. |
  | `_AT_Debug` | Chaîne | Fenêtre ou console | Journalisation de console ou nouvelle fenêtre. |
  | `adobe_mc_ref` |  |  | Transmet l’URL de référence de la page par défaut à la nouvelle page. Lorsqu’utilisé avec la version 2.1 (ou ultérieure) de `AppMeasurement.js`, [!DNL Adobe Analytics] utilise cette valeur de paramètre comme URL de référence sur la nouvelle page. |
  | `adobe_mc_sdid` |  |  | Transmet [!DNL Supplemental Data Id] (SDID) et [!DNL Experience Cloud Org Id] de la page par défaut à la nouvelle page. La transmission de ces ID permet à [!UICONTROL Analytics for Target] (A4T) de &quot;regrouper&quot; la requête [!DNL Target] sur la page par défaut avec la requête [!DNL Analytics] sur la nouvelle page. |

* L’interface utilisateur de [!UICONTROL Target QA Mode] affiche uniquement la première URL d’une expérience dans une activité multi-page. L’hypothèse est que vous créez un test de parcours et que vous passez de l’URL 1 à l’URL 2. Toutefois, si vous souhaitez accéder à l’URL 2 indépendamment, copiez tous les paramètres d’URL fournis par rapport à l’URL 1 et appliquez-les à l’URL 2 après avoir placé un « ? ». comme vous le voyez dans l’URL 1.
* Les liens d’aperçu de l’AQ des activités pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. Réessayez les liens d’aperçu. Archivez les activités enregistrées qui ne sont plus utilisées de manière active pour empêcher que ce problème se produise.

## Compatibilité de la bibliothèque Target JavaScript [!UICONTROL QA Mode] {#compatibility}

[!DNL Target] prend en charge les bibliothèques JavaScript suivantes :

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [SDK web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr)

Le tableau suivant répertorie les différents types d’activité et indique si le mode [!UICONTROL Activity QA] est pris en charge pour chaque bibliothèque :

| Type d’activité | at.js 1.x | at.js 2.x | SDK Web Platform |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | Oui | Oui | Oui |
| [!UICONTROL Auto-Allocate] | Oui | Oui | Oui |
| [!UICONTROL Auto-Target] | Oui | Oui | Oui |
| [!UICONTROL Automated Personalization] (AP) | Oui | Oui | Oui |
| [!UICONTROL Experience Targeting] (XT) | Oui | Oui | Oui |
| [!UICONTROL Multivariate Test] (MVT) | Oui | Oui | Oui |
| [!UICONTROL Recommendations] | Oui | Oui | Oui |