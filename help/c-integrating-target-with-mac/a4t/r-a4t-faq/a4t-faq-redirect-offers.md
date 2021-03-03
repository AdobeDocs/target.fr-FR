---
keywords: faq;questions fréquentes;analytics for target;a4T;redirection;offres de redirection;adobe-mc-sdid;adobe_mc_ref
description: Trouvez des réponses aux questions relatives à l’utilisation des offres de redirection lors de l’utilisation d’Analytics pour la Cible (A4T). A4T vous permet d’utiliser le rapports Analytics pour les activités de Cible.
title: Où puis-je trouver des FAQ sur les Offres de redirection avec A4T ?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 69%

---


# FAQ sur les offres de redirection - A4T

Cette rubrique contient des réponses aux questions fréquemment posées sur l’utilisation des offres de redirection lorsque [!DNL Adobe Analytics] est utilisé comme source de rapports pour [!DNL Adobe Target] (A4T).

## Analytics for Target (A4T) prend-il en charge les offres de redirection ?{#section_46B8B03ED4D542C6AD875F5F61176298}

Oui, si votre implémentation utilise [!DNL at.js]. Toutefois, votre implémentation doit respecter la configuration minimale requise ci-dessous pour utiliser les offres [de redirection](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) dans les activités qui utilisent Analytics comme source de création de rapports.

