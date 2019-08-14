---
description: Cette rubrique contient des réponses aux questions fréquentes sur l’utilisation des offres de redirection lors de l’utilisation d’Analytics comme source de création de rapports pour Target (A4T).
keywords: faq;questions fréquentes;analytics for target;a4T;redirection;offres de redirection;adobe-mc-sdid;adobe_mc_ref
seo-description: Cette rubrique contient des réponses aux questions fréquentes sur l’utilisation des offres de redirection lors de l’utilisation d’Analytics comme source de création de rapports pour Target (A4T).
seo-title: FAQ sur les offres de redirection - A4T
solution: Target
title: FAQ sur les offres de redirection - A4T
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
translation-type: tm+mt
source-git-commit: b75b6463aa278505ae4f75d43f56f9bfa6313ede

---


# FAQ sur les offres de redirection - A4T{#redirect-offers-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur l’utilisation des offres de redirection lors de l’utilisation d’Analytics comme source de création de rapports pour Target (A4T).

## Analytics for Target (A4T) prend-il en charge les offres de redirection ?{#section_46B8B03ED4D542C6AD875F5F61176298}

Oui, si vous utilisez [!DNL at.js] dans votre mise en œuvre. Toutefois, votre implémentation doit respecter la configuration minimale requise ci-dessous pour utiliser les offres [de redirection](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) dans les activités qui utilisent Analytics comme source de création de rapports.

>[!NOTE]
>
>Une sortie de problèmes connue qui entraîne un nombre limité de clients utilisant des redirections avec A 4 T pour afficher un pourcentage plus élevé de taux d'accès désassemblés. See [Known issues and resolved issues](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Quelles sont les conditions prélables requises pour utiliser les offres de redirection avec A4T ?{#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Votre mise en œuvre doit satisfaire aux exigences minimales suivantes :

* Service d’identification des visiteurs d’Experience Cloud : [!DNL visitorAPI.js] version 2.3.0 ou ultérieure.
* Adobe Analytics : [!DNL appMeasurement.js] version 2.1.
* Adobe Target : [!DNL at.js] version 1.6.2 ou ultérieure.

   La bibliothèque [!DNL mbox.js] ne prend pas en charge les offres de redirection avec A4T. Votre implémentation doit utiliser [!DNL at.js].

Les trois bibliothèques doivent être incluses sur la page comportant l’offre de redirection et sur la page vers laquelle est redirigé le visiteur.

## Pourquoi y a-t-il parfois des incohérences de données entre A4T et Analytics ?

