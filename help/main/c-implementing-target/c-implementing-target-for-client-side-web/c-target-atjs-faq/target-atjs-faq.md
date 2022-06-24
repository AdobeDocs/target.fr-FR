---
keywords: at.js faq;questions fréquentes sur at.js;faq;flicker;chargeur;chargeur de page;interdomaine;taille de fichier;taille fichier;domaine x;at.js et mbox.js;x uniquement;interdomaine;safari;app à une seule page;sélecteurs manquants;sélecteurs;application à une seule page;tt.omtrdc.net;spa;Adobe Experience Manager;AEM;adresse ip;httponly;HttpOnly;secure;ip;domaine de cookie
description: Consultez les réponses aux questions fréquentes sur la bibliothèque JavaScript at.js d’Adobe  [!DNL Target] .
title: Quelles sont les questions et réponses fréquentes concernant at.js ?
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2604'
ht-degree: 92%

---

# Forum aux questions sur at.js

Réponses aux questions fréquentes sur la bibliothèque JavaScript at.js [!DNL Adobe Target].

## Quels sont les avantages d’utiliser at.js au lieu de mbox.js ? {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

La bibliothèque [!DNL at.js] remplace la bibliothèque [!DNL mbox.js]. La bibliothèque [!DNL mbox.js] n’est plus prise en charge. Pour la plupart des utilisateurs, [!DNL at.js] offre cependant des avantages en comparaison de [!DNL mbox.js].

Autres avantages : [!DNL at.js] réduit les délais de chargement des pages pour les implémentations web, renforce la sécurité et offre des options d’implémentation optimisées pour les applications d’une seule page.

Le diagramme suivant illustre les performances de chargement de page avec mbox.js et at.js.

![](assets/atjs_vesus_mboxjs.png)

Comme illustré ci-dessus, avec mbox.js, le contenu de la page ne commençait à charger qu’une fois l’appel [!DNL Target] terminé. Avec at.js, le contenu de la page commence à charger dès que l’appel de [!DNL Target] est initié, sans attendre qu’il soit terminé.

## Quel est l’impact de at.js et mbox.js sur le temps chargement de la page ?  {#page-load}

Bon nombre de clients et de consultants souhaitent connaître l’impact d’[!DNL at.js] et de [!DNL mbox.js] sur le délai de chargement des pages, particulièrement en ce qui concerne les nouveaux utilisateurs et les utilisateurs réguliers. Il est, malheureusement, difficile de mesurer l’influence d’[!DNL at.js] ou de [!DNL mbox.js] sur le délai de chargement des pages et d’avancer des chiffres concrets en raison de l’implémentation de chaque client.

Toutefois, si l’API visiteur est présente sur la page, [!DNL Target] peut mieux comprendre comment [!DNL at.js] et [!DNL mbox.js] influencent le délai de chargement des pages.

>[!NOTE]
>
>L’API visiteur et [!DNL at.js] ou [!DNL mbox.js] ont un impact sur le délai de chargement des pages uniquement lorsque vous utilisez la mbox globale (en raison de la technique de masquage du corps). Les mboxes régionales ne sont pas impactées par l’intégration de l’API visiteur.

Les sections suivantes décrivent la séquence d’actions pour les nouveaux visiteurs et les visiteurs récurrents :

### Nouveaux visiteurs

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js / mbox.js est chargé, analysé, puis exécuté.
1. Si la fonction de création automatique de mbox globale est activée, la bibliothèque JavaScript de Target :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!DNL Experience Cloud Visitor ID].
   * Comme il s’agit d’un nouveau visiteur, l’API visiteur déclenche une requête inter-domaines sur demdex.net.
   * Une fois les données [!DNL Experience Cloud Visitor ID] récupérées, une requête vers [!DNL Target] est déclenchée.

