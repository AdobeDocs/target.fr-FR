---
keywords: score de capture, score
description: La mesure d’engagement Score de capture calcule une note globale d’après la valeur attribuée aux pages visitées sur le site, dès l’instant où le visiteur voit la première mbox d’affichage de la campagne pour la première fois.
title: Score de capture
subtopic: Prise en main
topic: Standard
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Score de capture{#capture-score}

La mesure d’engagement Score de capture calcule une note globale d’après la valeur attribuée aux pages visitées sur le site, dès l’instant où le visiteur voit la première mbox d’affichage de la campagne pour la première fois.

L’exemple suivant illustre le mode de calcul de la note dans une campagne qui teste deux expériences, la première avec une image de chat, la seconde avec une image de chien.

![](assets/example_score.png)

Dans cet exemple, le premier visiteur teste l’expérience Chat. Supposons qu’une mbox globale transmette une note de page basée sur la valeur de la page. Si le spécialiste du marketing a saisi l’engagement du nombre de pages sur une mesure de succès associée à `**any mbox**`, la note de visite est incrémentée dès lors que la mbox d’affichage entourant l’image du chat est vue.

La première page ajoute 1 au score, la deuxième page 0,25, la troisième et la quatrième 0,10 chacune, soit un total de 1;45. Ce chiffre peut être interprété comme une monnaie ou un nombre de points. Lors d’une autre visite, un visiteur accède à l’expérience Chien et même s’il voit moins de pages, la note est de 2,10 (elle est supérieure à la visite précédente car le visiteur a vu des pages ayant plus de valeur).

Vous pouvez prendre en compte les coûts d’acquisition du compte et les recettes des liens affiliés en transmettant des adbox et des redirecteurs, comme illustré dans le flux de page ci-après. Notez que, dans cet exemple, les deux mbox dans la page article obtiennent une note, représentant certainement un CPM connu.

![](assets/example_score2.png)

**Attribution d’une note à une page**

Vous pouvez attribuer une valeur à une page de votre site en fonction de l’importance que vous lui donnez. Par exemple, il est possible qu’un site de cuisine vende des annonces publicitaires à un tarif plus élevé sur ses pages d’articles de fond que dans sa section Expérience. Les articles de fond ont donc plus de valeur que l’expérience. La note des pages permet d’estimer la « valeur globale » d’une visite, si bien que la personne qui lit davantage d’articles de fond obtient plus de points que celle qui se contente de parcourir les expériences.

Vous pouvez attribuer une note à une page de deux manières :

* Dans le code de mbox, créez un paramètre de mbox appelé `mboxPageValue`.

   Exemple : `('global_mbox', 'mboxPageValue=10');`

   La valeur spécifiée est ajoutée à la note chaque fois que la page contenant cette mbox est vue. Si plusieurs mbox dans la page incluent des valeurs de notation, la note de la page correspond au total de toutes les valeurs des mbox. `mboxPageValue` est un paramètre réservé utilisé pour transmettre des valeurs dans une mbox pour capturer un score d’engagement. Il est possible de transmettre des valeurs positives et négatives. La somme est calculée à la fin de chaque visite d’un visiteur pour calculer le score total de la visite.

* Transmettez le paramètre `?mboxPageValue=n` dans l’URL pour la page.

   Exemple : `https://www.mydomain.com?mboxPageValue=5`

   Avec cette méthode, la valeur indiquée est ajoutée à la note de chaque mbox dans la page. Par exemple, si vous transmettez le paramètre `?mboxPageValue=10` et que la page contient trois mbox, la note de la page est 30.

>[!NOTE] {class="- topic/note "}
>
>Les mbox situées au-dessus de la première mbox d’affichage de la campagne ne sont pas incluses dans le score.

La bonne pratique consiste à attribuer des valeurs dans le code de mbox, ce qui permet d’obtenir des valeurs de mesure précises, en fonction du contenu de chaque mbox.

>[!NOTE] {class="- topic/note "}
>
>Pour simplifier la maintenance, vous pouvez configurer les attributions de valeurs de page de votre site dans le fichier [!DNL at.js] ou [!DNL mbox.js] en appliquant une certaine logique JavaScript conditionnelle. Vous n’avez ainsi plus besoin d’ajouter du code supplémentaire dans vos pages. Pour plus d’informations, contactez le gestionnaire de compte.

Vous pouvez combiner les deux méthodes mais la note résultat peut être plus élevée que prévu. Si, par exemple, vous attribuez la valeur 10 à chacune des trois mbox et aucune note à une quatrième mbox, puis que vous transmettez le paramètre d’URL `?mboxPageValue=5`, la note de votre page sera 50 : 30 pour les trois mbox avec les valeurs attribuées et 5 pour chacune des quatre mbox dans la page.

Le compteur est incrémenté avec la première mbox d’affichage, pas avec la mbox d’entrée. Par exemple, si vous entrez dans la campagne dans la page d’accueil qui ne comporte pas de mbox d’affichage, puis que vous créez un lien vers la page catalogue contenant une mbox d’affichage, le compteur est incrémenté lorsque vous consultez la page catalogue.

Vous pouvez également transmettre des valeurs négatives sur certaines pages qui vous coûtent de l’argent ou qu’un visiteur ne devrait pas voir. Les valeurs négatives affectent également la note globale. Cette technique peut être utilisée sur une page que les visiteurs atteignent à partir d’une annonce publicitaire, de telle sorte que vous connaissez le coût par clic. Ou, par exemple, elle peut être utilisée pour une page d’assistance technique ou de contact, à partir de laquelle vous savez que les visiteurs vont appeler ou demander un support.