Certaines incohérences de données sont attendues. Pour plus d’informations, voir [Écarts de données attendus entre Target et Analytics lors de l’utilisation ou de la non-utilisation de A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

## Pourquoi les pages vues sont-elles parfois comptabilisées sur la page originale et la page de redirection ? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

Ce n'est pas un problème lorsque vous utilisez at. js version 1.6.3 ou ultérieure. Cette situation de concurrence affecte uniquement les clients qui utilisent des versions antérieures. L'équipe Target gère deux versions d'at. js : la version actuelle et la deuxième version. Upgrade at.js as necessary to ensure that you are running a [supported version](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Si vous utilisez une version antérieure non prise en charge d'at. js, il est possible qu'une condition de concurrence puisse se produire et que l'appel Analytics se déclenche avant que la redirection ne s'exécute sur la première page. Le cas échéant, les pages vues sur la page originale et la page de redirection peuvent toutes être comptabilisées. Cette situation entraîne la comptabilisation d’une page vue supplémentaire sur la première page, bien que le visiteur ne l’ait jamais véritablement consultée.

Il est recommandé d’utiliser le compositeur basé sur les formulaires pour créer une activité de redirection afin d’accélérer la redirection de la page. Cela est dû à l’emplacement d’exécution du code sur la page. Il est également recommandé de créer une offre de redirection pour chaque expérience où la redirection renvoie la page originale, y compris l’expérience par défaut. De cette façon, si une erreur de comptabilisation survient, elle se produit sur toutes les expériences et n’invalide donc pas les rapports et l’analyse pour ce test.

La raison pour laquelle vous souhaitez utiliser des offres de redirection pour toutes les expériences de l'activité, y compris l'expérience par défaut (contrôle), consiste à mettre les mêmes conditions sur toutes les expériences. Par exemple, si l'expérience par défaut ne dispose pas d'offre de redirection, mais que les autres expériences comportent des offres de redirection, la vitesse de l'expérience sans l'offre de redirection présente un avantage inhérent. Les offres de redirection sont recommandées pour des scénarios temporaires uniquement, comme les tests. Les offres de redirection ne sont pas recommandées pour les scénarios permanents, tels que la personnalisation. Après avoir déterminé le « gagnant », vous devez supprimer la redirection pour améliorer les performances de chargement des pages.

For more information about this issue, see the "Redirect offers" information in [Known Issues](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Puis-je utiliser les offres de redirection avec A4T si j’utilise la bibliothèque JavaScript mbox.js ?{#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

La bibliothèque [!DNL mbox.js] ne prend pas en charge les offres de redirection avec A4T. Votre implémentation doit utiliser [!DNL at.js].

## Le compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires sont-ils tous les deux pris en charge ?{#section_FDA26FE7909B48539DA770559E687677}

Oui, les deux compositeurs sont pris en charge du moment que vous utilisez les offres de redirection intégrées.

Si vous utilisez votre propre code personnalisé pour la redirection, vous devez vous assurer de générer les deux nouveaux paramètres associés aux URL de redirection (`adobe_mc_sdid` et `adobe_mc_ref`, tel qu’expliqué ci-dessus).

## Quels sont les nouveaux paramètres de chaîne de requête ajoutés aux URL de redirection ?{#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Les paramètres de chaîne de requête suivants sont associés aux offres de redirection :

| Paramètre | Description |
|--- |--- |
| `adobe_mc_sdid` | Le paramètre `adobe_mc_sdid` transfère l’ID de données supplémentaire (SDID) et l’ID Experience Cloud Org de la page par défaut vers la nouvelle page afin que A4T « relie » la requête Target de la page par défaut à la requête Analytics de la nouvelle page. |
| `adobe_mc_ref` | Le paramètre `adobe_mc_ref` transfère l’URL de référence de la page par défaut vers la nouvelle page. Lorsque vous l’utilisez avec AppMeasurement.js version 2.1 (ou ultérieure), Analytics utilise la valeur de ce paramètre comme URL de référence de la nouvelle page. |

Ces paramètres sont automatiquement ajoutés aux URL de redirection lorsque vous utilisez les offres de redirection intégrées dans le compositeur d’expérience visuelle et le compositeur d’expérience d’après les formulaires, lorsque le service Identifiant visiteur est mis en œuvre dans la page. Si vous utilisez votre propre code de redirection personnalisé dans le compositeur d’expérience visuelle ou le compositeur d’expérience d’après les formulaires, vous devez vous assurer de transférer ces paramètres avec votre code personnalisé.

## Mes serveurs web retirent ces paramètres de mes URL. Que dois-je faire ? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Vous devez demander à votre équipe informatique de mettre ces paramètres (`adobe_mc_sdid` et `adobe_mc_ref`) sur liste blanche.

## Que puis-je faire si je n’utilise pas A4T avec mon activité de redirection et que je ne souhaite pas que ces paramètres supplémentaires s’ajoutent à mes URL ?{#section_9E608D75FF9349FE96C65FEDD7539F45}

Si vous n’utilisez pas A4T avec votre activité de redirection, que le service Identifiant visiteur est mis en œuvre et que vous ne souhaitez pas que ces paramètres soient automatiquement ajoutés à vos URL, vous devez utiliser une redirection personnalisée.

Cependant, il est recommandé de conserver le paramètre `adobe_mc_ref` dans l’URL pour signaler correctement les informations référentes à [!DNL Analytics].

## Pourquoi les paramètres adobe_mc_ref and adobe_mc_sdid comportent-ils un codage URL double dans mon implémentation ?{#section_5EFE5F012B944C40865731EA18E7E79E}

Si vous utilisez A4T et que vous redirigez des offres, Target ajoute les paramètres `adobe_mc_ref` et `adobe_mc_sdid` à l’URL. Ces valeurs sont déjà en codage URL. La plupart du temps, tout fonctionne comme prévu, mais certains clients peuvent avoir des équilibrages de charge ou des serveurs Web qui tentent de coder à nouveau les paramètres de la chaîne de requête.

En raison de ce double codage, lorsque l’API visiteur tente de décoder la valeur `adobe_mc_sdid`, elle ne parvient pas à extraire le SDID et en génère un nouveau. Des valeurs de SDID incorrectes sont alors envoyées à Target et à Analytics, donnant lieu à un fractionnement inégal des redirections dans les rapports Analytics.

Dans ce cas, nous vous recommandons de discuter avec leur équipe informatique pour vous assurer que les paramètres `adobe_mc_ref` et `adobe_mc_sdid` sont sur liste blanche afin que ces valeurs ne soient jamais transformées.

## Pourquoi l’URL de référence doit être transférée à la page suivante ?{#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Supposons qu’un visiteur clique sur un lien sur [!DNL `www.google.com`] pointant vers votre page d’accueil ([!DNL `www.mysite.com/index.html]`), sur laquelle une activité de redirection a lieu. Il est donc redirigé vers une nouvelle page ([!DNL `www.mysite.com/index2.html`]).

Auparavant, la requête [!DNL Analytics] sur la nouvelle page signalait l’URL de référence [!DNL `www.mysite.com/index.html`] au lieu de [!DNL `www.google.com`]. Dans [!DNL Analytics], cela générait des rapports inexacts concernant les URL de référence (dans les rapports sur les canaux marketing, par exemple). Les rapports manquaient la véritable provenance du visiteur, c’est-à-dire [!DNL `www.google.com`].

Avec [!DNL at.js] version 0.9.6 (ou ultérieure) et [!DNL AppMeasurement.js] 2.1 (ou version ultérieure), la requête [!DNL Analytics] de la nouvelle page signale l’URL référente [!DNL `www.google.com`].

## Puis-je utiliser des offres de redirection/HTML personnalisées ?{#section_E49F9A83A286488C8F1098A040203D7E}

Non, vous devez utiliser une offre de redirection intégrée pour les activités qui utilisent [!DNL Analytics] comme source des rapports (A4T). Pour [!DNL Target], les offres HTML sont opaques : [!DNL Target] ne peut pas savoir si un code HTML spécifique contient le code JavaScript qui instancie une redirection.
