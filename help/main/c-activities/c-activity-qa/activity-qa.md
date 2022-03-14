---
keywords: qa;mode qa; activité qa;url qa;url qa;url d’aperçu;url d’aperçu;url d’aperçu
description: Découvrez comment utiliser Adobe [!DNL Target] URL d’assurance qualité pour vérifier simplement et de manière exhaustive la qualité des activités avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’assurance qualité qui restent segmentés à partir des données d’activité actives.
title: Comment vérifier la qualité des activités ?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1759'
ht-degree: 37%

---

# AQ d’activité

Utilisation d’URL AQ dans [!DNL Adobe Target] pour effectuer une AQ d’activité de bout en bout simple avec des liens d’aperçu qui ne changent jamais, un ciblage d’audience facultatif et une création de rapports d’AQ qui restent segmentés à partir des données d’activité actives.

[!UICONTROL AQ d’activité] permet de tester entièrement votre [!DNL Target] activités avant de les lancer en direct. Le [!UICONTROL AQ d’activité] Cette fonctionnalité comprend :

* Liens à partager avec les membres de l’équipe qui ne changent jamais ou ne nécessitent aucune régénération, quelles que soient les mises à jour apportées aux expériences ou aux activités. Cette fonctionnalité vous permet de tester entièrement vos activités sur l’ensemble du parcours d’utilisateurs.
* Des conditions d’audience facultatives afin que les responsables du marketing puissent tester les critères de ciblage ou les ignorer pour soumettre à l’assurance qualité (QA) l’aspect des expériences sans avoir à respecter les conditions d’audience.
* La création de rapports QA est capturée afin que les responsables du marketing puissent confirmer que les mesures s’incrémentent comme prévu et que les données des rapports QA sont conservées indépendamment des rapports de production (pour les rapports non-A4T).
* La possibilité de prévisualiser une expérience seule ou avec d’autres activités actives satisfaisant les critères de diffusion (page/demande/audience de ciblage).
* La capacité à vérifier la qualité de l’ensemble du parcours de l’utilisateur. Vous avez accès à votre site une fois avec le lien AQ et vous parcourez ensuite le site entier en mode AQ d’activité. Vous restez dans l’AQ d’activité jusqu’à ce vous mettiez fin à la session ou que vous utilisiez le [signet d’applet AQ de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  pour vous libérer de l’AQ d’activité]. Cette fonctionnalité est utile si vous avez une activité qui s’étend sur plusieurs pages web.

   >[!NOTE]
   >
   >Cette fonctionnalité est vraie pour les implémentations d’at.js avec la version 2.*x* ou plus tard. Pour at.js 1.*x* implémentations, cette fonctionnalité est vraie uniquement si le navigateur du visiteur ne bloque pas les cookies tiers.

## Accès et partage d’une URL AQ {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. À partir d’une activité [!UICONTROL Présentation] , cliquez sur la page **[!UICONTROL AQ d’activité]** lien.

   ![Liens de l’AQ d’activité](assets/qa_link.png)

1. Configurez les paramètres suivants :

   ![Options de configuration des liens d’assurance qualité](assets/qa_link_config.png)

   * **[!UICONTROL Faire correspondre les règles d’audience pour afficher les expériences]:** Parfois, vous souhaitez confirmer que la correspondance de l’audience fonctionne. D’autres fois, vous souhaitez vérifier l’aspect de l’activité. Si ce paramètre est activé, les testeurs doivent satisfaire aux exigences de ciblage pour pouvoir voir les expériences. Pour les activités de ciblage d’expérience (XT), une seule URL d’activité est fournie. L’expérience que vous voyez est déterminée par le fait que vous vous qualifiez pour l’une des règles de ciblage.

      Si ce paramètre est désactivé, le fait de cliquer sur les liens vous montre les expériences, que vous vous qualifiez ou non. Lors de l’exécution de l’AQ, vous pouvez basculer entre la nécessité ou non de respecter le ciblage d’audience.

   * **Afficher le contenu par défaut pour toutes les autres activités :** Si cette option est activée, le contenu par défaut s’affiche pour toutes les autres activités. Par exemple, l’aperçu s’affiche isolément sans tenir compte de toutes les autres activités actives sur la même page/[!DNL Target] requête.

      Si ce paramètre est désactivé, considérez ce qui suit :

      * En cas de conflits entre l’activité que vous testez et d’autres activités actives, [les règles de priorité normale](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) s’appliquent. En raison des collisions, il est possible que vous ne puissiez pas voir l’activité que vous avez l’intention de vérifier la qualité.
      * Les mesures s’incrémentent pour les activités vues, mais uniquement dans l’environnement de création de rapports d’AQ.