### Visiteurs récurrents

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js / mbox.js est chargé, analysé, puis exécuté.
1. Si la fonction de création automatique de mbox globale est activée, la bibliothèque JavaScript de [!DNL Target] :

   * instancie l’objet visiteur ;
   * La bibliothèque [!DNL Target] tente de récupérer les données [!DNL Experience Cloud Visitor ID].
   * l’API visiteur récupère les données du cookies ;
   * Une fois les données [!DNL Experience Cloud Visitor ID] récupérées, une requête vers [!DNL Target] est déclenchée.

>[!NOTE]
>
>Pour les nouveaux visiteurs, si l’API visiteur est présente, [!DNL Target] doit se connecter plusieurs fois pour s’assurer que les requêtes [!DNL Target] contiennent les données [!DNL Experience Cloud Visitor ID]. Pour les visiteurs réguliers, [!DNL Target] se connecte uniquement à [!DNL Target] pour récupérer le contenu personnalisé.

## Pourquoi les temps de réponse semblent-ils plus lents après la mise à niveau d’une version précédente d’at.js vers la version 1.0.0 ? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] version 1.0.0 (et ultérieure) déclenche toutes les demandes en parallèle. Les versions précédentes exécutent les requêtes de manière séquentielle, ce qui signifie que les requêtes sont placées en file d’attente et que [!DNL Target] attend que la première requête se termine avant de passer à la suivante.

La façon dont les versions précédentes d’[!DNL at.js] exécutent les demandes est sujette au « blocage d’en-tête de ligne ». Dans [!DNL at.js] version 1.0.0 et ultérieure, est passé à l’exécution de demandes parallèles.[!DNL Target]

Si vous consultez par exemple la cascade de l’onglet réseau pour [!DNL at.js] 0.9.1, vous verrez que la demande suivante ne démarre pas tant que la précédente n’est pas terminée. [!DNL Target] Cette séquence ne fonctionne pas avec [!DNL at.js] version 1.0.0 et ultérieure, où toutes les requêtes démarrent en même temps.

En termes de temps de réponse, mathématiquement, cette séquence peut se résumer comme suit :

<ul class="simplelist"> 
 <li> at.js 0.9.1 : Temps de réponse de tous [!DNL Target] requests = somme du temps de réponse des demandes </li> 
 <li> at.js 1.0.0 et versions ultérieures : Temps de réponse de tous [!DNL Target] requêtes = temps de réponse maximal des requêtes </li> 
</ul>

La bibliothèque [!DNL at.js] version 1.0.0 exécute les requêtes plus rapidement. En outre, les demandes [!DNL at.js] sont asynchrones, de sorte que ne bloque pas le rendu de la page. [!DNL Target] Même si le traitement des requêtes ne prend que quelques secondes, la page rendue est toujours visible. Toutefois, certaines parties de la page sont masquées, et ce, jusqu’à ce que [!DNL Target] reçoive une réponse du Edge de [!DNL Target].

## Puis-je charger la bibliothèque [!DNL Target] de manière asynchrone ? {#section_AB9A0CA30C5440C693413F1455841470}

La version 1.0.0 d’at.js permet de charger la bibliothèque [!DNL Target] de manière asynchrone.

Pour charger at.js de manière asynchrone, procédez comme suit :

* L’approche par le biais des balises dans [!DNL Adobe Experience Platform] est celle recommandée.
* Vous pouvez également charger at.js de manière asynchrone en ajoutant l’attribut async à la balise du script qui charge at.js. Utilisez un élément semblable au suivant :

   ```
   <script src="<URL to at.js>" async></script>
   ```

* Vous pouvez également charger at.js de manière asynchrone en utilisant le code suivant :

   ```
   var script = document.createElement('script'); 
   script.async = true; 
   script.src = "<URL to at.js>"; 
   document.head.appendChild(script);
   ```

Le chargement d’at.js de manière asynchrone est un excellent moyen d’éviter de bloquer le rendu du navigateur. Cependant, cette technique peut entraîner un scintillement de la page web.

