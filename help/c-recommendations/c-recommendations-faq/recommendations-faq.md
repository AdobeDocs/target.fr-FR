---
keywords: résolution de problèmes;questions fréquentes;FAQ;forums aux questions;recommandations;caractères spéciaux;pondération des attributs;similarité de contenu
description: Vue d'une liste de questions fréquentes et de réponses sur l'Adobe [!DNL Target] activités Recommendations.
title: Où puis-je trouver des questions et des réponses sur  [!DNL Target] Recommendations ?
feature: Recommandations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
translation-type: tm+mt
source-git-commit: eaa4266337129807714a0d1bda8f2baa87b7afbf
workflow-type: tm+mt
source-wordcount: '2957'
ht-degree: 36%

---

# ![PREMIUM](/help/assets/premium.png)Forum aux questions (FAQ) de Recommandations

Liste des questions fréquentes (FAQ) sur les [!DNL Adobe Target] [!DNL Recommendations] activités.

## Pourquoi [!UICONTROL la recherche catalogue] n’affiche-t-elle pas les résultats corrects lorsque je recherche sur un attribut personnalisé avec une valeur numérique ?

Lorsque vous effectuez une recherche catalogue sur un attribut personnalisé doté d’une valeur numérique, les résultats traitent l’attribut personnalisé comme un type de chaîne plutôt que comme une valeur numérique.

Actuellement, aucune fonctionnalité disponible ne permet aux clients de modifier le type d’un attribut. Pour apporter une modification, [ouvrez un problème client](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) référençant les attributs dont le type doit être passé de chaîne à numérique.

## Combien de temps faut-il pour que les mises à jour des éléments de mon catalogue soient répercutées sur mon site ?

La période et les résultats varient selon la façon dont les éléments sont mis à jour.

| Source | Détails |
| --- | --- |
| Attributs d’élément mis à jour par mbox ou API | <ul><li>Recommendations est mis à jour dans les 15 minutes.</li><li>Les recommandations et les attributs d’article existants s’affichent jusqu’à ce que des mises à jour soient disponibles.</li><li>La recherche catalogue est mise à jour après l’index catalogue (3-8 heures).</li></ul> |
| Attributs d’élément mis à jour via le flux | <ul><li>Recommendations est mis à jour après l’assimilation du flux (2-8 heures).</li><li>Les recommandations et les attributs d’article existants s’affichent jusqu’à ce que des mises à jour soient disponibles.</li><li>La recherche catalogue est mise à jour après l’assimilation du flux (2-8 heures) et après l’index catalogue suivant (3-8 heures). La recherche catalogue est mise à jour dans un délai de 5 à 16 heures au total.</li></ul> |
| Article supprimé du catalogue via l’interface utilisateur ou l’API de la Cible | <ul><li>Recommendations est mis à jour dans les 15 minutes.</li><li>Les recommandations et les attributs d’article existants s’affichent jusqu’à ce que des mises à jour soient disponibles.</li><li>La recherche catalogue est mise à jour après l’index catalogue (3-8 heures).</li></ul> |
| Élément ajouté au catalogue par mbox ou API | <ul><li>Recommendations est mis à jour après l’exécution de l’algorithme. Les exécutions d’algorithmes sont planifiées toutes les 12 heures pour les algorithmes de 1 à 2 jours et toutes les 24 heures pour les algorithmes de plus de 7 jours.</li><li>Les recommandations existantes s’affichent jusqu’à ce que des mises à jour soient disponibles si l’élément ajouté n’est pas une clé demandée.</li><li>Les recommandations de sauvegarde s’affichent jusqu’à ce que des mises à jour soient disponibles si l’élément ajouté est une clé demandée.</li><li>La recherche catalogue est mise à jour après l’index catalogue (3-8 heures).</li></ul> |
| Élément ajouté au catalogue par flux | <ul><li>Recommendations est mis à jour après l’assimilation du flux (2 à 8 heures). Les exécutions d’algorithmes suivantes sont planifiées toutes les 12 heures pour les algorithmes de 1 à 2 jours et toutes les 24 heures pour les algorithmes de plus de 7 jours. Recommendations est mis à jour dans un délai de 2 à 32 heures au total.</li><li>Les recommandations existantes s’affichent jusqu’à ce que des mises à jour soient disponibles si l’élément ajouté n’est pas une clé demandée.</li><li>Les recommandations de sauvegarde s’affichent jusqu’à ce que des mises à jour soient disponibles si l’élément ajouté est une clé demandée.</li><li>La recherche catalogue est mise à jour après l’assimilation du flux (2-8 heures) et après l’index catalogue (3-8 heures). La recherche catalogue est mise à jour dans un délai de 5 à 16 heures au total.</li></ul> |

