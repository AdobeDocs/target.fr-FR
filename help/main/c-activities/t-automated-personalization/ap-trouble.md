---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explorez les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation des activités Automated Personalization (AP) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés à Automated Personalization ?
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 91%

---

# ![PREMIUM](/help/main/assets/premium.png) Résolution des problèmes liés à la personnalisation automatisée

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lorsque vous utilisez Automated Personalization, ainsi que quelques suggestions de solutions.

## Mon activité AP prend trop de temps pour générer des modèles. {#section_20028B204DBB4D77A324BA193434AEE2}

Plusieurs modifications de configuration de l’activité peuvent diminuer le temps escompté pour la création des modèles, dont le nombre d’expériences incluses dans votre test Automated Personalization, le trafic entrant sur votre site et le critère de mesure de succès sélectionné.

**Solution :** passez en revue la configuration de votre activité et déterminez si des modifications sont souhaitables pour accélérer la compilation des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdrez pas les données d’activité si vous modifiez le critère de mesure de succès en passant du RPV à la conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Y a-t-il des offres ou des expériences que vous pouvez exclure de votre activité ? La réduction du nombre d’expériences dans une activité peut accélérer le temps nécessaire à la compilation des modèles.
* Existe-t-il une page à trafic élevée sur laquelle cette activité serait plus efficace ? Plus les lieux de votre activité génèrent de trafic et de conversions, plus les modèles se compileront rapidement.

## Mon activité AP n’a généré aucun effet élévateur. {#section_8900BC8968474438B8092F7A94C0C6CF}

Plusieurs facteurs sont requis pour qu’une activité AP génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées de manière à créer une différence du point de vue de l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Assurez-vous de calculer les tailles d’échantillon à l’avance, de manière à garantir que la puissance est suffisante pour détecter un effet élévateur raisonnable et d’exécuter le test A/B pendant une durée déterminée sans l’arrêter ni y apporter de modifications. Si le résultat d’un test A/B révèle un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionnera. Bien sûr, la personnalisation peut fonctionner même s’il n’y a aucune différence en termes de taux de réponse global entre les expériences. En règle générale, les problèmes proviennent de ce que les offres ou les lieux n’ont ne pas un impact suffisant sur l’objectif d’optimisation pour être détectés de façon statistiquement pertinente.

## L’URL de mon activité AP affiche le contenu de l’offre sur des pages incorrectes. {#section_82A224406DBF4107B05204BEFBBE458C}

Dans AP, les règles de test d’URL et de modèle sont ajoutées au [!DNL Target] contrainte d’entrée de requête (par exemple, target-global-mbox), où elles ne sont évaluées qu’une seule fois. Une fois qu’un utilisateur est admissible pour une activité, les règles de ciblage au niveau de la requête Target ne sont pas réévaluées. L’audience de ciblage est toutefois ajoutée aux règles de ciblage d’emplacement.

**Solution :** ajoutez les règles de modèle nécessaires en tant qu’audience d’entrée de la campagne. L’évaluation de l’audience s’effectue à chaque demande/appel.

Ce problème sera corrigé dans une prochaine version.

## Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties. {#section_076D1F44298C4E4A849AC52F5A33214D}

Ce comportement est attendu.

Dans une activité Automated Personalization, dès qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, l’utilisateur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 est dépendant de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1, puis A1, A1 n’est toujours pas converti car dès que C1 est converti, le visiteur est libéré.

## Les URL de mes expériences ne fonctionnent pas comme prévu. {#section_7B08DA1F30AA483E9406336DAF361BA4}

* Si vous ne pouvez pas accéder à l’aperçu dans le nouvel onglet (en raison du cache du navigateur), essayez d’actualiser la page deux ou trois fois ou copiez le lien et ouvrez-le dans un nouveau navigateur ou une nouvelle session.
* Régénérez les liens d’URL d’Experience si vous avez modifié des contenus et partagez les nouveaux liens avec les autres membres de votre équipe.