Vous pouvez éviter le scintillement à l’aide d’un extrait de code de masquage préalable qui masque la page (ou les parties spécifiées), puis la révèle après le chargement d’at.js et de la requête globale. Vous devez ajouter le fragment de code avant le chargement d’at.js.

Si vous déployez at.js par le biais d’une implémentation [!DNL Adobe Experience Platform] asynchrone, assurez-vous d’inclure le fragment de code de masquage préalable directement sur vos pages, avant le code intégré d’implémentation de [!DNL Target] avec [!DNL Adobe Experience Platform].

Si vous déployez at.js par le biais d’une implémentation synchrone de la gestion dynamique des balises, le fragment de code prémasqué peut être ajouté au moyen d’une règle de chargement de page déclenchée en haut de la page.

Pour plus d’informations, voir [Gestion du scintillement par at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/){target=_blank}.

## Est-ce qu’at.js est compatible avec l’intégration [!DNL Adobe Experience Manager] (Experience Manager) ? {#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 avec FP-11577 (ou ultérieur) prend maintenant en charge les mises en œuvre d’[!DNL at.js] avec son intégration des [!UICONTROL Services Cloud d’Adobe Target]. 

## Comment empêcher le scintillement au chargement des pages avec at.js ? {#section_4D78AAAE73C24E578C974743A3C65919}

Target propose plusieurs solutions pour éviter le scintillement au chargement des pages. Pour plus d’informations, voir [Prévention du scintillement avec at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/){target=_blank}.

## Quelle est la taille de fichier d’at.js ? {#section_6A25C9A14C66441785A7635FEF5C4475}

Le fichier at.js fait environ 109 Ko une fois téléchargé. Cependant, comme la plupart des serveurs compressent automatiquement les fichiers pour les rendre plus légers, at.js ne fait plus que 34 Ko environ une fois compressé (avec GZIP ou une autre méthode) sur votre serveur et chargé lorsque des utilisateurs visitent votre site web. Les paramètres de compression du serveur sur lequel vous avez installé at.js déterminent sa taille réelle après compression.

## Pourquoi le fichier at.js est-il plus volumineux que le fichier mbox.js ? {#section_AA1C43897E46448FA3E26EEC10ED7E51}

Les implémentations at.js utilisent une seule bibliothèque ([!DNL at.js]), tandis que les implémentations mbox.js en utilisent réellement deux ([!DNL mbox.js] et [!DNL target.js]). Il serait donc préférable donc de comparer at.js à mbox.js *et* `target.js`. Si l’on compare la taille des fichiers gzip des deux versions, at.js version 1.2 fait 34 Ko, tandis mbox.js version 63 fait 26,2 Ko. ``

Le fichier at.js est plus volumineux, car il effectue beaucoup plus d’analyses DOM que le fichier mbox.js, du fait que le fichier at.js doit interpréter les données « brutes » qu’il récupère dans la réponse JSON. mbox.js utilisait `document.write()` et toute l’analyse était effectuée par le navigateur.

Malgré une taille de fichier plus importante, nos tests démontrent que les pages se chargent plus rapidement avec at.js qu’avec mbox.js. En outre, at.js offre une sécurité accrue, car il ne charge pas de fichiers supplémentaires de manière dynamique ni n’utilise `document.write`.

## at.js inclut-il jQuery ? Puis-je supprimer cette partie du fichier at.js si jQuery figure déjà dans mon site web ? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

Actuellement, at.js utilise des parties de jQuery ; c’est pourquoi l’avis de licence MIT s’affiche en haut du fichier at.js. jQuery n’est pas exposé et n’interfère pas avec la bibliothèque jQuery déjà présente sur votre page, qui peut être d’une autre version. Il n’est pas possible de supprimer le code jQuery dans at.js.

## at.js prend-il en charge Safari et un interdomaine défini sur x-uniquement ? {#section_114EC271A6E045E1B2183B66F1B71285}

