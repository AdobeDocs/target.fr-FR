---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explorez les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation des activités [!UICONTROL Automated Personalization] (AP) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés aux activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 32%

---

# Résolution des problèmes [!UICONTROL Automated Personalization]

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez faire face lors de l’utilisation de [!UICONTROL Automated Personalization] (AP) et quelques suggestions de solutions.

## Mon activité [!UICONTROL Automated Personalization] prend trop de temps pour créer des modèles. {#section_20028B204DBB4D77A324BA193434AEE2}

+++Voir les détails

Plusieurs modifications de configuration de l’activité peuvent diminuer le temps escompté pour la création des modèles, notamment le nombre d’expériences incluses dans votre activité [!UICONTROL Automated Personalization], le trafic entrant sur votre site et la mesure de succès sélectionnée.

**Solution :** Vérifiez la configuration de votre activité et vérifiez si vous êtes prêt à apporter des modifications afin d’améliorer la vitesse de compilation des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdez pas les données d’activité si vous changez la mesure de succès de Recettes par visiteur (RPV) en conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Y a-t-il des offres ou des expériences que vous pouvez exclure de votre activité ? La réduction du nombre d’expériences dans une activité accélère le temps de création des modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus le trafic et les conversions sont importants dans les emplacements de vos activités, plus les modèles sont rapides à générer.

+++

## Mon activité [!UICONTROL Automated Personalization] n’a pas généré d’effet élévateur. {#section_8900BC8968474438B8092F7A94C0C6CF}

+++Voir les détails

Plusieurs facteurs sont nécessaires pour qu’une activité [!UICONTROL Automated Personalization] génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent se trouver à un endroit qui change l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Veillez à calculer les tailles d’échantillon à l’avance. Le calcul anticipé des tailles d’échantillon permet de s’assurer qu’il y a suffisamment d’énergie pour voir un effet élévateur raisonnable. Vous pouvez ensuite exécuter le test A/B pendant une durée fixe sans l’arrêter ni apporter de modifications. Si un résultat de test A/B indique un effet élévateur statistiquement significatif pour une ou plusieurs expériences, il est probable qu’une activité personnalisée soit réussie. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres ou les emplacements n’ont pas un impact suffisant sur l’objectif d’optimisation à détecter avec une signification statistique.

+++

## Mon URL d’activité [!UICONTROL Automated Personalization] affiche le contenu de l’offre sur des pages incorrectes. {#section_82A224406DBF4107B05204BEFBBE458C}

+++Voir les détails

Dans [!UICONTROL Automated Personalization], les règles de test d’URL et de modèle sont ajoutées à la contrainte d’entrée de requête [!DNL Target] (par exemple, target-global-mbox), où elles sont évaluées une seule fois. Une fois qu’un utilisateur est admissible pour une activité, les règles de ciblage au niveau de la requête Target ne sont pas réévaluées. L’audience de ciblage est toutefois ajoutée aux règles de ciblage d’emplacement.

**Solution :** Ajoutez les règles de modèle nécessaires en tant qu’audience d’entrée de l’activité. L’évaluation de l’audience s’effectue à chaque demande/appel.

+++

## Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties. {#section_076D1F44298C4E4A849AC52F5A33214D}

+++Voir les détails

Ce comportement est attendu.

Dans une activité [!UICONTROL Automated Personalization], une fois qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif postérieur) est convertie, le visiteur est libéré de l’expérience et l’activité redémarre.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 dépend de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1 puis A1, A1 n’est toujours pas converti, car lorsque C1 est converti, le visiteur est libéré.

+++

## Les URL de mes expériences ne fonctionnent pas comme prévu. {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++Voir les détails

* Si vous ne parvenez pas à afficher l’aperçu dans le nouvel onglet (en raison du cache du navigateur), essayez de l’actualiser deux ou trois fois. Vous pouvez également copier le lien et l’ouvrir dans un nouveau navigateur ou une nouvelle session.
* Régénérez les liens d’URL d’Experience si vous avez modifié des contenus et partagez les nouveaux liens avec les autres membres de votre équipe.

+++