1. Cliquez sur **[!UICONTROL Terminé]** pour enregistrer les modifications.
1. Partagez les URL de lien d’activité avec les membres de votre organisation pour les tests.

   Les liens d’activité n’expirent jamais et vous n’avez pas besoin de renvoyer les liens si quelqu’un modifie une activité ou une expérience. Cependant, si vous appliquez une audience différente de la variable [!UICONTROL Bibliothèque d’audiences], plutôt que de simplement modifier l’activité, un nouveau lien est généré, que vous devez partager à nouveau.

   Chaque URL de lien d’activité (pour l’expérience A, l’expérience B, etc.) vous permet de démarrer le parcours utilisateur à partir de l’expérience correspondante. Cliquez sur l’URL générée pour une expérience, puis passez à la navigation normale sur le site pour afficher les expériences sur plusieurs pages (s’il existe plusieurs pages). Une seule URL est générée par expérience, même si celle-ci s’étend sur plusieurs pages (tests de modèle ou tests de plusieurs pages).

   Vous pouvez parcourir le site pour afficher les autres pages, car la variable [!UICONTROL AQ d’activité] Le mode est collant. Cette situation est vraie pour les implémentations d’at.js avec la version 2.*x* ou plus tard. Pour at.js 1.*x* Implémentations, cette situation n’est vraie que si le navigateur du visiteur ne bloque pas les cookies tiers.

1. Pour afficher les rapports générés à partir des URL de lien d’activité, cliquez sur le **[!UICONTROL Rapports]** , cliquez sur la page **[!UICONTROL Paramètres]** Icône (  ![](assets/icon_gear.png) ), puis sélectionnez **[!UICONTROL Trafic du mode AQ]** de la **[!UICONTROL Environnement]** liste déroulante.

## Considérations {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Le [!UICONTROL AQ d’activité] s’affiche sur la page [!UICONTROL Présentation] de tous les types d’activités sauf [!UICONTROL Ciblage automatique] et [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Les liens d’aperçu de l’AQ des activités pour les activités enregistrées peuvent ne pas se charger si votre compte comporte trop d’activités enregistrées. ] La nouvelle tentative des liens d’aperçu doit fonctionner. Pour éviter que cette situation ne se reproduise, archivez les activités enregistrées qui ne sont plus utilisées de manière active.
* [!UICONTROL Les URL AQ d’activité sont disponibles avec les activités avec Analytics en tant que source des rapports (A4T). ] Accès générés lors de l’exécution de l’AQ à l’aide de [!UICONTROL AQ d’activité] flux vers la même suite de rapports que celle où les données de l’activité sont transmises même après activation de l’activité.
* [!UICONTROL L’AQ d’activité n’affiche pas de contenu pour les activités archivées ni les activités dont le délai est écoulé. ] Si vous désactivez une activité terminée, vous devez enregistrer à nouveau l’activité pour [!UICONTROL AQ d’activité] au travail.
* Activités importées dans [!DNL Target Standard/Premium] (de [!DNL Target Classic], par exemple) ne prennent pas en charge les URL AQ.
* Dans [!UICONTROL Affectation automatique] et [!UICONTROL Recommendations] activités, le modèle n’est pas affecté par les visites capturées dans [!UICONTROL AQ d’activité].
* [!UICONTROL AQ d’activité] est collant. Une fois que vous avez consulté un site web dans [!UICONTROL AQ d’activité], votre [!DNL Target] doit expirer ou vous devez [!DNL Target] de [!UICONTROL AQ d’activité] avant de pouvoir afficher votre site comme un visiteur type. Utilisez le [signet d’applet AQ de Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  pour vous libérer de l’AQ d’activité].

   Vous pouvez également vous libérer manuellement en chargeant une page de votre site avec le `at_preview_token`paramètre doté d’une valeur vide (par exemple, `https://www.mysite.com/?at_preview_token=`).