Après l’importation d’un fichier de flux ou la réception de mises à jour d’entité par le biais de l’API ou de la mbox, les modifications suivantes sont répercutées en moins de 60 minutes :

* Si un élément a été précédemment exclu mais doit maintenant être inclus, l’élément sera inclus lors de la prochaine exécution de l’algorithme (12-24 heures).

   Cette situation se produit car [!DNL Target] applique des exclusions en ligne et hors ligne. Lorsqu’un élément est récemment exclu, l’exclusion en ligne s’applique rapidement. Lorsqu’un élément est récemment inclus, l’exclusion en ligne disparaît rapidement, mais l’exclusion hors ligne disparaît jusqu’à l’exécution de l’algorithme suivant.

* Si un élément a été précédemment inclus mais doit maintenant être exclu, l’élément est exclu selon les &quot;attributs d’élément mis à jour...&quot;. ligne de temps décrite ci-dessus en fonction de la source du flux (15 minutes par mbox/API ou 12 à 24 heures par flux).

Les modifications suivantes ne sont pas prises en compte avant que l’algorithme suivant ne s’exécute (dans les 12 à 24 heures) :

* Les attributs d’élément utilisés dans les règles de collection utilisées pour l’activité.
* Les attributs d’élément utilisés dans une promotion basée sur un attribut ou une collection associée à l’activité.
* Une catégorie d’éléments où l’élément apparaît pour une « catégorie en cours » ou une « catégorie préférée » dans l’algorithme Meilleures ventes ou Le plus consulté.
* Un classement des éléments recommandés lorsque l’attribut modifié est un attribut personnalisé utilisé comme clé personnalisée pour un algorithme.
* Classement des éléments recommandés en fonction d’un ou de plusieurs attributs modifiés lorsque la logique de recommandation est &quot;Éléments avec des attributs similaires&quot;, lorsque des facteurs de pondération &quot;Similarité de contenu&quot; sont utilisés ou lorsque des facteurs de pondération &quot;Attribut&quot; sont utilisés.

>[!NOTE]
>
>Un fichier de flux est considéré comme importé lorsque son état passe de « Importation des éléments » à « Préparation des mises à jour de l’index de recherche ». Les mises à jour peuvent prendre plus de 60 minutes pour être reflétées dans l’interface utilisateur de la recherche de catalogue ; La recherche catalogue est à jour lorsque l’état du flux devient &quot;Mises à jour terminées&quot;. Même si la recherche catalogue n’est pas encore à jour, votre site reflète les mises à jour des périodes répertoriées ci-dessus. La durée de mise à jour de l’index de recherche catalogue la plus récente s’affiche sur la page Recherche catalogue.

## Combien de temps faut-il pour qu&#39;une modification de la configuration de mes paramètres d&#39;activité, d&#39;offre, de promotions ou de critères [!UICONTROL Recommendations] soit répercutée sur mon site ?

* Une modification des paramètres de promotion peut prendre jusqu’à cinq heures pour être reflétée sur site.
* Une modification des autres paramètres de critère peut ne pas être prise en compte avant la prochaine exécution de l’algorithme :

   * Certains paramètres de critère (par exemple, &quot;ajout d’une règle d’inclusion dynamique&quot;) sont immédiatement reflétés.
   * D’autres paramètres de critères (par exemple, &quot;suppression d’une règle d’inclusion dynamique&quot;, changement de fenêtre de recherche en amont, etc.) ne peuvent pas être incorporés avant la prochaine exécution de l’algorithme.
   * Les exécutions d’algorithmes sont déclenchées par ces modifications mais peuvent prendre jusqu’à 24 heures. Les algorithmes s’exécutent également toutes les 12 à 24 heures.