Non, si le suivi inter-domaines est défini sur x-uniquement et que les cookies tiers sont désactivés dans Safari, [!DNL mbox.js] et at.js définissent un cookie désactivé et aucune demande de mbox n’est exécutée pour le domaine de ce client spécifique.

Pour prendre en charge les visiteurs Safari, il convient d’avoir un x-domaine « désactivé » (définit uniquement un cookie propriétaire) ou « activé » (définit un cookie propriétaire sur Safari, ainsi que des cookies propriétaires et tiers sur les autres navigateurs).

## Puis-je utiliser le compositeur d’expérience visuelle (VEC) de [!DNL Target] dans mes applications monopages ? {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

Oui, vous pouvez utiliser le VEC pour votre SPA si vous utilisez at.js 2.x. Pour plus d’informations, consultez [Compositeur d’expérience visuelle monopage (SPA)](/help/main/c-experiences/spa-visual-experience-composer.md).

## Puis-je utiliser le débogueur [!DNL Adobe Experience Cloud] avec les implémentations d’at.js ? {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

Oui. Vous pouvez également utiliser mboxTrace à des fins de débogage ou les outils de développement de votre navigateur pour inspecter les demandes de réseau, en filtrant sur « mbox » pour isoler les appels mbox.

## Puis-je utiliser des caractères spéciaux dans les noms mbox avec at.js ? {#section_8E31D2E8A27642098934D7DACFB2A600}

Oui, comme avec mbox.js.

## Pourquoi mes mbox ne se déclenchent-elles pas sur mes pages web ? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Les clients de [!DNL Target] utilisent parfois des instances basées sur le cloud avec [!DNL Target] à des fins de test ou de preuve de concept. Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines, sauf si vous personnalisez le paramètre `cookieDomain` à l’aide de targetGlobalSettings(). Pour plus d’informations, voir [Utilisation d’instances basées sur le cloud avec Target](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/targeting-using-cloud-based-instances/){target=_blank}.

## Les adresses IP peuvent-elles être utilisées comme domaine de cookie lors de l’utilisation d’at.js ? {#section_8BEEC91A3410459D9E442840A3C88AF7}

Oui, si vous utilisez [at.js version 1.2 ou ultérieure](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}. Néanmoins, [!DNL Adobe] vous recommande vivement de rester à jour avec la dernière version.

>[!NOTE]
>
>Remarque : Les exemples suivants ne sont pas nécessaires si vous utilisez la version 1.2 ou ultérieure d’at.js.

Selon la manière dont vous utilisez [targetGlobalSettings](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}, vous devrez peut-être apporter des modifications supplémentaires au code après le téléchargement d’at.js. Par exemple, si vous avez besoin de paramètres légèrement différents pour vos mises en œuvre [!DNL Target] sur plusieurs sites web et que vous ne parvenez pas à définir ces paramètres dynamiquement à l’aide d’un code JavaScript personnalisé, effectuez ces personnalisations manuellement après avoir téléchargé le fichier et avant de le transférer vers le site web correspondant.

Les exemples suivants permettent d’utiliser la fonction `targetGlobalSettings()` d’at.js pour insérer un fragment de code permettant de prendre en charge les adresses IP.

Cet exemple concerne une adresse IP unique :

