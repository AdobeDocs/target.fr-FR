---
keywords: déboguer mbox;dépannage mbox;problèmes mbox;scintillement;mboxDebug;mboxTrace;jeton;débogueur;priorité;priorité d’activité;débogueur Adobe Experience Cloud;orderConfirmPage mbox;SiteCatalyst;acheter mbox;meilleure vente
description: Obtenez des suggestions pour résoudre les problèmes si votre page n’affiche pas le contenu attendu. Découvrez comment déboguer la diffusion de contenu dans Adobe Target.
title: Comment puis-je résoudre les problèmes liés à la diffusion de contenu ?
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
TQID: 'https://experienceleague.adobe.com/nkaoqcuoqMm67AnEjSg6dCnFDy-jvlwvD1a6YeXTkwk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 22dff18ca8369805557788d62c4eaf09f9764494
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 55%
---
# Résolution des problèmes liés à la diffusion de contenu {#content-trouble}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment déboguer la diffusion de contenu dans [!DNL Adobe Target] lorsque votre page n’affiche pas le contenu attendu.

>[!ENDSHADEBOX]

Lorsqu’une page n’affiche pas le contenu attendu, la cause peut être une erreur dans le code d’activité, une requête [!DNL Target] manquante ou mal placée, ou un conflit avec une autre activité. Vérifiez soigneusement le code de votre activité ou de votre campagne, car une faute de frappe ou une autre erreur peut empêcher l’affichage du contenu attendu. Utilisez ensuite mboxTrace, mboxDebug ou Adobe Experience Cloud Debugger pour examiner la requête [!DNL Target].

**mboxDebug** est particulièrement utile lorsque vous configurez [!DNL Target] sur votre page, pour vous assurer que la requête [!DNL Target] se déclenche et que le cookie est défini. Cependant, il n’entre pas dans les détails utiles au débogage de la diffusion de contenu. Si votre activité ne s’affiche pas sur la page ou qu’un contenu indésirable s’affiche, utilisez mboxTrace pour examiner et déboguer la page en détail.

## Outils de débogage {#debugging-tools}

### Récupérer le jeton d’autorisation {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace et mboxDebug pouvant exposer les données de campagne et de profil à des tiers externes, un jeton d’autorisation est nécessaire. Le jeton d’autorisation peut être récupéré dans l’interface utilisateur de [!DNL Target]. Le jeton est valide pendant six heures.

Vous devez disposer de l’une des autorisations utilisateur suivantes pour générer un jeton d’authentification :