## Combien de temps faut-il pour que le comportement d’un utilisateur (par exemple, cliquer sur le produit A et acheter le produit B) se reflète dans les recommandations *que reçoit* l’utilisateur ?

* Le produit/contenu actuellement affiché/acheté influence les recommandations que l’utilisateur reçoit sur la même demande de contenu de page vue/Cible.
* Le comportement historique des utilisateurs, tel que &quot;dernier produit consulté&quot;, &quot;produit le plus consulté&quot; et l’historique d’affichage/d’achat global est mis à jour avec cette demande et influence les recommandations que l’utilisateur reçoit sur la prochaine demande de contenu de page vue/Cible. Par exemple, les algorithmes &quot;Éléments récemment consultés&quot; et &quot;Éléments recommandés pour vous&quot; sont mis à jour avec chaque vue/achat de produit et sont répercutés sur la demande de contenu suivante.

## Combien de temps faut-il pour que le comportement d&#39;un utilisateur (par exemple, cliquer sur le produit A et acheter le produit B) soit reflété dans les recommandations *que les autres* utilisateurs reçoivent ?

Le comportement des utilisateurs dans l’agrégat est intégré au traitement des algorithmes hors ligne, chaque exécution d’algorithme ayant lieu toutes les 12 à 24 heures.

## Que dois-je faire si des caractères spéciaux rompent ma matrice ?{#section_D27214116EE443638A60887C7D1C534E}

Utilisez des valeurs échappées dans JavaScript. Les guillemets ( &quot; ) peuvent rompre la matrice. Le fragment de code suivant est un exemple de valeurs échappées :

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## Pourquoi tous les critères, y compris les critères personnalisés, ne sont-ils pas disponibles pour sélection lors de la création d’une activité de recommandations ? {#section_B2265AC8B8A94E0298D495A05C5D817F}

Les critères disponibles sont basés sur la catégorie actuelle. Lorsque vous créez des offres de recommandations, le sélecteur d’algorithme affiche les critères en fonction de l’ID de catégorie.

Si l’emplacement sur lequel vous appliquez ce critère ne contient pas l’ID de catégorie, certains critères ne sont pas disponibles dans le sélecteur d’algorithmes.

Si vous utilisez un emplacement où l’ID de catégorie est présent dans la mbox, le sélecteur de critères contient tous les critères applicables.

Target comporte un paramètre [Filtrer les critères incompatibles](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) permettant de contrôler le filtrage intelligent du sélecteur d’algorithmes.

>[!NOTE]
>
>Ce paramètre s’applique seulement aux activités créées dans le compositeur d’expérience visuelle. Ce paramètre ne s’applique pas aux activités créées dans le compositeur d’expérience d’après les formulaires (Target ne dispose pas de contexte d’emplacement).

Pour accéder au paramètre [!UICONTROL Filtrer les critères incompatibles], cliquez sur [!UICONTROL Recommandations] > [!UICONTROL Paramètres] :

![](assets/recs_settings_filter.png)

Si le paramètre [!UICONTROL Filtrer les critères incompatibles] n’est PAS activé, Target ne filtre pas les algorithmes dans le sélecteur d’algorithmes et tous les algorithmes s’affichent.

Si le paramètre [!UICONTROL Filtrer les critères incompatibles] est activé, dans les activités du compositeur d’expérience visuelle, Target lit les paramètres entityId et categoryId à partir de l’emplacement sélectionné, puis affiche des algorithmes basés sur `currentItem|currentCategory` (si des valeurs respectives sont présentes à cet emplacement). Par conséquent, par défaut, seuls les algorithmes compatibles pour l’emplacement sélectionné sont affichés dans le sélecteur d’algorithmes.

Si le paramètre [!UICONTROL Filtrer les critères incompatibles] est activé, vous pouvez toujours afficher des algorithmes non compatibles en désélectionnant la case [!UICONTROL Compatible] lors de la sélection des critères.

![](assets/compatible_checkbox.png)

La liste suivante contient des cas spéciaux pour lesquels Target n’affiche pas la case [!UICONTROL Compatible] :