```
if (window.location.hostname === '123.456.78.9') { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

Cet exemple concerne une plage d’adresses IP :

```
if (/^123\.456\.78\..*/g.test(window.location.hostname)) { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

## Pourquoi des messages d’avertissement du type « Actions avec sélecteurs manquants » s’affichent-ils ? {#section_C36BED5B16634361A1BA46FCB731489D}

Ces messages ne sont pas liés à la fonctionnalité [!DNL at.js]. La bibliothèque [!DNL at.js] tente de signaler tout ce qui est introuvable dans l’élément DOM.

L’affichage de ce message d’avertissement peut s’expliquer par les causes suivantes :

* La page est créée dynamiquement et at.js ne parvient pas à trouver l’élément.
* La page est créée lentement (en raison de la lenteur du réseau) et at.js ne parvient pas à trouver le sélecteur dans le DOM.
* La structure de la page sur laquelle s’exécute l’activité[!UICONTROL  a été modifiée. Si vous rouvrez l’activité dans le ]Compositeur d’expérience visuelle (VEC), un message d’avertissement s’affiche. Mettez à jour l’activité afin que tous les éléments nécessaires soient détectés.
* La page sous-jacente fait partie d’une [!UICONTROL Application monopage] (SPA) ou la page contient des éléments qui apparaissent plus bas dans la page et le « mécanisme d’interrogation des sélecteurs » [!DNL at.js] ne parvient pas à trouver ces éléments. Augmenter le `selectorsPollingTimeout` peut aider. Pour plus d’informations, voir [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.
* Les mesures de suivi des clics tentent de s’ajouter à chaque page, indépendamment de l’URL à laquelle elles ont été configurées. Bien que sans danger, cette situation entraîne l’affichage répété de ces messages.

   Pour des résultats optimaux, téléchargez et utilisez la dernière version d’[!DNL at.js]. Pour plus d’informations, voir [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} et [Téléchargement d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}.

## À quoi correspond le domaine tt.omtrdc.net auquel les appels au serveur de [!DNL Target] sont adressés ? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] est le nom de domaine du réseau EDGE d’Adobe utilisé pour recevoir tous les appels au serveur pour Target.

## Pourquoi at.js n’utilise-t-il pas toujours les indicateurs de cookie HttpOnly et Secure ? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly ne peut être défini que via un code côté serveur. [!DNL Target]Les cookies, tels que mbox, étant créés et enregistrés via le code JavaScript, ne peut pas utiliser l’indicateur de [!DNL Target] cookie HttpOnly. [!DNL Target] utilise la définition HttpOnly pour les cookies tiers définis du côté serveur lorsque le suivi inter-domaines est activé.

Secure ne peut être défini que via JavaScript lorsque la page a été chargée via HTTPS. Si la page se charge initialement via HTTP, JavaScript ne peut pas définir cet indicateur. En outre, si l’indicateur Secure est utilisé, le cookie est disponible uniquement sur les pages HTTPS. Pour les pages chargées via HTTPS, [!DNL Target] définit les attributs Secure et SameSite=None.

Pour garantir le suivi correct des utilisateurs par [!DNL Target] et parce que les cookies sont générés côté client, [!DNL Target] n’utilise aucun de ces indicateurs, sauf dans les situations mentionnées ci-dessus.

## À quelle fréquence la bibliothèque at.js déclenche-t-elle une demande de réseau ? {#section_57C5235DF7694AF093A845D73EABADFD}

Toutes les prises de décision de [!DNL Target] se font côté serveur. Cela signifie que at.js déclenche une demande de réseau à chaque rechargement de page, ou qu’une API publique de at.js est appelée.

## Dans le meilleur des cas, peut-on espérer que l’utilisateur ne subisse pas d’effets visibles liés au masquage, au remplacement et à l’affichage de contenu lors du chargement d’une page ? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js tente d’éviter le masquage préalable de l’ensemble HTML BODY ou autres éléments DOM pendant une période prolongée, mais cela dépend des conditions du réseau et de la configuration des activités. at.js fournit [paramètres](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank} Vous pouvez utiliser pour personnaliser BODY en masquant le style CSS. Par exemple, au lieu de masquer l’ensemble du HTML BODY, vous pouvez pré-masquer certaines parties de la page. On s’attend à ce que ces parties contiennent des éléments DOM à « personnaliser ».

## Quelle est le déroulement des événements dans une situation type, dans laquelle un utilisateur est admissible pour une activité ? {#section_56E6F448E901403FB77DF02F44C44452}

La requête at.js est une requête `XMLHttpRequest` asynchrone. Les étapes exécutées sont donc les suivantes :

1. La page charge.
1. at.js pré-masque l’ensemble HTML BODY. Il existe un paramètre qui permet de pré-masquer un conteneur plutôt que l’ensemble HTML BODY.
1. La bibliothèque at.js déclenche une demande.
1. Une fois la réponse de [!DNL Target] reçue, [!DNL Target] extrait les sélecteurs CSS.
1. Grâce aux sélecteurs CSS, [!DNL Target] crée des balises de style pour pré-masquer les éléments DOM qui seront personnalisés.
1. Le style de pré-masquage de l’ensemble HTML BODY est supprimé.
1. [!DNL Target] lance l’interrogation pour les éléments DOM.
1. Si un élément DOM est trouvé, [!DNL Target] apporte des modifications au modèle DOM et le STYLE de pré-masquage de l’élément est supprimé.
1. Si Target ne trouve pas d’élément DOM, un délai d’attente global supprime le masquage des éléments afin d’éviter de faire face à une page endommagée.

## À quelle fréquence le contenu des pages est-il complétement chargé et visible lorsqu’at.js finit par supprimer le masquage de l’élément modifié par l’activité ? {#section_01AFF476EFD046298A2E17FE3ED85075}

Dans le cas ci-dessus, à quelle fréquence le contenu des pages est-il complétement chargé et visible lorsqu’at.js finit par supprimer le masquage de l’élément modifié par l’activité ? Autrement dit, la page est entièrement visible, excepté le contenu de l’activité, qui apparaît légèrement après le reste du contenu.

at.js ne bloque pas le rendu de la page. L’utilisateur peut apercevoir certaines zones vides dans la page, représentant les éléments personnalisés par [!DNL Target]. Si le contenu qui doit être appliqué contient peu d’actifs distants, tels que des scripts et des images, tout devrait être rendu rapidement.

## Quel serait l’impact d’une page entièrement en cache dans le cas ci-dessus ? Le contenu de l’activité aurait-il plus de chance d’être visible une fois le reste du contenu de la page chargé ? {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

Si une page est mise en cache sur un réseau CDN proche de l’emplacement géographique de l’utilisateur, mais loin du serveur Edge de [!DNL Target], le délai risque d’être un peu plus long. Les serveurs Edge de [!DNL Target] sont bien répartis autour du globe, ce n’est donc pas un problème la plupart du temps.

## Est-il possible que la bannière principale s’affiche, puis change après un court instant ? {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

Dans le cas suivant :

Le délai d’attente de [!DNL Target] est de cinq secondes. Un utilisateur charge une page qui a une activité afin de personnaliser une image principale. at.js envoie une requête pour déterminer s’il faut appliquer une activité, mais dans un premier temps, ne reçoit pas de réponse. On considère que l’utilisateur consulte le contenu de l’image principale, car [!DNL Target] n’a pas envoyé de réponse pour savoir si oui ou non une activité y est associée. Au bout de quatre secondes, [!DNL Target] envoie une réponse avec le contenu de l’activité.

À ce stade, est-il possible d’afficher la version alternative ? Donc, après les quatre secondes, l’image principale a pu changer et l’utilisateur a pu remarquer ce changement ?

Initialement, l’élément DOM de l’image principale est masqué. Une fois la réponse de [!DNL Target] reçue, at.js apporte les modifications aux éléments DOM, comme le changement d’image, et affiche l’image principale personnalisée.

## Quel doctype HTML at.js requiert-il ?

at.js requiert le doctype HTML 5.

Cette syntaxe est la suivante :

`<!DOCTYPE html>`

Le doctype HTML 5 garantit le chargement de la page en mode standard. Lors du chargement en mode quirks, certaines API JS dont le fichier at.js dépend sont désactivées. [!DNL Target] désactive at.js en mode quirks.
