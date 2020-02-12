---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: Si votre page n’affiche pas le contenu attendu, vous pouvez prendre quelques mesures pour déboguer la diffusion de contenu dans Adobe Target.
title: Résolution des problèmes de diffusion de contenu dans Adobe Target
subtopic: Multivariate Test
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Résolution des problèmes liés à la diffusion de contenu{#troubleshoot-content-delivery}

Si votre page n’affiche pas le contenu attendu, quelques étapes permettent de déboguer la diffusion du contenu.

* Vérifiez minutieusement le code de votre activité ou campagne. Une coquille ou d’autres erreurs pourraient empêcher le contenu de s’afficher.
* Utilisez mboxTrace ou mboxDebug pour dépanner la mbox.
* Utilisez le débogueur Adobe Experience Cloud, un outil convivial qui fournit pratiquement les mêmes informations que mboxDebug, pour résoudre les problèmes liés à la mbox.

mboxDebug est tout particulièrement utile lorsque vous configurez Target sur votre page afin de vérifier que la mbox est déclenchée et que le cookie est défini. Néanmoins, mboxDebug n’entre pas dans le type de détail qui est utile lors du débogage de la diffusion du contenu. Si votre activité ne s’affiche pas sur la page ou qu’un contenu indésirable s’affiche, utilisez mboxTrace pour examiner et déboguer la page en détail.

## Récupération du jeton d’autorisation à utiliser avec les outils de débogage {#section_BED130298E794D1FA229DB7C3358BA54}

mboxTrace et mboxDebug pouvant exposer des données de campagne et de profil à des parties externes, un jeton d’autorisation est requis. Le jeton d’autorisation peut être récupéré dans l’interface utilisateur de [!DNL Target]. Le jeton est valide pendant six heures.

Pour récupérer le jeton d’autorisation :

1. Cliquez sur **[!UICONTROL Configuration]** > **[!UICONTROL Mise en œuvre]**.
1. Sélectionnez **[!UICONTROL mbox.js]** ou **[!UICONTROL at.js]**.
1. Cliquez sur **[!UICONTROL Générer un jeton d’authentification]**.

   ![Générer un jeton d’autorisation](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. Ajoutez le jeton généré en tant que paramètre de votre URL pour activer l’un des outils de débogage avancé.

   ![Jeton d’autorisation](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace vous permet de recevoir des informations de suivi jointes aux réponses de la mbox. Les informations de suivi reflètent le résultat d’un appel de mbox (par exemple, une conversion ou une impression) ainsi que toute donnée supplémentaire qui peut permettre de déterminer pour quelles raisons ce résultat spécifique a été obtenu, par exemple un jeu de branches disponibles parmi lesquelles la sélection a été effectuée dans une campagne. Utilisez ces informations pour déboguer la diffusion du contenu.

Les paramètres suivants sont disponibles :

| Options mboxTrace | Résultat |
|--- |--- |
| `?mboxTrace=console` | Imprime dans le journal de la console sous la forme d’objets.<br>Pour at.js, au lieu d’ouvrir une nouvelle fenêtre de navigateur ou d’afficher les résultats dans la console comme dans mbox.js, vous devrez contrôler la demande de réseau et effectuer une recherche sous Aperçu (Chrome) ou Réponse (Firefox). |
| `?mboxTrace=json` | Imprime dans le journal de la console sous la forme d’une chaîne JSON littérale |
| `?mboxTrace=window` | Imprime dans une fenêtre contextuelle sous la forme d’une chaîne JSON |
| `?mboxTrace=disable` | Désactive le mode de session de suivi. |

**Exemple d’un appel mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

Le résultat présente des informations très détaillées sur le contenu. mboxTrace affiche des détails sur la campagne ou sur l’activité et le profil. mboxTrace fournit également un instantané du profil avant l’exécution et un instantané des modifications après l’exécution. mboxTrace affiche également les campagnes ou les activités qui ont été évaluées pour chaque emplacement.

Certaines des informations incluent des segments correspondants et non correspondants et des ID cibles :

* **SegmentId** : ID des segments, provenant de la bibliothèque des segments réutilisables ou segments anonymes créés pour la campagne spécifique.
* **TargetId** : ID des cibles, provenant de la bibliothèque des expressions cibles ou cibles anonymes créées pour tout segment de la campagne.
* **Unmatched** : la demande n’a pas abouti dans cet appel pour les segments ou les cibles.
* **Matched** : la demande a abouti pour les segments ou les cibles spécifiées.

**Utilisation de mboxTrace sur les pages Recommandations** : l’ajout de mboxTrace en tant que paramètre de requête sur les pages comportant des Recommandations remplace la conception de Recommandations sur la page par une fenêtre de détails de mboxTrace, qui présente des informations détaillées sur vos recommandations, notamment :

* Les recommandations renvoyées par rapport aux recommandations demandées
* La clé utilisée et si elle génère des recommandations
* Les recommandations générées par des critères par rapport aux recommandations de sauvegarde
* La configuration des critères
* Les exclusions et inclusions appliquées
* Les règles de collection

Il n’est pas nécessaire d’inclure `=console`, `=json` ou `=window` dans le paramètre de requête. Lorsque vous avez finalisé le traitement des détails mboxTrace, ajoutez `=disable` et appuyez sur **[!UICONTROL Entrée]** pour revenir au mode d’affichage normal.

mboxTrace n’a aucun impact sur le fonctionnement et l’aspect de votre site. La conception habituelle de Recommandations sera présentée aux visiteurs.

## mboxDebug {#mboxdebug}

Pour utiliser mboxDebug, ajoutez un paramètre mboxDebug à la fin de votre URL. Le tableau suivant contient des informations sur les paramètres d’URL liés à la mbox.

>[!NOTE]
>
>Certains paramètres mboxDebug sont disponibles avec ou sans authentification.

| Paramètres d’URL | Objectif |
|--- |--- |
| `mboxDebug=1` | Debugger<br>Si vous ajoutez ce paramètre à une URL avec des mbox définies, une fenêtre contextuelle contenant des informations importantes sur le débogage s’affiche. Les informations de cookie, ainsi que les valeurs PCid et ID de session sont écrites et toutes les URL des mbox sont visibles. Cliquez sur l’URL d’une mbox pour afficher la réponse de cette mbox. Pour plus d’informations, reportez-vous au fichier [mbox_debug.pdf](/help/assets/mbox_debug.pdf). |
| `mboxDebug=x-cookie` | Modification du cookie |
| `mboxDisable=1` | Désactivation des mbox dans la page |
| `mboxDebug=x-profile` | Affichage des jeux de profils |
| `mboxDebug=x-time` | Affichage du temps de réponse pour chaque requête de mbox |
| `mboxOverride.browserIp=<Insert IP address>` | Test de géociblage<br>Effectuez un test de géociblage avec ce paramètre d’URL. Saisissez une adresse IP comme valeur de cet attribut et la fonction de géociblage de Test&amp;Target évalue cette adresse IP par rapport à un géociblage ou à une segmentation défini dans une campagne. |

>[!NOTE]
>
>Assurez-vous que le fragment d’URL se trouve après les paramètres de chaîne de requête. Tout ce qui suit le premier `#` est un identifiant de fragment et provoque le mauvais fonctionnement des paramètres de débogage.

## Débogueur Adobe Experience Cloud {#section_A2798ED3A431409690A4BE08A1BFCF17}

Le débogueur Adobe Experience Cloud vous permet de comprendre rapidement et facilement votre implémentation Target. Vous pouvez afficher rapidement la configuration de votre bibliothèque, examiner les demandes pour vérifier que vos paramètres personnalisés sont transmis correctement, activer la journalisation de la console et désactiver toutes les demandes Target. Authentifiez-vous dans Experience Cloud afin de pouvoir utiliser le puissant outil Mbox Trace pour inspecter vos qualifications d’activité et d’audience ainsi que votre profil de visiteur.

Pour plus d’informations, consultez les vidéos de formation ci-dessous :

Pour plus d’informations, voir [Débogage d’at.js à l’aide du débogueur](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)Adobe Experience Cloud.

## Si le chargement de target.js échoue au cours de la diffusion {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

Mbox.js envoie un cookie appelé « em-disabled » au visiteur si target.js ne se charge pas au cours de la diffusion. Ce cookie empêche les offres créées en utilisant le compositeur d’expérience visuelle d’effectuer un rendu sur le site. Les visiteurs dotés de ce cookie ne voient pas le contenu du test et ne sont pas comptabilisés dans les rapports d’activité. Tous les autres contenus d’offres (provenant de campagnes dans Target Classic par exemple) continuent à se charger. Le cookie possède une durée de vie de 30 minutes à partir de l’échec du chargement.

## Les meilleurs vendeurs n’apparaissent pas dans Recommandations {#section_3920C857270A406C80BE6CBAC8221ECD}

La mbox *`SIteCatalyst: purchase`* ne peut pas être utilisée pour les données de trafic de l’algorithme Purchase. Utilisez plutôt la mbox *`orderConfirmPage`*.

## Vérifier la priorité des activités {#section_3D0DD07240F0465BAF655D0804100AED}

Les activités basées sur des formulaires créées avec [!DNL Target Standard/Premium] peuvent être en conflit avec les activités créées dans l’interface utilisateur [!DNL Target Classic] qui ont la même priorité et qui utilisent la même mbox.

## Le code personnalisé ne donne pas les résultats escomptés dans Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target ne prend plus en charge Internet Explorer 8.

## Le contenu JavaScript diffusé avec la mbox globale ne charge pas lorsque vous utilisez mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Procédez à la mise à niveau vers [!DNL mbox.js] version 58 ou ultérieure.

Les versions 58 et ultérieures de mbox.js exécutent le contenu non JavaScript pour la mbox globale immédiatement après la balise HTML `BODY`. Le contenu JavaScript situé à l’intérieur des balises `<script>` pour la mbox globale s’exécute après le déclenchement de l’événement `DOMContentLoaded`. Cet ordre de diffusion du contenu garantit que le contenu JavaScript pour la mbox globale est diffusé et affiché correctement.

## Le cookie Target n’est pas défini {#section_77AFEB541C0B495EB67E29A4475DF960}

Si votre site comporte un sous-domaine, tel que [!DNL us.domain.com], mais que le cookie Target doit être défini sur [!DNL domain.com] (plutôt que [!DNL us.domain.com]), vous devez remplacer le paramètre `cookieDomain`. Pour plus d’informations, voir [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Le contenu de Target scintille ou n’est pas affiché si un élément fait également partie de la personnalisation AEM. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Si un élément DOM fait partie du ciblage de personnalisation d’Adobe Experience Manager (AEM) et d’une activité Target, le contenu de Target peut scintiller ou ne pas s’afficher.

Pour remédier à cela, vous pouvez désactiver la personnalisation AEM dans les pages qui exécutent Target.

## Les offres de redirection et distantes ne fonctionnent pas en raison d’une URL non valide. {#section_7D09043B687F43B39DAEDF17D00375AC}

Si l’offre de redirection ou distante utilise une URL non valide, elle risque de ne pas être livrée.

Pour les offres de redirection, la réponse mbox peut contenir `/* invalid redirect offer URL */`

OU

Pour les offres distantes, la réponse mbox peut contenir `/* invalid remote offer URL */`

Vous pouvez vérifier la réponse mbox dans le navigateur ou utiliser mboxTrace. Reportez-vous à [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) pour plus d’informations sur les URL valides.

## les mbox ne se déclenchent pas sur mon site.

at.js ne déclenche pas les mbox Target si vous utilisez un type doctype non valide. at.js requiert le doctype HTML 5.

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Ajouter l’extension Badge de ![didacticiel](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Balise ![du didacticiel de débogage de base de Target](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Badge ![du didacticiel de suivi des mbox](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)