* Autorisation au moins **[!UICONTROL Éditeur]** (ou **[!UICONTROL Approbateur]**)

  Pour plus d’informations concernant les clients [!DNL Target Standard], consultez [Spécifier les rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*. Pour plus d’informations concernant les clients [!DNL Target Premium], consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Rôle d’administrateur au niveau de l’espace de travail/du profil de produit

  Les espaces de travail sont disponibles uniquement pour les clients [!DNL Target Premium]. Pour plus d’informations, consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Droits d’administrateur (autorisation Sysadmin) au niveau du produit [!DNL Adobe Target]

Pour récupérer le jeton d’autorisation :

1. Accédez À **[!UICONTROL Administration]** > **[!UICONTROL Implémentation]**.
1. Dans la section Outils du débogueur, cliquez sur **[!UICONTROL Générer un nouveau jeton d’authentification]**.

   ![Générer un nouveau jeton d’authentification](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Ajoutez le jeton généré en tant que paramètre de votre URL pour activer l’un des outils de débogage avancé.

   ![Jeton d’autorisation](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

### mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace vous permet de recevoir des informations de suivi jointes aux réponses de [!DNL Target]. Les informations de suivi reflètent le résultat d’un appel [!DNL Target] (par exemple, une conversion ou une impression) ainsi que toute donnée supplémentaire qui peut permettre de déterminer pour quelles raisons ce résultat spécifique a été obtenu, par exemple un jeu de branches disponibles parmi lesquelles la sélection a été effectuée dans une campagne. Utilisez ces informations pour déboguer la diffusion du contenu.

Les paramètres suivants sont disponibles :

| Options mboxTrace | Résultat |
|--- |--- |
| `?mboxTrace=console` | Imprime dans le journal de la console sous la forme d’objets.<br>Pour at.js, plutôt que dʼafficher une nouvelle fenêtre de navigation ou de générer une sortie dans la console comme cʼétait le cas dans mbox.js (aujourd’hui obsolète), vous devez inspecter la requête réseau et rechercher sous Aperçu (Chrome) ou Réponse (Firefox). |
| `?mboxTrace=json` | Imprime dans le journal de la console sous la forme d’une chaîne JSON littérale |
| `?mboxTrace=window` | Imprime dans une fenêtre contextuelle sous la forme d’une chaîne JSON |
| `?mboxTrace=disable` | Désactive le mode de session de suivi |

**Exemple d’un appel mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

Le résultat présente des informations détaillées sur le contenu. mboxTrace affiche les détails de votre campagne ou activité et de votre profil. Il fournit également un instantané du profil avant l’exécution et un instantané de ce qui a changé après l’exécution. mboxTrace affiche également les campagnes ou les activités qui ont été évaluées pour chaque emplacement.

Certaines des informations incluent des segments correspondants et non correspondants et des ID cibles :

* **SegmentId** : ID des segments, provenant de la bibliothèque des segments réutilisables ou segments anonymes créés pour la campagne spécifique.
* **TargetId** : ID des cibles, provenant de la bibliothèque des expressions cibles ou cibles anonymes créées pour tout segment de la campagne.
* **Unmatched** : la demande n’a pas abouti dans cet appel pour les segments ou les cibles.
* **Matched** : la demande a abouti pour les segments ou les cibles spécifiées.

**Utilisation de mboxTrace sur les pages de recommandations** : l’ajout de mboxTrace en tant que paramètre de requête sur les pages comportant des recommandations remplace la conception Recommendations sur la page par une fenêtre de détails de mboxTrace, qui présente des informations détaillées sur vos recommandations, notamment :

* Les recommandations renvoyées par rapport aux recommandations demandées
* La clé utilisée et si elle génère des recommandations
* Les recommandations générées par des critères par rapport aux recommandations de sauvegarde
* La configuration des critères
* Les exclusions et inclusions appliquées
* Les règles de collection

Vous n’avez pas besoin d’inclure `=console`, `=json` ou `=window` dans le paramètre de requête. Une fois les détails mboxTrace terminés, ajoutez `=disable` et appuyez sur **[!UICONTROL Entrée]** pour revenir au mode d’affichage normal.

mboxTrace n’a aucun impact sur le fonctionnement et l’aspect de votre site. Les visiteurs visualisent la conception habituelle de Recommandations.

### mboxDebug {#mboxdebug}

Pour utiliser mboxDebug, ajoutez un paramètre mboxDebug à la fin de votre URL. Le tableau suivant contient des informations sur les paramètres d’URL liés à la réponse [!DNL Target].

Notez que certains paramètres mboxDebug sont disponibles avec ou sans authentification.

| Paramètres d’URL | Objectif |
|--- |--- |
| `mboxDebug=1` | Débogueur<br>Si vous ajoutez ce paramètre à une URL avec des requêtes Target définies, une fenêtre pop-up contenant des informations importantes sur le débogage s’affiche. Les informations de cookie ainsi que les valeurs PCid et ID de session sont écrites et toutes les URL sont visibles. Cliquez sur une URL de requête Target pour afficher la réponse de cette requête [!DNL Target]. Pour plus d’informations, reportez-vous au fichier [mbox_debug.pdf](/help/main/assets/mbox_debug.pdf). |
| `mboxDisable=1` | Désactivation des mbox dans la page |
| `mboxOverride.browserIp=<Insert IP address>` | Test de géociblage<br>Effectuez un test de géociblage avec ce paramètre d’URL. Saisissez une adresse IP comme valeur pour cet attribut. Le géociblage [!DNL Target] évalue cette adresse IP pour la comparer à tout autre géociblage ou ensemble de segmentation dans une campagne. |

>[!NOTE]
>
>Assurez-vous que le fragment d’URL figure après les paramètres de chaîne de requête. Tout ce qui suit le premier `#` est un identifiant de fragment et entraîne le mauvais fonctionnement des paramètres de débogage.

### Débogueur Adobe Experience Cloud {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger vous aide à comprendre votre implémentation [!DNL Target]. Vous pouvez afficher la configuration de votre bibliothèque, vérifier que vos paramètres personnalisés sont correctement transmis, activer la journalisation de la console et désactiver toutes les requêtes [!DNL Target]. Une fois authentifié dans Experience Cloud, vous pouvez utiliser mboxTrace pour inspecter vos qualifications d’activité et d’audience ainsi que votre profil de visiteur.

Pour plus d’informations, consultez les [vidéos de formation](#training-videos) à la fin de cette page et [Déboguer at.js à l’aide du débogueur Adobe Experience Cloud](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/target-debugging-atjs.html){target=_blank}.

## Problèmes courants {#common-problems}

+++ Les meilleurs vendeurs n’apparaissent pas dans Recommandations

L&#39;appel *`SiteCatalyst: purchase`* ne peut pas être utilisé pour les données de trafic de l&#39;algorithme Purchase. Utilisez plutôt l’appel *`orderConfirmPage`*.

+++

</br>

+++ Les activités basées sur des formulaires entrent en conflit avec les activités Target Classic

Les activités basées sur des formulaires créées avec [!DNL Target Standard/Premium] peuvent être en conflit avec les activités créées dans l’interface utilisateur [!DNL Target Classic] qui ont la même priorité et qui utilisent la même requête [!DNL Target]. Pour plus d&#39;informations, voir [Priorité des activités](/help/main/c-activities/priority.md).

+++

</br>

+++ Le cookie [!DNL Target] n’est pas défini

Si votre site comporte un sous-domaine, tel que [!DNL us.domain.com], mais que le cookie [!DNL Target] doit être défini sur [!DNL domain.com] (au lieu de [!DNL us.domain.com]), vous devez remplacer le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=fr){target=_blank}.

+++

</br>

+++ Le contenu scintille ou n’est pas affiché lorsqu’un élément fait également partie de la personnalisation Adobe Experience Manager

Si un élément DOM fait partie du ciblage de personnalisation Adobe Experience Manager (AEM) et d’une activité [!DNL Target], le contenu [!DNL Target] peut scintiller ou ne pas s’afficher.

Pour remédier à cette situation, vous pouvez désactiver la personnalisation AEM sur les pages sur lesquelles s’exécute [!DNL Target].

+++

</br>

+++ Les offres de redirection et distantes ne fonctionnent pas en raison d’une URL non valide

Si l’offre de redirection ou distante utilise une URL non valide, elle risque de ne pas être livrée.

* Pour les offres de redirection, la réponse [!DNL Target] peut contenir `/* invalid redirect offer URL */`.
* Pour les offres distantes, la réponse [!DNL Target] peut contenir `/* invalid remote offer URL */`.

Vous pouvez vérifier la réponse [!DNL Target] dans le navigateur ou à l’aide de mboxTrace. Reportez-vous à [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) pour plus d’informations sur les URL valides.

+++

</br>

+++ [!DNL Target] requêtes ne se déclenchent pas sur mon site

at.js ne déclenche pas les requêtes [!DNL Target] si vous utilisez un type doctype non valide. at.js requiert le doctype HTML 5.

+++

## Activités avec paramètres de chaîne de requête dans l’URL {#query-strings}

L’**[!UICONTROL URL de l’activité]** détermine la page qui qualifie les visiteurs pour l’activité et effectue le rendu des expériences de l’activité aux utilisateurs. Lorsque vous y êtes invité au cours de la création de lʼactivité, la saisie de lʼURL dans son entièreté ne garantit pas toujours que le contenu sera diffusé sur la page du site, en particulier sʼil sʼagit dʼURL contenant des paramètres de chaîne de requête.

Par défaut, le [!UICONTROL compositeur d’expérience visuelle] (VEC) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez également spécifier une autre page au cours de la création de lʼactivité.

Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle, cliquez sur **[!UICONTROL Configurer l’icône d’engrenage]** > sélectionnez **[!UICONTROL Diffusion de la page]** > puis spécifiez l’URL de votre choix dans le champ **[!UICONTROL URL de l’activité]**.

![Configuration de lʼinterface utilisateur des paramètres de Diffusion de page](assets/configure-page-delivery.png)

Lorsque l’URL contient des paramètres de chaîne de requête, la page peut ne pas être qualifiée pour l’activité ou afficher le contenu personnalisé. Quelle que soit votre audience ciblée, vous pouvez inclure des règles de modèle en plus de l’URL de base pour définir vos paramètres de requête.

Les options suivantes peuvent être utilisées pour inclure des règles de modèle supplémentaires :

* **Option 1:** Répliquez l&#39;URL et conservez-la dans la règle de modèle avec l&#39;option « contains »

  +++ Afficher le paramétrage des règles de modèle

  Cette option garantit que lʼURL qualifie pour lʼactivité, mais vous devez être conscient quʼelle risque dʼinfluencer vos données de rapport en ajoutant des enregistrements supplémentaires aux URL qui contiennent lʼURL de base.

  Dans ce scénario, lʼURL est `https://shopping.mycart.com?type=Summers%20Offers` et la règle de modèle supplémentaire « contient » la même URL, séparée par un opérateur OU :

  ![Réplication de lʼURL dans les règles de modèle](assets/option1.png)

  +++

* **Option 2:** Restreignez la condition d&#39;URL « contains » uniquement avec la chaîne de requête

  +++ Afficher le paramétrage des règles de modèle

  Le risque abordé dans lʼoption précédente est également présent ici. Toutefois, la configuration conditionnelle est désormais uniquement limitée à la chaîne de requête.

  Dans ce scénario, lʼURL est `https://shopping.mycart.com?type=Summers%20Offers` et la règle de modèle supplémentaire « contient » uniquement la chaîne de requête, séparée par un opérateur OU :

  ![La règle de modèle contient uniquement la chaîne de requête](assets/option2.png)

  +++

* **Option 3 :** Au lieu de cibler l’URL complète, utilisez une partie spécifique de l’URL

  +++ Afficher le paramétrage des règles de modèle

  Dans ce scénario, l’URL est `https://shopping.mycart.com?type=Summers%20Offers` et les règles de modèle supplémentaires spécifient une **[!UICONTROL requête]** avec **[!UICONTROL type]** > **[!UICONTROL is (sensible à la casse)]** > type=Summers%20Offers, séparés par un opérateur OR :

  ![Règle de modèle se limitant à une partie spécifique de lʼURL](assets/option3.png)

  +++

## Échappement des guillemets doubles dans les valeurs d’attribut de profil {#escape}

Lorsque vous envoyez des valeurs contenant des guillemets doubles dans un attribut de profil [!DNL Target], vous devez double échappement, comme illustré ci-dessous.

```
adobe.target.trackEvent({
    "mbox": "data-collection",
    "params":    {
        "profile.tagLine": "Escape \\\"Double Quotes\\\" like this."
    }
});
```

## Vidéos de formation {#training-videos}

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Ajouter l’extension ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Débogage de base d’Adobe Target ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
