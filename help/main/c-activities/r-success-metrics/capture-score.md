---
keywords: score de capture, score
description: Découvrez la mesure d’engagement Score de capture dans Adobe [!DNL Target] qui calcule une note globale d’après la valeur attribuée aux pages visitées sur le site.
title: Qu’est-ce que la mesure Score de capture ?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 48%

---

# Score de capture

La mesure d’engagement Score de capture dans [!DNL Adobe Target] calcule une note globale d’après la valeur attribuée aux pages visitées sur le site, dès l’instant où le visiteur voit la première requête [!DNL Target] d’affichage de la campagne pour la première fois.

L’exemple suivant illustre le mode de calcul de la note dans une campagne qui teste deux expériences, la première avec une image de chat, la seconde avec une image de chien.

![image exemple_score](assets/example_score.png)

Dans cet exemple, le premier visiteur teste l’expérience Chat. Supposons qu’une requête [!DNL Target] globale transfère un score de page en fonction de la valeur de la page. Si le spécialiste du marketing a capturé l’engagement du nombre de pages sur une mesure de succès associée à `**any Target request**`, la note de visite est incrémentée dès lors que la demande d’affichage autour de l’image du chat est vue.

La première page ajoute 1 au score, la deuxième page 0,25, la troisième et la quatrième 0,10 chacune, soit un total de 1;45. Ce chiffre peut être interprété comme une monnaie ou un nombre de points. Lors d’une autre visite, un visiteur accède à l’expérience Chien et même s’il voit moins de pages, la note est de 2,10 (elle est supérieure à la visite précédente car le visiteur a vu des pages ayant plus de valeur).

Vous pouvez prendre en compte les coûts d’acquisition du compte et les recettes des liens affiliés en transmettant des adbox et des redirecteurs, comme illustré dans le flux de page ci-après. Notez que, dans cet exemple, les deux requêtes [!DNL Target] sur la page de l’article transmettent un score, représentant éventuellement un CPM connu.

![example_score2 image](assets/example_score2.png)

## Attribution d’un score de page

Vous pouvez attribuer une valeur à une page de votre site en fonction de l’importance que vous lui donnez. Par exemple, il est possible qu’un site de cuisine vende des annonces publicitaires à un tarif plus élevé sur ses pages d’articles de fond que dans sa section Expérience. Les articles de fond ont donc plus de valeur que l’expérience. La note des pages permet d’estimer la « valeur globale » d’une visite, si bien que la personne qui lit davantage d’articles de fond obtient plus de points que celle qui se contente de parcourir les expériences.

Vous pouvez attribuer une note à une page de deux manières :

* Dans la requête [!DNL Target], créez un paramètre appelé `mboxPageValue`.

  Exemple : `('global_mbox', 'mboxPageValue=10');`

  La valeur spécifiée est ajoutée au score chaque fois que la page avec cette requête [!DNL Target] est consultée. Si plusieurs requêtes de la page incluent des valeurs de score, le score de la page correspond au total de toutes les valeurs de requête. `mboxPageValue` est un paramètre réservé utilisé pour transmettre des valeurs dans une requête Target pour capturer un score d’engagement. Il est possible de transmettre des valeurs positives et négatives. La somme est calculée à la fin de chaque visite d’un visiteur pour calculer le score total de la visite.

* Transmettez le paramètre `?mboxPageValue=n` dans l’URL pour la page.

  Exemple : `https://www.mydomain.com?mboxPageValue=5`

  Grâce à cette méthode, la valeur spécifiée est ajoutée au score pour chaque requête [!DNL Target] sur la page. Par exemple, si vous transmettez le paramètre `?mboxPageValue=10` et qu’il y a trois requêtes [!DNL Target] sur la page, le score de la page est 30.

>[!NOTE]
>
>Les requêtes Target situées au-dessus de la première requête [!DNL Target] d’affichage de l’activité ne seront pas incluses dans le score.

La bonne pratique consiste à attribuer des valeurs dans la requête [!DNL Target]. Cela permet d’être précis dans les valeurs que vous mesurez, en fonction du contenu de chaque requête.

>[!NOTE]
>
>Pour faciliter la maintenance, vous pouvez configurer les attributions de valeurs de note de page de votre site dans le fichier [!DNL at.js] avec une logique JavaScript conditionnelle. Vous n’avez ainsi plus besoin d’ajouter du code supplémentaire dans vos pages. Pour plus d’informations, contactez le gestionnaire de compte.

Vous pouvez combiner les deux méthodes mais la note résultat peut être plus élevée que prévu. Par exemple, si vous attribuez une valeur de 10 à chacune des trois requêtes [!DNL Target] et aucun score à une quatrième requête, puis que vous transmettez le paramètre d’URL `?mboxPageValue=5`, le score de votre page sera 50, 30 pour les trois requêtes avec des valeurs attribuées, et 5 pour chacune des quatre requêtes de la page.

Le compteur commence par la première requête d’affichage, et non par la requête d’entrée. Par exemple, si vous saisissez l’activité sur la page d’accueil qui ne comporte pas de demande d’affichage, puis que vous créez un lien vers la page de catalogue contenant une demande d’affichage, le compteur démarre lorsque vous accédez à la page de catalogue.

Vous pouvez également transmettre des valeurs négatives sur certaines pages qui vous coûtent de l’argent ou qu’un visiteur ne devrait pas voir. Les valeurs négatives affectent également la note globale. Cette technique peut être utilisée sur une page que les visiteurs atteignent à partir d’une annonce publicitaire, de telle sorte que vous connaissez le coût par clic. Ou, par exemple, elle peut être utilisée pour une page d’assistance technique ou de contact, à partir de laquelle vous savez que les visiteurs vont appeler ou demander un support.
