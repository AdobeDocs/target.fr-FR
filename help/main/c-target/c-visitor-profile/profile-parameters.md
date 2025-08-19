---
keywords: script de profil;attributs de script de profil;bonnes pratiques de script de profil;déboguer;débogage;scripts;scripts de profil;attributs;attribut;paramètre
description: Découvrez les attributs spécifiques au visiteur, stockés dans le profil du visiteur, pour fournir des informations sur ce dernier, qui peuvent être utilisées dans vos activités Adobe  [!DNL Target] .
title: Que sont les attributs de profil ?
feature: Audiences
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: 356b04745b58670b4bf39be929e785b8490d78ff
workflow-type: tm+mt
source-wordcount: '2426'
ht-degree: 92%

---

# Attributs de profil

Les attributs de profil dans [!DNL Adobe Target] sont des paramètres spécifiques au visiteur. Ces attributs sont stockés dans le profil du visiteur pour fournir des informations sur le visiteur, qui peuvent être utilisées dans vos activités.

Un profil utilisateur contient des informations démographiques et comportementales sur le visiteur d’une page web. Ces informations peuvent inclure l’âge, le genre, les produits achetés, la dernière heure de la visite, etc. [!DNL Target] utilise ces informations pour personnaliser le contenu diffusé à ce visiteur ou à cette visiteuse.

Lorsqu’un visiteur parcourt votre site web ou revient pour une nouvelle session, les attributs de profil enregistrés dans le profil peuvent servir à cibler le contenu ou à consigner des informations pour le filtrage de segments.

Pour configurer les attributs de profil :

1. Cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Profile Scripts.]**

   ![Onglet Scripts de profil](/help/main/c-target/c-visitor-profile/assets/create-script.png)

1. Cliquez sur **[!UICONTROL Create Script]**.

   ![Boîte de dialogue Créer un script de profil](/help/main/c-target/c-visitor-profile/assets/profile-script.png)

   Les types suivants d’attributs de profil sont disponibles :

   | Type de paramètre | Description |
   |--- |--- |
   | mbox | Transmis directement au moyen du code de page lors de la création de la mbox. Voir [Transférer les paramètres à une mbox globale](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=fr){target=_blank} dans le *Guide de développement de Target*..<P>**Remarque** : [!DNL Target] est limité à 50 attributs de profil uniques par appel de mbox. Si vous devez transmettre plus de 50 attributs de profil à [!DNL Target], transmettez-les à l’aide de la méthode [!UICONTROL Profile Update API]. Pour plus d’informations, consultez [Mise à jour de profils](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=fr){target=_blank} dans le *Guide du développeur de Target*. |
   | Profil | Défini directement avec un extrait de code JavaScript. Ces extraits peuvent stocker les totaux en cours, tel que le total des dépenses d’un client ou d’une cliente. Ils sont exécutés pour chaque requête de mbox. Voir *Attributs de script de profil* ci-dessous. |

## Attributs de script de profil {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Définissez un attribut de script de profil avec son extrait de code JavaScript associé.

Vous pouvez utiliser des scripts de profil pour capturer les attributs des visiteurs au cours de plusieurs visites. Les scripts de profil sont des extraits de code définis dans [!DNL Target] à l’aide d’une forme de code JavaScript côté serveur. Par exemple, vous pouvez utiliser un script de profil pour capturer la fréquence à laquelle un visiteur visite votre site, et la date de sa dernière visite.

Les scripts de profil sont différents des paramètres de profil. Les paramètres de profil capturent des informations sur les visiteurs grâce à l’implémentation du code mbox de [!DNL Target].

## Création de scripts de profil {#section_CB02F8B97CAF407DA84F7591A7504810}

Les scripts de profil sont disponibles sous l’onglet [!UICONTROL Audiences] de l’interface [!DNL Target] .

Pour ajouter un script de profil, cliquez sur l’onglet **[!UICONTROL Profile Scripts]**, **[!UICONTROL Create Script]**, puis écrivez votre script.

Ou

Pour copier un script de profil existant, à partir de la liste [!UICONTROL Profile Scripts], cliquez sur l’icône représentant des points de suspension pour sélectionner le script souhaité, puis cliquez sur **[!UICONTROL Duplicate]**.

Vous pouvez ensuite modifier l’audience pour créer une audience similaire.

