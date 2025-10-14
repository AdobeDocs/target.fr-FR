---
keywords: qa;mode qa; qa d’activité;url qa;url qa;url qa;prévisualiser l’url;prévisualiser les url
description: Découvrez comment utiliser les URL Adobe [!DNL Target] QA pour effectuer facilement un contrôle qualité d’activité de bout en bout avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et un compte rendu des performances d’assurance qualité qui reste segmenté à partir des données d’activité en direct.
title: Comment Puis-Je Contrôler La Qualité Des Activités ?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1658'
ht-degree: 27%

---

# AQ d’activité

Utilisez les URL d’assurance qualité dans [!DNL Adobe Target] pour effectuer facilement une assurance qualité de bout en bout de l’activité avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et un compte rendu des performances d’assurance qualité qui reste segmenté à partir des données d’activité en direct.

[!UICONTROL Activity QA] vous permet de tester entièrement vos activités [!DNL Target] avant de les lancer en direct. La fonctionnalité [!UICONTROL Activity QA] comprend les éléments suivants :

* Liens à partager avec les membres de l’équipe qui ne changent jamais ou ne nécessitent aucune régénération, quelles que soient les mises à jour apportées aux expériences ou aux activités. Cette fonctionnalité vous permet de tester entièrement vos activités sur l’ensemble du parcours utilisateur.
* Des conditions d’audience facultatives afin que les responsables du marketing puissent tester les critères de ciblage ou les ignorer pour soumettre à l’assurance qualité (QA) l’aspect des expériences sans avoir à respecter les conditions d’audience.
* La création de rapports QA est capturée afin que les responsables du marketing puissent confirmer que les mesures s’incrémentent comme prévu et que les données des rapports QA sont conservées indépendamment des rapports de production (pour les rapports non-A4T).
* La possibilité de prévisualiser une expérience isolément ou avec d’autres activités en direct satisfaisant aux critères de diffusion (page/[!DNL Target] requête/audience).
* La capacité à vérifier la qualité de l’ensemble du parcours de l’utilisateur. Vous avez accès à votre site une fois avec le lien AQ et vous parcourez ensuite le site entier en mode AQ d’activité. Vous restez dans le QA d’activité jusqu’à la fin de la session ou jusqu’à ce que vous utilisiez le signet cible [QA](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) pour vous forcer à quitter la [!UICONTROL Activity QA]. Cette fonctionnalité est utile si une activité s’étend sur plusieurs pages web.

  >[!NOTE]
  >
  >Cette fonctionnalité s’applique aux implémentations d’at.js avec la version 2.*x* ou version ultérieure. Pour at.js 1.*implémentations x*, cette fonctionnalité n’est valable que si le navigateur du visiteur ne bloque pas les cookies tiers.

## Accès et partage d’une URL AQ {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. Dans la page [!UICONTROL Overview] d&#39;une activité, cliquez sur **[!UICONTROL Activity QA]**.

