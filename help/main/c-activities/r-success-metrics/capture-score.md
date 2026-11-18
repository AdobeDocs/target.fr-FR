---
keywords: score de capture, score
description: Découvrez la mesure d’engagement Capture Score dans Adobe [!DNL Target] qui calcule un score agrégé en fonction de la valeur affectée aux pages visitées sur le site.
title: Qu’est-ce que la mesure Score de capture ?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
TQID: 'https://experienceleague.adobe.com/iqCPEY9x7Lg9TlAhxn8e-B1XOnUfNgUWFdOf8Bw2F3w'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: eb2bfbe8-b0f3-4cc3-ae8d-af79179585eb
    internal-label: Success metrics
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 13%
---
# Score de capture {#capture-score}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment la mesure d’engagement Capturer le score calcule le score d’une visite et comment attribuer un score à une page.

>[!ENDSHADEBOX]

La mesure d’engagement Capturer le score dans [!DNL Adobe Target] calcule un score agrégé en fonction de la valeur affectée aux pages qu’un visiteur ou une visiteuse consulte sur votre site. Le score commence au moment où le visiteur voit pour la première fois la première demande d’affichage [!DNL Target] de l’activité.

L’exemple suivant montre comment le score est calculé dans une activité qui teste deux expériences, l’une avec une image de chat et l’autre avec une image de chien.

![Flux de page de la visite d’expérience de chat, avec un score pour chaque page](assets/example_score.png)

Dans cet exemple, le premier visiteur voit l’expérience du chat. Supposons qu’une requête [!DNL Target] globale réussisse dans un score de page en fonction de la valeur de la page. Si le spécialiste marketing a capturé l’engagement du nombre de pages sur une mesure de succès associée à **une requête Target**, le score de visite s’accumule pour toute requête affichée après la demande d’affichage autour de l’image de chat.

La première page ajoute 1 au score, la deuxième page 0,25, la troisième 0,10 et la quatrième 0,10, pour un total de 1,45. Ce total peut être interprété comme une devise ou des points. Lors d’une visite distincte, un visiteur voit l’expérience du chien. Bien que ce visiteur consulte moins de pages, le score est de 2,10, ce qui est supérieur à l’autre visite, car il a consulté des pages plus importantes.

Vous pouvez prendre en compte les coûts d’acquisition du compte et les recettes des liens affiliés en transmettant des adbox et des redirecteurs, comme illustré dans le flux de page ci-après. Dans cet exemple, les deux requêtes [!DNL Target] sur la page d’article transmettent un score, représentant peut-être un CPM connu.

![Flux de page avec coûts d’acquisition et chiffre d’affaires des liens affiliés transmis sous forme de scores](assets/example_score2.png)

## Attribuer un score de page

Vous pouvez attribuer une valeur à une page de votre site en fonction de l’importance que vous lui donnez. Par exemple, un site de cuisine peut vendre des annonces pour plus d’argent sur ses pages d’articles que dans sa section d’expérience. Les articles de fonctionnalités ont alors plus de valeur que la section d’expérience. Un score de page vous permet de développer une « valeur » globale d’une visite, de sorte qu’une personne qui lit plus d’articles de fond obtient plus de « points » qu’une personne qui ne fait que parcourir les expériences.

Vous pouvez attribuer une note à une page de deux manières :

* Dans la requête [!DNL Target], créez un paramètre appelé `mboxPageValue`.

  Exemple : `('global_mbox', 'mboxPageValue=10');`

  La valeur spécifiée est ajoutée au score chaque fois que la page contenant cette requête [!DNL Target] est consultée. Si plusieurs requêtes sur la page incluent des valeurs de score, le score de la page correspond au total de toutes les valeurs de requête. `mboxPageValue` est un paramètre réservé utilisé pour transmettre des valeurs dans une requête [!DNL Target] afin de capturer un score d’engagement. Il est possible de transmettre des valeurs positives et négatives. La somme est calculée à la fin de chaque visite afin de déterminer le score total de la visite.

* Transmettez le paramètre `?mboxPageValue=n` dans l’URL de la page.

  Exemple : `https://www.mydomain.com?mboxPageValue=5`

  La valeur spécifiée est ajoutée au score pour chaque requête [!DNL Target] sur la page. Par exemple, si vous transmettez le paramètre `?mboxPageValue=10` et qu’il y a trois requêtes [!DNL Target] sur la page, le score de la page est de 30.

>[!NOTE]
>
>Le compteur commence par la première demande d’affichage de l’activité, et non la demande d’entrée, et les [!DNL Target] demandes situées au-dessus de cette demande ne sont pas incluses dans le score. Par exemple, si vous saisissez l’activité sur la page d’accueil, qui ne comporte pas de demande d’affichage, puis que vous la liez à une page de catalogue contenant une demande d’affichage, le compteur commence lorsque vous passez à la page de catalogue.

La bonne pratique consiste à attribuer des valeurs dans la requête [!DNL Target]. Cette méthode permet d’être précis sur les valeurs que vous mesurez, en fonction du contenu de chaque requête.

>[!NOTE]
>
>Pour faciliter la maintenance, vous pouvez configurer les affectations de valeur de score de page de votre site dans le fichier [!DNL at.js] avec une logique JavaScript conditionnelle. Cette approche élimine la nécessité d’ajouter plus de code à vos pages. Pour plus d’informations, contactez le gestionnaire de compte.

Vous pouvez combiner les deux méthodes mais la note résultat peut être plus élevée que prévu. Par exemple, vous attribuez une valeur de 10 à chacune des trois requêtes [!DNL Target] et aucun score à une quatrième requête, puis transmettez le paramètre d’URL `?mboxPageValue=5`. Le score de la page est de 50 : 30 pour les trois requêtes avec des valeurs attribuées, plus 20 pour le paramètre d’URL (5 pour chacune des quatre requêtes sur la page).

Vous pouvez également transmettre des valeurs négatives sur certaines pages qui vous coûtent de l’argent ou qu’un visiteur ne devrait pas voir. Les valeurs négatives affectent également le score global. Cette technique peut être utilisée sur une page que les visiteurs atteignent à partir d’une publicité, de sorte que vous sachiez à combien s’élève le CPC. Il peut également être utilisé sur une page d’assistance ou de contact, où les visiteurs et visiteuses peuvent appeler ou demander de l’aide.
