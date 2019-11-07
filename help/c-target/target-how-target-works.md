---
keywords: ciblage;cookie;cookie propriétaire
description: Adobe Target intègre vos pages web par l’intermédiaire de la bibliothèque JavaScript at.js ou mbox.js.
title: Fonctionnement du ciblage
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Fonctionnement du ciblage{#how-targeting-works}

Adobe Target intègre vos pages web par l’intermédiaire de la bibliothèque JavaScript at.js ou mbox.js.

[!DNL Target Classic] utilisait des mbox autour des zones de votre page dans lesquelles vous souhaitez afficher un contenu ciblé ou collecter des données. Ces mbox ne sont pas requises dans [!DNL Target Standard]. Vous avez simplement besoin d’une seule bibliothèque JavaScript référencée sur chaque page pour exécuter vos activités d’optimisation.

Chaque fois qu’un visiteur demande une page compatible, [!DNL Target]Target utilise le processus suivant pour diffuser des offres :

1. Un client demande une page de votre serveur et l’affiche dans le navigateur.
1. Un cookie propriétaire est défini dans le navigateur du client afin de définir un identifiant visiteur unique.

   Un [!DNL Experience Cloud visitor ID] est également défini si vous utilisez le profil marketing principal.

1. La page effectue un appel à [!DNL Target] via le fichier [!DNL target.js] ou une mbox sur votre page.
1. [!DNL Target] référence le profil associé au visiteur.
1. [!DNL Target] exécute tout script de profil associé à ce profil.
1. [!DNL Target] calcule sa réponse.
1. Le contenu s’affiche selon les règles de votre activité ou campagne.

L’offre affichée dans un test A/B de base est choisie de manière aléatoire. Suite à ce fractionnement aléatoire du trafic, il se peut qu’il faille beaucoup de trafic initial avant que les pourcentages ne s’équilibrent. Si, par exemple, vous disposez d’une activité comportant deux expériences, l’expérience initiale est choisie de manière aléatoire. Si le trafic est léger, il est possible que le pourcentage des visiteurs puisse être réorienté vers une seule expérience. Quand le trafic augmente, les pourcentages doivent être plus égaux.
