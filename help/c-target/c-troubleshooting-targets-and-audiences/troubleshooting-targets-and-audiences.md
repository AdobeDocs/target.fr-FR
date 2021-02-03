---
keywords: résolution des problèmes;questions fréquentes;FAQ;forum aux questions;cibles;audiences
description: Liste des questions fréquentes sur les audiences et le ciblage des expériences.
title: FAQ sur les cibles et les Audiences
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 68%

---


# FAQ sur le ciblage et les audiences{#targets-and-audiences-faq}

Liste des questions fréquentes sur les audiences et le ciblage des expériences.

## Comment la Cible évalue-t-elle les URL dans le ciblage ? {#url}

La cible évalue les URL différemment selon que vous utilisez le ciblage d’URL d’audience lors de la création d’une activité ou si vous utilisez le ciblage d’URL lors de la création d’une audience.

Examinez l’URL suivante :

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### Ciblage des URL d’Audience

Pour appliquer le ciblage d’URL d’audience, lors de la création d’une activité, sur la page Expériences (étape 1 du processus guidé en trois étapes), cliquez sur l’icône d’engrenage, cliquez sur Diffusion de page, puis spécifiez l’URL de votre choix.

![URL de la Diffusion de page](/help/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

Le ciblage des URL d’Audience recherche une correspondance URL exacte. Si l’URL correspond, la Cible ne tient pas compte d’une autre logique. Dans l’URL ci-dessus, si l’activité est définie sur se déclencher sur `www.example.com`, l’URL correspond pour les URL suivantes, car le ciblage des URL d’audience n’est pas lié à la requête :

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

Outre le ciblage des audiences sur l’URL, vous pouvez également spécifier des valeurs spécifiques qui peuvent se trouver dans la requête.

### Ciblage d’URL

Pour appliquer le ciblage d’URL, lors de la création d’une audience, cliquez sur Ajouter la règle, sur Pages du site, sélectionnez une option dans la première liste déroulante (Page active, Page précédente ou Landing page), sélectionnez l’URL dans la deuxième liste déroulante, spécifiez un évaluateur, puis spécifiez l’URL de votre choix.

![Pages du site > Page active > URL](/help/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

Le ciblage d’URL transforme l’URL en un ensemble de règles à évaluer :

* Domaine d’URL = `example.com`
* Chemin = chemin1/chemin2/chemin3
* queryStringParam1 = test123
* queryStringParam2 = test7

## Lors de la création de chaînes d’URL complexes, [!DNL Target] évalue-t-il l’intégralité de l’URL ?

Si vous utilisez plusieurs fois le même nom de paramètre dans une chaîne URL, HTTP prend en compte le nom du premier paramètre et ignore les paramètres suivants portant le même nom.

Par exemple, dans la chaîne URL suivante :

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

la première instance du paramètre `Category` est évaluée et le second paramètre `Category` est ignoré.

Il est recommandé d’associer plusieurs valeurs à une seule catégorie, comme illustré ci-dessous :

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## Lors de la création d’audiences, pourquoi les audiences préconfigurées sous Bibliothèque Target apparaissent-elles dans d’autres catégories ?{#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

Les audiences préconfigurées de la catégorie Bibliothèque Target sont des audiences héritées, également présentes dans d’autres catégories. À titre d’exemple, l’audience héritée Bibliothèque Target > Nouveaux visiteurs a un équivalent mis à jour : Profil du visiteur > Nouveau visiteur.

La bonne pratique consiste à utiliser les audiences les plus récentes, car elles sont plus performantes. Toutefois, puisque certains clients continuent peut-être à utiliser des audiences préconfigurées héritées, celles-ci n’ont pas été supprimées de l’interface Target.

## Comment savoir de quelle manière le trafic sera divisé entre les audiences ? {#section_067EEFB956E7465CBF77EC86834470AB}

Par défaut, le trafic est divisé uniformément entre les expériences. Néanmoins, vous pouvez indiquer des cibles en pourcentage pour chaque expérience. Dans ce cas, un nombre aléatoire est généré et utilisé pour choisir l’expérience à afficher. Les pourcentages résultants peuvent ne pas correspondre exactement aux cibles spécifiées, mais un trafic plus élevé signifie que les expériences doivent être fractionnées en tenant davantage compte des objectifs de cible.

## Quelle expérience s’affiche si un utilisateur remplit les conditions requises pour une activité contenant plusieurs expériences avec plusieurs audiences admissibles ?  {#section_94A60B11212D48FD8AB0803C6C7E7253}

L’utilisateur est admissible pour la première expérience/audience qui s’affiche sur la page [!UICONTROL Target] de l’activité.

Par exemple, dans l’illustration suivante, un utilisateur situé en Aquitaine qui utilise un périphérique Windows est admissible pour l’expérience A (audience Windows) et l’expérience C (audience Aquitaine). Cet utilisateur verra s’afficher l’expérience A parce qu’elle figure plus haut que l’expérience C dans la liste de la page Target.

![](assets/audiences_order.png)

## Pourquoi les noms d’une même audience sont-ils différents dans Target, dans Adobe Audience Manager (AAM) et dans la bibliothèque d’audiences dans les services principaux ?{#section_F67E61A607B6444C8DAA4F99C3E95AED}

Les noms d’audience dans [!DNL Target] sont uniques. Toutefois, dans [!DNL AAM] et dans le [!DNL Audience Library], plusieurs audiences peuvent avoir le même nom (si elles se trouvent dans différents dossiers). Si [!DNL Target] rencontre un nom d’audience qui correspond à une audience [!DNL AAM] ou [!DNL Audience Library], [!DNL Target] ajoute « #&lt;number> » au nom.

Vous pouvez, par exemple, avoir les audiences suivantes : « Utilisateurs de PC » (dans [!DNL AAM]) et « Utilisateurs de PC #1 » (dans [!DNL Target]).

## Pourquoi ne puis-je pas renommer une audience ?{#section_54E420556F534D20836E261E253D8B97}

Certaines audiences Target sont prédéfinies ; « Nouveaux visiteurs » et « Visiteurs récurrents », par exemple. Les utilisateurs ne peuvent pas renommer ces audiences prédéfinies.

## Pourquoi tous les paramètres de profil ne s’affichent-ils pas dans l’interface utilisateur de Target ?  {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] est limitée à 50 attributs de profil uniques par appel de mbox. Si vous devez transmettre plus de 50 attributs de profil à [!DNL Target], vous pouvez le faire en appliquant la méthode d’API [!UICONTROL Mise à jour du profil]. Pour en savoir plus, voir [Mise à jour du profil](https://developers.adobetarget.com/api/#authentication-tokens) dans la documentation des API Adobe Target.

## Pourquoi les visiteurs voient-ils des expériences pour une activité AP alors que cela ne devrait pas être le cas ?{#section_41CECEAE0881446A8D9F3B016857914B}

Les activités Automated Personalization sont évaluées une seule fois par session. Si des sessions actives ont été qualifiées pour une expérience particulière et que de nouvelles offres y sont maintenant incorporées, les utilisateurs verront le nouveau contenu en même temps que les offres précédemment affichées. Du fait que leur qualification pour ces expériences est déjà validée, ils continueront de les voir pendant toute la durée de la session. S’il est souhaitable de procéder à cette évaluation pour chaque visite de page unique, vous devez sélectionner le type d’activité XT (ciblage d’expérience).

## Pourquoi les modifications apportées aux audiences créées via l’API ne sont-elles pas reflétées dans l’interface utilisateur Target ?  {#section_6BEB237CAC004A06A290F9644E5BF0FB}

Contrairement aux offres et aux scripts de profil, les modifications apportées par l’API aux audiences créées via Target Standard ne sont actuellement pas resynchronisées sur l’interface utilisateur Target.

## Les chaînes qui représentent des nombres (les nombres à virgule flottante sont également pris en charge) sont considérées comme des nombres.{#strings-that-represent-numbers}

Si la partie gauche et la partie droite des expressions égales peuvent être analysées par un nombre, les deux parties sont considérées comme des nombres et non comme des chaînes.

Par exemple :

| Valeur | Critères de ciblage | Résultats |
| --- | --- | --- |
| 1.0 | est égal à 1 | true |
| 1 | equalsIgnoreCase 1.0 | true |
| 1,230 | est égal à 1 | true |
| 1,500 | est égal à 1,5 | true |
| 1,200 | est inférieur à 2 | true |
| 2 | est supérieur à 3.0 | false |
| 045 | est égal à 45 | true |

Les nombres écrits en notation scientifique sont toujours comparés en tant que chaînes.

Par exemple :

« 4 e -2 » est uniquement égal à « 4 e -2 ». Elle *n’est pas* égale à « 0,04 ».