Les scripts de profil exécutent des « catchers » d’attribut de profil pour chaque requête d’emplacement. Lorsqu’une requête d’emplacement est reçue, [!DNL Target] détermine quelle activité doit exécuter et afficher le contenu approprié à cette activité et à cette expérience. [!DNL Target] effectue également le suivi de la réussite de l’activité et exécute tous les scripts de profil pertinents. Ce processus vous permet de suivre les informations relatives à la visite, comme le lieu, l’heure et le nombre de fois qu’un visiteur a accédé à votre site, ses achats précédents, etc. Ces informations sont alors ajoutées au profil du visiteur afin que vous puissiez mieux suivre l’activité de ce visiteur sur votre site.

Les attributs de script de profil contiennent les balises `user.` insérées avant le nom de l’attribut. Par exemple :

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

Gardez à l’esprit les informations suivantes :

* Reportez-vous aux attributs de script de profil (y compris lui-même) dans le code avec `user.get('parameterName')`.
* Enregistrez les variables susceptibles d’être sélectionnées lors de la prochaine exécution du script (dans la requête de mbox suivante) avec `user.setLocal('variable_name', 'value')`. Référencez la variable avec `user.getLocal('variable_name')`. Ce processus s’avère utile lorsque vous souhaitez référencer la date et l’heure de la dernière requête.

  Ces valeurs persistent comme un script de profil, mais vous n’y avez accès que depuis le script dans lequel elles ont été définies.

* Les paramètres et les valeurs sont sensibles à la casse. Respectez la casse des paramètres et valeurs que vous recevez durant l’activité ou le test.
* Pour plus d’informations sur la syntaxe JavaScript, consultez la section « Référence JavaScript pour les paramètres de profil de script » ci-dessous.
* Le paramètre reste dans le profil après désactivation du script. Les utilisateurs dont les profils contiennent déjà un paramètre utilisé dans une audience d’activité sont inclus dans cette activité.
* Les scripts de profil ne peuvent pas être supprimés lorsqu’ils sont utilisés dans une activité.
* Ajout d’une remarque indiquant que la création de scripts de profil dépendants qui utilisent le résultat d’un script de profil dans un autre script n’est pas recommandée. L’ordre d’exécution du script de profil n’est pas garanti.

## Affichage des cartes d’informations de script de profil {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

Vous pouvez afficher des cartes pop-up d’informations de script de profil similaires aux cartes d’informations d’offre. Ces cartes d’informations de script de profil vous permettent d’afficher la liste des activités faisant référence au script de profil sélectionné, ainsi que d’autres métadonnées utiles.

Par exemple, la carte d’informations de script de profil suivante est accessible en cliquant sur l’icône [!UICONTROL Info] du script de profil souhaité dans la liste ([!UICONTROL Audiences] > [!UICONTROL Profile Scripts]).

L’onglet [!UICONTROL Script Info] contient les informations suivantes : nom, description et code de script.

![Carte d’informations du script de profil](assets/profile_script_info_card.png)

Cliquez sur **[!UICONTROL View full details]** pour afficher les audiences et les activités qui font référence au script de profil sélectionné.

