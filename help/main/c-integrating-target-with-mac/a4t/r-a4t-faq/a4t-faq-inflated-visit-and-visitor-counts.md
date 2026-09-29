---
keywords: faq;questions fréquentes;analytics for target;a4T;exagéré;visite;visiteur;hit partiel;orphelin;hit partiel
description: Trouvez des réponses aux questions sur le nombre de visites et de visiteurs exagéré lors de l’utilisation d’Analytics for [!DNL Target] (A4T). Découvrez comment minimiser les « données partielles ».
title: Où puis-je trouver des FAQ sur le nombre de visites et de visiteurs exagérés avec A4T ?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 69%
---
# FAQ sur le nombre exagéré de visiteurs ou de visites - A4T

Cette rubrique contient des réponses aux questions fréquentes sur les classifications et sur l’utilisation d’Analytics comme source des rapports pour Target (A4T).

## Je constate un pic du nombre de visites. Comment puis-je savoir si ces visites sont causées par des accès aux données partielles ? {#section_28506672C6224ED18AC74F6A02F6F811}

+++Réponse
Vous pouvez contacter [le service à la clientèle Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour récupérer un rapport Données partielles. Ces informations ne sont pas disponibles directement dans l’interface utilisateur [!DNL Analytics].

+++

## Quelles sont les causes possibles des hits contenant des données partielles ? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++Réponse
Les hits contenant des données partielles résultent souvent d’une implémentation incorrecte, par exemple en cas d’identifiants de suites de rapports mal alignés. Il existe également des causes légitimes telles que les pages lentes, les erreurs de page, les offres de redirection dans une activité ou les versions de bibliothèque obsolètes.

+++

## Existe-t-il des types particuliers d’activités [!DNL Target] qui sont plus susceptibles de provoquer des accès aux données partielles ? {#section_69837442A9B84366BEFDA4588B31E574}

+++Réponse
Les offres de redirection redirigent immédiatement l’utilisateur vers une page différente, ce qui signifie que l’appel [!DNL Analytics] ne se déclenche pas sur la première page.

+++
