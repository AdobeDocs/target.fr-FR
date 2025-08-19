---
keywords: déboguer mbox;dépannage mbox;problèmes mbox;scintillement;mboxDebug;mboxTrace;jeton;débogueur;priorité;priorité d’activité;débogueur Adobe Experience Cloud;orderConfirmPage mbox;SiteCatalyst;acheter mbox;meilleure vente
description: Obtenez des suggestions pour résoudre les problèmes si votre page n’affiche pas le contenu attendu. Découvrez comment déboguer la diffusion de contenu dans Adobe Target.
title: Comment puis-je résoudre les problèmes liés à la diffusion de contenu ?
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 89%

---

# Résolution des problèmes liés à la diffusion de contenu

Si votre page n’affiche pas le contenu attendu, quelques étapes permettent de déboguer la diffusion du contenu.

* Vérifiez minutieusement le code de votre activité ou campagne. Une coquille ou d’autres erreurs pourraient empêcher le contenu de s’afficher.
* Utilisez mboxTrace ou mboxDebug pour dépanner la requête [!DNL Target].
* Utilisez le débogueur Adobe Experience Cloud, un outil convivial qui fournit pratiquement les mêmes informations que mboxDebug, pour résoudre les problèmes liés à la requête [!DNL Target].

mboxDebug est tout particulièrement utile lorsque vous configurez [!DNL Target] sur votre page afin de vérifier que la requête Target est déclenchée et que le cookie est défini. Néanmoins, mboxDebug n’entre pas dans le type de détail qui est utile lors du débogage de la diffusion du contenu. Si votre activité ne s’affiche pas sur la page ou qu’un contenu indésirable s’affiche, utilisez mboxTrace pour examiner et déboguer la page en détail.

## Récupérez le jeton d’autorisation à utiliser avec les outils de débogage {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace et mboxDebug pouvant exposer des données de campagne et de profil à des parties externes, un jeton d’autorisation est requis. Le jeton d’autorisation peut être récupéré dans l’interface utilisateur de [!DNL Target]. Le jeton est valide pendant six heures.

Vous devez disposer de l’une des autorisations utilisateur suivantes pour générer un jeton d’authentification :

