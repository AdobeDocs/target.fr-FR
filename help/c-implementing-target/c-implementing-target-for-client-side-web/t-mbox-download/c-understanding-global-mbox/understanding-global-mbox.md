---
description: Informations sur la mbox globale, nom utilisé pour faire référence à l’appel serveur unique effectué en haut de chaque page Web dans votre implémentation Adobe Target.
keywords: mbox globale, mettre en œuvre mbox.js, mettre en œuvre at.js
seo-description: Informations sur la mbox globale, nom utilisé pour faire référence à l’appel serveur unique effectué en haut de chaque page Web dans votre implémentation Adobe Target.
seo-title: Présentation de la mbox globale
solution: Target
subtopic: Prise en main
title: Présentation de la mbox globale dans Adobe Target
topic: Standard
uuid: d8f48c94-6487-437b-828f-f9be7da58f48
translation-type: tm+mt
source-git-commit: dd22b54f94c52ac680ee7e58fb691307eadb97e8

---


# Présentation de la mbox globale{#understand-the-global-mbox}

Informations sur la mbox globale, nom utilisé pour faire référence à l’appel serveur unique effectué en haut de chaque page Web dans votre implémentation Adobe Target.

Par défaut, la mbox globale est nommée [!DNL target-global-mbox]. Si nécessaire, vous pouvez la renommer pour votre compte.

Il existe plusieurs différences entre une mbox ordinaire (mbox non globale) et la mbox globale, notamment :

| mbox ordinaire | mbox globale |
|--- |--- |
| Généralement, une mbox ordinaire encapsule le contenu à l’aide d’une balise `<DIV>`. | La mbox globale est « vide » et n’encapsule aucun contenu. |
| Le contenu d’une seule activité peut être distribué dans une mbox ordinaire. | Le contenu de plusieurs activités peut être distribué dans une réponse à une mbox globale. |

Si plusieurs activités sont diffusées via la mbox globale ou via plusieurs mbox ordinaires, [!DNL Target] [détermine la priorité](../../../../c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) par laquelle l’activité (ou les activités) sont diffusées vers une page Web.

D’autres données au niveau de la page peuvent être envoyées à [!DNL Target] avec la mbox globale, en utilisant la fonction `targetPageParams`. Ceci est similaire à la fonctionnalité du paramètre de mbox. Pour plus d’informations, veuillez consulter la section [Transfert de paramètres vers une mbox globale](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