* Si vous avez spécifié &quot;URL&quot; lors de la création de l’activité [perfectionnements dans le compositeur d’après les formulaires](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [options de remise de page dans le compositeur d’expérience visuelle)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), l’URL d’assurance qualité ne fonctionne pas car [!UICONTROL AQ d’activité] ajoute les paramètres d’URL. Pour résoudre ce problème, cliquez sur l’URL AQ pour accéder à votre site, supprimez les paramètres ajoutés depuis l’URL, puis chargez la nouvelle URL.
* Si vous disposez d’at.js 1.*x*, [!UICONTROL AQ d’activité] n’est pas attractif si vous utilisez Safari ou un autre navigateur qui bloque les cookies tiers. Dans ce cas, vous devez ajouter les paramètres d’aperçu à chaque URL à laquelle vous accédez. La même chose est vraie si vous avez implémenté [CNAME](/help/main/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md).
* Si une activité utilise plusieurs audiences d’expérience (par exemple, un site des États-Unis et du Royaume-Uni inclus dans la même activité), les liens QA ne sont pas générés pour les quatre combinaisons (Expérience A/US Site, Expérience A/Royaume-Uni Site, Expérience B/US Site, Expérience B/Royaume-Uni Site). Seuls deux liens AQ (Expérience A et Expérience B) sont créés et les utilisateurs doivent se qualifier pour l’audience appropriée pour voir la page. Une personne chargée de l’assurance qualité au Royaume-Uni ne peut pas consulter le site des États-Unis.
* Tous les paramètres et toutes les valeurs `at_preview` sont déjà encodés sous forme d’URL. La plupart du temps, tout fonctionne comme prévu. Certains clients doivent toutefois charger des équilibreurs ou des serveurs Web qui tentent de coder à nouveau les paramètres de chaîne de requête.

   En raison de ce double encodage, lorsque [!DNL Target] tente de décoder la variable `at_preview_token`, [!DNL Target] Impossible d’extraire la valeur de jeton correcte, ce qui entraîne un mauvais aperçu.

   Adobe vous recommande de discuter avec votre équipe informatique pour vous assurer que tous les paramètres d’aperçu sont placés sur la liste autorisée afin que ces valeurs ne soient jamais transformées.

   Le tableau suivant répertorie les paramètres qui peuvent être placés sur la liste autorisée dans votre domaine :

   | Paramètre | Type | Valeur | Description |
   |--- |--- |--- |--- |
   | `at_preview_token` | Chaîne chiffrée | Obligatoire ; aucune valeur par défaut | Entité chiffrée qui contient la liste des identifiants de campagne pouvant être exécutés en mode AQ. |
   | `at_preview_index` | Chaîne | Vide | Le format du paramètre est `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>. Les deux index commencent par 1. |
   | `at_preview_listed_activities_only` | Booléen (true/false) | Valeur par défaut : false | Si la valeur est définie sur « true », toutes les campagnes spécifiées dans les paramètres `at_preview_index` seront traitées.<br>Si « false », toutes les campagnes de la page sont traitées, même si elles n’ont pas été spécifiées dans le jeton d’aperçu. |
   | `at_preview_evaluate_as_true_audience_ids` | Chaîne | Vide | Liste de segmentId-s séparés par des traits de soulignement (&quot;_&quot;) qui doivent toujours (au niveau du ciblage et de la création de rapports) être évalués sur &quot;true&quot; dans la portée de [!DNL Target] requête. |
   | `_AT_Debug` | Chaîne | Fenêtre ou console | Journalisation de console ou nouvelle fenêtre. |
   | `adobe_mc_ref` |  |  | Transmet l’URL de référence de la page par défaut à la nouvelle page. Lorsqu’utilisé avec la version 2.1 (ou ultérieure) de `AppMeasurement.js`, [!DNL Adobe Analytics] utilise cette valeur de paramètre comme URL de référence sur la nouvelle page. |
   | `adobe_mc_sdid` |  |  | Transmet la variable [!DNL Supplemental Data Id] (SDID) et [!DNL Experience Cloud Org Id] de la page par défaut à la nouvelle page. Transmission de ces identifiants autorisée [!UICONTROL Analytics pour Target] (A4T) pour &quot;assembler&quot; la variable [!DNL Target] sur la page par défaut avec la propriété [!DNL Analytics] sur la nouvelle page. |

* Le [!UICONTROL Mode AQ de Target] L’interface utilisateur affiche uniquement la première URL d’une expérience dans une activité multi-page. L’hypothèse est que vous créez un test de parcours et que vous passez de l’URL 1 à l’URL 2. Toutefois, si vous souhaitez accéder à l’URL 2 indépendamment, copiez tous les paramètres d’URL fournis par rapport à l’URL 1 et appliquez-les à l’URL 2 après avoir placé un « ? ». comme vous le voyez dans l’URL 1.

## Compatibilité du [!UICONTROL Mode AQ] de la bibliothèque JavaScript de Target {#compatibility}

[!DNL Target] prend en charge les bibliothèques JavaScript suivantes :

* [at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [SDK web Adobe Experience Platform](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

Le tableau suivant répertorie les différents types d’activité et indique si [!UICONTROL AQ d’activité] Le mode est pris en charge pour chaque bibliothèque :

| Type d’activité | at.js 1.x | at.js 2.x | SDK Web Platform |
| --- | --- | --- | --- |
| [!UICONTROL Test A/B] | Oui | Oui | Oui |
| [!UICONTROL affectation automatique] | Oui | Oui | Oui |
| [!UICONTROL ciblage automatique] | Non | Non | Non |
| [!UICONTROL Automated Personalization] (AP) | Non | Non | Non |
| [!UICONTROL Ciblage d’expérience] (XT) | Oui | Oui | Oui |
| [!UICONTROL Test multivarié] (MVT) | Oui | Oui | Oui |
| [!UICONTROL Recommendations] | Oui | Oui | Oui |

## Prévisualisation des URL {#preview}

Les URL d’aperçu de l’expérience peuvent être générées pour tous les [!DNL Target] types d’activité. Les URL d’aperçu vous permettent d’afficher le contenu de l’expérience directement sur votre site avant que l’activité ne soit activée à des fins d’aperçu et d’assurance qualité. Les URL d’aperçu de l’expérience contournent le ciblage pour forcer l’affichage d’une expérience particulière.

Pour plus d’informations sur le fonctionnement des URL d’aperçu avec [!UICONTROL Automated Personalization] (AP), voir [Prévisualisation des activités Automated Personalization avec des URL de prévisualisation de l’expérience](/help/main/c-activities/t-automated-personalization/experience-preview.md).

Pour accéder à une URL d’aperçu et la partager à partir d’une **[!UICONTROL Présentation]** , cliquez sur la page **[!UICONTROL AQ d’activité]** lien.

>[!NOTE]
>
>Le [!UICONTROL AQ d’activité] Le lien et l&#39;URL de prévisualisation sont identiques pour toutes les activités autres que [!DNL Target] activités AP.

Le tableau suivant répertorie les différents types d’activité et indique si la fonctionnalité d’aperçu des URL est prise en charge pour chaque bibliothèque ou API :

| Type d’activité | at.js 1.x | at.js 2.x | SDK Web Platform |
| --- | --- | --- | --- |
| [!UICONTROL Test A/B] | Oui | Oui | Oui |
| [!UICONTROL affectation automatique] | Oui | Oui | Oui |
| [!UICONTROL Ciblage automatique] | Oui | Oui | Oui |
| [!UICONTROL Automated Personalization] (AP) | Oui | Oui | Oui |
| [!UICONTROL Ciblage d’expérience] (XT) | Oui | Oui | Oui |
| [!UICONTROL Test multivarié] (MVT) | Oui | Oui | Oui |
| [!UICONTROL Recommendations] | Oui | Oui | Oui |