1. Configurez les paramètres suivants :

   * **[!UICONTROL Match audience rules to see experiences]:** Parfois, vous souhaitez confirmer que la correspondance d’audience fonctionne. D’autres fois, vous souhaiterez vérifier l’aspect et la fonctionnalité de l’activité. Si ce paramètre est activé, les testeurs doivent satisfaire aux exigences de ciblage pour pouvoir voir les expériences. Pour les activités de ciblage d’expérience (XT), une seule URL d’activité est fournie. L’expérience que vous voyez est déterminée par le fait que vous vous qualifiez pour l’une des règles de ciblage.

     Si ce paramètre est désactivé, le fait de cliquer sur les liens vous montre les expériences, que vous vous qualifiez ou non. Lors de l’exécution de l’AQ, vous pouvez basculer entre la nécessité ou non de respecter le ciblage d’audience.

   * **Afficher le contenu par défaut pour toutes les autres activités :** si cette option est activée, le contenu par défaut est affiché pour toutes les autres activités. Par exemple, l’aperçu s’affiche de manière isolée sans prendre en compte toutes les autres activités actives sur la même demande de page/[!DNL Target].

     Si ce paramètre est désactivé, tenez compte de ce qui suit :

      * En cas de conflits entre l’activité que vous testez et d’autres activités actives, les [&#x200B; règles de priorité normales &#x200B;](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) s’appliquent. En raison de collisions, il est possible que vous ne puissiez pas voir l’activité que vous prévoyez d’AQ.
      * Les mesures s’incrémentent pour les activités vues, mais uniquement dans l’environnement de création de rapports d’AQ.

1. Cliquez sur **[!UICONTROL Done]** pour enregistrer vos modifications.
1. Partagez les URL de lien d’activité avec des membres de votre organisation à des fins de test.

   Les liens d’activité n’expirent jamais et vous n’avez pas besoin de renvoyer de liens si quelqu’un modifie une activité ou une expérience. Cependant, si vous appliquez une audience différente de la [!UICONTROL Audience Library], plutôt que de simplement modifier l’activité, un nouveau lien est généré et vous devez le partager à nouveau.

   Chaque URL de lien d’activité (pour l’expérience A, l’expérience B, etc.) vous permet de démarrer le parcours utilisateur à partir de l’expérience correspondante. Cliquez sur l’URL générée pour une expérience, puis poursuivez votre navigation normale sur le site pour afficher les expériences sur plusieurs pages (s’il en existe plusieurs). Une seule URL est générée par expérience, même si l’expérience s’étend sur plusieurs pages (test de modèles ou test de plusieurs pages).

   Vous pouvez parcourir le site pour afficher les autres pages, car le mode [!UICONTROL Activity QA] est contigu. Cette situation est vraie pour les implémentations d’at.js avec la version 2.*x* ou version ultérieure. Pour at.js 1.*x*, cette situation est uniquement vraie si le navigateur du visiteur ne bloque pas les cookies tiers.

1. Pour afficher les rapports générés à partir des URL de lien d’activité, cliquez sur la page de **[!UICONTROL Reports]** de l’activité, cliquez sur l’icône **[!UICONTROL Settings]** ( ![icon_gear image](assets/icon_gear.png) ), puis sélectionnez **[!UICONTROL QA Mode Traffic]** dans la liste déroulante **[!UICONTROL Environment]** .

## Abandonner le mode AQ

[!UICONTROL Activity QA] est collant. Après avoir parcouru un site web en [!UICONTROL Activity QA], votre session [!DNL Target] doit expirer ou vous devez être libéré [!DNL Target] de [!UICONTROL Activity QA] avant de pouvoir afficher votre site comme un visiteur standard.

### at.js 2.*x*

Si votre site comporte at.js 2.*x* déployé, utilisez le signet d’assurance qualité [Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) pour vous forcer à quitter l’[!UICONTROL Activity QA]. Le chargement d’une page de votre site avec une valeur vide, comme décrit dans la puce suivante, ne supprime *pas* le cookie d’assurance qualité du navigateur lorsqu’at.js 2.*x* est déployé.

### Paramètres at.js 1.*x*

Si votre site comporte at.js 1.*x* déployé, en plus d’utiliser le signet d’assurance qualité [Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879), vous pouvez également vous forcer manuellement à quitter le site en chargeant une page de votre site avec le paramètre `at_preview_token` avec une valeur vide. Par exemple :

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

Si le [[!UICONTROL Platform Web SDK]](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr){target=_blank} est déployé sur votre site, vous pouvez forcer manuellement à quitter le site en chargeant une page sur votre site avec le paramètre `at_qa_mode` avec une valeur vide. Par exemple :

`https://www.mysite.com/?at_qa_mode=`

## Considérations {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Le QA d’activité étant désormais disponible pour tous les types d’activités [!DNL Target], la fonction « Prévisualiser les activités Automated Personalization avec les URL de prévisualisation d’expérience » n’est plus nécessaire.
* Les liens d’aperçu [!UICONTROL Activity QA] pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. Toute nouvelle tentative d’affichage des liens d’aperçu devrait fonctionner. Pour éviter que cette situation ne se reproduise, archivez les activités enregistrées qui ne sont plus utilisées activement.
* Les URL [!UICONTROL Activity QA] sont disponibles avec les activités dont la source de création de rapports est [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Accès générés lors de l’assurance qualité à l’aide d’[!UICONTROL Activity QA] flux vers la même suite de rapports où les données de l’activité sont transmises même après la mise en ligne de l’activité.
* [!UICONTROL Activity QA] n’affiche pas le contenu des activités archivées ou dont la date de fin est dépassée. Si vous désactivez une activité terminée, vous devez enregistrer à nouveau l’activité pour que [!UICONTROL Activity QA] fonctionne.
* Les activités importées dans [!DNL Target Standard/Premium] (à partir de [!DNL Target Classic], par exemple) ne prennent pas en charge les URL d’assurance qualité.
* Dans les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Recommendations], le modèle n’est pas affecté par les visites capturées dans [!UICONTROL Activity QA].
* Si vous avez spécifié « URL is » lors de la création de l’activité [affinements dans le compositeur basé sur les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [options de diffusion de page dans le compositeur d’expérience visuelle)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), l’URL d’assurance qualité ne fonctionne pas, car [!UICONTROL Activity QA] ajoute des paramètres d’URL. Pour résoudre ce problème, cliquez sur l’URL AQ pour accéder à votre site, supprimez les paramètres ajoutés depuis l’URL, puis chargez la nouvelle URL.
* Si vous disposez d’at.js 1.*x*, le mode [!UICONTROL Activity QA] n’est pas contigu si vous utilisez Safari ou un autre navigateur qui bloque les cookies tiers. Dans ce cas, vous devez ajouter les paramètres de prévisualisation à chaque URL à laquelle vous accédez. Il en va de même si vous avez implémenté [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html?lang=fr){target=_blank}.
* Si une activité utilise plusieurs audiences d’expérience (par exemple, un site des États-Unis et du Royaume-Uni qui est inclus dans la même activité), les liens d’assurance qualité ne sont pas générés pour les quatre combinaisons (site Experience A/US, site Experience A/UK, site Experience B/US, site Experience B/UK). Seuls deux liens AQ (Expérience A et Expérience B) sont créés et les utilisateurs doivent se qualifier pour l’audience appropriée pour voir la page. Un responsable du contrôle qualité au Royaume-Uni ne peut pas voir le site américain.
* Tous les paramètres et toutes les valeurs `at_preview` sont déjà encodés sous forme d’URL. La plupart du temps, tout fonctionne comme prévu. Cependant, certains clients doivent utiliser des équilibreurs de charge ou des serveurs Web qui tentent à nouveau de coder les paramètres de chaîne de requête.

  En raison de ce double codage, lorsque [!DNL Target] tente de décoder le `at_preview_token`, [!DNL Target] ne parvient pas à extraire la valeur correcte du jeton, ce qui entraîne le dysfonctionnement de l’aperçu.

  placer sur la liste autorisée [!DNL Adobe] vous recommande de vous adresser à votre équipe informatique pour vous assurer que tous les paramètres de prévisualisation sont traités de manière à ce que ces valeurs ne soient en aucun cas transformées.

  Placer sur la liste autorisée Le tableau suivant répertorie les paramètres qui peuvent être traités dans votre domaine :

  | Paramètre | Type | Valeur | Description |
  |--- |--- |--- |--- |
  | `at_preview_token` | Chaîne chiffrée | Obligatoire ; aucune valeur par défaut | Une entité chiffrée contenant la liste des identifiants de campagne qui peuvent être exécutés en mode assurance qualité. |
  | `at_preview_index` | Chaîne | Vide | Le format du paramètre est `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>Les deux index commencent par 1. |
  | `at_preview_listed_activities_only` | Booléen (true/false) | Valeur par défaut : false | Si la valeur est définie sur « true », toutes les campagnes spécifiées dans les paramètres `at_preview_index` seront traitées.<br>Si « false », toutes les campagnes de la page sont traitées, même si elles n’ont pas été spécifiées dans le jeton d’aperçu. |
  | `at_preview_evaluate_as_true_audience_ids` | Chaîne | Vide | Liste séparée par des traits de soulignement (« _ ») des identifiant de segment qui doivent toujours (au niveau du ciblage et du compte rendu des performances) être évalués comme « true » dans la portée de la requête [!DNL Target]. |
  | `_AT_Debug` | Chaîne | Fenêtre ou console | Journalisation de console ou nouvelle fenêtre. |
  | `adobe_mc_ref` |  |  | Transmet l’URL de référence de la page par défaut à la nouvelle page. Lorsqu’utilisé avec la version 2.1 (ou ultérieure) de `AppMeasurement.js`, [!DNL Adobe Analytics] utilise cette valeur de paramètre comme URL de référence sur la nouvelle page. |
  | `adobe_mc_sdid` |  |  | Transmet le [!DNL Supplemental Data Id] (SDID) et le [!DNL Experience Cloud Org Id] de la page par défaut à la nouvelle page. La transmission de ces identifiants permet à [!UICONTROL Analytics for Target] (A4T) de « regrouper » la requête [!DNL Target] sur la page par défaut avec la requête [!DNL Analytics] sur la nouvelle page. |

* L’interface utilisateur de [!UICONTROL Target QA Mode] n’affiche que la première URL d’une expérience dans une activité multipage. L’hypothèse est que vous créez un test de parcours et que vous passez de URL1 à URL2. Toutefois, si vous souhaitez accéder à l’URL 2 indépendamment, copiez tous les paramètres d’URL fournis par rapport à l’URL 1 et appliquez-les à l’URL 2 après avoir placé un « ? ». comme vous le voyez dans l’URL 1.
* Les liens d’aperçu de l’AQ des activités pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. Réessayez les liens d’aperçu. Archivez les activités enregistrées qui ne sont plus utilisées activement pour empêcher ce problème de se produire.

## Compatibilité des [!UICONTROL QA Mode] de bibliothèque JavaScript Target {#compatibility}

[!DNL Target] prend en charge les bibliothèques JavaScript suivantes :

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=fr)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=fr)
* [SDK web Adobe Experience Platform](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=fr)

Le tableau suivant répertorie les différents types d’activités et indique si [!UICONTROL Activity QA] mode est pris en charge pour chaque bibliothèque :

| Type d’activité | at.js 1.x | at.js 2.x | SDK web de Platform |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | Oui | Oui | Oui |
| [!UICONTROL Auto-Allocate] | Oui | Oui | Oui |
| [!UICONTROL Auto-Target] | Oui | Oui | Oui |
| [!UICONTROL Automated Personalization] (AP) | Oui | Oui | Oui |
| [!UICONTROL Experience Targeting] (XT) | Oui | Oui | Oui |
| [!UICONTROL Multivariate Test] (VMT) | Oui | Oui | Oui |
| [!UICONTROL Recommendations] | Oui | Oui | Oui |