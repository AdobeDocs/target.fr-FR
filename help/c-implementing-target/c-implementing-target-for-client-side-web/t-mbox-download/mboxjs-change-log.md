---
keywords: modifications de mbox.js, versions de mbox.js
description: Cette page présente les modifications apportées à chaque version de mbox.js.
title: Détails de la version mbox.js
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2397'
ht-degree: 95%

---


# Informations détaillées sur les versions du fichier mbox.js{#mbox-js-version-details}

Cette page présente les modifications apportées à chaque version de mbox.js.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : Le 31 mars 2021, la bibliothèque mbox.js ne  [!DNL Adobe Target] sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront un impact sur vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Il est recommandé à tous les utilisateurs de procéder à la mise à niveau vers la version 57 ou ultérieure de mbox.js. Certains utilisateurs ont rencontré des problèmes de temporisation empêchant le chargement de `target.js`. La version 57 corrige ce problème. Si, toutefois, vous utilisez le service [!DNL Experience Cloud Visitor ID], vous devez installer la version 58 ou ultérieure.

La réponse de Target aux appels de vos pages dépend de la version de la bibliothèque Target utilisée, de la présence de l’implémentation de l’identifiant visiteur et de l’existence de ce dernier. Pour plus d’informations, voir [Réponses d’appel Target par version de bibliothèque](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0).

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. Pour plus d’informations, voir [Migration vers at.js depuis mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## mbox.js version 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Version de Target :** 17.7.1

[!DNL mbox.js] La version 63 est désormais disponible. Pour plus d’informations, voir [Téléchargement de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md).

Les améliorations et correctifs suivants sont inclus dans la version 63 de [!DNL mbox.js] :

* Correction d’un problème relatif à la génération des SDID lors de l’utilisation de `mboxDefine()` et de `mboxUpdate()`. Ce problème n’affecte que les clients disposant de l’API visiteur sur la page.

## mbox.js version 62 {#section_723A9119FE204183847D3B0929A99B41}

* Correction des problèmes de scintillement des activités de redirection affichées dans des navigateurs Google Chrome.
* Ajout du paramètre `secureOnly`, qui indique si mbox.js doit utiliser le protocole HTTPS seulement ou s’il peut permuter entre les protocoles HTTP et HTTPS en fonction du protocole de la page. Ce paramètre avancé est défini par défaut sur false.

## mbox.js version 61 {#section_F3B59C5578B64883AE013B9342151193}

**Version de Target :** 16.7.2

**Date de publication :** 28 juillet 2016

mbox.js version 61 contient les améliorations suivantes :

* L’algorithme de génération d’ID mboxSession dans l’API JavaScript Date génère désormais une chaîne aléatoire plutôt que d’utiliser un horodatage et une chaîne aléatoire.
* Les détails suivants s’appliquent uniquement si vous disposez de l’API visiteur sur la page :

   * [!DNL mbox.js] La version 61 ne remplace pas la propriété `loadTimeout` de l’API visiteur. Les clients peuvent utiliser `visitorApiTimeout` + `visitorApiPageDisplayTimeout` pour contrôler l’intégration de l’API visiteur.
   * Ajout d’un paramètre `optoutEnabled` pour prendre en charge la future fonctionnalité d’exclusion d’Adobe Experience Cloud. La valeur par défaut est false. Si cette propriété est activée, toutes les demandes sont exécutées de manière asynchrone via le point de terminaison [!DNL /ajax], tout comme dans la version 60.
   * Le masquage du contenu est désactivé par défaut. Target utilise le masquage du contenu uniquement lorsque la création automatique de la mbox globale est activée et que le masquage du contenu est activé.
   * S’il n’y a pas de cookies d’ID de visiteur Experience Cloud, toutes les demandes s’exécutent de manière asynchrone sur [!DNL /ajax] lors du chargement de la première page. Au second chargement d’une page, Target utilise le processus normal, car les valeurs d’identifiant visiteur existent déjà.
   * Si vous utilisez Adobe Analytics comme source des rapports de votre activité, vous ne devez pas spécifier de serveur de suivi durant la création d’activités si vous utilisez mbox.js version 61 (ou ultérieure) ou at.js version 0.9.1 (ou ultérieure). La bibliothèque mbox.js ou at.js envoie automatiquement les valeurs du serveur de suivi à [!DNL Target]. Pendant la création de l’activité, vous pouvez laisser le champ [!UICONTROL Serveur de suivi] vide sur la page [!UICONTROL Objectifs et paramètres].

## mbox.js version 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Version de Target :** 16.4.1

**Date de publication :** 21 avril 2016

Par défaut, le contenu des pages n’est pas masqué. La version 60 masque le contenu des pages uniquement lorsque l’option Créer automatiquement la mbox globale est activée. Elle utilise la propriété CSS `opacity:0` pour masquer la page plutôt que `display:none`. Cela garantit la diffusion correcte des sites réactifs et l’alignement avec [!DNL at.js].

Deux paramètres vous permettent d’activer le masquage du contenu :

* `bodyHidingEnabled` La valeur par défaut est false, ce qui signifie que la balise HTML BODY n’est pas masquée.

* bodyHiddenStyle

   La valeur par défaut est `body{opacity:0}`. Cette valeur peut être modifiée et remplacée par autre chose, par exemple `body{display:none}`.

Ces paramètres peuvent être remplacés en incluant par exemple :

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

La technique de masquage des pages utilise des balises de style pour ajouter et supprimer des styles. Cela garantit que les styles du site restent inchangés après l’exécution du code de masquage des pages.

**Utilisateurs de DTM :** notez que cela vous empêchera d’utiliser l’option d’importation automatique, puisqu’il n’est pas possible d’enregistrer la configuration ci-dessus dans l’interface utilisateur de Target. Il vous faudra suivre les instructions ci-dessus, puis coller le contenu dans la zone de code de l’option d’hébergement personnalisé.

De plus, dans la version 60, si le fichier [!DNL visitorAPI.js] est présent pour le service d’identification des visiteurs Experience Cloud, toutes les mbox sont demandées par l’intermédiaire d’un point de terminaison AJAX. Cela est requis, car les méthodes de l’API visiteur sont asynchrones. Cette approche présente l’avantage de réduire considérablement le temps de début du rendu, car les demandes de mbox ne bloquent pas le rendu. Cela signifie aussi que l’ensemble du contenu des offres [!DNL Target] s’exécute de manière asynchrone. Le code des offres doit donc être écrit en conséquence. Les offres contenant `document.write` et d’autres codes dont l’exécution est supposée avoir lieu au chargement initial de la page ne s’exécuteront pas comme prévu.

* Appels asynchrones dans la version 60

   Lorsque la version 60 est utilisée avec le service d’identification des visiteurs, tous les appels de mbox sont effectués de manière asynchrone. Cela diffère de la façon dont les mbox ont toujours fonctionné. Soyez donc prudent si vous effectuez la mise à niveau vers cette version. Voir [Points à prendre en compte concernant le caractère asynchrone des mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953) de la documentation [!DNL at.js] ([!DNL at.js] utilise également des appels asynchrones) pour comprendre certains des risques auxquels vous vous exposez.
* Les scénarios de nouveaux visiteurs peuvent présenter un scintillement.

   Lorsque les versions 58 à 60 sont utilisées avec le service d’identification des visiteurs, les appels de mbox ne seront déclenchés qu’une fois l’identifiant visiteur défini (ou lorsque le délai d’attente aura été dépassé). Cela se produit au premier chargement de page d’un nouveau visiteur.

## mbox.js version 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Version de Target :** 16.2.1

**Date de publication :** 17 février 2016

mbox.js version 59 contient les améliorations suivantes :

* La désactivation de la mbox a été réduite à 30 minutes.
* Un problème lié au masquage/à l’affichage des pages a été corrigé.

   Au lieu d’utiliser `display:none` pour masquer une page comme dans la version 58, la propriété `opacity:0` est utilisée. Cela permet de résoudre des problèmes liés aux sites réactifs qui étaient dus à l’ancienne méthode de masquage d’une page.

## mbox.js version 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Version de Target :** 15.7.1

**Date de publication :** 30 juillet 2015

Cette version de mbox.js est nécessaire si vous utilisez Analytics comme source de création des rapports pour Target et est vivement recommandée pour les profils et audiences.

La version 58 de mbox.js assure que le service d’identification des visiteurs Experience Cloud envoie un identifiant de visiteur avant que les appels Target ne soient effectués. Cela permet que les données d’audience qui sont partagées à l’aide du service de base des profils et des audiences soient disponibles pour le premier appel Target dans la session du visiteur. Pour éviter le scintillement du contenu par défaut avant le renvoi du contenu du test, Target masque la balise `<BODY>` jusqu’au renvoi du service d’identification des visiteurs. `display:none` est utilisé pour masquer la page.

Cette mise à jour corrige également un problème lié à l’utilisation d’Analytics comme source des rapports pour Target. Ce problème entraînait le signalement d’un nombre exagéré de visiteurs dans Analytics pour les visites n’incluant qu’une seule page.

Mbox.js définit les valeurs d’expiration en cas de non-renvoi du service d’identification des visiteurs. L’expiration par défaut pour le service d’identification des visiteurs est de 500 ms (0,5 seconde). Une expiration supplémentaire définit la limite supérieure pour la durée au cours de laquelle la balise `<BODY>` sera masquée. Par défaut, elle est de 500 ms (0,5 seconde). Ces expirations peuvent être modifiées en insérant le code suivant avant la référence mbox.js sur chaque page :

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

Les versions 58 et ultérieures de mbox.js exécutent le contenu non JavaScript pour la mbox globale immédiatement après la balise HTML `BODY`. Le contenu JavaScript situé à l’intérieur des balises `<script>` pour la mbox globale s’exécute après le déclenchement de l’événement `DOMContentLoaded`. Cet ordre de diffusion du contenu garantit que le contenu JavaScript pour la mbox globale est diffusé et affiché correctement.

## mbox.js version 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Version de Target :** 15.4.1

**Date de publication :** 21 avril 2015

Les modifications suivantes ont été apportées dans cette version :

* La réponse mbox globale auto-créée pour Target Standard n’utilise plus document.write() ou ne crée plus un `<div>` element.

   Cela supprime l’obligation pour le fichier mbox.js d’être le dernier élément de la `<head>` page. Un contrôle qualité puissant est recommandé lors de la mise à niveau vers cette nouvelle version.

   Cette modification peut provoquer des modifications de comportement lors de la diffusion de certains types d’offres. Vous trouverez ci-dessous les conditions spécifiques qui doivent être prises en considération :

   * Le contenu HTML renvoyé dans le cadre d’une « offre de module externe » ne donne pas le rendu attendu mais le code JavaScript des offres s’exécute comme prévu.
   * Les offres JavaScript qui sont renvoyées à la mbox globale peuvent comporter du code JavaScript incorporé dans la balise `<script>` ou référencé par un attribut `src`.

      Pour ce faire, ajoutez l’attribut `async` à l’appel de script, comme suit :

      `<script src='external-url' async='true'></script>`

      Notez que l’attribut `async` n’a qu’une prise en charge limitée dans Internet Explorer (détails ici : [https://developer.mozilla.org/fr/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)). Vous devez donc exclure des tests incluant des scripts tiers les visiteurs qui utilisent des versions anciennes d’IE.

* Correction de problèmes rapportés dans la version 56 en raison de modifications dans la section Extra JavaScript de mbox.js. L’ensemble du code de la section Extra JavaScript est à nouveau disponible dans la portée globale.

La fonctionnalité suivante n’est pas prise en charge dans mbox.js version 57 :

* Une mbox globale auto-créée générée dans Target Standard ne fonctionne pas avec les types d’offres hébergés provenant de Target Classic. Les types d’offres incluent « offre sur votre site » et « offre en dehors de Test&amp;Target ».

   Cela signifie que, dans Target Classic, vous ne devez pas sélectionner la mbox globale auto-créée depuis Target Standard lorsque l’une de ces offres est requise.
* Seuls les modules externes JavaScript sont pris en charge.

   Si une offre de module externe associe du code JavaScript et du contenu HTML, alors le code JavaScript est exécuté mais le contenu HTML n’est pas affiché.

mbox.js version 57 inclut également des correctifs importants :

* Correction d’un problème en raison duquel le module externe de SiteCatalyst ne fonctionnait pas dans mbox.js v56.
* Correction d’un problème qui créait des erreurs JavaScript supplémentaires en raison d’une modification de la portée.
* Annulation de modification du constructeur de mboxFactory.

## mbox.js version 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Version de Target :** 15.1.2

**Date de publication :** 17 février 2015

>[!NOTE]
>
>Certains utilisateurs ont rencontré des problèmes de temporisation empêchant le chargement de `target.js`. La version 57 corrige ce problème. Toutefois, si vous utilisez le service [!DNL Experience Cloud Visitor ID]Identifiant visiteur Experience Cloud, vous devez installer la version 58 ou ultérieure.

Les modifications suivantes ont été apportées dans cette version :

* Modifications de Recommendations Premium afin de prendre en charge le transfert des paramètres dans une mbox globale.
* Ajout d’un délai d’attente de 5 secondes à l’appel de charge target.js. Dans le cas exceptionnel où le fichier ne se charge pas, la page s’affiche mais aucune activité Target Standard ne s’affiche.
* Déplacement de la section « Extra JavaScript » à exécuter avant la mbox globale.

   Tous les paramètres dans v56+ sont espacés par nom. Si des fonctions sont déclarées dans la section « Extra JavaScript », elles doivent comporter le préfixe `window`.

   Par exemple :

   `function foo {`

   `}`

   Devient :

   `window.foo = function() {`

   `}`

   Toute variable qui doit être accessible globalement doit également comporter le préfixe `window`.

* Ajout d’un cookie nommé « em-disabled » que mbox.js donne à l’utilisateur si target.js n’arrive pas à se charger lors de la diffusion. Ce cookie empêche les offres créées en utilisant le compositeur d’expérience visuelle d’effectuer un rendu sur le site. Les utilisateurs dotés de ce cookie ne voient pas le contenu du test et ne sont pas comptabilisés dans les rapports d’activité. Tous les autres contenus d’offres (provenant des campagnes dans Target Classic par exemple) continuent à se charger. Le cookie possède une durée de vie de 30 minutes à partir de l’échec du chargement.

## mbox.js version 55

**Version de Target :** 15.1

**Date de publication :** 19 janvier 2015

Modification de la version 53 avec des correctifs IE.

## mbox.js version 54

**Version de Target :** 14.9.2

**Date de publication :** 30 septembre 2014

Modification de l’implémentation des mbox globales à AJAX depuis document.write. Cette modification supprime l’obligation que le fichier mbox.js soit le dernier élément de la section de la page. `<head>`. Cette version n’est disponible que par API. Les clients peuvent la télécharger et utiliser ce fichier mbox.js. Avec cette implémentation, le contenu peut scintiller sur certains sites. De ce fait, validez l’intégration sur votre site.

## mbox.js version 53

**Version de Target :** 14.9.1

**Date de publication :** 14 septembre 2014

Correction d’un problème en raison duquel les paramètres des pages Target ne se déclenchaient pas correctement dans Internet Explorer.

## mbox.js version 52

**Version de Target :** 14.8

**Date de publication :** 14 août 2014

La fonction mboxParameter fonctionne désormais dans Target Standard et Premium.

Correction d’un problème qui empêchait le suivi d’Analytics de fonctionner dans IE 9 et 11. Cette modification n’affecte que les utilisateurs d’Analytics.

Désormais, vous pouvez [transférer des paramètres](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) sous la forme d’un tableau, d’un objet JSON ou d’une liste délimitée par des virgules (prise en charge antérieurement) vers target-global-mbox à l’aide de la fonction targetPageParams().

Nouvelle dénomination de M2PcId et de tout ce qui est lié à l’identifiant visiteur.

Autorisation de l’effacement du defaultDiv d’une mbox enregistrée.

## mbox.js version 51

**Version de Target :** 14.6

**Date de publication :** 25 juin 2014

Correction d’un bogue en raison duquel un cookie incorrect était défini dans les sites comportant deux caractères dans leur domaine de premier niveau.

Correction d’un bogue mineur dans mbox.js qui provoquait le retour de valeurs de mot-clic.

## mbox.js version 50

Amélioration de la synchronisation entre Target Standard et Target Classic.

## mbox.js version 49

Amélioration de la prise en charge d’Internet Explorer 10 pour les mbox imbriquées.

## mbox.js version 48

Ajout de la prise en charge d’Adobe Analytics en tant que source de création de rapports pour Target.

## mbox.js version 47

mbox.js prend maintenant en charge l’utilisation d’un nom de mbox globale personnalisée pour Target Standard.

## mbox.js version 46

Ajout de la prise en charge complète du service d’identifiant visiteur Experience Cloud pour l’implémentation à ligne de code unique de Target Standard. Cela active l’intégration Adobe Analytics côté serveur et le profil partagé Experience Cloud.

A corrigé un problème avec la fourniture de contenu dans IE10 en mode document.

## mbox.js version 45

Ajout de la prise en charge complète du service d’identifiant visiteur Experience Cloud. Cela active l’intégration Adobe Analytics côté serveur et le profil partagé Experience Cloud.

## mbox.js version 44

Ajout d’un nouveau paramètre à l’URL par mboxVizTarget :

mboxDOMLoaded

## mbox.js version 43

Ajout de la prise en charge de Target Standard.

## mbox version 42

Ajout de la prise en charge initiale du service d’identifiant visiteur partagé Experience Cloud.

## mbox version 41

* Même avec le paramètre x-uniquement, désactivez le cookie propriétaire pour accélérer le chargement et empêcher l’actualisation continue des pages.

   Un cookie de délai d’attente est défini si l’appel de Target ne revient pas dans le délai. C’est une méthode plus rapide que de n’utiliser que le cookie tiers. Avec seulement le cookie tiers, la page est continuellement actualisée en attendant une réponse appropriée des serveurs Target.

* Correction de la limitation de trafic pour qu’elle survienne uniquement lorsque mbox.js est activé.

   Ce problème survenait si un client avait une limite de trafic sur son fichier mbox.js, provoquant le non-fonctionnement du paramètre de délai d’attente. Cela résultait en une actualisation de la page en attendant une réponse appropriée des serveurs Target.

* Correction du module externe SiteCatalyst pour qu’il utilise toujours le récupérateur Ajax.

   Avant cette modification, dans certains cas, pour les utilisateurs du module externe Test&amp;Target to SiteCatalyst, selon le moment où le module se chargeait, un document.write éliminant la page pouvait être déclenché.

## mbox version 38

Ajout de la prise en charge de l’intégration de SiteCatalyst basé sur la page à Test&amp;Target (doit être activée).

## mbox version 37

Clés d’URL codées.

## mbox version 36

Mbox changée pour utiliser tt.omtrdc.net.

## mbox version 35

* Le débogage de la mbox est maintenant toujours distant.
* Ajout du paramètre mboxTime. Ce paramètre correspond à l’heure telle que la voit l’utilisateur, en ms depuis l’époque, GMT. Ceci est calculé une seule fois.

## mbox version 34

* Faites en sorte de toujours obtenir la dernière balise div par défaut plutôt que de vous référer à une version en mémoire cache.

   Ceci corrige un problème lié à une balise div de contenu par défaut en mémoire cache dans l’objet DOM en raison d’un événement mboxUpdate, qui fournissait le contenu pour la balise div par défaut.

* mbox.getDefaultDiv a un nouveau paramètre booléen en option. S’il est vrai, il renvoie la balise div par défaut actuelle. S’il est faux, il renvoie la dernière balise div par défaut en mémoire cache.
* Mise à jour de mbox.loaded pour prendre en charge le chargement Ajax.
* Le paramètre mboxURL est maintenant codé à l’aide de encodeURIComponent plutôt que d’un caractère d’échappement.
* Vérifiez si encodeURIComponent est pris en charge par le navigateur et affichez le contenu par défaut dans le cas contraire. Supprimez toujours les options de configuration mbox.js suivantes :
   * encode\_mbox\_parameters
   * mbox\_signal\_support