![Carte d’informations du script de profil > Onglet Utilisation du script](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>L’onglet [!UICONTROL Script Usage] n’affiche pas les activités qui font référence au script de profil sélectionné dans les situations suivantes :
>
> * L’activité est à l’état [!UICONTROL Draft].
> * Le contenu ou l’offre utilisé dans l’activité utilise des variables de script (une offre insérée au sein de l’activité ou une offre dans la bibliothèque d’offres).

## Désactivation par Target des scripts de profil dans certaines situations {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

Désactivation automatique des scripts de profil par [!DNL Target], par exemple si leur exécution est trop longue ou s’ils contiennent trop d’instructions.

Lorsque le profil de script est désactivé, une icône d’alerte jaune s’affiche en regard du script de profil dans l’interface utilisateur de Target, comme illustré ci-dessous :

![image profile_script_invalid](assets/profile_script_invalid.png)

Passez la souris sur l’icône pour afficher les détails de l’erreur, comme illustré ci-dessous :

![image profile_script_hover](assets/profile_script_hover.png)

Voici quelques-unes des raisons qui poussent généralement le système à désactiver les scripts de profil :

* Une variable indéfinie est référencée.
* Une valeur incorrecte est référencée. Cette erreur survient généralement lors du référencement de valeurs d’URL et d’autres données saisies par l’utilisateur sans validation correcte.
* Trop d’instructions JavaScript sont utilisées. [!DNL Target] est limité à 2 000 instructions JavaScript par script. Toutefois, une simple lecture manuelle du script JavaScript ne permet pas de calculer cette limite d’instructions. Par exemple, Rhino traite tous les appels de fonction et les « nouveaux » appels comme 100 instructions. Tout appel à une fonction utilise 100 instructions. Par ailleurs, le nombre d’instructions peut aussi dépendre de la taille des données saisies, telles les valeurs d’URL.
* Le non-respect des [bonnes pratiques](/help/main/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) répertoriées ci-dessous.

## Bonnes pratiques {#best}

Les recommandations ci-dessous visent à vous aider à créer des scripts de profil simplifiés avec un minimum d’erreurs en rédigeant un code qui échoue normalement, de sorte qu’ils sont traités sans forcer un arrêt des scripts du système. Ces instructions sont la synthèse de bonnes pratiques dont l’efficacité a été prouvée. Elles doivent être appliquées conjointement avec les principes et recommandations stipulés par la communauté de développement Rhino.

* Dans le script utilisateur, définissez comme variable locale la valeur actuelle du script. Définissez un basculement sur une chaîne vide.
* Validez la variable locale en vérifiant qu’il ne s’agit pas d’une chaîne vide.
* Utilisez les fonctions de manipulation de type chaîne plutôt que des expressions régulières.
* Utilisez des boucles for limitées plutôt que des boucles for ou while ouvertes.
* Ne dépassez pas 1 300 caractères ou 50 itérations de boucle.
* Ne dépassez pas 2 000 instructions JavaScript. [!DNL Target] est limité à 2 000 instructions JavaScript par script. Toutefois, une simple lecture manuelle du script JavaScript ne permet pas de calculer cette limite d’instructions. Par exemple, Rhino traite tous les appels de fonction et les « nouveaux » appels comme 100 instructions. Par ailleurs, le nombre d’instructions peut aussi dépendre de la taille des données saisies, telles les valeurs d’URL.
* Faites attention non seulement aux performances du script, mais aussi aux performances combinées de tous les scripts. [!DNL Adobe] recommande d’utiliser moins de 5 000 instructions au total. Compter le nombre d’instructions n’est pas évident, mais ce qu’il faut retenir est que les scripts supérieurs à 2 000 instructions sont automatiquement désactivés. Le nombre de scripts de profil actif ne doit pas être supérieur à 300. Chaque script est exécuté à chaque appel de mbox. Exécutez uniquement le nombre de scripts nécessaire.
* Dans une expression regex, un point étoile n’est presque jamais nécessaire au début (par exemple : `/.*match/`, `/a|.*b/`). La recherche regex commence à partir de toutes les positions dans une chaîne (sauf si elle est liée à `^`). Par conséquent, le point-étoile est déjà sous-entendu. L’exécution d’un script peut être interrompue si une expression regex de ce type est mise en correspondance avec des données d’entrée suffisamment longues (qui peuvent ne pas dépasser quelques centaines de caractères).
* En cas d’échec global, encadrez le script dans un try/catch.
* Les recommandations suivantes peuvent vous aider à limiter la complexité des scripts de profil. Les scripts de profil peuvent exécuter un nombre limité d’instructions.

  Bonne pratique :

   * Veillez à ce que les scripts de profil restent petits et aussi simples que possible.
   * Évitez les expressions régulières ou utilisez uniquement des expressions régulières simples. Même des expressions simples peuvent nécessiter de nombreuses instructions d’évaluation.
   * Évitez les approches récursives.
   * La performance des scripts de profil doit être testée avant qu’ils ne soient ajoutés à [!DNL Target]. Tous les scripts de profil s’exécutent dans chaque requête de mbox. Si les scripts de profil ne s’exécutent pas correctement, l’exécution des requêtes de mbox est plus longue, ce qui peut avoir un impact sur le trafic et la conversion.
   * Si les scripts de profil deviennent trop complexes, pensez à utiliser des [jetons de réponse](/help/main/administrating-target/response-tokens.md).

* Pour plus d’informations, consultez la documentation sur le moteur JS Rhino.

## Déboguer les scripts de profil {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

Les méthodes suivantes permettent de déboguer les scripts de profil :

>[!NOTE]
>
>Utiliser [!DNL console.log] dans un script de profil ne permet pas de produire la valeur du profil, car les scripts de profil s’exécutent côté serveur.

* **Ajouter des scripts de profil comme jetons de réponse aux scripts de profil de débogage :**

  Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]**, cliquez sur **[!UICONTROL Response Tokens]**, puis activez le script de profil à déboguer.

  Chaque fois que vous chargez une page comportant [!DNL Target]pour votre site, une partie de la réponse de [!DNL Target] contient votre valeur pour le script de profil donné, comme indiqué ci-dessous :

  ![image debug_profile_script_1](assets/debug_profile_script_1.png)

