---
keywords: Script de profil;attributs de script de profil;activités s’excluant mutuellement
description: Découvrez comment utiliser les attributs de profil pour configurer des tests dans Adobe [!DNL Target] qui comparent plusieurs activités, mais ne laissent pas les mêmes visiteurs participer à chaque activité.
title: Puis-je utiliser des scripts de profil pour tester des activités mutuellement exclusives ?
feature: Audiences
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
source-git-commit: 34db233e0790f8ef04309c3f4b5acd12b7cdd5ad
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 74%

---

# Utilisation des scripts de profil pour le test des activités s’excluant mutuellement

Vous pouvez utiliser des attributs de profil dans [!DNL Adobe Target] pour configurer des tests qui comparent deux activités ou plus mais ne laissent pas les mêmes visiteurs participer à chaque activité.

Grâce à ces tests, un visiteur d’une activité n’aura aucune influence sur les résultats des tests des autres activités. Lorsqu’un visiteur participe à plusieurs activités, il peut s’avérer difficile de déterminer si des effets positifs ou négatifs sont ressortis de l’expérience du visiteur sur une seule activité, ou si des interactions entre plusieurs activités ont affecté les résultats d’une ou de plusieurs activités.

Imaginons que vous souhaitiez tester deux branches de votre système d’e-commerce. Vous pouvez tester en rouge le bouton &quot;Ajouter au panier&quot; au lieu de bleu. Vous pouvez aussi tester un nouveau processus de passage en caisse dans lequel le nombre des étapes passe de cinq à deux. Si les deux activités ont le même événement de succès (un achat terminé), il peut être difficile de déterminer si le bouton rouge améliore les conversions ou si ces mêmes conversions ont également été augmentées en raison de l’amélioration du processus de passage en caisse. En séparant les tests en activités s’excluant mutuellement, vous pouvez tester chaque modification une par une.

Tenez compte des informations suivantes lorsque vous utilisez les scripts de profil suivants :

* Le script de profil doit être exécuté avant le lancement de l’activité et le script doit rester inchangé pendant toute la durée de celle-ci.
* Cette technique réduit le volume de trafic dans l’activité, ce qui peut nécessiter une exécution plus longue de l’activité. Vous devez prendre ce facteur en compte lors de l’estimation de la durée de l’activité.

## Configuration de deux activités

Pour répartir les visiteurs dans des groupes qui voient chacun une activité différente, vous devez créer un attribut de profil. Un attribut de profil peut placer un visiteur dans un ou plusieurs groupes. Pour définir un attribut de profil appelé « twogroups », créez le script suivant :

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 100); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` détermine si l’attribut de profil *twogroups* est défini pour le visiteur actif. Si ce n’est pas le cas, aucune autre action n’est nécessaire.

* `var ran_number=Math.floor(Math.random() *100)` déclare une nouvelle variable appelée ran_number, définit sa valeur sur une valeur décimale aléatoire comprise entre 0 et 1, puis la multiplie par 100 et l’arrondit à l’unité inférieure pour créer une plage comprise entre 0 et 100, ce qui s’avère utile pour spécifier un pourcentage de visiteurs qui visualisent l’activité.

* `if (ran_number <= 49)` commence une routine qui détermine le groupe auquel le visiteur appartient. Si le nombre renvoyé est compris entre 0 et 49, le visiteur est affecté au GroupeA. Si le nombre renvoyé est compris entre 50 et 100, le visiteur est affecté au GroupeB. Le groupe détermine l’activité que voit le visiteur.

Après avoir créé l’attribut de profil, configurez la première activité pour cibler la population souhaitée en exigeant que le paramètre de profil utilisateur `user.twogroups` correspond à la valeur spécifiée pour GroupA.

>[!NOTE]
>
>Sélectionnez une mbox plus haut sur la page. Ce code détermine si un visiteur expérimente l’activité. Tant que le navigateur rencontre d’abord une mbox, celle-ci peut être utilisée pour définir cette valeur.

Configurez la seconde campagne pour que le paramètre de profil utilisateur `user.twogroups` corresponde à la valeur spécifiée pour le GroupeB.

## Configuration de trois activités ou davantage

La configuration de trois activités ou plus s’excluant mutuellement est similaire à la configuration de deux campagnes, à condition de modifier l’attribut de profil JavaScript afin de créer un groupe distinct pour chaque activité et de déterminer qui voit chacune d’elles. La génération des nombres aléatoire est différente selon que vous créez un nombre de groupes pair ou impair.

Par exemple, pour créer quatre groupes, utilisez le code JavaScript suivant :

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 100); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

Dans cet exemple, la formule mathématique utilisée pour générer le nombre aléatoire affectant un visiteur à un groupe est la même que celle utilisée avec deux groupes seulement. Une valeur décimale aléatoire est générée, puis arrondie pour créer un entier.

Si vous créez un nombre de groupes impair ou un nombre qui n’est pas divisible par 100, n’arrondissez pas le nombre décimal à un entier. Si vous décidez de ne pas arrondir les nombres décimaux, vous pouvez spécifier des plages de nombres qui ne sont pas des entiers. Pour cela, il vous suffit de modifier la ligne suivante :

`var ran_number=Math.floor(Math.random()*100);`

à :

`var ran_number=Math.random()*100;`

Par exemple, pour répartir les visiteurs dans trois groupes égaux, utilisez le code suivant :

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 100; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
