---
keywords: faq;questions fréquentes;analytics for target;a4T;exagéré;visite;visiteur;accès partiel;orphelin;accès partiel
description: Trouvez des réponses aux questions sur le nombre de visites et de visiteurs exagérés lors de l’utilisation d’Analytics for [!DNL Target] (A4T). Découvrez comment minimiser les « données partielles ».
title: Où puis-je trouver des FAQ sur le nombre de visites et de visiteurs exagérés avec A4T ?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 69%

---

# FAQ sur le nombre exagéré de visiteurs ou de visites - A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Je constate un pic du nombre de visites. Comment puis-je savoir si ces visites sont causées par des accès aux données partielles ? {#section_28506672C6224ED18AC74F6A02F6F811}

+++Réponse
Vous pouvez contacter [le service à la clientèle Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour récupérer un rapport Données partielles. Ces informations ne sont pas disponibles directement dans l’interface utilisateur [!DNL Analytics].

+++

## Quelles sont les causes possibles des accès à données partielles ? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++Réponse
Les accès à données partielles résultent souvent d’une implémentation incorrecte, par exemple en cas d’identifiants de suites de rapports mal alignés. Il existe également des causes légitimes telles que les pages lentes, les erreurs de page, les offres de redirection dans une activité ou les versions de bibliothèque obsolètes.

+++

## Existe-t-il des types particuliers d’activités [!DNL Target] qui sont plus susceptibles de provoquer des accès aux données partielles ? {#section_69837442A9B84366BEFDA4588B31E574}

+++Réponse
Les offres de redirection redirigent immédiatement l’utilisateur vers une page différente, ce qui signifie que l’appel [!DNL Analytics] ne se déclenche pas sur la première page.

+++