* Au moins [!UICONTROL Editor] autorisation (ou [!UICONTROL Approver])

  Pour plus d’informations concernant les clients [!DNL Target Standard], consultez [Spécifier les rôles et autorisations](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) dans *Utilisateurs*. Pour plus d’informations concernant les clients [!DNL Target Premium], consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Rôle d’administrateur au niveau de l’espace de travail/du profil de produit

  Les espaces de travail sont disponibles uniquement pour les clients [!DNL Target Premium]. Pour plus d’informations, consultez [Configuration des autorisations d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Droits d’administrateur (autorisation Sysadmin) au niveau du produit [!DNL Adobe Target]

Pour récupérer le jeton d’autorisation :

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Dans la section Outils du débogueur, cliquez sur **[!UICONTROL Generate New Authentication Token]**.

   ![Générer un nouveau jeton d’authentification](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Ajoutez le jeton généré en tant que paramètre de votre URL pour activer l’un des outils de débogage avancé.

   ![Jeton d’autorisation](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

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

Le résultat présente des informations détaillées sur le contenu. mboxTrace affiche des détails sur la campagne ou sur lʼactivité et le profil. Lʼoutil fournit également un instantané du profil avant lʼexécution et un instantané des modifications après lʼexécution. mboxTrace affiche également les campagnes ou les activités qui ont été évaluées pour chaque emplacement.

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

Il n’est pas nécessaire d’inclure `=console`, `=json` ou `=window` dans le paramètre de requête. Lorsque vous avez terminé d’afficher les détails de mboxTrace, ajoutez des `=disable` et appuyez sur **[!UICONTROL Enter]** pour revenir au mode d’affichage normal.

mboxTrace n’a aucun impact sur le fonctionnement et l’aspect de votre site. Les visiteurs visualisent la conception habituelle de Recommendations.

## mboxDebug {#mboxdebug}

Pour utiliser mboxDebug, ajoutez un paramètre mboxDebug à la fin de votre URL. Le tableau suivant contient des informations sur les paramètres d’URL liés à la réponse [!DNL Target].

>[!NOTE]
>
>Certains paramètres mboxDebug sont disponibles avec ou sans authentification.

| Paramètres d’URL | Objectif |
|--- |--- |
| `mboxDebug=1` | Débogueur<br>Si vous ajoutez ce paramètre à une URL avec des requêtes Target définies, une fenêtre pop-up contenant des informations importantes sur le débogage s’affiche. Les informations de cookie ainsi que les valeurs PCid et ID de session sont écrites et toutes les URL sont visibles. Cliquez sur une URL de requête Target pour afficher la réponse de cette requête [!DNL Target]. Pour plus d’informations, reportez-vous au fichier [mbox_debug.pdf](/help/main/assets/mbox_debug.pdf). |
| `mboxDisable=1` | Désactivation des mbox dans la page |
| `mboxOverride.browserIp=<Insert IP address>` | Test de géociblage<br>Effectuez un test de géociblage avec ce paramètre d’URL. Saisissez une adresse IP comme valeur de cet attribut et la fonction de géociblage de Test&amp;Target évalue cette adresse IP par rapport à un géociblage ou à une segmentation défini dans une campagne. |

>[!NOTE]
>
>Assurez-vous que le fragment d’URL figure après les paramètres de chaîne de requête. Tout ce qui suit le premier `#` est un identifiant de fragment et entraîne le mauvais fonctionnement des paramètres de débogage.

## Débogueur Adobe Experience Cloud  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Le débogueur Adobe Experience Cloud vous permet de comprendre rapidement et facilement votre implémentation Target. Vous pouvez afficher rapidement la configuration de votre bibliothèque, examiner les demandes pour vérifier que vos paramètres personnalisés sont transmis correctement, activer la journalisation de la console et désactiver toutes les demandes Target. Authentifiez-vous dans Experience Cloud afin de pouvoir utiliser le puissant outil MboxTrace pour inspecter vos qualifications d’activité et d’audience ainsi que votre profil de visiteur.

Pour plus d’informations, consultez les vidéos de formation ci-dessous :

Pour des informations plus détaillées, consultez [Débogage dʼat.js à lʼaide dʼAdobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/target-debugging-atjs.html){target=_blank}.

## Les meilleurs vendeurs n’apparaissent pas dans Recommendations  {#section_3920C857270A406C80BE6CBAC8221ECD}

L’appel *`SiteCatalyst: purchase`* ne peut pas être utilisé pour les données de trafic de l’algorithme Purchase. Utilisez plutôt l’appel *`orderConfirmPage`*.

## Vérifier la priorité des activités {#section_3D0DD07240F0465BAF655D0804100AED}

Les activités basées sur des formulaires créées avec [!DNL Target Standard/Premium] peuvent être en conflit avec les activités créées dans l’interface utilisateur [!DNL Target Classic] qui ont la même priorité et qui utilisent la même requête [!DNL Target].

## Le code personnalisé ne donne pas les résultats escomptés dans Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target ne prend plus en charge Internet Explorer 8.

## Le cookie Target n’est pas défini {#section_77AFEB541C0B495EB67E29A4475DF960}

Si votre site comporte un sous-domaine, tel que [!DNL us.domain.com], mais que le cookie Target doit être défini sur [!DNL domain.com] (plutôt que [!DNL us.domain.com]), vous devez remplacer le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=fr){target=_blank}.

## Le contenu de Target scintille ou nʼest pas affiché si un élément fait également partie de la personnalisation Adobe Experience Manager. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Si un élément DOM fait partie du ciblage de personnalisation d’Adobe Experience Manager (AEM) et d’une activité Target, le contenu de Target peut scintiller ou ne pas s’afficher.

Pour remédier à cette sitation, vous pouvez désactiver la personnalisation AEM dans les pages qui exécutent Target.

## Les offres de redirection et distantes ne fonctionnent pas en raison d’une URL non valide.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Si l’offre de redirection ou distante utilise une URL non valide, elle risque de ne pas être livrée.

Pour les offres de redirection, la réponse [!DNL Target] peut contenir `/* invalid redirect offer URL */`.

Ou

Pour les offres distantes, la réponse [!DNL Target] peut contenir `/* invalid remote offer URL */`.

Vous pouvez vérifier la réponse [!DNL Target] dans le navigateur ou utiliser mboxTrace. Reportez-vous à [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) pour plus d’informations sur les URL valides.

## [!DNL Target]Les requêtes ne se déclenchent pas sur mon site.

at.js ne déclenche pas les requêtes Target si vous utilisez un type doctype non valide. at.js requiert le doctype HTML 5.

## Assurez-vous que les activités [!DNL Target] gèrent correctement les URL avec des paramètres de chaîne de requête. {#query-strings}

L’[!UICONTROL Activity URL] détermine la page qui qualifie les visiteurs pour l’activité et effectue le rendu des expériences de l’activité aux utilisateurs. Lorsque vous y êtes invité au cours de la création de lʼactivité, la saisie de lʼURL dans son entièreté ne garantit pas toujours que le contenu sera diffusé sur la page du site, en particulier sʼil sʼagit dʼURL contenant des paramètres de chaîne de requête.

Par défaut, le [!UICONTROL Visual Experience Composer] (VEC) ouvre la page spécifiée dans vos [paramètres du compositeur d’expérience visuelle](/help/main/administrating-target/visual-experience-composer-set-up.md). Vous pouvez également spécifier une autre page au cours de la création de lʼactivité.

Pour afficher une autre page après l’ouverture du compositeur d’expérience visuelle, cliquez sur le **[!UICONTROL Configure gear icon]** > sélectionnez **[!UICONTROL Page Delivery]** > puis spécifiez l’URL de votre choix dans le champ [!UICONTROL Activity URL] .

![Configuration de lʼinterface utilisateur des paramètres de Diffusion de page](assets/configure-page-delivery.png)

Mais comment dois-je procéder si lʼURL contient des paramètres de chaîne de requête ? Cette méthode fonctionnera-t-elle et permettra-t-elle dʼafficher le contenu personnalisé ? Dans ce scénario, quelle que soit votre audience ciblée, vous pouvez inclure des règles de modèle en plus de lʼURL de base pour définir vos paramètres de requête.

Les options suivantes peuvent être utilisées pour inclure des règles de modèle supplémentaires :

### Option 1 : répliquez l’URL et conservez-la dans la règle de modèle avec l’option « contient ».

Cette option garantit que lʼURL qualifie pour lʼactivité, mais vous devez être conscient quʼelle risque dʼinfluencer vos données de rapport en ajoutant des enregistrements supplémentaires aux URL qui contiennent lʼURL de base.

Dans ce scénario, lʼURL est `https://shopping.mycart.com?type=Summers%20Offers` et la règle de modèle supplémentaire « contient » la même URL, séparée par un opérateur OU :

![Réplication de lʼURL dans les règles de modèle](assets/option1.png)

### Option 2 : restreindre la condition d’URL « contains » uniquement avec la chaîne de requête.

Le risque abordé dans lʼoption précédente est également présent ici. Toutefois, la configuration conditionnelle est désormais uniquement limitée à la chaîne de requête.

Dans ce scénario, lʼURL est `https://shopping.mycart.com?type=Summers%20Offers` et la règle de modèle supplémentaire « contient » uniquement la chaîne de requête, séparée par un opérateur OU :

![La règle de modèle contient uniquement la chaîne de requête](assets/option2.png)

### Option 3 : au lieu de cibler lʼURL complète, limitez-vous à une portion spécifique de lʼURL.

Dans ce scénario, l’URL est `https://shopping.mycart.com?type=Summers%20Offers` et les règles de modèle supplémentaires spécifient un [!UICONTROL Query] avec [!UICONTROL type] > [!UICONTROL is (case sensitive)] > type=Summers%20Offres, séparé par un opérateur OR :

![Règle de modèle se limitant à une partie spécifique de lʼURL](assets/option3.png)

## L’échappement des guillemets doubles dans [!DNL Target] valeur d’attribut de profil ne fonctionne pas comme prévu. {#escape}

Lorsque vous envoyez des valeurs contenant des guillemets doubles dans un attribut de profil [!DNL Target], vous devez ajouter un double échappement, comme illustré ci-dessous.

```
adobe.target.trackEvent({
    "mbox": "data-collection",
    "params":    {
        "profile.tagLine": "Escape \\\"Double Quotes\\\" like this."
    }
});
```

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Ajoutez l’extension ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Débogage de base d’Adobe Target ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Badge de tutoriel](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
