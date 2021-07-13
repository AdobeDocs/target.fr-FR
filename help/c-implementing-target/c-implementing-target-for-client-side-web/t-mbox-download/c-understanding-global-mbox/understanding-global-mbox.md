---
keywords: mbox globale, implémentation d’at.js
description: Découvrez la mbox globale dans Adobe Target, nom utilisé pour faire référence à l’appel de serveur unique effectué en haut de chaque page web dans votre  [!DNL Target] implémentation.
title: Qu’est-ce qu’une mbox globale ?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 82%

---

# Présentation de la mbox globale

Informations sur la mbox globale, nom désignant l’appel de serveur effectué en haut de chaque page web dans votre mise en œuvre [!DNL Adobe Target].

Par défaut, la mbox globale est nommée `target-global-mbox`. Si nécessaire, vous pouvez la renommer pour votre compte.

Il existe plusieurs différences entre une mbox ordinaire (mbox non globale) et la mbox globale, notamment :

| mbox ordinaire | mbox globale |
|--- |--- |
| Généralement, une mbox ordinaire encapsule le contenu à l’aide d’une balise `<DIV>`. | La mbox globale est « vide » et n’encapsule aucun contenu. |
| Le contenu d’une seule activité peut être distribué dans une mbox ordinaire. | Le contenu de plusieurs activités peut être distribué dans une réponse à une mbox globale. |

Si plusieurs activités sont diffusées via la mbox globale ou via plusieurs mbox ordinaires, [!DNL Target] [détermine la priorité](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) par laquelle l’activité (ou les activités) sont diffusées vers une page Web.

D’autres données au niveau de la page peuvent être envoyées à [!DNL Target] avec la mbox globale, en utilisant la fonction `targetPageParams`. Ceci est similaire à la fonctionnalité du paramètre de mbox. Pour plus d’informations, veuillez consulter la section [Transfert de paramètres vers une mbox globale](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