* **Utiliser l’outil de débogage mboxTrace pour déboguer les scripts de profil.**

  Cette méthode nécessite un jeton d’autorisation que vous pouvez générer en cliquant sur **[!UICONTROL Target]** > **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Generate Authorization Token]** dans la section [!UICONTROL Debugger tools] .

  Vous ajoutez ensuite ces deux paramètres à l’URL de votre page après le « ? » : `mboxTrace=window&authorization=YOURTOKEN`.

  Ajouter ces paramètres fournit un peu plus d’informations que le jeton de réponse, car vous obtenez un instantané avant exécution et un instantané après exécution de votre profil. Cela affiche également tous vos profils disponibles.

  ![image debug_profile_script_2](assets/debug_profile_script_2.png)

## FAQ sur le script de profil {#section_1389497BB6D84FC38958AE43AAA6E712}

**Est-il possible d’utiliser des scripts de profil pour capturer les informations d’une page dans une couche de données ?**

Les scripts de profil ne parviennent pas à lire directement la page, car ils sont exécutés côté serveur. Les données doivent être transmises par le biais d’une requête de mbox ou d’autres [méthodes de transfert de données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}. Une fois que les données se trouvent dans [!DNL Target], les scripts de profil peuvent les lire, sous la forme de paramètre de mbox ou de profil.

## Référence JavaScript pour les paramètres de profil de script

Des connaissances simples en Javascript sont nécessaires pour utiliser efficacement les paramètres de profil de script. Cette section sert de référence rapide pour que vous puissiez exploiter cette fonctionnalité en quelques minutes seulement.

Les paramètres de profil de script se trouvent sous l’onglet mbox/profiles. Vous pouvez écrire des programmes Javascript qui renvoient un type Javascript (chaîne, entier, tableau, etc.).

### Exemples de paramètres de profil de script {#examples}

**Name :** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

Crée une variable pour la mesure du jour en millisecondes. Si le nom de la mbox est `orderThankyouPage`, définissez un attribut de profil utilisateur local (invisible) nommé `lastPurchaseTime` pour montrer la valeur de la date et de l’heure actuelles. La valeur de la dernière heure d’achat est lue et, si elle est définie, [!DNL Target] renvoie le temps écoulé depuis le dernier achat, divisé par le nombre de millisecondes par jour (ce qui donne le nombre de jours depuis le dernier achat).

**Name :** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Crée une variable appelée `frequency`, en l’initialisant à la valeur précédente ou à 0, en l’absence de valeur précédente. Si le nom de la mbox est `orderThankyouPage`, la valeur incrémentée est renvoyée.

**Name :** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Crée une variable appelée `monetaryValue`, en recherchant la valeur actuelle d’un visiteur donné (ou la valeur 0 s’il n’y avait aucune valeur précédente). Si le nom de la mbox est `orderThankyouPage`, la nouvelle valeur monétaire est renvoyée en ajoutant la précédente et la valeur du `orderTotal` paramètre transmis à la mbox.

**Nom :** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

Crée une variable appelée `adobeQA` pour effectuer le suivi d’un utilisateur pour [AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md).

### Objets et méthodes {#objects}

Les objets et méthodes suivantes peuvent être référencés par des paramètres de profil de script :