>[!NOTE]
>
>Un problème connu entraîne un nombre limité de clients utilisant des redirections avec A4T pour afficher un pourcentage plus élevé de taux d’accès désassemblés. Reportez-vous à la section [Problèmes connus et problèmes résolus](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Quelles sont les exigences minimales pour utiliser les offres de redirection avec A4T ? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Votre mise en œuvre doit satisfaire aux exigences minimales suivantes :

* Service d’identification des visiteurs d’Experience Cloud : [!DNL visitorAPI.js] version 2.3.0 ou ultérieure.
* Adobe Analytics : [!DNL appMeasurement.js] version 2.1.
* Adobe Target : [!DNL at.js] version 1.6.2 ou ultérieure.

   La bibliothèque [!DNL mbox.js] ne prend pas en charge les offres de redirection avec A4T. Votre implémentation doit utiliser [!DNL at.js].

Les trois bibliothèques doivent être incluses sur la page comportant l’offre de redirection et sur la page vers laquelle est redirigé le visiteur.

## Pourquoi y a-t-il parfois des incohérences de données entre A4T et Analytics ?

Certaines incohérences de données sont attendues. Pour plus d’informations, voir [Écarts de données attendus entre Target et Analytics lors de l’utilisation ou de la non-utilisation de A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

## Pourquoi les pages vues sont-elles parfois comptabilisées sur la page originale et la page de redirection ? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

Lors de l’utilisation d’at.js version 1.6.3 ou ultérieure, le comptage des vues de page sur les deux pages n’est pas un problème. Cette situation de concurrence affecte uniquement les clients qui utilisent des versions antérieures. L’équipe Target gère deux versions seulement d’at.js : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour at.js si nécessaire pour vous assurer que vous utilisez une [version prise en charge](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Si vous utilisez une version antérieure d’at.js non prise en charge, il est possible qu’une condition de concurrence puisse se produire et que l’appel Analytics se déclenche avant que la redirection ne s’exécute sur la première page. Cette situation peut entraîner le comptage des vues de page sur la page d’origine et sur la page de redirection. Cette situation entraîne la comptabilisation d’une page vue supplémentaire sur la première page, bien que le visiteur ne l’ait jamais véritablement consultée.

Il est recommandé d’utiliser le compositeur basé sur les formulaires pour créer une activité de redirection afin d’accélérer la redirection de la page en raison de l’emplacement d’exécution du code sur la page. Il est également recommandé de créer une offre de redirection pour chaque expérience où la redirection renvoie la page originale, y compris l’expérience par défaut. La création d’une offre de redirection pour chaque expérience garantit que si un mauvais comptage se produit, il se produit dans toutes les expériences. Rapports et analyse sont toujours valables pour le test.

L’utilisation des offres de redirection pour toutes les expériences de l’activité, y compris l’expérience par défaut (contrôle), permet de mettre les mêmes conditions sur toutes les expériences. Par exemple, si l’expérience par défaut ne comporte pas d’offre de redirection alors que les autres en ont, la vitesse de l’expérience sans offre de redirection présente un avantage inhérent. Les offres de redirection sont recommandées pour des scénarios temporaires uniquement, comme les tests. Les offres de redirection ne sont pas recommandées pour les scénarios permanents tels que la personnalisation. Après avoir déterminé le « gagnant », vous devez supprimer la redirection pour améliorer les performances de chargement des pages.

Pour en savoir plus sur ce problème, consultez « Offres de redirection » dans la section [Problèmes connus](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Puis-je utiliser les offres de redirection avec A4T si j’utilise la bibliothèque JavaScript mbox.js ?{#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

La bibliothèque [!DNL mbox.js] ne prend pas en charge les offres de redirection avec A4T. Votre implémentation doit utiliser [!DNL at.js].

## Le compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires sont-ils tous les deux pris en charge ?{#section_FDA26FE7909B48539DA770559E687677}

Oui, les deux compositeurs sont pris en charge du moment que vous utilisez les offres de redirection intégrées.

Si vous utilisez votre propre code personnalisé pour la redirection, vous devez vous assurer de générer les deux nouveaux paramètres associés aux URL de redirection (`adobe_mc_sdid` et `adobe_mc_ref`, tel qu’expliqué ci-dessus).

## Quels sont les nouveaux paramètres de chaîne de requête ajoutés aux URL de redirection ?{#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Les paramètres de chaîne de requête suivants sont associés aux offres de redirection :

| Paramètre | Description |
|--- |--- |
| `adobe_mc_sdid` | Le paramètre `adobe_mc_sdid` transmet l’ID de données supplémentaire (SDID) et l’ID d’organisation Experience Cloud de la page par défaut à la nouvelle page. Ces identifiants permettent à A4T de &quot;réunir&quot; la requête de Cible sur la page par défaut avec la requête Analytics sur la nouvelle page. |
| `adobe_mc_ref` | Le paramètre `adobe_mc_ref` transfère l’URL de référence de la page par défaut vers la nouvelle page. Lorsqu’il est utilisé avec AppMeasurement.js version 2.1 (ou ultérieure), Analytics utilise cette valeur de paramètre comme URL de référence sur la nouvelle page. |

Ces paramètres sont automatiquement ajoutés aux URL de redirection lorsque vous utilisez les offres de redirection intégrées dans le compositeur d’expérience visuelle et le compositeur d’expérience d’après les formulaires, lorsque le service Identifiant visiteur est mis en œuvre dans la page. Si vous utilisez votre propre code de redirection personnalisé dans le compositeur d’expérience visuelle ou le compositeur d’expérience d’après les formulaires, vous devez vous assurer de transférer ces paramètres avec votre code personnalisé.

## Mes serveurs web retirent ces paramètres de mes URL. Que dois-je faire ?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Contactez votre équipe informatique pour que ces paramètres ( `adobe_mc_sdid` et `adobe_mc_ref`) soient placés sur la liste autorisée.

## Que puis-je faire si je n’utilise pas A4T avec mon activité de redirection et que je ne souhaite pas que ces paramètres supplémentaires s’ajoutent à mes URL ?{#section_9E608D75FF9349FE96C65FEDD7539F45}

Utilisez une redirection codée de manière personnalisée si :

* Vous n’utilisez pas A4T avec votre activité de redirection.
* Le service d’identification des Visiteurs est mis en oeuvre
* Vous ne souhaitez pas que ces paramètres soient automatiquement ajoutés à vos URL

Cependant, il est recommandé de conserver le paramètre `adobe_mc_ref` dans l’URL pour signaler correctement les informations référentes à [!DNL Analytics].

## Pourquoi les paramètres adobe_mc_ref and adobe_mc_sdid comportent-ils un codage URL double dans mon implémentation ?{#section_5EFE5F012B944C40865731EA18E7E79E}

Si vous utilisez A4T et que vous redirigez des offres, Target ajoute les paramètres `adobe_mc_ref` et `adobe_mc_sdid` à l’URL. Ces valeurs sont déjà en codage URL. La plupart du temps, tout fonctionne comme prévu, mais certains clients peuvent avoir des équilibrages de charge ou des serveurs Web qui tentent de coder à nouveau les paramètres de la chaîne de requête.

En raison de ce double codage, lorsque l’API visiteur tente de décoder la valeur `adobe_mc_sdid`, elle ne parvient pas à extraire le SDID et en génère un nouveau. Ce processus conduit à l’envoi de valeurs SDID incorrectes à la Cible et à Analytics et à l’affichage d’une division inégale pour les redirections dans les rapports Analytics.

L’Adobe vous recommande de consulter votre équipe informatique pour vous assurer que `adobe_mc_ref` et `adobe_mc_sdid` sont placés sur la liste autorisée afin que ces valeurs ne soient pas transformées d’aucune manière.

## Pourquoi l’URL de référence doit-elle être transmise à la nouvelle page ? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Supposons qu’un visiteur clique sur un lien [!DNL `www.google.com`] vers votre page d’accueil (`www.mysite.com/index.html`) sur lequel une activité de redirection est active, puis qu’il soit redirigé vers une nouvelle page (`www.mysite.com/index2.html`).

Auparavant, la requête [!DNL Analytics] sur la nouvelle page signalait l’URL de référence [!DNL `www.mysite.com/index.html`] au lieu de [!DNL `www.google.com`]. Dans [!DNL Analytics], cela générait des rapports inexacts concernant les URL de référence (dans les rapports sur les canaux marketing, par exemple). Les rapports manquaient la véritable provenance du visiteur, c’est-à-dire [!DNL `www.google.com`].

Avec [!DNL at.js] version 0.9.6 (ou ultérieure) et [!DNL AppMeasurement.js] 2.1 (ou ultérieure), la requête [!DNL Analytics] sur la nouvelle page signale une URL référente de [!DNL `www.google.com`].

## Puis-je utiliser des offres de redirection/HTML personnalisées ?{#section_E49F9A83A286488C8F1098A040203D7E}

Non, vous devez utiliser une offre de redirection intégrée pour les activités qui utilisent [!DNL Analytics] comme source des rapports (A4T). Pour [!DNL Target], les offres HTML sont opaques : [!DNL Target] ne peut pas savoir si un code HTML spécifique contient le code JavaScript qui instancie une redirection.
