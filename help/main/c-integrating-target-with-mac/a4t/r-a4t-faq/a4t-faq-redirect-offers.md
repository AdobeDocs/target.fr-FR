---
keywords: faq;questions fréquentes;analytics for target;a4T;redirection;offres de redirection;adobe-mc-sdid;adobe_mc_ref
description: Trouvez des réponses aux questions sur l’utilisation des offres de redirection lors de l’utilisation d’Analytics for [!DNL Target] (A4T). A4T vous permet d’utiliser la création de rapports Analytics pour les activités  [!DNL Target] .
title: Où puis-je trouver des questions fréquentes sur les offres de redirection avec A4T ?
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: bb41de751246a77e71e65c11f020bc39f3105da6
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 50%

---

# FAQ sur les offres de redirection - A4T

Cette rubrique contient les réponses aux questions fréquentes sur l’utilisation des offres de redirection lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Analytics for Adobe Target (A4T) prend-il en charge les offres de redirection ? {#section_46B8B03ED4D542C6AD875F5F61176298}

+++Réponse
Oui, si votre implémentation utilise [!DNL at.js]. Toutefois, votre implémentation doit respecter la configuration minimale requise ci-dessous pour utiliser les offres [de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) dans les activités qui utilisent Analytics comme source de création de rapports.

+++

## ![Badge Adobe Experience Platform Web SDK &#x200B;](/help/main/assets/platform.png) le [!DNL Adobe Experience Platform Web SDK] prend-il en charge les offres de redirection pour A4T ? {#platform}

+++Réponse
Les questions fréquentes suivantes fournissent des informations supplémentaires sur l’utilisation d’A4T et sur les offres de redirection avec l’[!DNL Platform Web SDK] .

+++

### Analytics for Target (A4T) prend-il en charge les offres de redirection ?

+++Réponse
Oui, A4T via Platform Web SDK prend en charge les [offres de redirection](/help/main/c-experiences/c-manage-content/offer-redirect.md).

+++

### Le [!UICONTROL Visual Experience Composer] (compositeur d’expérience visuelle) et le [!UICONTROL Form-Based Experience Composer] sont-ils pris en charge ?

+++Réponse
Oui, le [[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) et le [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) sont pris en charge si vous utilisez des offres de redirection intégrées.

+++

## Quelles sont les exigences minimales pour utiliser les offres de redirection avec A4T ? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++Réponse
Votre mise en œuvre doit satisfaire aux exigences minimales suivantes :

* Service d’identification des visiteurs d’Experience Cloud : [!DNL visitorAPI.js] version 2.3.0 ou ultérieure.
* Adobe Analytics : [!DNL appMeasurement.js] version 2.1.
* Adobe Target : [!DNL at.js] version 1.6.2 ou ultérieure.

Les trois bibliothèques doivent être incluses sur la page comportant l’offre de redirection et sur la page vers laquelle est redirigé le visiteur.

+++

## Pourquoi y a-t-il parfois des incohérences de données entre A4T et Analytics ?

+++Réponse
Certaines incohérences de données sont attendues. Pour plus d’informations, voir [Écarts de données attendus entre Target et Analytics lors de l’utilisation ou de la non-utilisation de A4T](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

+++

## Comment puis-je réduire les incohérences de distribution du trafic lors de l’utilisation des offres de redirection dans les activités A4T ? {#discrepancies}

+++Réponse
Un nombre limité de clients ont signalé des degrés de variance plus élevés dans la distribution du trafic lors de l’utilisation d’offres de redirection dans les activités configurées avec [!UICONTROL Analytics for Target] (A4T).

Tenez compte des points suivants :

* Un ordre incorrect des appels de [!DNL Target] et de [!DNL Analytics] peut être responsable de degrés de variance plus élevés.

  L’appel [!DNL Target] doit précéder l’appel [!DNL Analytics] sur la page source (où la redirection se produit) et sur la page de destination (où la redirection se termine).

* Veillez à utiliser les offres de redirection dans les activités de redirection A4T.
* S’il existe plusieurs demandes d’emplacement [!DNL Target] sur la page source (où la redirection se produit), [!DNL Adobe] vous recommande d’exécuter l’activité de redirection sur la première demande d’emplacement [!DNL Target].

  L’exécution de l’activité de redirection sur la première demande d’emplacement [!DNL Target] réduit les chances qu’une qualification d’activité se produise sur d’autres demandes d’emplacement [!DNL Target] et soit comptabilisée dans le rapport. Les visiteurs redirigés ne doivent pas être comptabilisés dans les rapports d’autres activités, car ils ne verront pas les expériences.

+++

## Pourquoi les pages vues sont-elles parfois comptabilisées sur la page originale et la page de redirection ? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++Réponse
Lors de l’utilisation de la version 1.6.3 ou ultérieure d’at.js, le comptage des pages vues sur les deux pages ne pose pas de problème. Cette situation de concurrence affecte uniquement les clients qui utilisent des versions antérieures. L’équipe Target gère deux versions seulement d’at.js : la version actuelle et la version la plus récente avant celle-ci. Mettez à jour at.js si nécessaire pour vous assurer que vous utilisez une [version prise en charge](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank}.

Si vous utilisez une version antérieure d’at.js non prise en charge, il est possible qu’une condition de concurrence puisse se produire et que l’appel Analytics se déclenche avant que la redirection ne s’exécute sur la première page. Cette situation peut entraîner le comptage de toutes les pages vues sur la page d’origine et sur la page de redirection. Cette situation entraîne la comptabilisation d’une page vue supplémentaire sur la première page, bien que le visiteur ne l’ait jamais véritablement consultée.

Il est recommandé d’utiliser le compositeur basé sur les formulaires pour créer une activité de redirection afin d’augmenter la vitesse de la redirection de la page en raison de l’emplacement d’exécution du code sur la page. Il est également recommandé de créer une offre de redirection pour chaque expérience où la redirection renvoie la page originale, y compris l’expérience par défaut. La création d’une offre de redirection pour chaque expérience garantit que si un comptage incorrect se produit, celui-ci se produit pour toutes les expériences. Les rapports et analyses sont toujours valides pour le test.

L’utilisation des offres de redirection pour toutes les expériences de l’activité, y compris l’expérience par défaut (contrôle), permet de mettre les mêmes conditions sur toutes les expériences. Par exemple, si l’expérience par défaut ne comporte pas d’offre de redirection alors que les autres en ont, la vitesse de l’expérience sans offre de redirection présente un avantage inhérent. Les offres de redirection sont recommandées pour des scénarios temporaires uniquement, comme les tests. Les offres de redirection ne sont pas recommandées pour les scénarios permanents tels que la personnalisation. Après avoir déterminé le « gagnant », vous devez supprimer la redirection pour améliorer les performances de chargement de la page.

+++

## Le compositeur d’expérience visuelle (VEC) et le compositeur d’expérience d’après les formulaires sont-ils tous les deux pris en charge ? {#section_FDA26FE7909B48539DA770559E687677}

+++Réponse
Oui, les deux compositeurs sont pris en charge du moment que vous utilisez les offres de redirection intégrées.

Si vous utilisez votre propre code personnalisé pour la redirection, vous devez vous assurer de générer les deux nouveaux paramètres associés aux URL de redirection (`adobe_mc_sdid` et `adobe_mc_ref`, tel qu’expliqué ci-dessus).

+++

## Quels sont les nouveaux paramètres de chaîne de requête ajoutés aux URL de redirection ? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++Réponse
Les paramètres de chaîne de requête suivants sont associés aux offres de redirection :

| Paramètre | Description |
|--- |--- |
| `adobe_mc_sdid` | Le paramètre `adobe_mc_sdid` transmet le SDID (Supplemental Data Id) et l’ID d’organisation Experience Cloud de la page par défaut à la nouvelle page. Ces identifiants permettent à A4T d’« assembler » la requête Target sur la page par défaut avec la requête Analytics sur la nouvelle page.<br>Le format attendu pour transmettre le SDID dans l’URL (pour les applications hybrides ou d’une application au site Web ou d’un site Web à un autre) est `ex. adobe_mc_sdid=SDID=123|MCORGID=123456789@AdobeOrg|TS=1498569322` |
| `adobe_mc_ref` | Le paramètre `adobe_mc_ref` transfère l’URL de référence de la page par défaut vers la nouvelle page. Utilisé avec AppMeasurement.js version 2.1 (ou ultérieure), Analytics utilise cette valeur de paramètre comme URL de référence sur la nouvelle page. |

Ces paramètres sont automatiquement ajoutés aux URL de redirection lorsque vous utilisez les offres de redirection intégrées dans le compositeur d’expérience visuelle et le compositeur d’expérience d’après les formulaires, lorsque le service Identifiant visiteur est mis en œuvre dans la page. Si vous utilisez votre propre code de redirection personnalisé dans le compositeur d’expérience visuelle ou le compositeur d’expérience d’après les formulaires, vous devez vous assurer de transférer ces paramètres avec votre code personnalisé.

+++

## Mes serveurs web retirent ces paramètres de mes URL. Que dois-je faire ? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++Réponse
Demandez à votre équipe informatique de placer sur la liste autorisée ces paramètres ( `adobe_mc_sdid` et `adobe_mc_ref`).

+++

## Que puis-je faire si je n’utilise pas A4T avec mon activité de redirection et que je ne souhaite pas que ces paramètres supplémentaires s’ajoutent à mes URL ? {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++Réponse
Utilisez une redirection codée sur mesure si :

* Vous n’utilisez pas A4T avec votre activité de redirection
* Le service d’identification des visiteurs est implémenté
* Vous ne souhaitez pas que ces paramètres soient automatiquement ajoutés à vos URL

Cependant, il est recommandé de conserver le paramètre `adobe_mc_ref` dans l’URL pour signaler correctement les informations référentes à [!DNL Analytics].

+++

## Pourquoi les paramètres adobe_mc_ref et adobe_mc_sdid sont-ils codés en double URL dans mon implémentation ? {#section_5EFE5F012B944C40865731EA18E7E79E}

+++Réponse
Si vous utilisez A4T et que vous redirigez des offres, Target ajoute les paramètres `adobe_mc_ref` et `adobe_mc_sdid` à l’URL. Ces valeurs sont déjà en codage URL. La plupart du temps, tout fonctionne comme prévu, mais certains clients peuvent avoir des équilibrages de charge ou des serveurs Web qui tentent de coder à nouveau les paramètres de la chaîne de requête.

En raison de ce double codage, lorsque l’API visiteur tente de décoder la valeur `adobe_mc_sdid`, elle ne parvient pas à extraire le SDID et en génère un nouveau. Ce processus entraîne l’envoi de valeurs SDID incorrectes à Target et Analytics et une répartition inégale des redirections s’affiche dans les rapports Analytics.

Adobe placer sur la liste autorisée vous recommande de consulter votre équipe informatique pour vous assurer que les `adobe_mc_ref` et les `adobe_mc_sdid` sont traités de manière à ce que ces valeurs ne soient en aucun cas transformées.

+++

## Pourquoi l’URL de référence doit-elle être transmise à la nouvelle page ? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++Réponse
Supposons qu’un visiteur clique sur un lien [!DNL `www.google.com`] vers votre page d’accueil (`www.mysite.com/index.html`) sur laquelle une activité de redirection est active, puis qu’il soit redirigé vers une nouvelle page (`www.mysite.com/index2.html`).

Auparavant, la requête [!DNL Analytics] sur la nouvelle page signalait une URL de référence de [!DNL `www.mysite.com/index.html`] au lieu de [!DNL `www.google.com`]. Dans [!DNL Analytics], cela générait des rapports inexacts concernant les URL de référence (dans les rapports sur les canaux marketing, par exemple). Les rapports avaient perdu le fait que vous êtes venu sur le site de [!DNL `www.google.com`].

Avec [!DNL at.js] version 0.9.6 (ou ultérieure) et [!DNL AppMeasurement.js] 2.1 (ou ultérieure), la requête [!DNL Analytics] sur la nouvelle page signale une URL de référence de [!DNL `www.google.com`].

+++

## Puis-je utiliser des offres de redirection/HTML personnalisées ? {#section_E49F9A83A286488C8F1098A040203D7E}

+++Réponse
Non, vous devez utiliser une offre de redirection intégrée pour les activités qui utilisent [!DNL Analytics] comme source des rapports (A4T). Pour [!DNL Target], les offres HTML sont opaques : [!DNL Target] ne peut pas savoir si un code HTML spécifique contient le code JavaScript qui instancie une redirection.

+++

### Puis-je utiliser des offres de redirection personnalisées/HTML avec le [!DNL Platform Web SDK] ?

+++Réponse
Non, vous devez utiliser une offre de redirection intégrée pour les activités qui utilisent A4T. Du point de vue [!DNL Target], les offres d’HTML sont opaques. [!DNL Target] ne pouvez pas savoir qu’un élément particulier d’HTML contient JavaScript qui instancie une redirection.

+++