| Objet ou méthode | Détails |
| --- | --- |
| `page.url` | URL actuelle |
| `page.protocol` | Protocole utilisé pour la page (http, https). |
| `page.domain` | Domaine d’URL actuel (avant la première barre oblique). Par exemple `www.acme.com`, dans `http://www.acme.com/categories/men_jeans?color=blue&size=small`. |
| `page.query` | Chaîne de requête de la page active. Tout ce qui suit le « ? ». Par exemple `blue&size=small`, dans `http://www.acme.com/categories/mens_jeans?color=blue&size=small`. |
| `page.param('<par_name>')` | Valeur du paramètre indiqué par `<par_name>`. Si l’URL actuelle correspond à la page de recherche de Google et que vous avez saisi `page.param('hl')`, vous obtenez « en » pour l’URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`. |
| `page.referrer` | Le même ensemble d’opérations que ci-dessus s’applique à l’URL référent et à l’URL de la page d’entrée (c.-à-d. referrer.url est l’adresse URL du référent). |
| `landing.url`, `landing.protocol`, `landing.query`, et `landing.param` | Semblable à celle de la page, mais pour la page de destination.<P>Pour que l’URL de la page de destination fonctionne comme prévu, définissez : `context` > `browser` > `host`. |
| `mbox.name` | Nom de la mbox active. |
| `mbox.param('<par_name>')` | Un paramètre de mbox par le nom donné dans la mbox active. |
| `profile.get('<par_name>')` | Paramètre du profil utilisateur créé par le client par nom `<par_name>`. Par exemple, si l’utilisateur ou l’utilisatrice définit un paramètre de profil nommé « gender », la valeur peut être extraite à l’aide de « profile.gender ». Renvoie la valeur de « `profile.<par_name>` » définie pour le visiteur actuel ou la visiteuse actuelle ; renvoie la valeur null si aucune valeur n’a été définie. Notez que `profile.get(<par_name>)` a la qualité d’un appel de fonction. |
| `user.get('<par_name>')` | Renvoie la valeur de « `user.<par_name>` » définie pour le visiteur actuel ou la visiteuse actuelle ; renvoie la valeur null si aucune valeur n’a été définie. |
| `user.categoryAffinity` | Renvoie le nom de la meilleure catégorie. |
| `user.categoryAffinities` | Renvoie un tableau avec les catégories les plus appropriées. |
| `user.isFirstSession` | Renvoie vrai s’il s’agit de la première session du visiteur. |
| `user.browser` | Renvoie l’agent utilisateur dans l’en-tête HTTP. À titre d’exemple, vous pouvez créer une cible d’expression pour cibler les utilisateurs Safari uniquement : `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### Opérateurs courants

Tous les opérateurs JavaScript standard sont présents et utilisables. Les opérateurs JavaScript peuvent être utilisés sur des chaînes et des nombres (et sur d’autres types de données). Aperçu rapide :

| Opérateur | Description |
| --- | --- |
| `==` | Indique l’égalité. Est définie sur vrai lorsque les opérandes des deux côtés sont égaux. |
| `!=` | Indique l’inégalité. Est définie sur vrai lorsque les opérandes de part et d’autre ne sont pas égaux. |
| `<` | Indique que la variable à gauche est inférieure à la variable à droite. Est évalué sur false si les variables sont égales. |
| `>` | Indique que la variable à gauche est supérieure à la variable à droite. Est évalué sur false si les variables sont égales. |
| `<=` | Même que `<` sauf si les variables sont égales, elles seront évaluées sur vraies. |
| `>=` | Même que `>` sauf si les variables sont égales, elles seront évaluées sur vraies. |
| `&&` | Applique « ET » de manière logique aux expressions à gauche et à droite - est uniquement vrai lorsque les deux côtés sont vrais (faux dans le cas contraire). |
| `||` | Applique « OU » de manière logique aux expressions à gauche et à droite - est uniquement vrai que si l’un des côtés est vrai (faux dans le cas contraire). |
| `//` | Vérifie si la source contient tous les éléments provenant de la cible booléenne (source Array, cible Array).<br>`//` extrait la sous-chaîne de la target (correspondant à regexp) et la décode `Array/*String*/ decode(String encoding, String regexp, String target)`.<br>Cette fonctionnalité prend également en charge l’utilisation de valeurs de chaîne constantes, de regroupement (`condition1 || condition2) && condition3` et d’expressions régulières `/[^a-z]$/.test(landing.referring.url)`). |

## Vidéo de formation : Scripts de profil ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo fournit des informations sur l’utilisation et la création des scripts de profil.

* Explication du concept de script de profil
* Explication de la différence entre un script de profil et un paramètre de profil
* Création d’un script de profil simple
* Utilisation du menu Jeton disponible pour accéder aux options disponibles
* Activation et désactivation des scripts de profil

>[!VIDEO](https://video.tv.adobe.com/v/17394)
