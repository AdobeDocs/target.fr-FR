---
description: Découvrez comment utiliser l’Adobe Mobile SDK pour présenter des expériences optimales à vos visiteurs d’applications mobiles.
title: Fonctionnement de  [!DNL Target] dans les applications mobiles
feature: Mise en oeuvre de Mobile
role: Developer
exl-id: 1a5f34dc-932d-47c7-b730-6d1658343fb4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 83%

---

# Fonctionnement de [!DNL Target] dans les applications mobiles

Le SDK Adobe Mobile contacte le serveur Target pour obtenir le contenu ainsi que d’autres points de données afin d’afficher l’expérience appropriée à l’utilisateur.

## Emplacements cibles et mesures de succès {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

Un *emplacement cible* est également appelé mbox. Un emplacement identifié dans l’application est activé à des fins de test ou de personnalisation (par exemple, le message de bienvenue sur l’écran d’accueil). Ces emplacements sont identifiés au cours du processus de création des tests.

Une *[mesure de succès](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)* est une action effectuée par un utilisateur qui détermine si une activité spécifique est réussie (il peut s’agir d’une inscription, d’un achat, de la réservation d’un ticket, etc.).

![](assets/mobile-target-location.png)

* **Emplacement cible :** le contenu qui s’affiche sous le bouton d’inscription.

   Cet utilisateur particulier se voit proposer une offre d’expédition gratuite jusqu’à 18 h. Cet emplacement peut être réutilisé sur plusieurs activités Target afin d’effectuer des tests A/B et des tâches de personnalisation.

* **Mesure de succès :** l’action effectuée par l’utilisateur lorsque celui-ci clique sur le bouton d’inscription.

**Comprendre le fonctionnement de Target dans le SDK**

![](assets/how-target-mobile-works.png)