* Les paramètres entityId et categoryId sont présents à l’emplacement, puis rien n’est filtré.
* Vous utilisez [!DNL mbox.js] version 55 ou antérieure.
* Aucun appel de mbox n’est déclenché depuis la page (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* Les paramètres de Target ne sont pas définis.

## Que dois-je faire si une collection dans Recommandations atteint zéro (0) ?  {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

Tenez compte des informations suivantes si vous voyez une collection atteindre zéro qui n’était pas auparavant à zéro :

* Vous pouvez réenregistrer la collection et voir si elle met à jour son numéro. En réenregistrant, la collection exécute à nouveau tous les algorithmes qui utilisent cette collection.
* Êtes-vous dans le bon environnement ? Accédez à [!DNL /target/products.html#recsSettings] pour revérifier (comme illustré ci-dessous).

   ![](assets/product_catalog.png)

* Votre index est-il à jour ? Accédez à [!DNL /target/products.html#productSearch] et vérifiez le nombre d’heures d’ancienneté de l’index (par exemple, &quot;Indexé il y a 3 heures&quot;). Vous pouvez actualiser l’index si nécessaire.
* Avez-vous modifié un élément dans le flux ou dans la couche de données qui fait que vos entités ne correspondent plus aux règles de collecte ? Assurez-vous que la CASSE correspond (sensible à la casse).
* Le flux a-t-il fonctionné correctement ? Quelqu’un a-t-il modifié le répertoire FTP, le mot de passe, etc. ?
* Target fait de son mieux pour que les mises à jour de la diffusion (sur la page/l’application du client) soient effectuées le plus rapidement possible. Néanmoins, la Cible doit également fournir une certaine représentation dans l’interface utilisateur au spécialiste du marketing. La cible ne retarde pas la mise à jour des diffusions à attendre que les mises à jour de l’interface utilisateur soient synchronisées. Vous pouvez utiliser [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md) pour voir ce qui se trouve dans le système au moment où une demande arrive.

## Quelle est la différence entre la pondération générale des attributs et la pondération des attributs spécifiques à la similarité de contenu ?{#section_FCD96598CBB44B16A4C6C084649928FF}

La pondération des attributs existe sous deux formes : « pondération standard des attributs » et « pondération des attributs de similarité de contenu ».

La « pondération standard des attributs » s’applique à la plupart, ou même à tous les types de critères (et pas seulement à la similarité de contenu). Ce type de pondération donne plus de poids à certaines valeurs d’attribut. Dans l’exemple suivant, les produits Nike obtiennent un bosse dans les recommandations de sortie.

![](assets/attribute_weighting_example.png)

La « pondération des attributs de similarité de contenu » s’applique uniquement aux critères de similarité de contenu.

Ce type de pondération est plus dynamique et repose sur la « clé de recommandation » actuelle (l’élément actuellement consulté). Dans l’exemple suivant (marque 16x), si un visiteur regardait des baskets Nike, il est plus susceptible de se voir recommander d’autres produits Nike (pas nécessairement seulement des baskets) plutôt que des baskets de concurrents. Si un visiteur visionne des baskets Adidas, ce visiteur est plus susceptible d’être recommandé pour les produits Adidas.

![](assets/content_similarity_example.png)

## Pourquoi [!DNL Target] est-il parfois incapable d&#39;afficher des recommandations ? {#section_DB3F40673AED42228E407C05437D99E9}

Il arrive parfois que Target ne parvienne pas à afficher des recommandations en raison du faible nombre de recommandations disponibles.

Le nombre de valeurs générées par critère est trois fois le nombre d’entités spécifiées dans la conception. Le filtrage d’exécution (par exemple la correspondance d’attributs inventaire/mbox) est appliqué une fois les valeurs générées 3 fois, aussi est-il possible que moins de 3 valeurs soient générées au moment de la livraison. Pour atténuer cette situation, augmentez le nombre d&#39;entités dans la conception en masquant d&#39;autres entités.

Le JavaScript suivant peut être utilisé au début de la conception pour augmenter le nombre d’entités demandées. Dans cet exemple, le nombre d’entités demandées serait de 30 (3x10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## Quelle est la taille limite d’un appel d’API pour les produits à insérer/mettre à jour ? Puis-je mettre à jour 50 000 produits en un seul appel en utilisant l’API au lieu d’un flux ?  {#section_434FE1F187B7436AA39B7C14C7895168}

Cible impose une limite de 50 Mo de publication au niveau de l’application ; toutefois, ce n’est que lorsque vous transmettez l’en-tête de type de contenu `application/x-www-form-urlencoded`.

Vous pourriez certainement essayer d’envoyer 50 000 produits en un seul appel. Si elle échoue, vous pouvez la diviser en lots. Adobe recommande aux clients de diviser leurs appels en 5 000 ou 10 000 lots de produits afin de réduire la probabilité d’expiration en raison de la charge du système.

## Dois-je spécifier le nom de la mbox lors de la création de critères Recommendations, de promotions ou de règles de test de modèle ? {#section_FFA42ABCC5954B48A46526E32A3A88A2}

Lors de la création d’une règle de test de critère de recommandation, de promotion ou de modèle basée sur un paramètre mbox, `mboxParameter` ne vous demande plus `mboxName`. Le nom de mbox est désormais optionnel. Cette modification vous permet d’utiliser les paramètres de plusieurs mbox ou de référencer un paramètre qui n’a pas encore été enregistré.

Pour sélectionner le paramètre désiré :

* Lors de la création d’une règle de test de critère, de promotion ou de modèle, sélectionnez un nom de paramètre dans la liste. Début de saisie des premiers caractères du nom de paramètre souhaité ou de saisie du nom complet du paramètre souhaité.
* Si vous vous souvenez du nom de mbox, mais pas du nom du paramètre, utilisez la case à cocher pour filtrer une mbox connue qui transmet le paramètre désiré.

Quelle que soit la méthode, il n’existe aucun lien entre la mbox et le paramètre. Les critères, la promotion ou la règle de test de modèle fonctionnent selon un paramètre dans toutes les mbox qui transmettent ce paramètre.

Si vous modifiez une règle de test de critère, de promotion ou de modèle existante, le critère de filtrage s’affiche avec le nom mbox fourni lors de la création.

## Pourquoi ne puis-je pas enregistrer mon activité de Recommandations héritée après avoir défini une nouvelle audience ?  {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

Assurez-vous que le nom de l’audience est unique. Si le nom que vous lui avez donné est celui d’une audience déjà existante, vous ne pouvez pas enregistrer votre activité de Recommandations héritée (activité de Recommandations créée avant octobre 2016).

## Quelle est la taille maximale d’un fichier CSV pour un chargement de flux ?  {#section_20F1AF4839A447B9889B246D6E873538}

Le nombre de lignes ou la taille de fichier pour le chargement de flux d’un fichier CSV sont illimités. Toutefois, il est recommandé de limiter la taille du fichier CSV à 1 Go afin d’éviter les erreurs lors du processus de téléchargement des fichiers. Si la taille du fichier dépasse 1 Go, il peut idéalement être divisé en plusieurs fichiers de flux. Le nombre de colonnes d’attributs personnalisés est limité à 100. Le nombre de caractères des attributs personnalisés est limité à 4 096. D&#39;autres limites sur la longueur des colonnes obligatoires sont disponibles sur la [page Limites de Cible](/help/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1).

## Puis-je exclure dynamiquement une entité ? {#exclude}

Dans la chaîne de requêtes, vous pouvez transférer des ID d’entité à des entités que vous souhaitez exclure de vos recommandations. Par exemple, vous pouvez exclure les articles qui se trouvent déjà dans le panier.

Pour activer la fonctionnalité d’exclusion, utilisez le paramètre mbox `excludedIds`. Ce paramètre pointe sur une liste d’ID d’entité séparés par des virgules. Par exemple, `mboxCreate(..., "excludedIds=1,2,3,4,5")`. La valeur est envoyée lors de la demande de recommandations.

L&#39;exclusion est effectuée pour l&#39;appel de Cible en cours uniquement ; les éléments ne sont pas exclus lors des appels de Cible suivants, sauf si la valeur `excludedIds` est retransmise. Pour exclure des éléments du panier des recommandations sur chaque page, continuez à transmettre la valeur `excludedIds` sur chaque page.

>[!NOTE]
>
>Si un trop grand nombre d’entités sont exclues, les recommandations se comportent comme s’il n’y avait pas assez d’entités pour remplir le modèle de recommandation.

Pour exclure `entityIds`, ajoutez le jeton `&excludes=${mbox.excludedIds}` à l’URL de contenu de l’offre. Lorsque l’URL de contenu est extraite, les paramètres requis sont substitués en utilisant les paramètres de requête mbox actuels.

Par défaut, cette fonctionnalité est activée pour les recommandations nouvellement créées. Les recommandations existantes doivent être enregistrées pour prendre en charge les Entités exclues dynamiquement.

## Que signifie la réponse NO_CONTENT parfois renvoyée dans la trace de contenu Recommendations ?

NO_CONTENT est renvoyé lorsque des recommandations ne sont pas disponibles pour la combinaison algorithme et clé demandée. En règle générale, cette situation se produit lorsque les sauvegardes sont désactivées pour l’algorithme et qu’une ou plusieurs des conditions suivantes sont également vérifiées :

* Les résultats ne sont pas encore prêts.

   Cette situation se produit généralement lors de la première enregistrement d’une activité nouvellement créée ou après des modifications de configuration apportées à la collection, aux critères ou aux promotions utilisés dans l’activité.

* Les résultats sont prêts, mais pas encore mis en cache sur le serveur Edge le plus proche, pour la combinaison algorithme/clé demandée.

   La requête initie une opération de mise en cache. Par conséquent, ce problème doit être résolu après quelques rechargements de page et/ou quelques minutes.

* Les résultats sont prêts, mais pas disponibles pour la valeur de clé fournie.

   Cette situation survient généralement lors de la demande de recommandations pour un élément ajouté au catalogue après l’exécution de l’algorithme le plus récent et se résoudra après la prochaine exécution de l’algorithme.

* Le rendu partiel du modèle est désactivé et les résultats disponibles ne sont pas suffisants pour remplir le modèle.

   Cette situation se produit généralement lorsque vous disposez d’une règle d’inclusion dynamique, qui filtres agressivement de nombreux éléments à partir des résultats possibles. Pour éviter toute situation, activez les sauvegardes et n’appliquez pas la règle d’inclusion aux sauvegardes, ou utilisez les critères de manière séquentielle avec un critère filtré moins agressif.

## Les recommandations basées sur les éléments récemment consultés persistent-elles sur plusieurs périphériques pour un seul visiteur ? {#persist-across-devices}

Lorsqu&#39;un visiteur lance une session, l&#39;ID de session est lié à une seule machine Edge et un cache de profil temporaire est stocké sur cette machine Edge. Les requêtes suivantes de la même session lisent ce cache de profil, y compris les éléments récemment consultés.

Lorsque la session se termine (généralement, lorsqu’elle expire après 30 minutes de non-activité), l’état de la session, y compris les éléments récemment consultés, est ensuite conservé dans un enregistrement d’profil plus permanent sur la même limite géographique.

Les sessions suivantes de différents périphériques peuvent alors accéder à ces éléments récemment consultés tant que la nouvelle session est liée au profil client via le même ID de Marketing Cloud (MCID), ID d’Experience Cloud (ECID) ou ID de client/mbox3rdPartyId.

Si un visiteur a deux sessions principales en même temps, les éléments récemment consultés sur un périphérique ne mettent pas à jour les éléments récemment consultés sur l’autre périphérique, sauf si les périphériques sont obligés de partager l’ID de session. Il existe une solution potentielle à ce problème, mais [!DNL Target] ne prend pas directement en charge le partage d&#39;un ID de session sur plusieurs périphériques. Le client doit gérer lui-même ce partage d’ID.

Ce comportement se produit toujours si un visiteur est principal sur un périphérique, puis devient principal sur l’autre périphérique quelques minutes plus tard. La session du premier périphérique n’expire pas pendant 30 minutes et il peut y avoir jusqu’à cinq minutes de retard avant que l’état du profil ne soit écrit à l’état permanent et traité. Comptez 35 minutes pour que la session expire et que le profil soit stocké lors du test de ce comportement.

Si le visiteur ne dispose pas de deux sessions principales en même temps, les éléments récemment consultés sur un périphérique mettent à jour les éléments récemment consultés sur l’autre périphérique tant que la session est terminée. Comptez 35 minutes pour que la session expire lors du test de ce comportement.
